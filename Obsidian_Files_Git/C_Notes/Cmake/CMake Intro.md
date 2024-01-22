How the C/CPP Program works: 
1. Source Code 
2. ToolChain  预处理，头文件展开，去注释，
3. Compiler 得到汇编文件
4. 汇编器处理得到二进制文件
5. Linux： .o  Windows: .obj （不可执行）
6. 得到可执行二进制程序

文件少：可用命令

### 多文件

1. Makefile ->makefile
2. Cmake 更高级不依赖于平台 -> cmakelists.txt
	1. 执行cmake命令行生成makefile文件，再执行make命令用makefile调用一系列操作系统内的指令

>CMake 可以生成执行文件也可以生成
>	库文件： 1. 动态
>			2. 静态