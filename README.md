# 基于云原生API网关和阿里云OSS实现静态网站托管
## 简介：
静态网站是指所有的网页都由静态内容构成，包括HTML文件、CSS文件和客户端执行的脚本（例如JavaScript文件）。您可以将静态网站涉及的文件存储到OSS（Object Storage Service）的存储空间（Bucket），然后通过云原生API网关代理OSS中存储的静态网站内容。本方案实现基于云原生API网关和阿里云OSS实现静态网站托管。


## 项目架构：
假设有一个Web应用，对外域名为example.com，静态页面由OSS托管，并通过云原生API网关代理静态页面以及后端服务。架构示意图如下：

![image](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8070347271/CAEQTxiBgMDKn6nijBkiIDdkMzljMDEwYThjZDQyYWViMjFmYjUyYmQ5MDJjY2Mx4468809_20240628141726.469.svg)

- 所有静态页面的请求均被云原生API网关转发到OSS存储。例如，访问example.com或者example.com/index.html时，返回网站首页index.html。

- 其他业务的请求被云原生API网关转发到目标服务。例如，访问example.com/app时，返回后端服务处理请求的业务结果。

## 使用说明
假设您的业务域名为example.com，在浏览器地址栏分别输入example.com、example.com/index.html

已在OSS的Bucket中设置默认首页，所以在浏览器地址栏输入example.com，会返回index.html页面。

![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3245293761/p551346.png)


您也可以明确访问index.html文件。例如在浏览器地址栏输入example.com/index.html，也会返回index.html页面。

![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3245293761/p551348.png)