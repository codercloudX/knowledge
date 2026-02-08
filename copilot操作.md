### 1. General (常规/基础设置)

这部分决定了插件的基础行为模式和文件管理逻辑。

- **Copilot Plus (License Key)**:
    - 如果你购买了 Copilot Plus 订阅，在这里输入密钥。激活后可解锁免 Key 的模型、云端索引和 Agent 功能。

- **API Keys (API 密钥)**:
    - 点击 Set Keys 按钮，会弹出一个列表，让你分别输入 OpenAI, Anthropic, Google Gemini 等厂商的 API Key。

- **Default Chat Model (默认聊天模型)**:
    - 决定了你每次打开侧边栏时，默认加载哪个模型。
    - **建议**：设为你最常用且性价比最高的模型（如GLM，Qwen，Gemini）。

- **Default Mode (默认模式)**:
    - **Chat**: 普通聊天模式（仅依赖上下文轮数）。
    - **Vault QA**: 知识库问答模式（RAG 模式）。
    - **Copilot Plus**: Plus订阅用户能使用，拥有多模态能力的强大AI模式。
    - **建议**：如果你主要用来问笔记，设为 Vault QA；主要用来闲聊或润色，设为 Chat。

- **Open Plugin In (插件打开位置)**:
    - **Sidebar View**: 固定在右侧边栏（推荐，更稳定）。
    - **Editor**: 编辑器模式。

- **Send Shortcut (发送快捷键)**:
    - **Enter**: 回车发送，Shift+Enter 换行（适合短对话）。
    - **Shift+Enter**: Shift+Enter 发送，Enter 换行（适合写长 Prompt）。

- **Include Current Note in Context Menu (在上下文菜单中包含当前笔记)**:
    - 开启后，在侧边栏聊天时，AI 会默认读取你当前**正在编辑**的那篇笔记内容。
    - **场景**：当你需要 AI 帮你“总结这篇文章”或“润色这段话”时，**必须开启**。

- **Auto-Add Text Selection to Context (自动将选中文本添加到上下文)**:
    - 开启后，当你在编辑器里选中一段文字，这段文字会自动出现在聊天框的输入栏上方。
    - **场景**：针对性润色或翻译某段话时非常方便。

- **Images in Markdown (Markdown 中的图片)**:
    - 允许 AI 读取笔记语法 `![[]]` 中的图片。
    - **注意**：需要当前模型支持 Vision（视觉）能力（如Gemini）。

- **Suggested Prompts (建议提示词)**:
    - 在聊天框空闲时，显示一些预设的建议（如“总结这篇笔记”）。
    - **评价**：可以开启。

- **Relevant Notes (相关笔记)**:
    - 在 RAG (Vault QA) 模式下，AI 回答完问题后，会在底部列出它参考了哪些笔记（Source Documents）。
    - **建议**：**务必开启**。这是查证 AI 是否胡说八道的依据。

- **Autosave Chat (自动保存聊天)**:
    - 开启后，你的每一次对话都会被存为一个 Markdown 文件。
    - **建议**：可以开启，防止意外关闭插件导致思路丢失。

- **Generate AI Chat Title on Save (保存时生成 AI 标题)**:
    - 开启后，AI 会根据聊天内容自动起个名字（如“关于RAG的讨论”）。关闭则使用默认时间戳或前几个字。
    - **建议**：开启，方便日后查找。

- **Default Conversation Folder Name (默认对话文件夹名称)**:
    - 设置聊天记录存放在 Obsidian 的哪个文件夹下。默认是 `copilot-conversations`。

- **Default Conversation Tag (默认对话标签)**:
    - 给保存的聊天文件自动打上 tag（如 `#ai-conversations`），方便通过 Graph View 或 Dataview 检索。

- **Conversation Filename Template (对话文件名模版)**:
    - 自定义保存文件的命名规则。
    - `{topic}`: AI 生成的标题。
    - `{date}`, `{time}`: 日期时间变量。

**速查表：General 基础设置**

| 参数 (Parameter)              | 概括 (Summary)                          |
| :-------------------------- | :------------------------------------ |
| **Copilot Plus**            | 订阅激活码输入处，解锁高级功能。                      |
| **API Keys**                | 配置 OpenAI, Anthropic 等厂商 API Key 的入口。 |
| **Default Chat Model**      | 侧边栏默认启动的模型。                           |
| **Default Mode**            | 默认模式：聊天 (Chat) 或 查库 (Vault QA)。       |
| **Open Plugin In**          | 界面位置：侧边栏 (Sidebar) 或 编辑模式 (Editor)。   |
| **Send Shortcut**           | 发送键设置：Enter 或 Shift+Enter。            |
| **Include Current Note**    | **重要**：是否让 AI 读取当前正在编辑的笔记。            |
| **Auto-Add Text Selection** | **重要**：选中文字是否自动投喂给 AI。                |
| **Images in Markdown**      | 是否允许 AI 读取笔记中的图片 (需模型支持)。             |
| **Suggested Prompts**       | 是否显示“建议提示词”气泡。                        |
| **Relevant Notes**          | **重要**：RAG 模式下是否展示参考来源。               |
| **Autosave Chat**           | 是否自动保存聊天记录为 Markdown 文件。              |
| **Generate AI Chat Title**  | 是否让 AI 自动生成对话标题。                      |
| **Default Folder/Tag**      | 设置聊天记录的保存路径和标签。                       |

---

### 2. Model (模型管理)

这里管理你的AI模型和向量模型。

- **Refresh Built-ins (按钮，刷新内置模型)**: 获取插件开发者更新的最新模型列表。
- **Add Model (按钮，添加模型)**: 手动添加自定义模型（比如本地 Ollama 的特定模型）。
- **列表参数详解**:
    - **Model**: 模型名称（传给 API 的字符串）。
    - **Provider**: 供应商（OpenAI, Ollama, etc.）。
    - **Capabilities (能力)**:
        - 👁️ (Vision): 能看图。
        - 💡 (Reasoning): 具备强推理能力。
        - 🌐 (Web Search): 网络搜索能力。
    - **Enable (启用)**: 只有勾选的才会出现在聊天界面的下拉菜单中。
    - **CORS (跨域资源共享)**:
        - **解释**：如果你连接的是本地服务器（如 Ollama 或 LM Studio）且遇到连接错误，尝试勾选这个。通常云端 API 不需要勾选。
    - **Actions (操作)**: 编辑参数或删除模型。
- **Conversation turns in context (上下文轮数)**:
    - **默认 15**。指 AI 能“记住”之前的多少轮对话。
    - **逻辑**：数值越大，AI 记性越好，但消耗 Token 越多（越贵），且可能超出上下文窗口限制。


**速查表：Model 常规管理参数 (列表与设置)**

| 参数 (Parameter) | 概括 (Summary) |
| :--- | :--- |
| **Refresh Built-ins** | 获取插件官方最新的内置模型列表。 |
| **Add Model** | 打开添加自定义模型的窗口 (见上表)。 |
| **List: Enable** | 勾选后，模型才会显示在聊天界面的下拉列表中。 |
| **List: CORS** | 针对列表中的模型单独开启跨域支持 (用于本地模型)。 |
| **Conversation turns** | 上下文记忆轮数 (默认 15)，数值越大越费 Token。 |


#### 窗口： Add Custom Chat Model (添加自定义聊天模型)

- **Model Name (模型名称) [必填]**
    - **深度释义**：这是 API 请求体（JSON Body）中 model 字段的**精确字符串值**。
    - **避坑**：这不是给你随便起名字的地方。
        - 比如 **Gemini** 的API Key，填 `gemini-3.0-pro-preview`。
        - 如果是 **Ollama**，你必须填 `qwen2.5:14b`（必须和你本地 `ollama list` 显示的一模一样）。
        - 如果是 **LM Studio**，同理，填 `Qwen/Qwen2.5-72B-Instruct`，和你LM Studio中的模型名一样。
    - **后果**：填错的话API就会报错。

- **Display Name (显示名称)**
    - **深度释义**：这是给人类看的 UI 标签。
    - **建议**：起一个短一点的名字，比如 Qwen-72B 或 DS-V3，因为它会显示在侧边栏狭窄的下拉菜单里。

- **Provider (供应商)**
    - **深度释义**：决定了插件底层使用哪种 **API 协议/SDK** 来发送请求。
    - **选项逻辑**：
        - **OpenAI**: 标准格式。绝大多数第三方（DeepSeek, SiliconFlow, Moonshot）都兼容这个格式。**首选**。
        - **Ollama**: 针对 Ollama 的原生接口（有时 Ollama 的 OpenAI 兼容接口会有流式传输 Bug，选这个更稳）。
        - **Azure / Google / Anthropic**: 对应各家私有协议。
        - **OpenRouter**: 实际上也是 OpenAI 格式，但插件可能会自动处理一些 OpenRouter 特有的 Header（如 Referer）。

- **Base URL (基础 URL)**
    - **深度释义**：API 的接入点（Endpoint），通常以 `/v1` 结尾。
    - **配置作业**：
        - **官方 OpenAI**: `https://api.openai.com/v1` (默认，可留空)。
        - **硅基流动**: `https://api.siliconflow.cn/v1`。
        - **本地 Ollama**: `http://localhost:11434/v1`。
        - **DeepSeek 官方**: `https://api.deepseek.com` (注意 DeepSeek 有时不需要 `/v1`，视 SDK 而定，通常加 `/v1` 没错)。

- **API Key (API 密钥)**
    - **深度释义**：鉴权令牌（Bearer Token）。
    - **注意**：如果你连接的是本地 Ollama，这里通常可以留空，或者随便填个 `sk-123`（有些 SDK 强制要求 Key 不为空）。

- **Model Capabilities (模型能力)**
    - **Reasoning (推理)**:
        - **功能**：勾选后，插件会适配“思维链”的展示方式（类似 **DeepSeek-R1**）。它可能会增加特定的超时设置，或者在 UI 上折叠 `<think>` 标签的内容。
    - **Vision (视觉)**:
        - **功能**：勾选后，聊天框会出现“上传图片”的按钮。
        - **警告**：只有当你确信这个模型支持多模态（如 GPT-4o, Claude 3.5, Gemini, Qwen-VL）时才勾选。如果给纯文本模型传图片，会直接报错。
    - **Websearch (联网搜索)**:
        - **功能**：这是 Copilot 插件的一个特殊标记。勾选后，如果你在 Agent 模式下，插件会更倾向于认为这个模型有能力处理搜索任务（或者是为了标记 Copilot Plus 提供的带搜索功能的模型）。对于自定义模型，通常不勾选，除非你接的是 Perplexity 的 API。

- **CORS (跨域资源共享)**
    - **深度释义**：**救命开关**。
    - **原理**：Obsidian 也是基于浏览器内核（Chromium）的。浏览器有安全策略，禁止网页随便向本地（localhost）或其他域名发请求。
    - **场景**：
        - 连接 **LM Studio或Ollama (localhost)** 时：**必须勾选**，或者你在 Ollama 启动参数里设置了环境变量 `OLLAMA_ORIGINS="*"`。
        - 连接 **云端 API** 时：通常不用勾选，除非该厂商的服务器没配置好 CORS 头。
    - **Test 按钮**：配置完点一下，显示 Success 再点 Add。


### 总结表格：Add Custom Chat Model 参数详解 (添加自定义聊天模型)

| 项名称 (Item Name)  | 中文名称   | 深度解析与配置建议 (Best Practice)                                                                                               |
| ---------------- | ------ | ----------------------------------------------------------------------------------------------------------------------- |
| **Model Name**   | 模型名称   | **【最关键】** 必须填写 API 要求的**精确模型 ID**（如 `gemini-3.0-pro-preview` / `qwen2.5:14b` / `Qwen/Qwen2.5-72B-Instruct`）。填错 API 会报错。 |
| **Display Name** | 显示名称   | UI 中展示的友好名称，**建议简短**（如 Qwen）。                                                                                           |
| **Provider**     | 供应商    | 决定 API 协议：**OpenAI**（通用，首选）、Ollama（本地原生接口）、Azure/Google/Anthropic（各家私有协议）、OpenRouter（OpenAI 格式但含额外 Header 处理）。          |
| **Base URL**     | 基础地址   | API 访问入口，如 `https://api.siliconflow.cn/v1`、`http://localhost:11434/v1`、`https://api.openai.com/v1` 等。                   |
| **API Key**      | API 密钥 | 鉴权 Token。连接本地模型可留空或填任意值（如 `sk-123`）。                                                                                    |
| **Reasoning**    | 推理能力   | 勾选后 UI 会显示 `<think>` 折叠内容，适配 DeepSeek-R1 等推理模型。非推理模型一般不勾选。                                                              |
| **Vision**       | 视觉能力   | 勾选后启用图片上传按钮。**仅限支持视觉输入的模型**（GPT / Gemini / Qwen-VL）。否则必报错。                                                              |
| **Websearch**    | 联网搜索   | Copilot 特有标记。多数自定义模型不要勾选。仅当接入 Perplexity 或具备真实联网能力的模型才勾选。                                                               |
| **CORS**         | 跨域开关   | 连接 **本地 Ollama/LM Studio (localhost)** 时必须勾选；云端 API 通常不需要。                                                              |
| **Test**         | 测试按钮   | 提交前必须点击验证连通性。成功后显示绿色 Success。                                                                                           |


#### 窗口： Add Custom Embedding Model (添加自定义嵌入模型)

这是配置 RAG “索引器”的地方。

- **Model Name (模型名称) [核心] **
    - **配置**：填你所使用的向量模型名称，比如`text-embedding-3-small`。列表中已经列出主流向量模型，建议使用列表中的，比如谷歌的Gemini向量模型，填写谷歌Gemini的API Key即可使用。

- **Provider (供应商)**
    - **配置**：下拉列表，选择你使用的向量模型的供应商。

- **Base URL & API Key**
    - 同上。填写你所使用的向量模型的URL和API Key。

- **Model Capabilities (模型能力)**
    - **Reasoning / Vision / Websearch**:
        - **深度建议**：**全部不要勾选！**
        - **原因**：这是插件 UI 复用了 Chat Model 的弹窗代码。Embedding 模型的工作是“把文字变成向量”，它不需要推理，不需要联网，目前的插件架构也不支持多模态向量化（Vision Embedding）。勾选这些可能会导致插件发送错误的参数给 API，导致报错。

- **Additional OpenAI Settings (额外的 OpenAI 设置)**
    - **功能**：点击展开后，通常允许你添加自定义 Headers（如 Organization-ID）。
    - **场景**：99% 的个人用户用不到。除非你是企业版 OpenAI 用户，需要指定计费归属的组织。

---

### 总结表格：Add Custom Embedding Model 参数详解 (添加自定义向量模型)

| 项名称 (Item Name)  | 中文名称 | 深度解析与配置建议 (Best Practice)                                             |
| :--------------- | :--- | :-------------------------------------------------------------------- |
| **Model Name**   | 模型名称 | **【最关键】** 必须填入 API 提供商规定的精确字符串 ID (如 `text-embedding-3-small`)，不能自定义。 |
| **Display Name** | 显示名称 | **自定义**。建议简短易读 (如 gemini-001)。                                        |
| **Provider**     | 供应商  | 填写所使用向量模型的供应商名称。                                                      |
| **Base URL**     | 基础地址 | 填写所使用向量模型的Base URL。                                                   |
| **API Key**      | 密钥   | 填写所使用向量模型的API Key，本地模型留空。                                             |
| **Reasoning**    | 推理能力 | 留空不勾选。                                                          …