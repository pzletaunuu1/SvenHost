# 全面探索 DeepSeek：本地部署、AI 编程、写作辅助、网页-PDF 全文翻译

## DeepSeek 简介

最近，**DeepSeek** 成为了热门话题。作为一名 AI 技术爱好者，我早在 DeepSeek 热度飙升之前就对其能力进行过多次探索和分享。本文将用简洁的方式，向大家介绍如何将 DeepSeek 融入写作、编程、翻译、总结等多种场景。

## DeepSeek 的获取方式

### 1. 在线使用

最简单的方式是直接在线使用 DeepSeek，访问以下链接即可体验：

plaintext
https://chat.deepseek.com/


### 2. 本地部署

对于需要本地部署的用户，可以通过 **Ollama** 进行安装。首先，访问 [Ollama 官网](https://ollama.com) 下载并安装 Ollama。安装完成后，在命令行中运行以下命令：

bash
ollama run deepseek-r1:7b


根据电脑或显卡的性能，可以选择从 `1.5b` 到 `671b` 的不同参数模型。更多详细参数可以参考：[Ollama DeepSeek 库](https://ollama.com/library/deepseek-r1)。

### 3. 官方 API

对于开发者，可以通过官方 API 调用 DeepSeek。首先，申请并获取 `api_key`，然后设置 `base_url` 为：

plaintext
https://api.deepseek.com/v1


以下是一个简单的 Python 调用示例：

python
from openai import OpenAI

client = OpenAI(api_key="your_api_key", base_url="https://api.deepseek.com")

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "system", "content": "You are a helpful assistant"},
        {"role": "user", "content": "Hello"},
    ],
    stream=False
)

print(response.choices[0].message.content)


### 4. 第三方 API

如果想要更经济实惠的方案，可以尝试使用 **Siliconflow** 提供的 API。注册后，用户可以免费获得 14 元额度，足够满足日常使用。注册地址如下：

plaintext
https://cloud.siliconflow.cn/i/YefhGWlT


Siliconflow 不仅支持 `OpenAI API`，还可以免费使用 `Qwen`、`GLM`、`Yi` 等模型。以下是一个调用示例：

python
from openai import OpenAI

client = OpenAI(api_key="your_api_key", base_url="https://api.siliconflow.cn/v1")
response = client.chat.completions.create(
    model='deepseek-ai/DeepSeek-R1',
    messages=[
        {'role': 'user', 
        'content': "机器学习算法与 Python 实战这个号值的关注吗？"}
    ],
    stream=True
)

for chunk in response:
    print(chunk.choices[0].delta.content, end='')


## DeepSeek 的应用场景

### DeepSeek + Cursor AI 辅助编程

通过 DeepSeek 的强大能力，编程效率得以大幅提升。在 **Cursor** 的设置中，添加 DeepSeek 的模型并填写 API 地址和 API Key 后，即可快速调用 DeepSeek 进行代码生成与优化。

### DeepSeek + Obsidian 辅助写作

在 **Obsidian** 中，通过安装 **Copilot** 插件，可以将 DeepSeek 集成到写作流程中。在插件的设置中，将 `deepseek-ai/DeepSeek-R1` 设置为默认模型，即可在 Obsidian 中通过侧边栏直接与 DeepSeek 进行对话。

### DeepSeek + 沉浸式翻译

通过 **沉浸式翻译插件**，可以将 DeepSeek 用于网页和 PDF 的全文翻译。安装插件后，在设置中选择 DeepSeek 或 Siliconflow 作为翻译服务，并粘贴获取到的 `api_key`，即可实现一键翻译。

## 结语

DeepSeek 的强大功能和灵活部署方式，使其成为 AI 领域的佼佼者。无论是编程、写作还是翻译，DeepSeek 都能为你提供高效的解决方案。如果你需要订阅海外线上服务，不妨试试 👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)。

本文完。