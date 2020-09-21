# IBM-Free-Vps->V2ray

## BIM
* IBM云官网：https://cloud.ibm.com/
* 注册账号 - 登录
* Cloud Foubdry -> 公共
* 新建->256M->Go社区
* 应用程序名自定义(访问得二级域名)
* 右部创建即可
* 创建后会跳转开机，点击右上 Cloud Shell 即可进入机器

## V2ray 安装脚本
* wget --no-check-certificate -O install.sh https://raw.githubusercontent.com/zhengjianyang/IBM-V2ray/master/install.sh && chmod +x install.sh  && ./install.sh
* 安装完后会输出 Vmess的链接,复制导入V2即可

## 安装说明
    1. 邮箱用户名和密码是用于重启IBM用,默认四天重启一次
    2. 自己开容器，环境自己选（看更新说明里的适用环境），安装时会让选择环境参数，1代表go代码，2代表python代码（代码取自IBM示例代码仅用于伪装，选谁都行）

    3. 需要设置v2ray伪装名称参数，自行命名（尽可能选择全英文字母）

    4. 能否使用一切随缘，只增加伪装

## cloudflare
* 官网：cloudflare.com
* 注册登录 - 登录后不用添加网站回到用户
* 创建 Workers
* 修改脚本：
```
addEventListener(
"fetch",event => {
let url=new URL(event.request.url);
url.hostname="IBM的访问地址";
let request=new Request(url,event.request);
event. respondWith(
fetch(request)
)
}
)
```
* 修改完保存并部署

## 修改V2节点
* 编辑刚才的节点
* 伪装host：Workers提供的地址

`soft-credit-e865.zhengjianyang1021.workers.dev`
* 地址(addr)：

`cloudflare.com`
* 或

`icook.tw`
