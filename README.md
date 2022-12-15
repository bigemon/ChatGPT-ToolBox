# ChatGPT-ToolBox

由ChatGPT负责编写的ChatGPT工具箱。除了向ChatGPT提供必要的数据，尽可能不由人类写任何代码。

当前版本提供以下功能：

1.关闭数据监管

2.会话导入导出

3.存档管理器

# 🔄更新

2022-12-16

. 增加存档管理

. 增加了带记忆的独立监管开关

2022-12-14

. 增加移动端nav覆盖，现在移动端竖屏可以正常使用导航栏

. 修改README里的相关书签链接，提供远端加载最新脚本的书签


# 预览：

<img width="880" alt="image" src="https://user-images.githubusercontent.com/3683548/207937403-e113a2b2-4b1b-4f06-8245-fd80eed4795d.png">




# ⚠️ 警告 ⚠️
1 . 导出的存档带有鉴权信息，不要分享给不认识的人，否则可能引起账户滥用

2 . 本项目为实验性项目.仅用于探索ChatGPT能力的可能性，请勿长期使用或滥用

3 . 导出的存档在鉴权过期时将会一起失效,请周知。




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
javascript:window.enableFakeMod='false'!=localStorage.getItem('enable_fakemod');var style=document.createElement('style');style.innerHTML='.switch{position:relative;display:inline-block;width:60px;height:34px;}.switch input{opacity:0;width:0;height:0;}.slider{position:absolute;cursor:pointer;top:0;left:0;right:0;bottom:0;background-color:#ccc;-webkit-transition:.4s;transition:.4s;}.slider:before{position:absolute;content:"";height:26px;width:26px;left:4px;bottom:4px;background-color:white;-webkit-transition:.4s;transition:.4s;}input:checked + .slider{background-color:#2196F3;}input:focus + .slider{box-shadow:0 0 1px #2196F3;}input:checked + .slider:before{-webkit-transform:translateX(26px);-ms-transform:translateX(26px);transform:translateX(26px);}.slider.round{border-radius:34px;}.slider.round:before{border-radius:50%;}',document.head.appendChild(style),window.boxInit=function(){for(var a=document.querySelectorAll('nav'),b=0;b<a.length;b++){var g=a[b],c=g.querySelectorAll('a');if(clearAllSaveData(),2<g.childNodes.length){for(var h=JSON.parse(localStorage.getItem('savedata'))||[],d=0;d<h.length;d++){var k=h[d],e=document.createElement('div');e.setAttribute('class','save-data flex py-3 px-3 items-center gap-3 rounded-md hover:bg-gray-500/10 transition-colors duration-200 text-white cursor-pointer text-sm flex-shrink-0 border border-white/20'),e.innerHTML='<a onclick=\'confirm("\u662F\u5426\u8981\u8F7D\u5165:'+k.name+'?") && loadData('+d+');\'style="max-width: calc(100% - 40px)"><font size="1" color="grey">'+k.time+'</font><br>'+k.name+'</a><a class="flex py-3 px-3 gap-3 rounded-md hover:bg-gray-500/10 transition-colors duration-200 text-white cursor-pointer text-sm flex-shrink-2 border border-white/40"style="position: absolute; right: 15px; color=red;"onclick=\'confirm("\u771F\u7684\u8981\u5220\u9664:'+k.name+'\u5417?") && confirm("\u5220\u9664\u4E4B\u540E\u5C06\u65E0\u6CD5\u627E\u56DE\uFF0C\u786E\u8BA4\u5220\u9664\uFF1F") && window.deleteData('+d+') && window.boxInit()\'>\u5220\u9664</a>',g.insertBefore(e,g.childNodes[1])}var f=document.createElement('a');f.setAttribute('class','save-data flex py-3 px-3 items-center gap-3 rounded-md hover:bg-gray-500/10 transition-colors duration-200 text-white cursor-pointer text-sm flex-shrink-0 border border-white/20'),f.innerHTML='[ + ] \u65B0\u5EFA\u5B58\u6863',f.onclick=function(){var k=exportSaveData();if(k){var l=prompt('\u8BF7\u7ED9\u5B58\u6863\u8D77\u4E2A\u7B80\u77ED\u7684\u540D\u5B57');l&&(saveData(-1,l,k),window.setTimeout(function(){window.boxInit()},300))}},g.insertBefore(f,g.childNodes[1]);var j=document.createElement('div');j.setAttribute('class','save-data flex py-3 px-3 items-center gap-3 rounded-md hover:bg-gray-500/10 transition-colors duration-200 text-white cursor-pointer text-sm flex-shrink-0 border border-white/20'),j.innerHTML='<svg t="1670527970700" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="9830" width="18" height="18"><path d="M514 114.3c-219.9 0-398.8 178.9-398.8 398.8 0 220 178.9 398.9 398.8 398.9s398.8-178.9 398.8-398.8S733.9 114.3 514 114.3z m0 685.2c-42 0-76.1-34.1-76.1-76.1 0-42 34.1-76.1 76.1-76.1 42 0 76.1 34.1 76.1 76.1 0 42.1-34.1 76.1-76.1 76.1z m0-193.8c-50.7 0-91.4-237-91.4-287.4 0-50.5 41-91.4 91.5-91.4s91.4 40.9 91.4 91.4c-0.1 50.4-40.8 287.4-91.5 287.4z" p-id="9831" fill="#dbdbdb"></path></svg>\u7981\u7528\u6570\u636E\u76D1\u7BA1<label class="switch" style="position: absolute; right: 15px;"><input id="cswitch" type="checkbox" '+(window.enableFakeMod?'checked=\'true\'':'')+' onclick="window.switchEnableFakeMod()" ><span class="slider"></span></label>',g.insertBefore(j,g.childNodes[1])}for(var d=0;d<c.length;d++)0<=c[d].innerHTML.indexOf('FAQ')&&(c[d].removeAttribute('href'),c[d].innerHTML='<svg t="1670527911492" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8753" width="16" height="16"><path d="M562.996016 643.229748V72.074369a50.996016 50.996016 0 0 0-101.992032 0v571.155379a50.996016 50.996016 0 0 0 101.992032 0z" fill="#dbdbdb" p-id="8754"></path><path d="M513.087915 144.080744L802.337317 432.446215a50.996016 50.996016 0 0 0 71.93838-72.210358L513.087915 0 149.588313 362.411687A50.996016 50.996016 0 0 0 221.594688 434.486056L513.087915 144.148738zM53.035857 643.229748v184.537583c0 109.471448 105.255777 192.832935 230.026029 192.832935h457.876228c124.770252 0 230.026029-83.361487 230.026029-192.832935V643.229748a50.996016 50.996016 0 1 0-101.992031 0v184.537583c0 47.256308-55.075697 90.840903-128.033998 90.840903H283.061886c-72.9583 0-128.033997-43.65259-128.033998-90.840903V643.229748a50.996016 50.996016 0 0 0-101.992031 0z" fill="#dbdbdb" p-id="8755"></path></svg>\u5BFC\u51FA',c[d].onclick=function(){var h=document.querySelector('textarea'),j=exportSaveData();j&&(h.value=j,alert('\u5B58\u6863\u5DF2\u5BFC\u51FA\u5230\u804A\u5929\u6846\u6587\u672C\u6846\uFF0C\u8BF7\u590D\u5236\u4FDD\u5B58'))}),0<=c[d].innerHTML.indexOf('OpenAI Discord')&&(c[d].removeAttribute('href'),c[d].innerHTML='<svg t="1670527878930" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="7606" width="16" height="16"><path d="M563.2 68.266667v573.44a51.2 51.2 0 0 1-102.4 0V68.266667a51.2 51.2 0 0 1 102.4 0z" fill="#dbdbdb" p-id="7607"></path><path d="M513.092267 616.584533l290.474666-289.518933a51.2 51.2 0 0 1 72.226134 72.4992L513.092267 761.173333 148.138667 397.448533A51.2 51.2 0 0 1 220.433067 324.949333l292.6592 291.6352z" fill="#dbdbdb" p-id="7608"></path><path d="M51.2 641.706667v185.275733c0 109.909333 105.6768 193.604267 230.946133 193.604267h459.707734c125.269333 0 230.946133-83.694933 230.946133-193.604267V641.706667a51.2 51.2 0 1 0-102.4 0v185.275733c0 47.445333-55.296 91.204267-128.546133 91.204267H282.146133c-73.250133 0-128.546133-43.8272-128.546133-91.204267V641.706667a51.2 51.2 0 0 0-102.4 0z" fill="#dbdbdb" p-id="7609"></path></svg>\u5BFC\u5165',c[d].onclick=function(){var h=prompt('\u8BF7\u9ECF\u8D34\u5B58\u6863\u5230\u8F93\u5165\u6846');importSaveData(h)}),0<=c[d].innerHTML.indexOf('Thread')&&(c[d].removeAttribute('href'),c[d].innerHTML='<svg t="1671124885588" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2722" data-darkreader-inline-fill="" width="16" height="16"><path d="M960 416V192l-73.056 73.056a447.712 447.712 0 0 0-373.6-201.088C265.92 63.968 65.312 264.544 65.312 512S265.92 960.032 513.344 960.032a448.064 448.064 0 0 0 415.232-279.488 38.368 38.368 0 1 0-71.136-28.896 371.36 371.36 0 0 1-344.096 231.584C308.32 883.232 142.112 717.024 142.112 512S308.32 140.768 513.344 140.768c132.448 0 251.936 70.08 318.016 179.84L736 416h224z" p-id="2723" fill="#dbdbdb" data-darkreader-inline-fill="" style="--darkreader-inline-fill:#303435;"></path></svg>\u91CD\u7F6E\u4F1A\u8BDD',c[d].onclick=function(){confirm('\u70B9\u51FB\u786E\u8BA4\u540E\u5C06\u5237\u65B0\u4F1A\u8BDD,\u5E76\u6E05\u9664\u6240\u6709\u52A0\u8F7D\u7684\u5B58\u6863\u72B6\u6001\u3002\u662F\u5426\u7EE7\u7EED?')&&(localStorage.removeItem('import_authorization'),localStorage.removeItem('next_parent_message_id'),localStorage.removeItem('next_conversation_id'),localStorage.removeItem('parent_message_id_last'),localStorage.removeItem('conversation_id_last'))})}};for(var button,buttons=document.getElementsByTagName('button'),i=0;i<buttons.length;i++)button=buttons[i],-1!==button.innerHTML.indexOf('sidebar')&&button.addEventListener('click',function(){window.setTimeout(function(){window.boxInit()},300)});window.boxInit(),alert('\u8D5B\u535A\u5DE5\u5177\u5A18v1.1.4\u811A\u672C\u5DF2\u542F\u7528\u3002\u672C\u5DE5\u5177\u7531ChatGPT\u5728\u6307\u5BFC\u4E0B\u81EA\u884C\u7814\u53D1~\r\n\r\n\u66F4\u65B0:\r\n1.\u65B0\u589E\u5B58\u6863\u7BA1\u7406\r\n2.\u300C\u5173\u95ED\u76D1\u7BA1\u300D\u5206\u79BB\u4E3A\u5355\u72EC\u5F00\u5173');var oldf=window.fetch;window.fetch=function(){for(var a=arguments.length,b=Array(a),c=0;c<a;c++)b[c]=arguments[c];if(b[0].includes('moderations')&&window.enableFakeMod)return new Response('{}',{status:200,statusText:'ok'});if(b[0].includes('conversation')){var d=new Headers(b[1].headers),h=d.get('authorization');localStorage.setItem('authorization_last',h);var j=localStorage.getItem('import_authorization');if(j&&(d.set('authorization',j),b[1].headers=d),b[1].body&&'POST'===b[1].method)if(localStorage.getItem('next_conversation_id')&&localStorage.getItem('next_parent_message_id')){var e=localStorage.getItem('next_conversation_id'),f=localStorage.getItem('next_parent_message_id');localStorage.removeItem('next_conversation_id'),localStorage.removeItem('next_parent_message_id');var g=JSON.parse(b[1].body);g.conversation_id=e,g.parent_message_id=f,b[1].body=JSON.stringify(g)}else{var k=JSON.parse(b[1].body);localStorage.setItem('conversation_id_last',k.conversation_id||''),localStorage.setItem('parent_message_id_last',k.parent_message_id||''),localStorage.setItem('body_last',b[1].body)}}return oldf.apply(void 0,b)};var resizeTimer=null;window.onresize=function(){resizeTimer&&clearTimeout(resizeTimer),resizeTimer=setTimeout(function(){window.boxInit()},200)};function exportSaveData(){var a=localStorage.getItem('conversation_id_last')||'',b=localStorage.getItem('parent_message_id_last')||'',c=localStorage.getItem('authorization_last');if(''==a||''==b||'undefined'==a||'undefined'==b)return void alert('\u8BF7\u81F3\u5C11\u8BF4\u4E24\u53E5\u8BDD\u518D\u4F7F\u7528\u8FD9\u4E2A\u529F\u80FD!');var e=JSON.stringify({conversation_id:a,parent_message_id:b,authorization:c}),f=window.btoa(e);return f}function importSaveData(a){var b=window.atob(a),c=JSON.parse(b);return void 0===c.conversation_id||void 0===c.parent_message_id?void alert('\u5B58\u6863\u635F\u574F\u6216\u6570\u636E\u6709\u8BEF\u3002'):void(localStorage.setItem('next_conversation_id',c.conversation_id),localStorage.setItem('next_parent_message_id',c.parent_message_id),alert('\u5B58\u6863\u5BFC\u5165\u6210\u529F'))}function saveData(a,b,c){var d=new Date,e=d.getDate(),f=d.getMonth()+1,g=d.getFullYear().toString().slice(-2),h=d.getHours(),j=d.getMinutes(),k=JSON.parse(localStorage.getItem('savedata'))||[],l={time:g+'-'+f.toString().padStart(2,'0')+'-'+e.toString().padStart(2,'0')+' '+h.toString().padStart(2,'0')+':'+j.toString().padStart(2,'0'),name:b?b:'\u5B58\u6863'+(k.length+1),data:c};0>a||a>=k.length?k.push(l):k[a]=l,localStorage.setItem('savedata',JSON.stringify(k)),alert('\u4FDD\u5B58\u5B8C\u6BD5')}function loadData(a){var b=JSON.parse(localStorage.getItem('savedata'))||[];if(0>a||a>=b.length)return alert('\u8BFB\u53D6\u5931\u8D25\uFF1A\u5B58\u6863\u7D22\u5F15\u8D85\u51FA\u8303\u56F4'),!1;var c=b[a];return importSaveData(c.data||''),!0}window.deleteData=function(a){var b=JSON.parse(localStorage.getItem('savedata'))||[];return 0>a||a>=b.length?(alert('\u5220\u9664\u5931\u8D25\uFF1A\u5B58\u6863\u7D22\u5F15\u8D85\u51FA\u8303\u56F4'),!1):(b.splice(a,1),localStorage.setItem('savedata',JSON.stringify(b)),!0)};function clearAllSaveData(){for(var e,a=document.querySelectorAll('nav'),b=0;b<a.length;b++){e=a[b].querySelectorAll('a.save-data');for(var c=0;c<e.length;c++)e[c].remove();for(var d=a[b].querySelectorAll('div.save-data'),c=0;c<d.length;c++)d[c].remove()}}window.switchEnableFakeMod=function(){var a=document.querySelector('input#cswitch'),b=!!a&&a.checked;b?(window.enableFakeMod=!0,localStorage.setItem('enable_fakemod',!0)):(window.enableFakeMod=!1,localStorage.setItem('enable_fakemod',!1))};
```


2 . 添加一个新的书签，删除所有地址url，黏贴上去并且保存。

<img width="508" alt="image" src="https://user-images.githubusercontent.com/3683548/207085565-7b2598c1-4db1-44d3-961e-143cf089a27a.png">



3 . 在ChatGPT聊天界面点击这个书签，即可激活

<img width="1150" alt="image" src="https://user-images.githubusercontent.com/3683548/207087766-46563180-b562-44c6-9b5e-4b25804e30e4.png">


## 移动端 Chrome 使用指南

移动端分两种情况。

大屏设备如iPad下的Chrome可以直接添加PC版本的书签。

如果是手机等小屏设备，则可能需要手动在地址栏输入开头部分的"javascript:"，手动粘贴精简版的后续部分。



书签无法正常使用的请往下看


1 . 复制以下代码

```
var xhr=new XMLHttpRequest();xhr.open('GET','https://ghproxy.com/https://raw.githubusercontent.com/bigemon/ChatGPT-ToolBox/main/toolbox-chrome-bookmark.js',true);xhr.onload=function(){if(xhr.readyState===4&&xhr.status===200){eval(xhr.responseText)}};xhr.send(null);
```

2 . 在手机Chrome手动输入“javascript:” （不含引号，注意是英文的:）

<img width="787" alt="image" src="https://user-images.githubusercontent.com/3683548/207089837-5d30d419-f25d-4a76-9689-6baa21982d63.png">

3 . 长按粘贴刚才复制的脚本到javascript:的后面。然后回车或开始即可应用

<img width="846" alt="image" src="https://user-images.githubusercontent.com/3683548/207090459-2362fb1d-ed96-4626-8d8d-18ce8cb14f1c.png">

<img width="1473" alt="image" src="https://user-images.githubusercontent.com/3683548/207090891-b0c634a0-dc7b-443a-a180-c7f0773a8af7.png">

