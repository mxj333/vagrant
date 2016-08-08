# vagrant
vagrant的安装、使用

https://vagrantcloud.com/ubuntu/boxes/trusty64

```
vagrant init ubuntu/trusty64; vagrant up --provider virtualbox
```
windows 7:
```
vagrant box add ubuntu/trusty64
```


https://github.com/kraksoft/vagrant-box-ubuntu/releases/download/14.04/ubuntu-14.04-amd64.box
------------------

下载封装好的boxes：

boxes是什么？就是各种已经打包好的虚拟环境镜像，供Vagrant使用。

下载安装boxes的方式有两种，

1、官方源直接添加

使用CMD，在任意目录使用如下命题，添加ubuntu14.04镜像


1
```
vagrant box add ubuntu/trusty64
```
上面命令，会调用系统的cURL，从https://vagrantcloud.com/ubuntu/trusty64 上面下载最新的ubuntu 14.04的镜像，并添加到vagrant中。

2、手动添加

由于网络连接的缘故，vagrantcloud.com的默认下载速度比较慢，可以手动先把镜像下载后，手动添加到vagrant中。

上http://www.vagrantbox.es/下载自己需要的镜像，然后执行如下命令即可


1
```
vagrant box add ubuntu/trusty64 ./box/trusty64.box

vagrant box add ubuntu/trusty64 ubuntu-14.04-amd64.box

vagrant box add bento/ubuntu-14.04 bentou-buntu-14.04.box

vagrant box add ubuntu/trusty64 ../software/VirtualBox/ubuntu-14.04-amd64.box

vagrant box add ubuntu/trusty64 ubuntu-14.04-amd64.box
```

上面是以window为参考，需注意box add命令的第二个参数我填的是相对路径，之前我在win平台下面，用绝对路径会找不到文件，建议box和vagrant的bin程序都放在同一个分区中，用相对路径添加。

初始化项目：

前面两步都是热身，当一起准备就绪之后，就可以初始化我们的项目了。

通过CMD进入我们的项目目录，然后执行 vagrant init ubuntu/trusty64 , init的参数为我们之前配置的box的别名。

如无意外，一个vagrant环境就已经配置好了，接下来，我们仅仅需要一句命令，就可以启动我们的vagrant环境


1

```
vagrant up
```

看到里面的启动成功的提示之后，就可以通过SSH登陆到我们的虚拟环境中了（window推荐使用Xshell4登陆）。

我们的vagrant虚拟环境搭建好之后，该怎么开发就怎么开发了。

参考：

http://www.vagrantup.com/
http://vagrantcloud.com/
http://www.vagrantbox.es/

===============================================
安装插件：

```
vagrant plugin install vagrant-vbguest
```

=================================
