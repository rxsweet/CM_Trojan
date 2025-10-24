# js混淆加密
 - https://obfuscator.io/#code
 - https://www.lddgo.net/encrypt/js
 - https://toolonline.net/js-obfuscator

简单加密使用上面网址，
复杂加密使用actions，
优先使用byjoey加密

## 一些信息
```
KV空间:
变量名称:amclubs
值:testV

节点地址：?sub  ?base64  ?clash  ?singbox
```
## _worker源码新版_sub.js - am的订阅器
1.删掉下面几行赋值的原内容，改成
```
let id = 'rx';
let uuid  = 'f223e098-393f-48bd-8331-5770a5bd5517';
let host = 'cf-node-trojan-vless.sweetrx.eu.org';
let ipUrl = 'https://raw.githubusercontent.com/rxsweet/cfip/main/ipUrl.txt';
let subConfig = "https://raw.githubusercontent.com/rxsweet/all/main/githubTools/cfClashConfig_cn.ini";
let ipLocal = [];
```
2.'function mainHandler'功能函数中：
注释掉：
```
    id = getEnvVar('ID', env) || ID || id;
    uuid = url.searchParams.get('UUID') || getEnvVar('UUID', env) || UUID;
    host = url.searchParams.get('HOST') || getEnvVar('HOST', env) || HOST;
```
3.'function getConfigContent'功能函数中：
修改if (!protType)后面代码为：
```
    if (!protType) {
        /*原代码
        protType = doubleBase64Decode(protTypeBase64);
        const responseBody1 = splitNodeData(uniqueIpTxt, noTLS, fakeHostName, fakeUserId, userAgent, protType, nat64, hostRemark);
        protType = doubleBase64Decode(protTypeBase64Tro);
        const responseBody2 = splitNodeData(uniqueIpTxt, noTLS, fakeHostName, fakeUserId, userAgent, protType, nat64, hostRemark);
        responseBody = [responseBody1, responseBody2].join('\n');
        */
        //关掉订阅vless后
        protType = doubleBase64Decode(protTypeBase64Tro);
        const responseBody2 = splitNodeData(uniqueIpTxt, noTLS, fakeHostName, fakeUserId, userAgent, protType, nat64, hostRemark);
        responseBody = [responseBody2].join('\n');
```
