# 抽签页面部署说明

## 功能说明

- 抽签结果为1、2、3三个数字之一
- 提供一次性链接分享功能，抽完即失效
- 包含动态抽签效果
- 结果实时反馈

## 部署步骤

### 方法一：使用GitHub Pages（推荐）

1. 在GitHub上创建一个新的仓库
2. 将 `index.html` 文件上传到仓库
3. 进入仓库设置，找到 "Pages" 选项
4. 选择分支为 `main`，目录为 `/`，点击 "Save"
5. 等待几分钟后，GitHub会生成一个可访问的URL
6. 通过该URL访问抽签页面，生成的分享链接即可在网络上传播

### 方法二：使用Vercel

1. 访问 https://vercel.com
2. 使用GitHub账号登录
3. 点击 "New Project"
4. 选择要部署的GitHub仓库
5. 点击 "Deploy"
6. 部署完成后，Vercel会生成一个可访问的URL

### 方法三：使用Netlify

1. 访问 https://www.netlify.com
2. 使用GitHub账号登录
3. 点击 "Add new site" → "Import an existing project"
4. 选择要部署的GitHub仓库
5. 点击 "Deploy site"
6. 部署完成后，Netlify会生成一个可访问的URL

## 本地测试

如果您想在本地测试，可以使用以下方法启动本地服务器：

### 使用Python

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

然后在浏览器中访问 http://localhost:8000

### 使用Node.js

如果您安装了Node.js和npm，可以使用 http-server 包：

```bash
npm install -g http-server
http-server -p 8000
```

然后在浏览器中访问 http://localhost:8000

## 注意事项

- 由于使用了LocalStorage存储已使用的链接ID，在不同设备上访问同一链接时，可能会出现链接未失效的情况
- 若要实现跨设备的链接失效功能，需要添加后端服务器存储已使用的链接ID
- 部署到网络后，生成的分享链接即可在网络上传播，他人通过链接访问后可以进行抽签
