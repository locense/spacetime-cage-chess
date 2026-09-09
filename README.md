# 时空牢笼棋 / Spacetime Cage Chess

> Web MVP archive for a topology-driven chess variant.  
> 基于拓扑棋盘规则的 Web MVP 备份。

## 项目状态 / Project Status

当前版本实现了本地双人 Web MVP：React + Vite + SVG 棋盘，以及独立、无 UI/网络依赖的 TypeScript 规则引擎。

This version implements a local two-player Web MVP: a React + Vite + SVG board and an independent TypeScript rules engine with no UI or network dependency.

## 已实现 / Included

- 48 个逻辑格、a/h 与 1/8 别名归一化，以及四角黑洞。
  48 logical squares, a/h and 1/8 alias normalization, and the four-corner black hole.
- 关闭/开启门户、中立建筑物捕获、原子状态提交与王安全回滚。
  Closed/open portals, neutral-building captures, atomic state application, and king-safety rollback.
- 分离的走法生成与攻击判定，支持车、象、后、王和兵。
  Separate move generation and attack detection for rooks, bishops, queens, kings, and pawns.
- 兵双步、过路兵、升变、三次重复、数子终局与 `DeadPositionDetector` 接口。
  Pawn double steps, en passant, promotion, threefold repetition, count-based endings, and a `DeadPositionDetector` interface.
- Vitest 验收与性质测试；验证命令见下方。
  Vitest acceptance and property tests; see verification commands below.

## 备份文件 / Archive Files

由于 GitHub 网页上传不会保留多文件上传的目录相对路径，本仓库保存了两份完整、可恢复的快照。

Because GitHub web uploads do not preserve relative paths for a multi-file monorepo upload, this repository contains two complete, recoverable snapshots.

| 文件 / File | 用途 / Purpose |
| --- | --- |
| `spacetime-cage-chess-mvp.zip` | 源码、测试与 workspace 配置的 ZIP 快照。<br />ZIP snapshot of source code, tests, and workspace configuration. |
| `spacetime-cage-chess-mvp.bundle` | 完整 Git bundle，包含 `main` 与提交 `e31bf5c`。<br />Complete Git bundle containing `main` and commit `e31bf5c`. |

## 恢复项目 / Restore the Project

### 从 ZIP 恢复 / From ZIP

```powershell
Expand-Archive .\spacetime-cage-chess-mvp.zip -DestinationPath .\spacetime-cage-chess
cd .\spacetime-cage-chess
```

### 从 Git bundle 恢复 / From the Git Bundle

```bash
git clone spacetime-cage-chess-mvp.bundle spacetime-cage-chess
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
