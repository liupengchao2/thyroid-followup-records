# 术后随访记录

一个适合手机使用的静态随访页面，用来记录每次复查、药量调整和化验单图片。项目不依赖后端，部署到 GitHub Pages 后就能直接在手机浏览器打开。

## 已实现

- 手机优先的单页界面
- 每次检查结果录入
- 每次用药调整录入
- 化验单图片上传、预览、绑定到某次复查
- 本地离线保存
- JSON 导出 / 导入
- 可选的 GitHub JSON 同步
- GitHub Pages 自动部署工作流

## 本地打开

直接双击 `index.html` 即可，或者在当前目录启动一个静态服务：

```bash
python3 -m http.server 8000
```

然后打开 `http://localhost:8000/`。

## 部署到 GitHub Pages

### 1. 登录 GitHub CLI

```bash
gh auth login
```

### 2. 初始化仓库并提交

```bash
git init
git checkout -b main
git add .
git commit -m "Create thyroid follow-up mobile app"
```

### 3. 创建 GitHub 仓库并推送

把下面的 `YOUR_NAME` 和仓库名替换成你自己的：

```bash
gh repo create thyroid-followup-mobile --public --source=. --remote=origin --push
```

### 4. 启用 GitHub Pages

进入仓库页面：

- `Settings`
- `Pages`
- `Build and deployment`
- 选择 `GitHub Actions`

推送后，工作流会自动发布。地址通常是：

```text
https://YOUR_NAME.github.io/thyroid-followup-mobile/
```

## 手机使用建议

- iPhone：用 Safari 打开后，点“分享”再点“添加到主屏幕”
- Android：用 Chrome 打开后，点菜单里的“安装应用”或“添加到主屏幕”
- 文字记录建议同步到 GitHub
- 图片建议优先本地保存，并定期导出 JSON 备份

## 关于 GitHub Token

页面里的 GitHub 同步功能是可选的。如果要在页面里直接上传 JSON：

- 建议使用 Fine-grained Personal Access Token
- 权限尽量只给目标仓库的 Contents 读写
- 不要在公共设备上保存 Token

