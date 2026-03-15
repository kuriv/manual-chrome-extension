# content

`content` 能操作当前页面的 DOM、监听页面事件。在插件目录中新建 `content.css` 文件内容如下。

```css
#watermark {
    background: rgba(0, 0, 0, .7);
    border-radius: 4px;
    bottom: 20px;
    color: #fff;
    font-size: 12px;
    padding: 8px 16px;
    pointer-events: none;
    position: fixed;
    right: 20px;
    z-index: 999;
}
```

在插件目录中新建 `content.js` 文件内容如下。

```javascript
const watermark = document.createElement('div');
watermark.id = 'watermark';
watermark.textContent = 'Hello World!';
document.body.appendChild(watermark);
```

`content` 注入后，所有页面都会在右下角显示自定义水印。
