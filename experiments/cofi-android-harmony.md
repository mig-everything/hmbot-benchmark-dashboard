# Cofi · Android → HarmonyOS

实验规划 · 2026-10-30 · 11 组。历史迁移自报完成 6 组，待运行 5 组。

**自报完成不代表独立验收通过。** 本轮仅登记计划与历史证据，尚未启动新实验。

| 模型 / ID | Harness | 迁移状态 | 独立验收 | 结果镜像（本地 Tart） |
|---|---|---|---|---|
| MiniMax / MiniMax-M3[1m] | DevEco Code 待锁定 | 待运行 | 待迁移 | 待产出 |
| MiniMax / MiniMax-M3[1m] | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-minimax-20261026` · 远程地址待补 |
| Qwen / qwen3.8-max | DevEco Code 待锁定 | 待运行 | 待迁移 | 待产出 |
| Qwen / qwen3.8-max | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-qwen-20261026` · 远程地址待补 |
| GLM / glm-5.3 | DevEco Code 0.2.3 | 迁移自报完成 | 待独立验收 | `cofi-deveco-pro-20261029` · 远程地址待补 |
| GLM / glm-5.3[1m] | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-glm-20261026` · 远程地址待补 |
| DeepSeek Pro / deepseek-v4-pro | DevEco Code 待锁定 | 待运行 | 待迁移 | 待产出 |
| DeepSeek Pro / deepseek-v4-pro | Claude Code 2.1.267 | 迁移自报完成 | 待独立验收 | `cofi-harmony-deepseek-pro-retest-20261028` · 远程地址待补 |
| DeepSeek Flash / deepseek-flash | DevEco Code 待锁定 | 待运行 | 待迁移 | 待产出 |
| DeepSeek Flash / deepseek-flash | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-deepseek-20261026` · 远程地址待补 |
| GPT / 待确定准确型号与 reasoning effort | Codex CLI 待锁定 | 待运行 | 待迁移 | 待产出 |

## 实验口径与待锁定项

- 固定源码：`e3212d7090b0dd3d81ec5a31cb0b0641f68c865a`。建议每组独立 Tart，8 CPU / 8 GiB，图形化和可见 Terminal。
- GPT 的准确型号、reasoning effort，以及待运行组的模型和 Harness 版本须在启动前锁定。
- 六组完成记录为历史证据；是否复用或统一重测待锁定。历史 Claude Code 为 2.1.267，基础镜像与 prompt 存在差异，不能宣称完全等条件对照。
- DeepSeek Pro 采用 10/28 重测；10/27 对旧版的测试不混入。其他历史测试存在定位/观测阻塞，不展示为有效综合分。
- 镜像栏为已核实存在的本地 Tart 克隆名称；远程下载地址尚未提供。发布结果镜像前需去除凭据。本页未上传磁盘或原始日志。
- OpenCode + GLM、Codex + GLM、DSH + GLM 和双账号实验不计入本矩阵。

[结构化数据](../data/cofi-android-harmony.json) · [HTML 页面](cofi-android-harmony.html)
