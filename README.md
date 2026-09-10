# 时空牢笼棋 / Spacetime Cage Chess

> Web MVP archive for a topology-driven chess variant.
> 基于拓扑棋盘规则的 Web MVP 备份。

## 项目状态 / Project Status

当前归档版本为 **2026-09-10**：本地双人 Web MVP，使用 React + Vite + SVG 棋盘，以及独立、无 UI/网络依赖的 TypeScript 规则引擎。

The current archive is **2026-09-10**: a local two-player Web MVP with a React + Vite + SVG board and an independent TypeScript rules engine with no UI or network dependency.

## 已实现 / Included

- 48 个逻辑格、a/h 与 1/8 别名归一化，以及四角黑洞。
  48 logical squares, a/h and 1/8 alias normalization, and the four-corner black hole.
- 关闭/开启门户、中立建筑物捕获、原子状态提交与王安全回滚。
  Closed/open portals, neutral-building captures, atomic state application, and king-safety rollback.
- 分离的走法生成与攻击判定，支持车、象、后、王和兵。
  Separate move generation and attack detection for rooks, bishops, queens, kings, and pawns.
- 兵双步、过路兵、升变、三次重复、数子终局与 `DeadPositionDetector` 接口。
  Pawn double steps, en passant, promotion, threefold repetition, count-based endings, and a `DeadPositionDetector` interface.
- 双方各连续走满 8 步、即 16 个半回合未吃掉对方棋子时，立即按子数结算；捕获门户建筑物不重置计数。
  Count-based settlement after 8 consecutive moves per side (16 plies) without capturing an opposing piece; portal-building captures do not reset the counter.
- Vitest 验收与性质测试：25 项通过。
  Vitest acceptance and property tests: 25 passing tests.

## 当前归档 / Current Archive

GitHub 网页上传不会保留多文件上传的 monorepo 相对路径，因此仓库保存完整、可恢复的 ZIP 与 Git bundle。

GitHub web uploads do not preserve relative paths for a multi-file monorepo upload, so this repository stores complete, recoverable ZIP and Git bundle archives.

| 文件 / File | 用途 / Purpose |
| --- | --- |
| `spacetime-cage-chess-mvp-2026-09-10.zip` | **当前版本**的源码、测试与 workspace 配置 ZIP 快照。<br />**Current** ZIP snapshot of source code, tests, and workspace configuration. |
| `spacetime-cage-chess-mvp-2026-09-10.bundle` | **当前版本**的完整 Git bundle，`main` 提交为 `f114ae3`。<br />**Current** complete Git bundle; `main` commit is `f114ae3`. |

旧版归档仍保留用于历史参考。

Earlier archives are retained for historical reference.

## 恢复项目 / Restore the Project

### 从 ZIP 恢复 / From ZIP

```powershell
Expand-Archive .\spacetime-cage-chess-mvp-2026-09-10.zip -DestinationPath .\spacetime-cage-chess
cd .\spacetime-cage-chess
```

### 从 Git bundle 恢复 / From the Git Bundle

```bash
git clone spacetime-cage-chess-mvp-2026-09-10.bundle spacetime-cage-chess
cd spacetime-cage-chess
```

## 验证 / Verify

```bash
pnpm install
pnpm test
pnpm build
```

## 架构 / Architecture

```text
apps/web              React + Vite local two-player board
apps/server           Placeholder for the future authoritative server
packages/rules        Pure TypeScript rules engine
packages/test-vectors Vitest acceptance and property tests
```

## 后续计划 / Next Steps

1. 扩展本地玩法测试与界面体验。 / Expand local gameplay tests and UX.
2. 接入 Colyseus 权威房间与回放。 / Add Colyseus authoritative rooms and replay.
3. 接入 PostgreSQL 持久化。 / Add PostgreSQL persistence.
4. 为已证明的将不死局面实现求解器。 / Implement a certified dead-position solver.

## 规则来源 / Rules Source

实现以《时空牢笼棋 规则规范 v1.1（拓扑修订版）》为规则数据来源；源码内仅保存规则实现与测试，不包含原规则文档。

Implementation follows Spacetime Cage Chess Rules Specification v1.1 (Topology Revision) as its rules-data source. Source archives contain only the implementation and tests, not the original rules document.
