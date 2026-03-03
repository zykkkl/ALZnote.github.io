# 启用 GitHub Actions 的步骤

## 问题诊断

你的 GitHub Actions 工作流配置文件正确，但 Actions 标签页没有任何运行记录，这通常是因为：

1. **GitHub Actions 在仓库中被禁用**
2. **工作流文件没有被正确推送到仓库**
3. **仓库权限设置问题**

## 解决方案

### 步骤 1: 启用 GitHub Actions

1. 访问你的 GitHub 仓库：https://github.com/zykkkl/ALZnote.github.io
2. 点击 **Settings**（设置）标签
3. 在左侧菜单中找到 **Actions** → **General**
4. 在 "Actions permissions" 部分，确保选择：
   - ✅ **Allow all actions and reusable workflows**（允许所有 actions 和可重用工作流）
   或
   - ✅ **Allow [organization] actions and reusable workflows**
5. 向下滚动，在 "Workflow permissions" 部分，选择：
   - ✅ **Read and write permissions**（读写权限）
   - ✅ 勾选 **Allow GitHub Actions to create and approve pull requests**
6. 点击 **Save** 保存设置

### 步骤 2: 验证工作流文件是否已推送

在本地运行以下命令检查：

```bash
cd e:\Github\ALZnote.github.io\ALZnote
git log --oneline -1
```

然后访问 GitHub 仓库，检查 `.github/workflows/deploy.yml` 文件是否存在。

### 步骤 3: 手动触发工作流

启用 Actions 后：

1. 访问仓库的 **Actions** 标签页
2. 在左侧应该能看到 "Deploy MkDocs" 工作流
3. 点击工作流名称
4. 点击右侧的 **Run workflow** 按钮
5. 选择 `main` 分支
6. 点击绿色的 **Run workflow** 按钮

### 步骤 4: 配置 GitHub Pages

确保 GitHub Pages 已正确配置：

1. 进入 **Settings** → **Pages**
2. **Source** 选择：`Deploy from a branch`
3. **Branch** 选择：`gh-pages` 分支，目录选择 `/ (root)`
4. 点击 **Save**

注意：首次运行工作流后才会创建 `gh-pages` 分支。

## 常见问题

### 如果 Actions 标签页不存在

某些仓库类型（如 fork 的仓库）默认禁用 Actions，需要手动启用：

1. 进入 **Settings** → **Actions** → **General**
2. 点击 **Enable Actions for this repository**

### 如果工作流运行失败

查看错误日志：

1. 进入 **Actions** 标签页
2. 点击失败的工作流运行
3. 点击失败的步骤查看详细错误信息

常见错误：
- **权限问题**：确保 Workflow permissions 设置为 "Read and write"
- **依赖安装失败**：检查 requirements.txt 中的包版本
- **构建失败**：检查 mkdocs.yml 配置是否正确

## 验证部署成功

工作流成功运行后：

1. 检查是否创建了 `gh-pages` 分支
2. 访问你的网站：https://zykkkl.github.io/ALZnote.github.io/ 或自定义域名
3. 如果使用自定义域名，确保在 Settings → Pages 中配置了 Custom domain

## 需要帮助？

如果按照以上步骤操作后仍然有问题，请提供：
- Actions 标签页的截图
- Settings → Actions → General 的配置截图
- 任何错误信息

我会帮你进一步诊断问题。
