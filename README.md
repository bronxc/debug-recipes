
Debug Recipes
=============

This is a repository of my notes collected while debugging various .NET and Windows problems. You can find here commands with example usages, scripts and other debugging materials.  It is still being constructed so some notes might not be finished - use on your own responsiblity. Try using the project search box while looking for a particular subject.

I hope you will find them useful. Any contribution is welcome.

Following sections are available:

Memory
------

- [CLR Memory model](memory/clr-memory.md)
- [Investigate .NET memory issues in dumps](dumps/analyze-net-memory-dumps.md)

Threading problems
------------------

- [Analysing locks in .NET](threading/analysing-locks-in-net.md)

Network issues
--------------

- [Collect and analyze network traces](network/network-tracing.md)
- [Identify network problems in memory dumps](network/network-problems-in-dumps.md)

Exceptions
----------

- [Collecting exception information in production](exceptions/collecting-exceptions-info.md)
- [Analyzing exceptions](exceptions/analyzing-exceptions.md)
- [Windows Error Reporting](exceptions/wer/wer-usage.md)
- [Aedebug](exceptions/aedebug/aedebug.md)
- [Adplus usage](exceptions/adplus/adplus.md)
- [DebugDiag](exceptions/debugdiag/debugdiag.md)

ADO.NET
-------

- [ETW tracing in ADO.NET](ado.net/ado.net-etw-tracing.md)
- [Debugging ADO.NET](ado.net/ado.net-debugging.md)

General
-------

- [JIT configuration for debugging](jit-configuration-for-debugging.md)
- [Windows debugging configuration](windows-debugging-configuration.md)
- [PDB files](pdb-files.md)

Tracing
-------

- [API hooking in Windws](tracing/api-hooking.md)

Tools & technics
----------------

### Debugging kernel

- [Debugging Windows kernel - setup](debugging-kernel/windows-kernel-debugging-setup.md)
- [Debugging Windows kernel - basics](debugging-kernel/windows-kernel-debugging.md)

### Memory dumps

- [Collect process memory dumps](dumps/windows-process-memory-dumps.md)
- [Collect kernel memory dumps](dumps/windows-kernel-memory-dumps.md)

### Debuggers

- [Debuging using Visual Studio](debugging-using-vs/README.md)
- [Debugging using mdbg](debugging-using-mdbg/mdbg.exe.md)
- [Debugging in WinDbg - tips](debugging-using-windbg/windbg-debugging.md)
- [Debugging .NET apps using windbg](debugging-using-windbg/windbg-clr-debugging.md)

Links
-----

- [.NET Debugging Quick Start -  a list of links for different parts of a .net debugging infrastructure](http://blogs.msdn.com/b/arvindsh/archive/2012/03/14/net-debugging-quick-start.aspx)
- [.NET Debugging for the Production Environment](http://channel9.msdn.com/Series/-NET-Debugging-Stater-Kit-for-the-Production-Environment)
- [.NET Debugging Starter Kit: for the Production Environment - 6 great videos about .NET and native debugging](http://channel9.msdn.com/Series/-NET-Debugging-Stater-Kit-for-the-Production-Environment)
- [Intersting library that binds github sources with solution](https://github.com/GeertvanHorrik/GitHubLink)
- [StackDump - stack dumps for .Net Applications](http://stackdump.codeplex.com/)
- [Defrag Tools #109 - Writing a CLR Debugger Extension Part 1](http://channel9.msdn.com/Shows/Defrag-Tools/Defrag-Tools-109-Writing-a-CLR-Debugger-Extension-Part-1)
- [Defrag Tools #110 - Writing a CLR Debugger Extension Part 2](http://channel9.msdn.com/Shows/Defrag-Tools/Defrag-Tools-110-Writing-a-CLR-Debugger-Extension-Part-2)
