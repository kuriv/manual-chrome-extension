# options

 options 是用于让用户配置插件参数的独立页面，可以通过扩展选项或 popup 内的链接打开。更新 `popup.html` 文件内容如下。

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
    <button id="btn-options">Options</button>
    <script type="text/javascript" src="popup.js"></script>
</body>
</html>
```

更新 `popup.css` 文件内容如下。

```css
body {
    text-align: center;
}

button {
    border: none;
    border-radius: 5px;
    color: #fff;
    cursor: pointer;
    font-size: 14px;
    font-weight: 500;
    margin: 10px;
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

#btn-options {
    background-color: #f472b6;
}

#btn-options:hover {
    background-color: #e8799f;
}

#btn-options:active {
    background-color: #d946ef;
}
```

更新 `popup.js` 文件内容如下。

```javascript
const btn_popup = document.querySelector('#btn-popup');
btn_popup.addEventListener('click', () => alert('Hello World!'));

const btn_options = document.querySelector('#btn-options');
btn_options.addEventListener('click', () => chrome.runtime.openOptionsPage());
```

在插件目录中新建 `options.html` 文件内容如下。

```html
<!DOCTYPE html>
<html lang="zh-Hans">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demo</title>
    <link rel="stylesheet" type="text/css" href="options.css">
</head>
<body>
    <h1>Hello World!</h1>
    <script type="text/javascript" src="options.js"></script>
</body>
</html>
```

在插件目录中新建 `options.css` 文件内容如下。

```css
h1 {
    text-align: center;
}
```

在插件目录中新建 `options.js` 文件内容如下。

```javascript
setInterval(() => console.log('Hello World!'), 3000);
```

