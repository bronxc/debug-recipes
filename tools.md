---
layout: page
title: Tools
---

### :feet: Tracing tools

#### [wtrace](https://github.com/lowleveldesign/wtrace)

A command-line tool for live recording ETW trace events on Windows systems. Wtrace collects, among others, File I/O and Registry operations, TPC/IP connections, and RPC calls. Its purpose is to give you some insights into what is happening in the system.

#### [dotnet-wtrace](http://github.com/lowleveldesign/dotnet-wtrace)

A cross-platform command-line tool for live recording .NET trace events. Dotnet-wtrace collects, among others, GC, network, ASP.NET Core, and exception events.

#### [withdll](https://github.com/lowleveldesign/withdll)

A small tool which can inject DLLs into already running and newly started processes. The injected DLL may, for example, trace or patch functions in the remote process.

### :beetle: Debugging tools

#### [lldext](https://github.com/lowleveldesign/lldext) (a WinDbg extension)

The repository contains the source code of a native lldext extension and my various scripts enhancing debugging with WinDbg.

#### [comon](https://github.com/lowleveldesign/comon) (a WinDbg extension)

A WinDbg extension showing traces of COM class creations and interface querying. You may use it to investigate various COM issues and better understand application logic.
