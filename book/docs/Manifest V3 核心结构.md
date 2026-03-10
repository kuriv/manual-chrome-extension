# Manifest V3 核心结构

Manifest V3 是 Chrome 扩展程序的配置标准，它本质是一个 `manifest.json` 配置文件，浏览器通过它识别插件的名称、权限、运行逻辑、界面入口等信息。

```json
{
	"manifest_version": 3,
    "name": "Demo",
    "version": "1.0",
    "description": "Hello World!",
    "icons": {
        "16": "icons/icon16.png",
		"48": "icons/icon48.png",
		"128": "icons/icon128.png"
    },
    "action": {
        "default_popup": "popup.html",
		"default_icon": "icons/icon48.png"
    },
    "background": {
        "service_worker": "background.js"
    },
    "content_scripts": [
    {
		"matches": ["<all_urls>"],
		"js": ["content.js"],
		"css": ["content.css"],
		"run_at": "document_end"
    }
    ],
    "permissions": ["storage", "tabs"],
    "host_permissions": ["<all_urls>"],
    "options_page": "options.html"
}
```

