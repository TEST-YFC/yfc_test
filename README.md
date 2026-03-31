git config --global http.proxy http://ywx1045122@proxyhes-gy.security.huawei.com:8080
git config --global https.proxy http://ywx1045122@proxyhes-gy.security.huawei.com:8080

# 3.配置ssh代理
touch ~/.ssh/config
# 编辑~/.ssh/config文件，输入以下内容：
# 注意proxyserver要改成专用代理服务器！！！！！！！！
Host gitee.com github.com gitcode.com atomgit.com
    User git
    IdentityFile ~/.ssh/id_rsa
    StrictHostKeyChecking accept-new
    ProxyCommand connect -H proxyhes-gy.security.huawei.com:8080 %h %p
    
    2.配置全局代理，打开空间内cmd，输入sysdm.cpl，可打开环境变量设置窗口
系统属性>高级>环境变量>系统环境变量
注意proxyserver要改成专用代理服务器！！！！！！！！
新建 变量名：http_proxy 变量值：http://proxyhes-gy.security.huawei.com:8080
新建 变量名：https_proxy 变量值：http://proxyhes-gy.security.huawei.com:8080

