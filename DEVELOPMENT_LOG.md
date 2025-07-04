# BitAgent 开发日志

> 本文档记录了 BitAgent 项目的历史开发日志，内容摘自原始 `GEMINI.md`。

---
- **`commit ee45dae` - feat(core): 为数据代理实现基于文件的缓存**
  - 创建了可复用的 `FileCache` 工具，并集成到 `DataTwitterAgent`，以减少冗余API调用并提升效率。
- **`commit adec17f` - feat(data): 实现用于社交媒体分析的 DataTwitterAgent**
  - 引入了 `DataTwitterAgent`，用于获取实时推文数据，为系统数据源增加了关键的社交情绪维度。
- **`commit 7596905` - feat(agent): 集成 LangGraph 实现高级决策流程**
  - 项目中引入 `LangGraph`，以支持更复杂的有状态Agent工作流。
  - 实现了“辩论图”原型，并集成到 `ChiefAgent` 的决策流程中。
- **`commit b91e189` - fix(system): 端到端测试的最终修复与数据更新**
  - 对各Agent和UI应用了最终修复，并更新回测数据集，确保系统端到端测试顺利通过。
- **`commit 5739444` - feat(backtest): 生成更丰富的数据集以增强测试**
  - 升级数据准备脚本，生成更丰富、全面的数据集，使回测KPI计算更有意义并解决了之前的错误。
- **`commit e4760d7` - fix(learner): Portfolio->Investor重构后的Agent导入修复**
  - 修复了 `StrategyLearnerAgent` 中的 `ModuleNotFoundError`，更新为重构后的 `InvestorAgent` 路径。
- **`commit afdcbab` - fix(ui): 菜单栏应用的最终稳定实现**
  - 通过混合 AppKit/SwiftUI 实现，交付了稳定的 macOS UI，解决了所有启动和显示问题。
- **`commit c144971` - fix(ui): 状态栏移到底部以保证显示稳定**
  - 通过将状态栏移至主窗口底部，彻底解决了UI显示问题，确保渲染可靠。
- **`commit 32effed` - feat(investor): 实现动态头寸规模管理**
  - 升级 `InvestorAgent`，基于固定分数风险模型提供动态头寸规模服务。
- **`commit 596ec77` - refactor(agent): PortfolioAgent 升级为 InvestorAgent**
  - 将 `PortfolioAgent` 重构为新的 `InvestorAgent`。
- **`commit 848a820` - fix(system): 彻底修复所有已知启动和UI bug**
  - 应用最终、全面的强力修复，解决所有反复出现的启动和UI数据流问题。
... *(以及所有更早的提交)*
