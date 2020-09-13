# JGCTutorialHome

[LWJGL3完整demo]  https://github.com/LWJGL/lwjgl3/blob/master/modules/samples/src/test/java/org/lwjgl/demo  
[VAO, VBO, EBO]  https://www.cnblogs.com/yy-86/articles/9545264.html  
[Texture Array]  http://www.zwqxin.com/archives/opengl/learn-texture-array.html  
[Geometry Shader]  http://www.zwqxin.com/archives/shaderglsl/talk-about-geometry-shader.html  
[MBOIT基于矩的顺序无关alpha混合]  https://cg.ivd.kit.edu/english/mboit.php  
[OpenGL进阶之Instancing]  https://www.cnblogs.com/hellobb/p/8891374.html  
[Geometry Instancing]  http://www.zwqxin.com/archives/opengl/talk-about-geometry-  instancing.html  
[Shader中的if和for效率问题以及使用策略]  https://blog.csdn.net/xiaoyafang123/article/details/84942201?utm_source=app  
[DrawCall理解和优化]  https://blog.csdn.net/sakyaer/article/details/44459881  
[Unity中基于Gpu Instance进行大量物体渲染的实现与分析]  https://blog.csdn.net/leonwei/article/details/73274808  
[LWJGL3教程 中译]  https://mouse0w0.github.io/lwjglbook-CN-Translation/  
[LWJGL3教程 CSDN]  https://blog.csdn.net/zoharwolf/article/details/49472857  
[OpenGL API文档 ]  https://www.khronos.org/registry/OpenGL-Refpages/gl4/  
[噪波详解]  https://blog.csdn.net/candycat1992/article/details/50346469  
[MC Forge Mod 1.12.2开发教程]  https://www.mcbbs.net/forum.php?mod=viewthread&tid=849410&extra=page%3D1%26filter%3Dtypeid%26typeid%3D1028  
[MC 物品NBT的写法]  https://emxtutorials.wordpress.com/adding-nbt-data-to-items/  
[Eclipse误删文件后如何恢复]  https://blog.csdn.net/fristjcjdncg/article/details/104219368  

本地库直接作为依赖，不然会崩  
glUseProgram在创建链接验证着色器等操作完成之前调用，会崩溃  

纹理这注意，<u>如果纹理大小为w16,h16，缓冲区为16*1(w16, h1)的大小</u>，那么你提交子数据的时候，  
<u>必须指定h参数为1</u>，否则JVM坟头草就七尺高了  


配置文件这里，json 序列化很顺手，对象序列化用这个很快，我用的gson  
配置文件推荐自己用antlr4自己写，现有的反人类  
性能的话，json>hocon>toml  
hocon就是个四不像，性能还差劲，差评  
