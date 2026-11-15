## 变更摘要

<!-- 做了什么、为什么；一条提交能说清就不要写三段。 -->

## 影响的 D 编号

<!-- 例：B2-D6（协作六件套 + main 保护）；没有就写「无」。 -->

- D：

## 契约影响

- [ ] 无
- [ ] 有（`schemas/**` / `molt/core/ports.py` / `docs/protocol.md` / ADR）

<!-- 有契约影响时：贴 ADR 链接；评审为建议，仓库不设 approve 数量门禁；冻结窗口（2026-11-12 18:00 UTC+8 后）
     只允许 ext 新增或新增记录类型。 -->

## 触碰范围

- [ ] holdout（`bench/holdout/**`、report 流、双分数）
- [ ] verifier / `scenario_version` 构件（`harness.py` / `verifier.py` / `task_provider.py` /
      `switches.schema.json` / `bench/**`）→ 必须升 `scenario_version` 并重跑基线
- [ ] 只新增候选文件（`genomes/` / `prompts/` / `tools/`）→ 只改 `genome_id`
- [ ] 以上都不涉及

## 验证证据（命令 + 输出）

实现 session 不得自行运行 pytest。请写出建议的测试命令与覆盖点，由主 session / 集成负责人在集成节点统一串行运行并填写结果。CI 自动测试照常执行。

```text
建议测试命令：<由实现 session 提供>
集成负责人测试结果：<由主 session 填写>
其他适用检查（ruff / schema / scenario）：<命令与结果>
```

<!-- 全量 `pytest` 为手动 / 集中执行，不属于 CI，非必贴项。 -->

```
<粘贴最后几行输出；没有输出的检查写「通过」并给出退出码>
```

涉及执行/门禁时补：

```bash
PYTHONDONTWRITEBYTECODE=1 uv run python -m molt gate --fixture tests/fixtures/gate/
PYTHONDONTWRITEBYTECODE=1 uv run python -m molt audit --scenario demo
```

## 回滚方式

<!-- 例：revert 本提交 / `molt revert --to <archive_id>` / 重新生成 web/data 并提交。 -->

## Checklist

- [ ] 测试：新增行为有用例；建议的测试命令和覆盖点已交给集成负责人，由其统一运行
- [ ] Schema：`schema validate --all` +
      `scenario validate --scenario scenarios/demo/scenario.json` 通过；`docs/protocol.md` 未手改
- [ ] 零写入：`git status --porcelain` 为空；`tests/test_zero_write.py` 通过
- [ ] Provenance：`run.ext.provenance.kind` 与实际一致（fixture 未标 live，replay 带 `replay_of_run_id`）
- [ ] 脱敏：diff 中无 key/token/个人信息；`redaction` 报告覆盖字段未泄漏
- [ ] claim 措辞符合 `docs/style.md` §六（描述性、附配对表、不跨 `scenario_version`）
