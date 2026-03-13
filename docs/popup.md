# popup

popup 是 Chrome 扩展程序核心交互界面之一，它是用户点击浏览器右上角插件图标时弹出的小窗口。在插件目录中新建 `popup.html` 文件内容如下。

```html
<!DOCTYPE html>
<html lang="zh-Hans">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demo</title>
    <link rel="stylesheet" type="text/css" href="popup.css">
</head>
<body>
    <button id="btn-popup">Click</button>
    <script type="text/javascript" src="popup.js"></script>
</body>
</html>
```

在插件目录中新建 `popup.css` 文件内容如下。

```css
button {
    border: none;
    border-radius: 5px;
    color: #fff;
    cursor: pointer;
    font-size: 14px;
    font-weight: 500;
    outline: 0;
    padding: 10px 20px;
    transition: all .2s ease;
    -webkit-tap-highlight-color: transparent;
}

button:hover {
    box-shadow: 0 2px 8px rgba(37, 99, 235, .2);
}

button:active {
    box-shadow: 0 1px 4px rgba(37, 99, 235, .15);
}

#btn-popup {
    background-color: #2563eb;
}

#btn-popup:hover {
    background-color: #1d4ed8;
}

#btn-popup:active {
    background-color: #1e40af;
}
```

在插件目录中新建 `popup.js` 文件内容如下。

```javascript
const btn_popup = document.querySelector('#btn-popup');
btn_popup.addEventListener('click', () => alert('Hello World!'));
```

由于 popup 生命周期较短，失去焦点即关闭，因此长时间任务需借助后台服务。
