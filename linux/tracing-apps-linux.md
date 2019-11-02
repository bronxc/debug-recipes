
strace

Dump information about a file: `file <executable>`

Shared symbols in the executable: `objdump -T <executable>`. Shared symbols are those that a given binary imports from other libraries (imports). To list private symbols use `objdump -t <executable>`. FIXME: explain output

    
ldd - shows dependencies of a given binary file

nm - list symbols from object file (-D for dynamic symbols)

readelf - various information about the ELF file

objdump - various information about the library/executable file
