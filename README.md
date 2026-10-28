# 我的技术文档

使用 MkDocs + Material 主题构建的静态文档站点，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

## 目录结构

```
github-pages/
├── docs/                    # Markdown 文档源文件
│   ├── index.md             # 主页
│   ├── about.md             # 关于页面
│   ├── guide.md             # 使用指南
│   └── api.md               # API 参考
├── .github/
│   └── workflows/
│       └── deploy.yml       # 自动部署工作流
├── mkdocs.yml               # MkDocs 配置
└── README.md
```

## 本地预览

```bash
pip install mkdocs-material
mkdocs serve
```

默认可在 http://127.0.0.1:8000 查看站点。

## 部署方式

向 `main` 分支推送 `docs/` 或 `mkdocs.yml` 的改动后，工作流会自动执行：

1. 检出代码
2. 安装 Python 3.9
3. 安装 `mkdocs-material`
4. `mkdocs build` 生成 `site/`
5. 将 `site/` 推送到 `gh-pages` 分支

GitHub Pages 从 `gh-pages` 分支提供静态页面。
