# HMBot Benchmark Dashboard

[打开阶段1-所有model harness组合的A2H实验](experiments/cofi-android-harmony.md)

独立页面：`experiments/cofi-android-harmony.html`，含 11 组实验、状态筛选及历史结果镜像登记。HTML 可直接打开，也可使用任意静态服务托管。

数据源：`data/cofi-android-harmony.json`。更新数据后运行 `python3 scripts/render.py` 同步生成 HTML 和 GitHub 文档版。页面登记执行进度与历史证据；实验调度由独立队列管理。阶段1复用6组历史结果、补跑5组，最多2台Tart并行，DeepSeek/GLM在北京时间夜间启动。

六组历史迁移自报完成不代表独立验收通过；本地 Tart 克隆名称不等于远程下载地址。尚未配置 GitHub Pages。
