# wuwa-achievement

鸣潮离线成就统计页面生成器。

本项目用于读取用户自行提供的 SQLite 数据库文件，并生成可直接部署到 GitHub Pages 的静态成就勾选页面。生成结果为自包含 HTML，不依赖后端服务，适合用于查看、搜索和手动标记成就完成情况。

在线页面：<https://wuwa.lyqgzbl.com/achievement/>

## 功能特点

- 生成简体中文成就清单页面
- 支持按分类浏览成就内容
- 支持在静态页面中手动勾选完成状态
- 输出单个自包含 HTML 文件，便于公开部署
- 仅读取命令行显式传入的数据库路径

## 所需输入

运行前需要自行准备以下文件：

- 成就配置数据库：`db_achievement.db`
- 简体中文文本数据库：一个或多个 `lang_multi_text*.db`

## 生成页面

在仓库根目录运行：

```bash
python -m Tools \
  --config-db /path/to/db_achievement.db \
  --multitext-db /path/to/lang_multi_text.db \
  --multitext-db /path/to/lang_multi_text_1sthalf.db \
  --out docs/achievement_tracker_zh.html
```

生成后的页面文件为：

```text
docs/achievement_tracker_zh.html
```

## 参数说明

- `--config-db`：`db_achievement.db` 的路径
- `--multitext-db`：`lang_multi_text*.db` 的路径，可重复传入多个
- `--out`：输出 HTML 路径，默认 `out/achievement_tracker_zh.html`
- `--root`：输出根目录，默认当前目录

