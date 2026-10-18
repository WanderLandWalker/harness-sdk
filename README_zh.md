<div align="center">
  <div>
    <a href="https://strandsagents.com">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://strandsagents.com/latest/assets/wordmark-github-dark.svg">
        <img src="https://strandsagents.com/latest/assets/wordmark-github-light.svg" alt="Strands" width="320">
      </picture>
    </a>
  </div>

  <h1>
    Strands Agents
  </h1>

  <h2>
    一种模型驱动（model-driven）的方式，仅凭几行代码即可构建 AI Agent。
  </h2>

  <div align="center">
    <a href="https://github.com/strands-agents/harness-sdk/graphs/commit-activity"><img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/m/strands-agents/harness-sdk"/></a>
    <a href="https://github.com/strands-agents/harness-sdk/issues"><img alt="GitHub open issues" src="https://img.shields.io/github/issues/strands-agents/harness-sdk"/></a>
    <a href="https://github.com/strands-agents/harness-sdk/pulls"><img alt="GitHub open pull requests" src="https://img.shields.io/github/issues-pr/strands-agents/harness-sdk"/></a>
    <a href="https://github.com/strands-agents/harness-sdk/blob/main/LICENSE.APACHE"><img alt="License" src="https://img.shields.io/github/license/strands-agents/harness-sdk"/></a>
    <a href="https://pypi.org/project/strands-harness/"><img alt="Python harness version" src="https://img.shields.io/pypi/v/strands-harness?label=Python%20harness"/></a>
    <a href="https://www.npmjs.com/package/@strands-agents/harness"><img alt="TypeScript harness version" src="https://img.shields.io/npm/v/%40strands-agents%2Fharness?label=TypeScript%20harness"/></a>
    <a href="https://www.npmjs.com/package/@strands-agents/cli"><img alt="CLI version" src="https://img.shields.io/npm/v/%40strands-agents%2Fcli?label=CLI"/></a>
    <a href="https://pypi.org/project/strands-agents/"><img alt="Python SDK version" src="https://img.shields.io/pypi/v/strands-agents?label=Python%20SDK"/></a>
    <a href="https://www.npmjs.com/package/@strands-agents/sdk"><img alt="TypeScript SDK version" src="https://img.shields.io/npm/v/%40strands-agents%2Fsdk?label=TypeScript%20SDK"/></a>
  </div>
  
  <p>
    <a href="https://strandsagents.com/">文档</a>
    ◆ <a href="https://github.com/strands-agents/samples">示例</a>
    ◆ <a href="https://github.com/strands-agents/harness-sdk/tree/main/strands-mcp">MCP 服务器</a>
    ◆ <a href="https://discord.gg/strands">Discord</a>
  </p>
</div>

> **语言**：本文档为简体中文翻译，[点此查看英文原版 README.md](README.md)。

Strands Agents 是一个开源 SDK，用于在 Python 和 TypeScript 中构建并运行 AI Agent。当你原本会自己动手写一个 agent 循环（agent loop）时，就该选择 Strands：它运行在你自己的进程里，没有托管的控制平面，却能覆盖一个手写循环最终会长成的那些职责。在一个 SDK 中，你就能获得[生命周期控制](https://strandsagents.com/docs/user-guide/concepts/agents/agent-loop/)（轮次上限、token 预算、取消、停止原因）、[工具](https://strandsagents.com/docs/user-guide/concepts/tools/)与[结构化输出](https://strandsagents.com/docs/user-guide/concepts/agents/structured-output/)、[MCP](https://strandsagents.com/docs/user-guide/concepts/tools/mcp-tools/)、[多 Agent 模式](https://strandsagents.com/docs/user-guide/concepts/multi-agent/multi-agent-patterns/)、[记忆](https://strandsagents.com/docs/user-guide/concepts/memory/overview/)与[会话](https://strandsagents.com/docs/user-guide/concepts/agents/session-management/)、[模型可移植性](https://strandsagents.com/docs/user-guide/concepts/model-providers/)、[流式传输](https://strandsagents.com/docs/user-guide/concepts/streaming/)、[护栏（guardrails）](https://strandsagents.com/docs/user-guide/safety-security/guardrails/)、[追踪](https://strandsagents.com/docs/user-guide/observability-evaluation/observability/)以及[评估（evals）](https://strandsagents.com/docs/user-guide/evals-sdk/quickstart/)。

在用编程 Agent 吗？为 Claude Code、Codex 或 Cursor 安装 Strands 插件。它会加上框架选型、脚手架、工具编写、MCP 服务器连接、Web 框架指南以及 LangGraph 迁移指引。安装与验证步骤参见 [在 AI 编程 Agent 中使用 Strands](https://strandsagents.com/docs/user-guide/build-with-ai/)。

本 monorepo（单一代码仓库）包含 Strands harness、Python 与 TypeScript SDK、文档站点，以及若干配套包：

| 目录 | 说明 |
|-----------|-------------|
| [`harness-py/`](harness-py/) | Python Strands harness：通过 `create_harness()` 一键组装好的 Agent（[PyPI](https://pypi.org/project/strands-harness/) · [文档](https://strandsagents.com/docs/user-guide/harness/)） |
| [`harness-ts/`](harness-ts/) | TypeScript Strands harness：通过 `createHarness()` 一键组装好的 Agent（[npm](https://www.npmjs.com/package/@strands-agents/harness) · [文档](https://strandsagents.com/docs/user-guide/harness/)） |
| [`strands-cli/`](strands-cli/) | `strands` CLI：在终端里快速搭建原型并与 harness Agent 对话（[npm](https://www.npmjs.com/package/@strands-agents/cli)） |
| [`strands-py/`](strands-py/) | Python SDK：agent 循环、模型提供商、工具（[PyPI](https://pypi.org/project/strands-agents/) · [releases](https://github.com/strands-agents/harness-sdk/releases?q=python%2F&expanded=false)） |
| [`strands-ts/`](strands-ts/) | TypeScript SDK：agent 循环、模型提供商、工具（[npm](https://www.npmjs.com/package/@strands-agents/sdk) · [releases](https://github.com/strands-agents/harness-sdk/releases?q=typescript%2F&expanded=false)） |
| [`strands-mcp/`](strands-mcp/) | MCP 服务器：为编程 Agent 提供用 Strands Agents 构建所需的知识（[PyPI](https://pypi.org/project/strands-agents-mcp-server/)） |
| [`site/`](site/) | [strandsagents.com](https://strandsagents.com) 文档站点的源码（Astro/Starlight） |
| [`team/`](team/) | 治理与跨 SDK 流程文档（准则、决策、PR 与兼容性指南，以及 `designs/` 提案） |
| [`test-infra/`](test-infra/) | 用于创建一部分集成测试所依赖的 AWS 资源（知识库、SSH 沙箱）的 CDK 栈 |

## 为什么选择 Strands

构建一个 agent harness。从头到尾掌控它。

- **按你的方式构建。** 任意模型、任意云。在你写下一行配置之前，上下文管理、执行限制与可观测性就已内置。规模增长时可切换后端；你的代码保持不变。
- **模型无关。** 一等公民级支持 Amazon Bedrock、Anthropic、OpenAI 和 Gemini，外加[众多其他提供商](https://strandsagents.com/docs/user-guide/concepts/model-providers/)以及自定义提供商。
- **保持掌控。** agent 循环默认会追踪每一个决策。Hooks 让你可以拦截任意步骤，对其进行记录、校验或重定向。
- **交付行之有效的结果。** 护栏（Guardrails）会在失误酿成后果之前就将其拦下。转向处理器（Steering handlers）让 Agent 能够自我纠正，而不是悄无声息地失败。

MCP、流式传输、多 Agent 模式与结构化输出都已内置。

## 快速开始

最简单的上手方式是使用 **[Strands harness](https://strandsagents.com/docs/user-guide/harness/)**，一个开箱即用、最先进的 Agent。只需一次 `create_harness()`（Python）或 `createHarness()`（TypeScript）调用，你就得到一个经过优化的 Agent，它在模型、工具、记忆、会话和上下文管理上都带有经过基准测试的默认配置——随时可以从想法带到生产。跟随 [harness 快速开始](https://strandsagents.com/docs/user-guide/harness/quickstart/)，或查看 [Python Strands harness](harness-py/) 与 [TypeScript Strands harness](harness-ts/) 包开始使用。

### Python

```bash
pip install strands-harness
```

```python
from strands_harness import create_harness

agent = create_harness()
agent("Find the slowest test in this repo and explain why it's slow")
```

### TypeScript

```bash
npm install @strands-agents/harness
```

```typescript
import { createHarness } from '@strands-agents/harness'

const agent = await createHarness()
await agent.invoke("Find the slowest test in this repo and explain why it's slow")
```

从这里开始，你能得到一个开箱即用的 Agent；当你想自己掌控 agent 循环、亲手接好工具、模型提供商和记忆时，再下沉到下方的 SDK。[harness 配置参考](https://strandsagents.com/docs/user-guide/harness/reference/configuration/) 记录了你能够覆盖的每一个默认值。

[快速入门指南](https://strandsagents.com/docs/user-guide/quickstart/overview/) 涵盖如何配置提供商（Amazon Bedrock、Anthropic、OpenAI、Gemini、Ollama 等）。

## 使用 SDK

Strands Harness SDK 让你走得更深、掌控 Agent 的每一部分：循环、工具、模型提供商、记忆、会话与 hooks。你可以在用过 Strands harness 之后再深入 SDK，或者当组装好的默认配置不够用时，直接从零开始构建你自己的 harness。

### Python

需要 Python 3.10+：

```bash
pip install strands-agents strands-agents-tools
```

```python
from strands import Agent
from strands_tools import calculator

agent = Agent(tools=[calculator])
agent("What is the square root of 1764")
```

[Python SDK README](strands-py/) 涵盖工具、模型提供商、MCP 与双向流式传输。

### TypeScript

需要 Node.js 22+：

```bash
npm install @strands-agents/sdk
```

```typescript
import { Agent } from '@strands-agents/sdk'

const agent = new Agent()
const result = await agent.invoke('What is the square root of 1764?')
console.log(result)
```

更多见 [TypeScript SDK README](strands-ts/)，包括 Zod 类型化工具、结构化输出与多 Agent 模式。

## 文档

想获得详细指引与示例，请查阅我们的文档：

- [用户指南](https://strandsagents.com/)
- [Strands Harness 指南](https://strandsagents.com/docs/user-guide/harness/)（[快速开始](https://strandsagents.com/docs/user-guide/harness/quickstart/) · [配置参考](https://strandsagents.com/docs/user-guide/harness/reference/configuration/)）
- [快速入门指南](https://strandsagents.com/docs/user-guide/quickstart/overview/)
- [Agent 循环](https://strandsagents.com/docs/user-guide/concepts/agents/agent-loop/)
- [双向流式传输](https://strandsagents.com/docs/user-guide/sdk/bidi/)（Python）
- [示例](https://strandsagents.com/docs/examples/)
- API 参考：[Python](https://strandsagents.com/docs/api/python/strands.agent.agent/) · [TypeScript](https://strandsagents.com/docs/api/typescript/)
- [生产与部署指南](https://strandsagents.com/docs/user-guide/deploy/operating-agents-in-production/)

文档本身就位于本 monorepo 的 [`site/`](site/) 目录下，我们欢迎与代码改动一并提交的文档 PR。

## 开发

Git 操作（提交、分支、PR）都在仓库根目录进行。每个包都有自己的工具链：

**Python SDK**（`strands-py/`）：
```bash
cd strands-py
pip install hatch
hatch test        # run unit tests
hatch fmt         # format & lint
```

**TypeScript SDK**（`strands-ts/`）：
```bash
npm ci            # install from repo root
npm run build     # build
npm test          # run unit tests
```

**文档站点**（`site/`）：
```bash
cd site
npm install
npm run dev       # local dev server at http://localhost:4321/
```

## 贡献 ❤️

我们欢迎贡献！详情请见我们的[贡献指南](CONTRIBUTING.md)，其中涵盖：
- 报告缺陷与功能需求
- 开发环境搭建
- 通过 Pull Request 贡献
- 行为准则
- 安全问题上报

## 与团队保持联系
来 [**Discord**](https://discord.com/invite/strands) 与 Strands 团队和其他用户见面吧

## 许可证

本项目依据 Apache License 2.0 授权——详见 [LICENSE.APACHE](LICENSE.APACHE) 文件。

## 安全

更多信息参见 [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications)。
