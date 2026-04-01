# OpenClaw Multi-Agent GameDev System
# 基于OpenClaw的多智能体并行游戏开发团队系统

## 📋 项目概述

本项目实现了一套基于OpenClaw规则体系的多智能体并行游戏开发团队系统，核心特性：

- **多智能体并行架构**：8个专业Agent可按组并行工作
- **独立上下文隔离**：每个Agent拥有独立的沙盒工作环境
- **消息队列通信**：Agent间通过文件消息队列进行异步通信
- **源文档保护**：验证时严格隔离，不污染源规则文档
- **CodeBuddy Team Mode集成**：利用CodeBuddy的Team功能实现真正的并行执行

## 🏗️ 项目结构

```
openclaw-multi-agent-gamedev/
├── rules/                        # 🔒 源规则文档（只读，受保护）
│   ├── agents/                   # Agent定义文件
│   ├── skills/                   # 技能包
│   ├── rule.md                   # 主规则
│   └── ...
├── config/                       # 系统配置
│   ├── system.yaml               # 核心系统配置
│   └── agents.yaml               # Agent详细配置
├── src/                          # 核心框架代码
│   ├── core/                     # 核心模块
│   │   ├── orchestrator.py       # 编排器 - 多Agent调度
│   │   ├── sandbox.py            # 沙盒管理器
│   │   ├── message_queue.py      # 消息队列
│   │   ├── context_manager.py    # 上下文管理器
│   │   └── pipeline.py           # 流水线引擎
│   ├── agents/                   # Agent实现
│   │   ├── base_agent.py         # Agent基类
│   │   ├── producer.py           # 制作人Agent
│   │   ├── project_manager.py    # 项目管理Agent
│   │   ├── planner.py            # 策划Agent
│   │   ├── tech_lead.py          # 主程Agent
│   │   ├── programmer.py         # 程序Agent
│   │   ├── qa.py                 # QA Agent
│   │   ├── ux_designer.py        # UX Agent
│   │   └── artist.py             # 美术Agent
│   ├── adapters/                 # 适配器层
│   │   ├── codebuddy_adapter.py  # CodeBuddy Team Mode适配器
│   │   └── rule_loader.py        # 规则加载器
│   └── utils/                    # 工具模块
│       ├── file_ops.py           # 文件操作（含保护检查）
│       └── logger.py             # 日志工具
├── .sandboxes/                   # Agent沙盒工作区（运行时生成）
│   ├── _message_queue/           # 全局消息队列
│   ├── _working_copies/          # 源文档工作副本
│   ├── 02_planner/               # 策划Agent沙盒
│   ├── 03_tech_lead/             # 主程Agent沙盒
│   ├── 04_programmer/            # 程序Agent沙盒
│   └── ...
├── .GameDev/                     # 开发流程产出物
│   ├── _ProjectManagement/       # 项目管理文档
│   └── {功能名}/                 # 各功能文档
├── tests/                        # 测试代码
└── docs/                         # 项目文档
```

## 🚀 快速开始

详见 `docs/` 目录下的使用文档。

## 📜 许可证

MIT License
