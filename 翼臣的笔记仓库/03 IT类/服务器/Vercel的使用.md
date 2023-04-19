> Vercel.app的域名目前已经被中国大陆地区**建立高墙。**基于Vercel搭建服务、托管页面前请考虑此影响。

**Vercel官网：**

[Dashboard - Vercel](https://vercel.com/dashboard)

-   每天100次部署，每月100GB流量。
-   导入的Github仓库有新的PR或者Commit，vercel都会自动拉取代码进行部署。
-   解析一个域名到Vercel，Vercel会自动申请和免费续期证书。
# 使vercel搭建的服务成功访问

> **请在自己的代理软件创建代理分流规则**

![[Pasted image 20230207163715.png]]
（Quantumult下代理规则的创建）

 **在Quantumult中，请在分流规则中添加HOST—SUFFIX模式，添加vercel.app参数，规则设为PROXY即可。**

