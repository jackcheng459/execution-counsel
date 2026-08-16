# execution-counsel v1.2.0 发布核验记录

核验日期：2026-08-16

发布分支：`agent/publish-v1.2.0`

当前状态：Private 仓库、Draft PR，尚未合并、公开、打标签或创建 Release。

## 发布范围

本仓库承载 `execution-counsel` 专家本体与仓库级审核记录。专家本体包括：

- `.codebuddy-plugin/plugin.json`
- `agents/execution-counsel.md`
- `skills/execution-intake-continuity`
- `skills/execution-case-workflow`
- `skills/legal-collab-toolkit`
- `avatars/expert-v1.2.0.png`
- `README.md`
- `CHANGELOG.md`

仓库级审核记录包括 `PUBLICATION_REVIEW.md` 和 `.github/reviews/`，不属于已评审安装候选的 16 个本体文件。

本仓库不包含本地备份、升级审计目录、安装候选 ZIP、运行日志、客户材料或案件原件。

## 候选包完整性

- 仓库内 16 个专家本体文件与 2026-08-11 已独立评审的 v1.2.0 安装候选逐文件一致。
- 候选 ZIP SHA-256：`7e67da503c9215ac04eefcd751412278770ab8a1887399f4394801341028cfd1`。
- 本体文件哈希见 [`.github/reviews/SOURCE_SHA256SUMS-v1.2.0.txt`](.github/reviews/SOURCE_SHA256SUMS-v1.2.0.txt)。
- 本轮曾发现 4 个文件与已评审候选不一致：`plugin.json` 追加作者信息、README 追加分支状态、两个 reference 清理行尾空格。现均已恢复为已评审字节，发布说明改放仓库级文件。

## 机械校验

- 2026-08-16 使用当前 WorkBuddy App 内置 `expert-manager` 在 `/private/tmp` 隔离目录校验和临时注册，均返回成功，校验结果为 0 错误、0 警告。
- 隔离脚本确认所有写入仅在 `/private/tmp`，注册项唯一，未产生 session marker，退出后自动清理。
- plugin 清单为有效 JSON；头像为 512 x 512 PNG。
- 3 个 Skill 的 `SKILL.md` 分别为 285、228、152 行，均不超过 500 行，frontmatter 名称与目录一致，引用文件均存在。
- 未发现软链接、可执行文件、外部依赖脚本、危险删除命令、凭据、真实案号或客户材料。
- 归档候选原有 44/44 专项机械检查、3/3 Skill 检查、6 项初始烟测和 5 项回归烟测。本轮以 16/16 哈希一致性确认该证据对当前本体仍然适用。
- 原专项校验脚本在当前系统默认 Python 下缺少 PyYAML，本轮未为此安装新依赖。这不影响 WorkBuddy 官方隔离校验结果。
- `git diff --check` 会报告 6 处空列表项的行尾空格。这些空格属于已评审候选的原字节，保留它们是为了维持哈希一致，不影响 Markdown 语义。

## Skill 审查结论

- 结论：`PASS_WITH_P3`，P0/P1/P2 均为 0。
- 详细报告见 [`.github/reviews/SKILL_LINT_REVIEW-20260816.md`](.github/reviews/SKILL_LINT_REVIEW-20260816.md)。
- 未授予开源许可、`author.name` 仍为 `WorkBuddy User`、`categoryId` 归入 `11-SecurityCompliance`、少量跨 Skill 相对引用，均记为 P3 或后续版本决策，不在 v1.2.0 中悄然改动。

## 法源入口复核

- 2026-08-16 重新通过最高人民法院、最高人民法院公报、国家法律法规数据库和最高人民检察院官方域名，定位了文件中列出的 7 个规范或发布入口。
- 当前环境直接打开部分最高法公报详情页会超时，国家法律法规数据库详情页会返回 403，但官方检索结果仍能确认标题、发布信息或有效标识。
- 本轮不将可访问性复核写成具体案件的法律结论。每次引用时仍须对规范全称、文号、效力、条文、时间效力和个案事实重新核验。

## 边界

- 专家只生成候选意见和待律师复核底稿。
- 不替律师决定案件承接、收费、金额口径、程序路径、文书签发或执行结果。
- 法源、法院查控、外部数据库和文件转换均须以当次真实调用与回读验证为准。
- 当前仓库未授予开源许可，公开可见不等于允许复制、修改或再分发。
- 发布归属人为程建都律师，拟公开联系方式为 `wx1811985798`。为保持 v1.2.0 候选字节一致，该信息未写入本版 `plugin.json`；如要写入包体，应作为新版本重新验证。

## 发布闸门

- Private 仓库与 Draft PR：已允许。
- 合并至 `main`：等待 Jack 单独确认。
- 改为 Public：等待 Jack 单独明确授权。
- 创建 `v1.2.0` 标签和 GitHub Release：等待正式放行后执行。
