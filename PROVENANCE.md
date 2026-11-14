# 来源与重构说明（Provenance）

**本仓库不是历史仓库。** 它不是 `FeiSaMa/molt` 的历史镜像，也不是一次正常开发的提交记录。
它是为了让代码可公开评审，按源仓库的最后合并状态**重新构造**出来的快照仓库。

## 一、来源

| 项 | 值 |
| --- | --- |
| 源仓库 | `https://github.com/FeiSaMa/molt` |
| 快照边界 | `a4b40c68f5bfd8ab64eb3713f28bbe0a99f50daf`（`feat(skill): Skill/MCP 运行时与审批门禁加固 (#15)`，2026-11-14 15:14:23 +0800） |
| 快照树哈希 | `c53957f2af6f95c60196e38ed25928fd372c96ea` |
| 文件数 | 657（不含本文件） |
| 重构时间 | 2026-11-14（本仓库各提交的时间戳即重构实际发生时间） |

## 二、这些提交是重构的，不是历史

- 每个提交的**内容树**与对应源提交逐字节相同；但**提交对象是新建的**：
  - 提交时间戳（author date 与 committer date）都是**重构时刻**，不是原提交时间；
  - 作者统一记为仓库维护者 `FeiSaMa <zzr211001@163.com>`，也就是执行这次重新发布的人；
  - 原提交的 SHA、原作者与原始时间以 trailer 形式记录在提交信息里
    （`Source-Commit` / `Original-Author` / `Original-Author-Date` / `Source-Repo`）；
  - 没有原仓库的 git 对象、没有 PGP 签名、没有原始 commit SHA。
- 源历史中的两个合并提交被**线性化**为单父提交（内容树不变，提交信息里标
  `Source-Kind: merge`）。
- 源历史的根提交是空树（`Initial commit`），这里保留为空提交，因此第一屏会看到一个
  0 文件的提交——这是源历史的形状，不是漏提交。
- 跨提交的路径都不改写：除本文件所在的最后一个提交外，每个提交的树与源提交一致。

## 三、逐提交映射

| # | 本仓库提交 | 源提交 | 原作者 | 原始时间 | 原提交标题 |
| --- | --- | --- | --- | --- | --- |
| 1 | `49670176bae8` | `db31f0e4a3a8` | Alexander <zzr211001@gmail.com> | 2026-10-25T22:09:40+08:00 | Initial commit |
| 2 | `e9aa7e3309e4` | `e3e15e5292bb` | Alexander <zzr211001@gmail.com> | 2026-10-25T22:28:54+08:00 | chore: 骨架与架构文档 |
| 3 | `703831ed4200` | `c4aef84b9525` | Alexander <zzr211001@gmail.com> | 2026-10-28T21:42:42+08:00 | docs: 调研综述与裁判独立性设计 |
| 4 | `97f0ee48f304` | `6849ecec8570` | Alexander <zzr211001@gmail.com> | 2026-10-28T21:44:16+08:00 | docs: 修正 Agno 条目 |
| 5 | `87ee1cfcda96` | `2d66c1d90237` | FeiSaMa <zzr211001@163.com> | 2026-11-10T21:13:06+08:00 | chore: 接入远端并同步本地 11-04 文档 |
| 6 | `e15298922aa6` | `6924e4230cbf` | Alexander <zzr211001@163.com> | 2026-11-10T22:37:25+08:00 | feat(core): B1 protocol + engine + fixture runtime (#1) |
| 7 | `80873c16a957` | `fc443cc5215c` | Alexander <zzr211001@163.com> | 2026-11-10T22:58:27+08:00 | feat(core): B2a LLM proposer + grid fallback (#2) |
| 8 | `0304e96be0c9` | `c548206b6a73` | Alexander <zzr211001@163.com> | 2026-11-10T23:13:37+08:00 | feat(web): B2d-0 最小 molt export，产出 web/data 数据面 (#3) |
| 9 | `0cea5128c091` | `da31fa5c32c8` | Alexander <zzr211001@163.com> | 2026-11-10T23:46:53+08:00 | feat(core): B2b Pi 1.5.0 adapter + sandbox (#4) |
| 10 | `358c831c3bd6` | `d585d2fffee9` | Alexander <zzr211001@163.com> | 2026-11-11T17:49:03+08:00 | feat: 10+5 + svc-config + demo + collaboration kit (#8) |
| 11 | `63a0a6fee33e` | `50713dce7160` | 董喆元 <3876139413@qq.com> | 2026-11-12T22:46:25+08:00 | feat(web): 零构建展示页 web/page（#10） |
| 12 | `9ba24b5b3925` | `c8eb09c803ee` | Alexander <zzr211001@163.com> | 2026-11-12T22:58:09+08:00 | feat(probe): 欠定约定族记忆探针（probe-4 + 研究报告）（#9） |
| 13 | `377752e988a7` | `b453ab6e4105` | Alexander <zzr211001@163.com> | 2026-11-13T15:57:31+08:00 | feat(security): 收紧审计证据链、memory 快照与 verifier 启动面 (#11) |
| 14 | `9636ce6aebdb` | `bbf751734bf0` | Alexander <zzr211001@163.com> | 2026-11-13T16:39:04+08:00 | feat(agent): 本地后端 API（probe 索引 + 会话流式） (#12) |
| 15 | `4fc1730741e7` | `eaf8a9054dc2` | FeiSaMa <zzr211001@163.com> | 2026-11-13T16:46:15+08:00 | feat(agent): 增加 /api/tasks 逐题结果接口 (#13) |
| 16 | `39054ac31d0a` | `f92a3f8dfae0` | By Diamond <74449864+By-Diamond@users.noreply.github.com> | 2026-11-13T19:09:50+08:00 | feat(web): 路演页接入实时数据源并重排屏序 |
| 17 | `59b45d4cad41` | `bc50cb1f42e6` | Alexander <zzr211001@163.com> | 2026-11-13T19:16:54+08:00 | Merge pull request #14 from FeiSaMa/feat/web-live-panel |
| 18 | `675098c7625e` | `a4b40c68f5bf` | Alexander <zzr211001@163.com> | 2026-11-14T15:14:23+08:00 | feat(skill): Skill/MCP 运行时与审批门禁加固（含 5 个实现提交 + 审批主体 fail-closed） (#15) |

## 四、如何自行校验

在源仓库的任意克隆里（对象库需包含 `a4b40c68`）：

```bash
git fetch https://github.com/FeiSaMa/bohack-molt.git main:bohack
git diff --stat a4b40c68 bohack -- . ':(exclude)PROVENANCE.md'   # 应为空
git rev-parse a4b40c68^{tree}                                   # c53957f2af6f95c60196e38ed25928fd372c96ea
git rev-parse bohack~1^{tree}                                   # 同上（去掉本文件那一个提交后应完全相等）
```

本仓库的末提交在上面比对时**只多一个 `PROVENANCE.md`**，其余 657 个文件的路径、内容与
可执行位都与快照树一致。

## 五、凭据扫描

- 源仓库 CI 的 `secret-scan` 作业（`.github/workflows/ci.yml`）在快照上通过。
- 本次重新发布前，对全部 18 个源提交的树用 gitleaks 风格规则复跑：`sk-` 前缀长串、
  `gh[pousr]_`、`AKIA`、`AIza`、`xox[baprs]-`、私钥头、`*_API_KEY=` 赋值、`hf_`、
  JWT 三段式、`KGAT_`——**0 命中**。
- `detect-secrets 1.5.0` 对三个含测试夹具的文件只报 1 条 `Secret Keyword`：
  `tests/test_chat_adapter.py:421`，由变量名 `secret` 触发。
- 这些 `sk-` 串都是**小写英文单词 + 连字符**的测试夹具（例如“单词-单词-数字”形态），
  字符集与长度都不符合真实凭据形态（DeepSeek 为 `sk-` + 32 位混合字符，OpenAI 为
  `sk-proj-` + 混合字符），且它们只出现在 `monkeypatch.setenv` 与断言里，用途是验证
  “只从指定环境变量读取 key”“key 不出现在 health/错误信息里”。
- 结论：是**测试夹具，不是凭据**。本文件与本次发布过程中没有输出任何候选值。

## 六、范围

- 原仓库 `FeiSaMa/molt` 未做任何改写（未改历史、未改分支、未改权限）。
- 本次发布没有部署任何服务：仓库只包含源码、文档与样例数据。
- 本仓库遵循源仓库的 `AGENTS.md`、`CONTRIBUTING.md`、`CODEOWNERS` 与许可证约定；
  如需以本仓库为准，以本文件说明的重构关系为准。
