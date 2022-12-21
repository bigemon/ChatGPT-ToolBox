# ChatGPT-ToolBox

由ChatGPT负责编写的ChatGPT工具箱。除了向ChatGPT提供必要的数据，尽可能不由人类写任何代码。

当前版本提供以下功能：

1.关闭数据监管



鉴于官方Thread管理已正式推送，前端相关功能已无存在意义。

之前导出Thread存档的如果发现未找到会话，请在导出的账号里寻找相关未命名会话。

↓↓会话管理功能现已移除↓↓

~~2.会话导入导出~~

~~3.存档管理器~~

# 预览：

<img width="880" alt="image" src="https://user-images.githubusercontent.com/3683548/207937403-e113a2b2-4b1b-4f06-8245-fd80eed4795d.png">

# 🔄更新

2022-12-16

~~. 增加存档管理~~ (官方会话管理已正式推送)

. 增加了带记忆的独立监管开关

2022-12-14

. 增加移动端nav覆盖，现在移动端竖屏可以正常使用导航栏

. 修改README里的相关书签链接，提供远端加载最新脚本的书签



# ⚠️ 警告 ⚠️
~~1 . 导出的存档带有鉴权信息，不要分享给不认识的人，否则可能引起账户滥用~~(会话管理功能暂时移除)

2 . 本项目为实验性项目.仅用于探索ChatGPT能力的可能性，请勿长期使用或滥用

~~3 . 导出的存档在鉴权过期时将会一起失效,请周知。~~




# 调教过程
↓移步知乎查看图文完整过程

https://zhuanlan.zhihu.com/p/591003498



# 使用方法
复制对应版本的JS全文，在浏览器里添加一个javascript:开头的书签即可。

## PC/MAC Chrome

1 . 复制以下代码

↓ ↓ 这段JS将会从仓库拉取最新版本的代码并且运行,但需要一点加载时间
```
javascript:var xhr=new XMLHttpRequest();xhr.open('GET','https://ghproxy.com/https://raw.githubusercontent.com/bigemon/ChatGPT-ToolBox/main/toolbox-chrome-bookmark.js',true);xhr.onload=function(){if(xhr.readyState===4&&xhr.status===200){eval(xhr.responseText)}};xhr.send(null);
```


↓↓ 当然,你也可以直接把完整JS保存到你的书签里运行。
这不需要任何加载时间，但有时候需要手动更新版本
```
window.enableFakeMod='false'!=localStorage.getItem('enable_fakemod');var style=document.createElement('style');style.innerHTML='.switch{position:relative;display:inline-block;width:60px;height:34px;}.switch input{opacity:0;width:0;height:0;}.slider{position:absolute;cursor:pointer;top:0;left:0;right:0;bottom:0;background-color:#ccc;-webkit-transition:.4s;transition:.4s;}.slider:before{position:absolute;content:"";height:26px;width:26px;left:4px;bottom:4px;background-color:white;-webkit-transition:.4s;transition:.4s;}input:checked + .slider{background-color:#2196F3;}input:focus + .slider{box-shadow:0 0 1px #2196F3;}input:checked + .slider:before{-webkit-transform:translateX(26px);-ms-transform:translateX(26px);transform:translateX(26px);}.slider.round{border-radius:34px;}.slider.round:before{border-radius:50%;}',document.head.appendChild(style),window.switchEnableFakeMod=function(){var a=document.querySelector('input#cswitch'),b=!!a&&a.checked;b?(window.enableFakeMod=!0,localStorage.setItem('enable_fakemod',!0)):(window.enableFakeMod=!1,localStorage.setItem('enable_fakemod',!1))},window.clearAllBoxItem=function(){for(var c,a=document.querySelectorAll('nav'),b=0;b<a.length;b++){c=a[b].querySelectorAll('div.toolbox-item');for(var d=0;d<c.length;d++)c[d].remove()}},window.boxInit=function(){window.clearAllBoxItem();for(var a=document.querySelectorAll('nav'),b=0;b<a.length;b++){var c=a[b],d=document.createElement('div');d.setAttribute('class','toolbox-item flex py-3 px-3 items-center gap-3 rounded-md hover:bg-gray-500/10 transition-colors duration-200 text-white cursor-pointer text-sm flex-shrink-0 border border-white/20'),d.innerHTML='<svg t="1670527970700" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="9830" width="18" height="18"><path d="M514 114.3c-219.9 0-398.8 178.9-398.8 398.8 0 220 178.9 398.9 398.8 398.9s398.8-178.9 398.8-398.8S733.9 114.3 514 114.3z m0 685.2c-42 0-76.1-34.1-76.1-76.1 0-42 34.1-76.1 76.1-76.1 42 0 76.1 34.1 76.1 76.1 0 42.1-34.1 76.1-76.1 76.1z m0-193.8c-50.7 0-91.4-237-91.4-287.4 0-50.5 41-91.4 91.5-91.4s91.4 40.9 91.4 91.4c-0.1 50.4-40.8 287.4-91.5 287.4z" p-id="9831" fill="#dbdbdb"></path></svg>\u7981\u7528\u6570\u636E\u76D1\u7BA1<label class="switch" style="position: absolute; right: 15px;"><input id="cswitch" type="checkbox" '+(window.enableFakeMod?'checked=\'true\'':'')+' onclick="window.switchEnableFakeMod()" ><span class="slider"></span></label>',c.insertBefore(d,c.childNodes[1])}},window.boxInit();var oldf=window.fetch;window.fetch=function(){for(var a=arguments.length,b=Array(a),c=0;c<a;c++)b[c]=arguments[c];if(b[0].includes('moderations')&&window.enableFakeMod)return new Response('{}',{status:200,statusText:'ok'});if(b[0].includes('conversation')){var d=new Headers(b[1].headers),h=d.get('authorization');localStorage.setItem('authorization_last',h);var j=localStorage.getItem('import_authorization');if(j&&(d.set('authorization',j),b[1].headers=d),b[1].body&&'POST'===b[1].method)if(localStorage.getItem('next_conversation_id')&&localStorage.getItem('next_parent_message_id')){var e=localStorage.getItem('next_conversation_id'),f=localStorage.getItem('next_parent_message_id');localStorage.removeItem('next_conversation_id'),localStorage.removeItem('next_parent_message_id');var g=JSON.parse(b[1].body);g.conversation_id=e,g.parent_message_id=f,b[1].body=JSON.stringify(g)}else{var k=JSON.parse(b[1].body);localStorage.setItem('conversation_id_last',k.conversation_id||''),localStorage.setItem('parent_message_id_last',k.parent_message_id||''),localStorage.setItem('body_last',b[1].body)}}return oldf.apply(void 0,b)};var resizeTimer=null;window.onresize=function(){resizeTimer&&clearTimeout(resizeTimer),resizeTimer=setTimeout(function(){window.boxInit();for(var c,a=document.getElementsByTagName('button'),b=0;b<a.length;b++)c=a[b],-1!==c.innerHTML.indexOf('sidebar')&&c.addEventListener('click',function(){window.setTimeout(function(){window.boxInit()},300)})},200)},window.onresize();
```


2 . 添加一个新的书签，删除所有地址url，黏贴上去并且保存。

<img width="508" alt="image" src="https://user-images.githubusercontent.com/3683548/207085565-7b2598c1-4db1-44d3-961e-143cf089a27a.png">



3 . 在ChatGPT聊天界面点击这个书签，即可激活(远端拉取版本需要等待1~5秒)

<img width="1150" alt="image" src="https://user-images.githubusercontent.com/3683548/207087766-46563180-b562-44c6-9b5e-4b25804e30e4.png">


## 移动端 Chrome 使用指南

移动端分两种情况。

大屏设备如iPad下的Chrome可以直接添加PC版本的书签。

如果是手机等小屏设备，建议添加到书签栏之后，起一个好记的名字，自动联想之后手动点击javascript:开头的部分。



书签无法正常使用的请往下看


1 . 复制以下代码

```
var xhr=new XMLHttpRequest();xhr.open('GET','https://ghproxy.com/https://raw.githubusercontent.com/bigemon/ChatGPT-ToolBox/main/toolbox-chrome-bookmark.js',true);xhr.onload=function(){if(xhr.readyState===4&&xhr.status===200){eval(xhr.responseText)}};xhr.send(null);
```

2 . 在手机Chrome新建一个书签，黏贴并且保存

<img width="332" alt="image" src="https://user-images.githubusercontent.com/3683548/208836281-02974798-be9d-4cdc-a890-19c835cf8c21.png">


3 . 在要激活的页面，地址栏手动输入刚才的书签名并且点击

<img width="347" alt="image" src="https://user-images.githubusercontent.com/3683548/208836169-5ea30330-054c-4407-847b-7a1da5286fb4.png">

