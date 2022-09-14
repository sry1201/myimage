# myimage
网络存储图片位置-picGo图床上传文件位置，typora markdown文本编辑器图片上传位置

# 构建免费图床

​		实现本地图片上传网络，并且可以快速的访问。

### 目的

> 图片上传网络，便于本地写好博客后，可以直接复制到bolg网站使用而不用修改图片连接。



### 工具

github：用于图片网络存储。

picGo : 图床工具，用于图片便捷上传。

jsdelivr：一家NPM（镜像）和github静态访问的cdn提供商。



### 步骤

1、下载 [picGo](https://molunerfinn.com/PicGo/),由于通过github下载，可能会比较慢，下载安装后选择显示的图床为github。

![image-20210108142422382](https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@master//blogImg/20210108142426.png)



2、注册github并且建立属于你自己的github仓库，这里我建立的仓库名称为 **myimage**。

![image-20210108144318658](https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@master//blogImg/20210108144321.png)

3、设置github的access token（设置号后保存） ,位置： 头像 --》 Settings -- 》Developer settings --》Personal access tokens  

4、拼接通过jsdelivr内容分发网络访问dgithub仓库中图片的地址前缀，参照 [jsdelivr](https://www.jsdelivr.com)首页地址说明。拼接地址说明如下：

https://cdn.jsdelivr.net/gh/ gihub注册的用户名/仓库名称@仓库分支名称

> 示例（示例中master和分支名称main对应的同样的效果）：https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@master/



5、将以上步骤中获取的信息填写到picGo应用中github图床的上传设置中。

![image-20210108145654531](https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@master//blogImg/20210108145656.png)



6、配置好了，在picGo的上传区域，点击图片上传即可。

​	成功示例：https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@main/blogImg/20210108133022.jpg

7、如果失败，检查相关配置

> 上传失败，仓库名称，分支名称，token有没有配置错误。
>
> 上传成功后，浏览器输入地址不能访问，检查设置的自定义域名是否有问题。



### 题外

#### 通过typera写blog时，实现自动的图片上传

​		[typera](https://www.typora.io/)(一款非常好用的markdown文本编辑器)，结合picGo使用后，本地的图片可以快速的上传到网络， 那么我们的blog写好之后就可以直接复制到各大blog平台，而复制之后图片访问问题。

1、通过上文中的地址下载和安装typera。

2、菜单栏--》格式--》图像--》全局图像设置--》上传服务设定。配置如下图。

![image-20210108152624245](https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@master/blogImg/20210108152626.png)

3、配置好之后，每次你复制剪切板图片到typera的编辑界面是，typera会显示上传按钮，上传后文章中图片地址会自动更新为网络图片地址。

> 注意，上述用法需要每次启动picGo之后才编辑 文章 。
>
> 需要配置picGo应用启动时本地服务的端口号。PicGo设置--》设置server --》端口设置成36677。

![image-20210108153431924](https://cdn.jsdelivr.net/gh/cloudinwinter/myimage@master/blogImg/20210108153433.png)



#### 吐槽一下之前遇到的坑

> 1、最开始是通过github pages 功能实现图片访问的，但是一个账号只能配置一个仓库实现github pages功能，这个功能已经被我blog使用了。而且访问速度在国内真的不快。
>
> 2、上传github正常仓库进行访问，大概提供的地址是这样的：https://raw.githubusercontent.com/cloudinwinter/myimage/main/blogImg/20210108132925.jpg，之前可以，现在浏览器提示有安全问题，虽然可以本地添加信任证书解决，但是不能指望其他人也添加吧，而且速度也不行。
>
> 3、试了一下gitee结合picGo使用，成功后地址示例：https://gitee.com/cloudinwinter/blogimg/raw/master/img/20201029152732.jpg，但是发现图片大于1M,需要登录之后才可以访问，这个真心不太靠谱。
>
> 4、最终bilibili一位up主的视频终于让我解决了这个问题，这里表示感谢，附上视频连接：https://www.bilibili.com/video/BV1f4411z73J?from=search&seid=9010025456989855396



