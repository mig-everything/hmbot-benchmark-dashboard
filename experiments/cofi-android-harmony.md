# 阶段1-所有model harness组合的A2H实验

实验规划 · 2026-10-30 · 11 组。历史迁移自报完成 6 组，待运行 5 组。

**自报完成不代表独立验收通过。** 已确认复用6组历史结果，补跑5组；当前执行状态以各行记录为准。

复用6组历史结果。3组完成预检但正式迁移未启动，等待桌面控制恢复；DeepSeek两组待北京时间夜间预检。

| 模型 / ID | Harness | 迁移状态 | 独立验收 | 结果镜像（本地 Tart） | 进度备注 |
|---|---|---|---|---|---|
| MiniMax / MiniMax-M3 | DevEco Code 0.2.3 | 待运行 | 待迁移 | 待产出 | 模型文本、读文件、shell 和独立手机 Demo 预检通过；待桌面控制恢复后从可见 Terminal 启动，正式迁移尚未开始。 日间优先 |
| MiniMax / MiniMax-M3[1m] | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-minimax-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| Qwen / qwen3.8-max | DevEco Code 0.2.3 | 待运行 | 待迁移 | 待产出 | 模型文本、读文件、shell 和独立手机 Demo 预检通过；待桌面控制恢复后从可见 Terminal 启动，正式迁移尚未开始。 使用用户指定网关；先前普通百炼凭据 401 已在新配置下解决。 日间优先 |
| Qwen / qwen3.8-max | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-qwen-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| GLM / glm-5.3 | DevEco Code 0.2.3 | 迁移自报完成 | 待独立验收 | `cofi-deveco-pro-20261029` · 远程地址待补 | 目录中的 pro 为旧名称，实际模型为 GLM。 历史结果已复用 |
| GLM / glm-5.3[1m] | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-glm-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| DeepSeek Pro / deepseek-v4-pro | DevEco Code 0.2.3 | 待运行 | 待迁移 | 待产出 | 模型 ID 暂沿用历史命名，启动前验证并锁定。 北京时间 20:00–08:00 启动 |
| DeepSeek Pro / deepseek-v4-pro | Claude Code 2.1.267 | 迁移自报完成 | 待独立验收 | `cofi-harmony-deepseek-pro-retest-20261028` · 远程地址待补 | 采用 10/28 重测；10/26 旧版测试结果不混入。 历史结果已复用 |
| DeepSeek Flash / deepseek-flash | DevEco Code 0.2.3 | 待运行 | 待迁移 | 待产出 | 模型 ID 暂沿用历史命名，启动前验证并锁定。 北京时间 20:00–08:00 启动 |
| DeepSeek Flash / deepseek-flash | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-deepseek-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| GPT / gpt-6-astra | Codex CLI 0.162.1 | 待运行 | 待迁移 | 待产出 | 模型文本、读文件、shell 和独立手机 Demo 预检通过；待桌面控制恢复后从可见 Terminal 启动，正式迁移尚未开始。 ChatGPT 登录；实际默认 medium，显式 high。 日间优先 |

## 实验口径与待锁定项

- 固定源码：`e3212d7090b0dd3d81ec5a31cb0b0641f68c865a`。每组独立 Tart，8 CPU / 8 GiB，图形化和可见 Terminal。
- Codex 使用 gpt-6-astra + ChatGPT 登录；实际默认 reasoning effort 为 medium，按用户要求显式设置 high。DeepSeek / GLM 限北京时间 20:00–08:00 启动，最多两台 Tart 并行。
- 六组历史完成记录已确认复用。历史 Claude Code 为 2.1.267，基础镜像与 prompt 存在差异，不能宣称完全等条件对照。
- DeepSeek Pro 采用 10/28 重测；10/27 对旧版的测试不混入。其他历史测试存在定位/观测阻塞，不展示为有效综合分。
- 镜像栏为已核实存在的本地 Tart 克隆名称；远程下载地址尚未提供。发布结果镜像前需去除凭据。本页未上传磁盘或原始日志。
- OpenCode + GLM、Codex + GLM、DSH + GLM 和双账号实验不计入本矩阵。

[结构化数据](../data/cofi-android-harmony.json) · [HTML 页面](cofi-android-harmony.html)
