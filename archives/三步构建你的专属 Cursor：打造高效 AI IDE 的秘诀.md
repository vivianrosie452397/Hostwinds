# 三步构建你的专属 Cursor：打造高效 AI IDE 的秘诀

![Cursor AI IDE](&thumbnail=660x2147483647&quality=80&type=jpg)

> **Cursor** 是一款近期爆火的 **AI IDE**，凭借着其强大的功能和创新的交互方式，迅速取代了 GitHub Copilot 的地位。Cursor 的成功不仅得益于其背后公司 **Anysphere** 获得的 **6000 万美元** A 轮融资，更因为它在用户价值上的持续深耕，找到了 **PMF（产品市场契合度）**。

## Cursor 成功的两大关键因素

### 1. 先进的 AI 模型
Cursor 之所以能够脱颖而出，在很大程度上归功于其采用了最先进的 **AI 模型**。早在 **2022 年 12 月**，当大多数人还在体验 **ChatGPT 3.5** 时，Cursor 就已经拿到了 **GPT-4** 的体验权限，并开始基于 GPT-4 构建 **AI Native IDE**。最近，Cursor 接入了 **Claude Sonnet 3.5**，进一步提升了代码生成的质量和成功率。如果没有 GPT-4 这样的模型，Cursor 无法实现其预期的 AI 功能。

![Cursor 模型选择](&thumbnail=660x2147483647&quality=80&type=jpg)

Cursor 还对模型进行了深度优化，例如通过本地代码分割上传至服务端进行 **embedding**，以及使用 **Speculative Decoding** 技术将输出速度提升至 **1000 个 token/秒**。这些技术极大地提升了模型的准确性和响应速度。

### 2. 创新的 AI 编程交互方式
Cursor 在交互方式上也进行了大胆创新。例如，其 **Cursor Tab** 功能支持多行补全、智能改写和下一次补全的预测，开发者只需通过 **Tab** 键即可完成大部分编程工作。此外，**Inline Chat** 功能允许开发者在编辑器中快速唤起输入框，通过自然语言生成代码，并实时观察代码逐行生成的过程。

![Cursor Inline Chat](&thumbnail=660x2147483647&quality=80&type=jpg)

Cursor 的 **聊天面板** 功能同样强大，支持对整个代码库进行问答的 **Codebase Agent**、可请求互联网的 **Web Agent** 以及快速索引在线文档的 **Doc Agent**。这些功能让 Cursor 成为了一款真正的 **AI Native IDE**。

## 为什么其他智能研发助手无法超越 Cursor？

自 **2022 年 12 月** ChatGPT 发布以来，大语言模型取得了突破性进展，催生了无数 AI 驱动的应用程序。然而，尽管 **Microsoft** 的 **GitHub Copilot**、**Amazon** 的 **CodeWhisperer** 等智能研发助手纷纷推出，它们仍然无法与 Cursor 相提并论。

这些插件基于 **VS Code** 和 **Jetbrains** 的插件体系，实现了代码补全等功能，但由于插件 API 的限制，无法实现像 Cursor 一样的 **多行补全** 和 **Inline Chat** 功能。Cursor 的创新交互让开发者能够专注于编辑器内的操作，大大提升了工作效率。

![智能研发助手与 Cursor 对比](&thumbnail=660x2147483647&quality=80&type=jpg)

## OpenSumi：AI 原生 IDE 框架

**OpenSumi** 是一个开源的、高性能的 IDE 研发框架，专门为构建 **AI 原生 IDE** 而设计。它提供了模块化开发方式，支持 **Web** 和 **Electron** 双端开发，并兼容 **VS Code** 插件生态。

### OpenSumi 的核心特点
1. **模块化开发**：提供 50+ IDE 原子模块，开发者可以根据需求自由组合。
2. **高扩展性**：支持依赖注入（Dependency Injection），方便替换底层实现。
3. **多端支持**：支持构建桌面端、Cloud IDE、Remote 模式等多种形态的 IDE。
4. **兼容 VS Code 插件生态**：无缝迁移用户使用习惯。

## 三步构建你的 Cursor

### 第一步：Fork & Clone CodeFuse IDE
首先，需要 **fork** 并 **clone** CodeFuse IDE 的代码库，并安装相关依赖。

bash
git clone git@github.com:codefuse-ai/codefuse-ide.git && cd codefuse-ide
yarn config set -H npmRegistryServer "https://registry.npmmirror.com"
export ELECTRON_MIRROR=https://npmmirror.com/mirrors/electron/
yarn
yarn run electron-rebuild


### 第二步：修改配置
CodeFuse IDE 支持集成任意模型服务，默认与本地模型对接。你可以在 `src/ai/browser/ai-model.contribution.ts` 中修改模型请求接口，支持任意兼容 **OpenAI** 规范的模型服务。

![模型请求设置](&thumbnail=660x2147483647&quality=80&type=jpg)

### 第三步：运行
使用 `yarn start` 运行你的自定义 AI IDE，享受 OpenSumi 带来的 AI 特性。

bash
yarn start


![CodeFuse IDE 运行效果](&thumbnail=660x2147483647&quality=80&type=jpg)

## 愿景：成为智能研发时代的 IDE 基建

在大模型技术飞速发展的时代，**VS Code** 和 **Jetbrains** 的插件 API 不应成为智能研发创新交互的天花板。**OpenSumi** 致力于为智能研发领域的创业公司提供更加专注的 AI 解决方案，帮助开发者专注于 AI 创新，而非 VS Code 的魔改。

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)