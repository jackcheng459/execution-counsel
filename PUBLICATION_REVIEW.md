# execution-counsel v1.2.0 发布核验记录

核验日期：2026-08-15

发布分支：`agent/publish-v1.2.0`

## 发布范围

本仓库仅承载 `execution-counsel` 专家本体：

- `.codebuddy-plugin/plugin.json`
- `agents/execution-counsel.md`
- `skills/execution-intake-continuity`
- `skills/execution-case-workflow`
- `skills/legal-collab-toolkit`
- `avatars/expert-v1.2.0.png`
- `README.md`
- `CHANGELOG.md`

本仓库不包含本地备份、升级审计目录、安装候选 ZIP、运行日志、客户材料或案件原件。

## 机械校验

- WorkBuddy `expert-manager` v0.1.0 结构校验通过。
- 唯一警告为 `displayDescription.zh` 长度 114 字，超过建议的 40 至 50 字。
- plugin 清单为有效 JSON。
- 头像为 512 x 512 PNG。
- 未发现软链接、可执行文件、API Key、Token、密码、真实案号或客户材料。
- 公开联系方式为 `wx1811985798`。
- GitHub 工作副本仅机械删除了 6 处空列表项的行尾空格，不改变文字和运行语义。

## 边界

- 专家只生成候选意见和待律师复核底稿。
- 不替律师决定案件承接、收费、金额口径、程序路径、文书签发或执行结果。
- 法源、法院查控、外部数据库和文件转换均须以当次真实调用与回读验证为准。
- 当前仓库未授予开源许可，公开可见不等于允许复制、修改或再分发。

## 发布闸门

- Private 仓库与 Draft PR：已允许。
- 合并至 `main`：等待 Jack 审阅。
- 改为 Public：等待 Jack 单独明确授权。
- 创建 `v1.2.0` 标签和 GitHub Release：等待正式放行后执行。
