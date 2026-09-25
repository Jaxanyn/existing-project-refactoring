# existing-project-refactoring

从现有代码和真实行为出发识别架构耦合与边界问题，制定可验证、可回滚的分阶段重构路径，在保持功能稳定的同时提升可维护性和扩展性。

该通用 Agent Skill 适用于支持 Agent Skills 格式的智能体。它帮助你理解已有代码结构与行为，识别耦合问题，并制定可验证、可回滚的分阶段重构计划。

## 使用

安装说明见 INSTALL.md。运行本地验证：

    python scripts/validate_skill.py

调用 Skill 后，先完成现状分析和重构计划并等待批准，再开始修改代码。

## 目录

- SKILL.md: 核心工作流
- references/: 按需加载的重构参考
- templates/: 现状审计、重构计划和回归矩阵
- examples/: 示例请求
- tests/: YingTu 真实场景验证记录
