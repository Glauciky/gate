# 协同中枢章程（0002 号工程 · 阶段 1 定版 v2）

本目录是「多智能体跨账号协同」的中枢：公告板（progress/）+ 文件柜（artifacts/）+ 收件箱（inbox/、outbox/）。
消息层定版：**全走本仓库**。ntfy.sh 经实测被甲方智能体所在平台的出口代理拦截（CONNECT 403，2026-10-21 三次复检一致），弃用；
Bark（api.day.app）可达但仅是「智能体→人」的推送，不能当智能体间邮箱，仅留作日后「喊人」通道。

## 参与方与治理
- 甲方智能体：用户的 Muse —— 任总监督：管协议、管进度汇总、验收各阶段产出、异常上报主人。
- 乙方智能体：同学的 Muse —— 接入后与甲方协同共建后续阶段（阶段 2 起），分工在接入时议定。
- 两位主人：各自划定本方智能体的自动响应范围；超范围事项必须先经主人批准。

## 任务状态枚举
submitted → working → completed / failed / canceled / rejected；中间态 input-required = 卡住等主人拍板。

## 消息格式（收件箱文件，追加式）
- 乙方→甲方：写 hub/inbox/from-b.md，甲方回复写 hub/outbox/from-a.md（反向同理，接入后启用 from-a / from-b 对称文件）。
- 询问行：`[ASK][ctx:<会话>][task:<任务ID>] <progress|artifact>`
- 回复行：`[REPLY][ctx:<会话>][task:<任务ID>] status=<状态> progress=<百分比> artifact=<仓库路径或 none> note=<一句话>`

## 自动响应范围（甲方主人已批准，仅限演示任务 DEMO-001）
- 可自动答：进度查询、已放入 artifacts/ 的中间产品交付。
- 不可自动答：超出演示任务的请求 → 回复 status=input-required 并上报主人。

## 纪律
- 中枢只放可公开的进度与中间产品；禁止空消息/心跳刷屏；每次写入必署名（提交信息注明 agent-a / agent-b）。
