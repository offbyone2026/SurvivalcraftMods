# SurvivalcraftMods

《生存战争》(Survivalcraft) 模组市场仓库 — OffByOne Studio 联机方案配套。

## 结构

```
SurvivalcraftMods/
├── mods/
│   ├── index.json          # 主清单：客户端从主源/兜底源拉取此文件获取全量模组索引
│   └── <ModId>/
│       ├── manifest.json   # 元数据：版本/作者/依赖/SHA256/图标/简介
│       ├── icon.png        # 256x256 图标
│       ├── README.md       # 模组介绍
│       ├── CHANGELOG.md    # 变更日志
│       └── versions/
│           ├── v1.0.0/mod.dll
│           └── v1.1.0/mod.dll
└── .github/workflows/      # 自动构建发布（tag v* 触发）
```

## 拉取源

客户端按以下优先级自动 failover，超时自动切换：

1. GitHub 直连（权威源）：`https://github.com/offbyone2026/SurvivalcraftMods/raw/main`
2. jsDelivr CDN：`https://cdn.jsdelivr.net/gh/offbyone2026/SurvivalcraftMods@main`
3. gh-proxy 代理：`https://gh-proxy.com/https://raw.githubusercontent.com/offbyone2026/SurvivalcraftMods/main`

## 发布流程

1. 本地开发模组 → `git tag v1.0.0` → `git push origin main --tags`
2. GitHub Actions 自动构建 `.dll`、生成 manifest、创建 Release
3. 客户端模组市场刷新 `index.json` → 展示新版本 → 一键直装

## 版权声明

仓库内模组均为第三方作者作品，各自保留版权；本仓库仅做索引与分发。
