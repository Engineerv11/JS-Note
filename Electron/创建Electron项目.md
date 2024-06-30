创建Electron项目
===

1. 输入指令 npm init，根据提示输入项目配置信息

2. 输入指令 npm install electron --save-dev 安装 Electron

3. 在根目录创建 index.js

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8" />
    <!-- https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP -->
    <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self'" />
    <meta http-equiv="X-Content-Security-Policy" content="default-src 'self'; script-src 'self'" />
    <title>Hello from Electron!</title>
</head>

<body>
    <h1>Hello from Electron!</h1>
    <p>Engineer (▼ヘ▼#)</p>
</body>

</html>
```

4. 在根目录创建 main.js

```javascript
const { app, BrowserWindow } = require('electron')

const createWindow = () =>
{
    const win = new BrowserWindow({
        width: 800,
        height: 600
    })

    win.loadFile('index.html')
}

app.whenReady().then(() =>
{
    createWindow()
})
```

5. 在 package.json 的 scripts 字段中添加一个 start 命令，内容为 electron .

```json
{
  "name": "launcher",
  "version": "1.0.0",
  "main": "main.js",
  "scripts": {
    "start": "electron .",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "description": "",
  "devDependencies": {
    "electron": "^31.1.0"
  }
}
```

6. 在终端输入 npm run start 运行
