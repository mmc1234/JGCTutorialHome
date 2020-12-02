# 配置OpenGL这个狗玩意

## glad

下载一下glad，具体下载方式网上有，很简单

有include和src两个目录，然后命令行进入glad的解压目录(ide内部自带)

```powershell
$ gcc ./src/glad.c -c -I./include/
$ ar -rc libglad.a glad.o
```

得到的libglad.a，放到你项目的/lib

include里的内容拷贝到你项目的/include

然后你就可以在代码里引用glad/glad.h了



## glfw

这玩意有点恶心，官网的文件不好使，你得有一个cmake和mingw

然后解压glfw的源码，往里面建立build目录

然后cmake-gui打开glfw源码的文件夹，并指定build目录

然后选择配置，生成器选择Mingw Makefiles，确定

然后勾选**BUILD_SHARED_LIBS**(我这里第一行就是)，然后生成



命令行进入build目录

```powershell
$ make glfw
```

等待完成，打开build/src，出现了libglfw3dll.a和glfw3.dll

libglfw3dll.a放进项目的/lib，glfw3.dll放到exe旁边就好了

然后在项目的根目录创建文件Makefile

内容如下:

```makefile
CXX		:= E:/Program Files (x86)/CD/MinGW/bin/gcc # your compiler
CXX_FLAGS       := -g -std=c++17 #flag

#dir
SRC		:= src 
INCLUDE         := ./include
LIB		:= ./lib

#lib
LIBRARIES	:= -lglad -lglfw3dll
EXECUTABLE	:= main

all:./$(EXECUTABLE)

run: all
	./$(EXECUTABLE)

$(EXECUTABLE):$(SRC)/*.cpp
	$(CXX) $(CXX_FLAGS) -I$(INCLUDE) -L$(LIB) $^ -o $@ $(LIBRARIES)
```

然后命令行里跳转到项目根目录，输入make all就编译好了
