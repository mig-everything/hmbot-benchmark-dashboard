# 阶段1-所有model harness组合的A2H实验

实验规划 · 2026-10-30 · 11 组。历史迁移自报完成 6 组，其余 5 组状态见下表。

**自报完成不代表独立验收通过。** 已确认复用6组历史结果，补跑5组；当前执行状态以各行记录为准。

14:17 北京时间：9组迁移自报完成（6组历史复用及本批MiniMax/DevEco、Qwen/DevEco、GPT/Codex）；本批三组均已归档校验并释放专属资源。Qwen首条prompt重复偏差保留，上述状态不等于独立验收。剩余DeepSeek Pro、Flash的DevEco两组已离线准备，等待北京时间20:00后独立预检和正式启动。

| 模型 / ID | Harness | 迁移状态 | 独立验收 | 结果镜像（本地 Tart） | 进度备注 |
|---|---|---|---|---|---|
| MiniMax / MiniMax-M3 | DevEco Code 0.2.3 | 迁移自报完成 | 待独立验收 | `s1-cofi-minimax-deveco-20261030` · 远程地址待补 | 13:17 后确认全部会话日志静默，归档693个文件并校验SHA；专属手机、relay与Tart已关闭，保留磁盘。agent自报14/14自检通过，未独立验收。自报限制包括PiP未实现、仅中英两语、未移植Wear OS及波浪环近似。首条prompt仅首尾空白差异。 日间优先 |
| MiniMax / MiniMax-M3[1m] | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-minimax-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| Qwen / qwen3.8-max | DevEco Code 0.2.3 | 迁移自报完成 | 待独立验收；存在 prompt 偏差 | `s1-cofi-qwen-deveco-20261030` · 远程地址待补 | 14:17 北京时间完成15分钟全会话静默复核，归档664文件及原生日志并校验SHA；手机/relay/VM已停止，磁盘保留。自报16种语言、11张设备截图、27文件arkts_check零错误；PiP/WearOS/动态快捷方式未迁移，Material You固定色板，冻结期回前台追补。首条消息误含两遍相同原始prompt；本轮不属于严格同prompt对照，不自动纠正或重跑。 日间优先 |
| Qwen / qwen3.8-max | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-qwen-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| GLM / glm-5.3 | DevEco Code 0.2.3 | 迁移自报完成 | 待独立验收 | `cofi-deveco-pro-20261029` · 远程地址待补 | 目录中的 pro 为旧名称，实际模型为 GLM。 历史结果已复用 |
| GLM / glm-5.3[1m] | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-glm-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| DeepSeek Pro / deepseek-v4-pro | DevEco Code 0.2.3 | 待运行 | 待迁移 | 待产出 | 独立8CPU/8GiB克隆及专属设备文件已离线准备，均未启动；任务/启动草案已保存，尚未做本轮模型和设备预检。等待北京时间20:00后继续，模型ID仍须实际预检锁定。 北京时间 20:00–08:00 启动 |
| DeepSeek Pro / deepseek-v4-pro | Claude Code 2.1.267 | 迁移自报完成 | 待独立验收 | `cofi-harmony-deepseek-pro-retest-20261028` · 远程地址待补 | 采用 10/28 重测；10/26 旧版测试结果不混入。 历史结果已复用 |
| DeepSeek Flash / deepseek-flash | DevEco Code 0.2.3 | 待运行 | 待迁移 | 待产出 | 独立8CPU/8GiB克隆及专属设备文件已离线准备，均未启动；任务/启动草案已保存，尚未做本轮模型和设备预检。等待北京时间20:00后继续，模型ID仍须实际预检锁定。 北京时间 20:00–08:00 启动 |
| DeepSeek Flash / deepseek-flash | Claude Code 2.1.267 | 迁移自报完成 | 历史测试已执行；定位/观测受阻，未判定验收通过 | `cofi-harmony-deepseek-20261026` · 远程地址待补 | 已确认复用历史结果。 历史结果已复用 |
| GPT / gpt-6-astra | Codex CLI 0.162.1 | 迁移自报完成 | 待独立验收 | `s1-cofi-gpt-codex-20261030` · 远程地址待补 | 14:02 北京时间完成15分钟全线程静默复核；已归档1204文件、2内部相对链接及原生日志并校验SHA；专属手机/relay/代理/VM已停止，保留磁盘。ArkTS + 离线ArkWeb；agent自报12核心测试、12组浏览器流程、19项设备内断言。WearOS、系统PiP、壁纸取色未迁移；通知/文件选择器未人工验收；unsigned HAP。gpt-6-astra/high与首条prompt SHA已核实。 日间优先 |

## 实验口径与待锁定项

- 固定源码：`e3212d7090b0dd3d81ec5a31cb0b0641f68c865a`。每组独立 Tart，8 CPU / 8 GiB，图形化和可见 Terminal。
- Codex 使用 gpt-6-astra + ChatGPT 登录；实际默认 reasoning effort 为 medium，按用户要求显式设置 high。DeepSeek / GLM 限北京时间 20:00–08:00 启动，最多两台 Tart 并行。
- 六组历史完成记录已确认复用。历史 Claude Code 为 2.1.267，基础镜像与 prompt 存在差异，不能宣称完全等条件对照。
- DeepSeek Pro 采用 10/28 重测；10/27 对旧版的测试不混入。其他历史测试存在定位/观测阻塞，不展示为有效综合分。
- 镜像栏为已核实存在的本地 Tart 克隆名称；远程下载地址尚未提供。发布结果镜像前需去除凭据。本页未上传磁盘或原始日志。
- OpenCode + GLM、Codex + GLM、DSH + GLM 和双账号实验不计入本矩阵。

[结构化数据](../data/cofi-android-harmony.json) · [HTML 页面](cofi-android-harmony.html)
