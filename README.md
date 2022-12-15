# ChatGPT-ToolBox

由ChatGPT负责编写的ChatGPT工具箱。除了向ChatGPT提供必要的数据，尽可能不由人类写任何代码。

当前版本提供以下功能：

1.关闭数据监管

2.会话存档导入导出

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
javascript:window.enableFakeMod=false;var buttons=document.getElementsByTagName('button');for(var i=0;i<buttons.length;i++){var button=buttons[i];if(button.innerHTML.indexOf('sidebar')!==-1){button.addEventListener('click',function(){window.setTimeout(function(){boxInit()},300)})}}function boxInit(){var navs=document.querySelectorAll('nav');for(var x=0;x<navs.length;x++){var nav=navs[x];var aEle=nav.querySelectorAll('a');for(var i=0;i<aEle.length;i++){if(aEle[i].innerHTML.indexOf('FAQ')>=0){aEle[i].removeAttribute('href');aEle[i].innerHTML='<svg t="1670527911492" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8753" width="16" height="16"><path d="M562.996016 643.229748V72.074369a50.996016 50.996016 0 0 0-101.992032 0v571.155379a50.996016 50.996016 0 0 0 101.992032 0z" fill="#dbdbdb" p-id="8754"></path><path d="M513.087915 144.080744L802.337317 432.446215a50.996016 50.996016 0 0 0 71.93838-72.210358L513.087915 0 149.588313 362.411687A50.996016 50.996016 0 0 0 221.594688 434.486056L513.087915 144.148738zM53.035857 643.229748v184.537583c0 109.471448 105.255777 192.832935 230.026029 192.832935h457.876228c124.770252 0 230.026029-83.361487 230.026029-192.832935V643.229748a50.996016 50.996016 0 1 0-101.992031 0v184.537583c0 47.256308-55.075697 90.840903-128.033998 90.840903H283.061886c-72.9583 0-128.033997-43.65259-128.033998-90.840903V643.229748a50.996016 50.996016 0 0 0-101.992031 0z" fill="#dbdbdb" p-id="8755"></path></svg>导出';aEle[i].onclick=function(){var conversation_id=localStorage.getItem("conversation_id_last")||"";var parent_message_id=localStorage.getItem("parent_message_id_last")||"";var authorization=localStorage.getItem("authorization_last");if(conversation_id==""||parent_message_id==""||conversation_id=="undefined"||parent_message_id=="undefined"){alert("请至少说两句话再使用这个功能!");return}var jsonObject={conversation_id:conversation_id,parent_message_id:parent_message_id,authorization:authorization};var jsonString=JSON.stringify(jsonObject);var base64String=window.btoa(jsonString);var textarea=document.querySelector("textarea");textarea.value=base64String;alert("存档已导出到聊天框文本框，请复制保存")}}if(aEle[i].innerHTML.indexOf('OpenAI Discord')>=0){aEle[i].removeAttribute('href');aEle[i].innerHTML='<svg t="1670527878930" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="7606" width="16" height="16"><path d="M563.2 68.266667v573.44a51.2 51.2 0 0 1-102.4 0V68.266667a51.2 51.2 0 0 1 102.4 0z" fill="#dbdbdb" p-id="7607"></path><path d="M513.092267 616.584533l290.474666-289.518933a51.2 51.2 0 0 1 72.226134 72.4992L513.092267 761.173333 148.138667 397.448533A51.2 51.2 0 0 1 220.433067 324.949333l292.6592 291.6352z" fill="#dbdbdb" p-id="7608"></path><path d="M51.2 641.706667v185.275733c0 109.909333 105.6768 193.604267 230.946133 193.604267h459.707734c125.269333 0 230.946133-83.694933 230.946133-193.604267V641.706667a51.2 51.2 0 1 0-102.4 0v185.275733c0 47.445333-55.296 91.204267-128.546133 91.204267H282.146133c-73.250133 0-128.546133-43.8272-128.546133-91.204267V641.706667a51.2 51.2 0 0 0-102.4 0z" fill="#dbdbdb" p-id="7609"></path></svg>导入';aEle[i].onclick=function(){var userInput=prompt("请黏贴存档到输入框");var decodedString=window.atob(userInput);var jsonObject=JSON.parse(decodedString);if(jsonObject.conversation_id===undefined||jsonObject.parent_message_id===undefined){alert("存档损坏或数据有误。");return}localStorage.setItem("next_conversation_id",jsonObject.conversation_id);localStorage.setItem("next_parent_message_id",jsonObject.parent_message_id);alert("存档导入成功")}}if(aEle[i].innerHTML.indexOf('Thread')>=0){aEle[i].removeAttribute('href');aEle[i].innerHTML='<svg t="1670527970700" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="9830" width="18" height="18"><path d="M514 114.3c-219.9 0-398.8 178.9-398.8 398.8 0 220 178.9 398.9 398.8 398.9s398.8-178.9 398.8-398.8S733.9 114.3 514 114.3z m0 685.2c-42 0-76.1-34.1-76.1-76.1 0-42 34.1-76.1 76.1-76.1 42 0 76.1 34.1 76.1 76.1 0 42.1-34.1 76.1-76.1 76.1z m0-193.8c-50.7 0-91.4-237-91.4-287.4 0-50.5 41-91.4 91.5-91.4s91.4 40.9 91.4 91.4c-0.1 50.4-40.8 287.4-91.5 287.4z" p-id="9831" fill="#dbdbdb"></path></svg>关闭监管&重置存档';aEle[i].onclick=function(){alert('模型监管接口将在点击确认后关闭，在此之前请确认您所在地法律法规！此外，导入的存档也将在刷新后失效。');window.enableFakeMod=true;localStorage.removeItem('import_authorization');localStorage.removeItem('next_parent_message_id');localStorage.removeItem('next_conversation_id');localStorage.removeItem('parent_message_id_last');localStorage.removeItem('conversation_id_last');var divs=document.getElementsByTagName('div');var lastDiv=null;for(var i=0;i<divs.length;i++){if(divs[i].innerHTML.includes("Free Research Preview")){lastDiv=divs[i]}}if(lastDiv){lastDiv.innerHTML="数据监管模式已关闭，请谨慎使用。";lastDiv.style.color="yellow"}}}}}}boxInit();alert("赛博工具娘v1.0.8脚本已启用。本工具全程由ChatGPT在指导下自行研发~\r\n\r\n更新:增加了移动端导航栏覆盖");const oldf=window.fetch;window.fetch=function(...args){if(args[0].includes("moderations")&&window.enableFakeMod){return new Response('{}',{status:200,statusText:"ok",})}if(args[0].includes("conversation")){var headers=new Headers(args[1].headers);const authorization=headers.get("authorization");localStorage.setItem("authorization_last",authorization);const au=localStorage.getItem("import_authorization");if(au){headers.set("authorization",au);args[1].headers=headers}if(args[1].body&&args[1].method==="POST"){if(localStorage.getItem("next_conversation_id")&&localStorage.getItem("next_parent_message_id")){var nextConversationId=localStorage.getItem("next_conversation_id");var nextParentMessageId=localStorage.getItem("next_parent_message_id");localStorage.removeItem("next_conversation_id");localStorage.removeItem("next_parent_message_id");var ob=JSON.parse(args[1].body);ob.conversation_id=nextConversationId;ob.parent_message_id=nextParentMessageId;args[1].body=JSON.stringify(ob)}else{const bb=JSON.parse(args[1].body);localStorage.setItem("conversation_id_last",bb.conversation_id||"");localStorage.setItem("parent_message_id_last",bb.parent_message_id||"");localStorage.setItem("body_last",args[1].body)}}}return oldf(...args)}
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

