## dumpdecrypted
Dumps decrypted iPhone Applications to a file - better solution than those GDB scripts for non working GDB versions
(C) Copyright 2011-2014 Stefan Esser

## How to compile it?
1.First, adjust the Makefile if you have a different iOS SDK installed.
2.And then, just use of the command : `make`, that operation will generate a dylib library.

## Usage
It dumps the shell of applications, wherever it comes from iPod/iPhone/iPad, even if those of that will download from the App Store.
iPod:~ root# 
```
DYLD_INSERT_LIBRARIES=dumpdecrypted.dylib /var/mobile/Applications/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/Scan.app/Scan
```
mach-o decryption dumper

## The log will be outputed while dumping an executable file in the Terminal 
DISCLAIMER: This tool is only meant for security research purposes, not for application crackers.

[+] Found encrypted data at address 00002000 of length 1826816 bytes - type 1.
[+] Opening /private/var/mobile/Applications/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/Scan.app/Scan for reading.
[+] Reading header
[+] Detecting header type
[+] Executable is a FAT image - searching for right architecture
[+] Correct arch is at offset 2408224 in the file
[+] Opening Scan.decrypted for writing.
[-] Failed opening. Most probably a sandbox issue. Trying something different.
[+] Opening /private/var/mobile/Applications/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/tmp/Scan.decrypted for writing.
[+] Copying the not encrypted start of the file
[+] Dumping the decrypted data into the file
[+] Copying the not encrypted remainder of the file
[+] Closing original file
[+] Closing dump file

## Blog
Here is blog that shows you the complete steps 
http://www.googleplus.party/2017/04/15/iOS-App-Dumps-Encrypted-Shell-and-Disassembling/

<br/>
<br/>

## dumpdecrypted
dumpdecrypted是一个脱壳工具，可以对从App Store上下载的应用进行脱壳，以便于安全分析人员可以进行分析。
这里要感谢Stefan Esser提供的这个开源的库，在我们做iOS逆向分析的时候，提供了很大的帮助！

## 如何编译它了？
1.下载这个库到你的电脑上（这里我使用的是MacBook Pro），并且`cd`到该库的目录；
2.在终端(Terminal)下使用命令 `make`，就可以生成一个`dumpdecrypted.dylib`文件，这个文件就是当我们对其他可执行文件进行脱壳时要使用的。

## 使用方式
这个库可以对从App Store下载的应用进行脱壳，可以是iPod,iPhone,iPad
例如：以下命令就是对Scan.app进行脱壳
```
DYLD_INSERT_LIBRARIES=dumpdecrypted.dylib /var/mobile/Applications/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/Scan.app/Scan
```
## 输入以下日志时是，当你对一个可执行文件进行脱壳时
DISCLAIMER: This tool is only meant for security research purposes, not for application crackers.

[+] Found encrypted data at address 00002000 of length 1826816 bytes - type 1.
[+] Opening /private/var/mobile/Applications/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/Scan.app/Scan for reading.
[+] Reading header
[+] Detecting header type
[+] Executable is a FAT image - searching for right architecture
[+] Correct arch is at offset 2408224 in the file
[+] Opening Scan.decrypted for writing.
[-] Failed opening. Most probably a sandbox issue. Trying something different.
[+] Opening /private/var/mobile/Applications/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/tmp/Scan.decrypted for writing.
[+] Copying the not encrypted start of the file
[+] Dumping the decrypted data into the file
[+] Copying the not encrypted remainder of the file
[+] Closing original file
[+] Closing dump file

## 博客详解
英文版
http://www.googleplus.party/2017/04/15/iOS-App-Dumps-Encrypted-Shell-and-Disassembling/

中文版
http://blog.csdn.net/u013538542/article/details/70196590



