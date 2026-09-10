# 乳腺癌术前新辅助治疗 · 个案管理师培训（答题视频课程）

GitHub Pages 静态站点。包含：1080P→720p 培训视频（温柔女声配音）、按语音断句的可开关字幕、5 道随堂单选题（答对才能继续观看）、全屏与手机适配。

## 文件清单

| 文件 | 用途 |
|---|---|
| `index.html` | 播放器页面（视频 Blob 预载、弹窗答题、字幕开关、全屏） |
| `video.mp4` | 720p H.264/AAC faststart 视频（约 10.3MB，无烧录字幕） |
| `sub_data.js` | 字幕数据（153 条，按语音断句） |
| `.nojekyll` | 关闭 GitHub Pages 的 Jekyll 处理，确保文件原样发布 |

## 当前状态（已完成）

本地 git 仓库已初始化并完成首次提交，5 个文件均已入库。只需在 GitHub 建一个**空仓库**（创建时不要勾选 README/.gitignore），然后执行：

```bash
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git branch -M main
git push -u origin main
```

首次推送会弹出浏览器授权窗口（Git Credential Manager），登录并授权一次即可。

> 提交身份目前是占位值（WorkBuddy / assistant@local），如需要可先修改：
> `git config user.name "你的名字"` 与 `git config user.email "你的邮箱"`，再执行
> `git commit --amend --reset-author --no-edit`。

## 发布步骤（GitHub Pages）

1. 在 GitHub 创建一个仓库（Public，免费账户 Pages 需公开仓库）。
2. 把本目录全部 4 个文件推送到默认分支（main）：

```bash
cd 本目录
git init
git add .
git commit -m "feat: 培训视频课程站点"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

3. 仓库 → Settings → Pages → Source 选择 `Deploy from a branch`，Branch 选 `main` / `(root)`，保存。
4. 等待 1~2 分钟，访问 `https://<你的用户名>.github.io/<仓库名>/` 即为分享链接。

## 注意事项

- 免费版 GitHub Pages 站点为**公开访问**，任何拿到链接的人都可观看；如内容敏感请改用私有部署方案。
- 单文件上限 100MB（video.mp4 约 10.3MB，远低于限制）；仓库建议小于 1GB。
- 更新视频后需 `git add . && git commit && git push`，并注意 GitHub CDN 缓存（可改名 video_v2.mp4 并同步修改 index.html 中的 fetch('video.mp4') 两处）。
