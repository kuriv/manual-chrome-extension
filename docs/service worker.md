# service worker

`service worker` 负责处理全局逻辑，它没有 DOM 访问权限，不能操作页面元素，空闲时会自动休眠，直至触发事件时唤醒。在插件目录中新建 `service-worker.js` 文件内容如下。

```javascript
chrome.runtime.onInstalled.addListener(details => {
    console.log(details);
    details.reason == 'install' ? console.log('Hello World!') : console.log('Welcome!');
});

chrome.runtime.onSuspend.addListener(() => console.log('Hello World!'));

chrome.runtime.onSuspendCanceled.addListener(() => console.log('Welcome!'));

chrome.tabs.onCreated.addListener(tab => console.log(tab.id, tab.url));
```

