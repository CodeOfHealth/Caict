

## Caict

> How hard is it gonna be?<br/>
> 一个仅仅3行代码的通信大数据行程卡演示

除 `README.md` 、 `redirect.html `与 `demo.png` 外，项目中其余文件均为原汁原味未经修改的官方前端文件<br/>
[Github](https://github.com/CodeOfHealth/Caict) | [Gitlab](https://gitlab.com/codeofhealth1/Caict) | [NotABug](https://notabug.org/CodeOfHealth/Caict)

#### How?

由于行程卡会保存上一次访问时留下的的明文数据至Localstorage，所以我们只需设置一些Localstorge的数据，然后跳转至`index.html#/result` 即可获得一个完美无缺的行程卡演示

```javascript
localStorage.setItem("resMsg", JSON.stringify({"status":"1","code":"00","errorDesc":"请求成功","result":{"color":"green","phone":"123****5678","time":"1970.01.01 00:00:00","message":"以Base64格式编码的'前7天到达或途径'图片"},"queryId":""}));
localStorage.setItem("loginkey", "1");
location.href = "./index.html#/result";
```

上述代码 Demo 请移步 `redirect.html`

#### More?

通过分析HTTP请求Stacktrace可得出： `./js/chunk-vendors.56730fc8.js` 中的 `_0xfa639a['exports']`函数负责发送XMLHttpRequest。移除该部分代码即可避免上传数据至服务器。**本Demo中并未移除该部分代码**<br/>
(15:83035  `_0xfa639a['exports']` [含] 至 15:86197 `(_0x219087);});};` [含] )

---

本项目仅供学习交流使用<br/>
因您个人违规使用而造成的任何后果请自行承担


