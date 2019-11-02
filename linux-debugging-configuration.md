

my /etc/sysctl.d/10-ptrace.conf (/proc/sys/kernel/yama/ptrace_scope):

```
# The PTRACE system is used for debugging.  With it, a single user process
# can attach to any other dumpable process owned by the same user.  In the
# case of malicious software, it is possible to use PTRACE to access
# credentials that exist in memory (re-using existing SSH connections,
# extracting GPG agent information, etc).
#
# A PTRACE scope of "0" is the more permissive mode.  A scope of "1" limits
# PTRACE only to direct child processes (e.g. "gdb name-of-program" and
# "strace -f name-of-program" work, but gdb's "attach" and "strace -fp $PID"
# do not).  The PTRACE scope is ignored when a user has CAP_SYS_PTRACE, so
# "sudo strace -fp $PID" will work as before.  For more details see:
# https://wiki.ubuntu.com/SecurityTeam/Roadmap/KernelHardening#ptrace
#
# For applications launching crash handlers that need PTRACE, exceptions can
# be registered by the debugee by declaring in the segfault handler
# specifically which process will be using PTRACE on the debugee:
#   prctl(PR_SET_PTRACER, debugger_pid, 0, 0, 0);
#
# In general, PTRACE is not needed for the average running Ubuntu system.
# To that end, the default is to set the PTRACE scope to "1".  This value
# may not be appropriate for developers or servers with only admin accounts.
kernel.yama.ptrace_scope = 1
```

From <https://wiki.ubuntu.com/SecurityTeam/Roadmap/KernelHardening#ptrace>:

ptrace Protection

As Linux grows in popularity, it will become a growing target for malware. One particularly troubling weakness of the Linux process interfaces is that a single user is able to examine the memory and running state of any of their processes. For example, if one application (e.g. firefox) was compromised, it would be possible for an attacker to attach to other running processes (e.g. gpg-agent) to extract additional credentials and continue to expand the scope of their attack.

This is not a theoretical problem. SSH session hijacking and even arbitrary code injection is fully possible if ptrace is allowed normally.

For a solution, some applications use prctl() to specifically disallow such ptrace attachment (e.g. ssh-agent). A more general solution is to only allow ptrace directly from a parent to a child process (i.e. direct gdb and strace still work), or as the root user (i.e. gdb BIN PID, and strace -p PID still work as root).

This behavior is controlled via the /proc/sys/kernel/yama/ptrace_scope sysctl value. The default is "1" to block non-child ptrace. A value of "0" restores the prior more permissive behavior, which may be more appropriate for some development systems and servers with only admin accounts. Using "sudo" can also grant temporarily ptrace permissions via the CAP_SYS_PTRACE capability, though this method allows the ptrace of any process.


