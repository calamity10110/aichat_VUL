# AIChat: All-in-one LLM CLI Tool

[![CI](https://github.com/sigoden/aichat/actions/workflows/ci.yaml/badge.svg)](https://github.com/sigoden/aichat/actions/workflows/ci.yaml)
[![Crates](https://img.shields.io/crates/v/aichat.svg)](https://crates.io/crates/aichat)
[![Discord](https://img.shields.io/discord/1226737085453701222?label=Discord)](https://discord.gg/mr3ZZUB9hG)

AIChat is an all-in-one LLM CLI tool featuring Shell Assistant, Chat-REPL, RAG, AI Tools & Agents, and More. 

## Install

### Package Managers

- **Rust Developers:** `cargo install aichat`
- **Homebrew/Linuxbrew Users:** `brew install aichat`
- **Pacman Users**: `pacman -S aichat`
- **Windows Scoop Users:** `scoop install aichat`
- **Android Termux Users:** `pkg install aichat`

### Pre-built Binaries

Download pre-built binaries for macOS, Linux, and Windows from [GitHub Releases](https://github.com/sigoden/aichat/releases), extract them, and add the `aichat` binary to your `$PATH`.

## Features

### Multi-Platform Support

Seamlessly integrate with over 20 leading LLM platforms via a unified interface, including OpenAI, Claude, Gemini (Google AI Studio), Ollama, Groq, Azure-OpenAI, VertexAI, Bedrock, Huggingface, Github Models, Mistral, Deepseek, AI21, XAI Grok, Cohere, Perplexity, Cloudflare, OpenRouter, Ernie, Qianwen, Moonshot,  ZhipuAI, Lingyiwanwu, Deepinfra, Fireworks, Siliconflow, Together, Jina, VoyageAI, and any OpenAI-Compatible platforms.

### Shell Assistant

Supercharge your command line experience. Simply describe your desired actions in natural language, and let AIChat translate your requests into precise shell commands. 

![aichat-execute](https://github.com/user-attachments/assets/0c77e901-0da2-4151-aefc-a2af96bbb004)

**OS-Aware Intelligence:** AIChat tailors commands to your specific operating system and shell environment.

### Chat-REPL

Bring a powerful Chat-REPL with features such as tab autocompletion, multi-line support, history search, configurable keybindings, and custom REPL prompt.

![aichat-repl](https://github.com/user-attachments/assets/218fab08-cdae-4c3b-bcf8-39b6651f1362)

### Multi-Form Input

Accept various forms of input, such as stdin, local files & dirs, and remote URLs.

| Input             | Example                              |
| ----------------- | ------------------------------------ |
| CMD input         | `aichat hello`                       |
| Stdin pipe        | `cat data.txt \| aichat`             |
| Local files       | `aichat -f data.txt`                 |
| Local images      | `aichat -f image.png`                |
| Local directories | `aichat -f dir/`                     |
| Remote URLs       | `aichat -f https://example.com`      |
| Combine Inputs    | `aichat -f dir/ -f data.txt explain` |

### Role

Define custom roles to tailor LLM behaviors, enhancing interactions and boosting productivity.

![aichat-role](https://github.com/user-attachments/assets/023df6d2-409c-40bd-ac93-4174fd72f030)

> The role consists of a prompt and model configuration.

### Session

Maintain context-aware conversations through sessions, ensuring continuity in interactions.

![aichat-session](https://github.com/user-attachments/assets/56583566-0f43-435f-95b3-730ae55df031)

> The left side uses a session, while the right side does not use a session.

### RAG (Chat with your documents)

Integrate external documents into your LLM conversations for more accurate and contextually relevant responses.


![aichat-rag](https://github.com/user-attachments/assets/359f0cb8-ee37-432f-a89f-96a2ebab01f6)

### Function Calling

Function calling supercharges LLMs by connecting them to external tools and data sources. This unlocks a world of possibilities, enabling LLMs to go beyond their core capabilities and tackle a wider range of tasks.

We have created a new repository [https://github.com/sigoden/llm-functions](https://github.com/sigoden/llm-functions) to help you make the most of this feature.

#### AI Tools

Integrate external tools to automate tasks, retrieve information, and perform actions directly within your workflow.

![aichat-tool](https://github.com/user-attachments/assets/7459a111-7258-4ef0-a2dd-624d0f1b4f92)

#### AI Agents (CLI version of OpenAI GPTs)

AI Agent = Instructions (Prompt) + Tools (Function Callings) + Documents (RAG).

![aichat-agent](https://github.com/user-attachments/assets/0b7e687d-e642-4e8a-b1c1-d2d9b2da2b6b)

### Local Server

AIChat comes with a built-in lightweight http server.

```
$ aichat --serve
Chat Completions API: http://127.0.0.1:8000/v1/chat/completions
Embeddings API:       http://127.0.0.1:8000/v1/embeddings
Rerank API:           http://127.0.0.1:8000/v1/rerank
LLM Playground:       http://127.0.0.1:8000/playground
LLM Arena:            http://127.0.0.1:8000/arena?num=2
```

#### Proxy LLM APIs

AIChat offers the ability to function as a proxy server for all LLMs. This allows you to interact with different LLMs using the familiar OpenAI API format, simplifying the process of accessing and utilizing these LLMs.

Test with curl:

```sh
curl -X POST -H "Content-Type: application/json" -d '{
  "model":"claude:claude-3-5-sonnet-20240620",
  "messages":[{"role":"user","content":"hello"}], 
  "stream":true
}' http://127.0.0.1:8000/v1/chat/completions
```

#### LLM Playground

The LLM Playground is a webapp that allows you to interact with any LLM supported by AIChat directly in your browser.

![aichat-llm-playground](https://github.com/user-attachments/assets/7f39fb78-a4ca-4007-a685-3a2b7d01dfdd)

#### LLM Arena

The LLM Arena is a web-based platform where you can compare different LLMs side-by-side. 

![aichat-llm-arena](https://github.com/user-attachments/assets/edabba53-a1ef-4817-9153-38542ffbfec6)

## Custom Themes

AIChat supports custom dark and light themes, which highlight response text and code blocks.

![aichat-themes](https://github.com/sigoden/aichat/assets/4012553/29fa8b79-031e-405d-9caa-70d24fa0acf8)

## Documentation

- [Chat-REPL Guide](https://github.com/sigoden/aichat/wiki/Chat-REPL-Guide)
- [Command-Line Guide](https://github.com/sigoden/aichat/wiki/Command-Line-Guide)
- [Role Guide](https://github.com/sigoden/aichat/wiki/Role-Guide)
- [RAG Guide](https://github.com/sigoden/aichat/wiki/RAG-Guide)
- [Environment Variables](https://github.com/sigoden/aichat/wiki/Environment-Variables)
- [Configuration Guide](https://github.com/sigoden/aichat/wiki/Configuration-Guide)
- [Custom Theme](https://github.com/sigoden/aichat/wiki/Custom-Theme)
- [Custom REPL Prompt](https://github.com/sigoden/aichat/wiki/Custom-REPL-Prompt)
- [FAQ](https://github.com/sigoden/aichat/wiki/FAQ)

# LLM Functions

This project empowers you to effortlessly build powerful LLM tools and agents using familiar languages like Bash, JavaScript, and Python. 

Forget complex integrations, **harness the power of [function calling](https://platform.openai.com/docs/guides/function-calling)** to connect your LLMs directly to custom code and unlock a world of possibilities. Execute system commands, process data, interact with APIs –  the only limit is your imagination.

**Tools Showcase**
![llm-function-tool](https://github.com/user-attachments/assets/40c77413-30ba-4f0f-a2c7-19b042a1b507)

**Agents showcase**
![llm-function-agent](https://github.com/user-attachments/assets/6e380069-8211-4a16-8592-096e909b921d)

## Prerequisites

Make sure you have the following tools installed:

- [argc](https://github.com/sigoden/argc): A bash command-line framework and command runner
- [jq](https://github.com/jqlang/jq): A JSON processor

## Getting Started with [AIChat](https://github.com/sigoden/aichat)

**Currently, AIChat is the only CLI tool that supports `llm-functions`. We look forward to more tools supporting `llm-functions`.**

### 1. Clone the repository

```sh
git clone https://github.com/sigoden/llm-functions
```

### 2. Build tools and agents

#### I. Create a `./tools.txt` file with each tool filename on a new line.

```
get_current_weather.sh
execute_command.sh
#execute_py_code.py
``` 

<details>
<summary>Where is the web_search tool?</summary>
<br>

The `web_search` tool itself doesn't exist directly, Instead, you can choose from a variety of web search tools.

To use one as the `web_search` tool, follow these steps:

1. **Choose a Tool:** Available tools include:
    * `web_search_cohere.sh`
    * `web_search_perplexity.sh`
    * `web_search_tavily.sh`
    * `web_search_vertexai.sh`

2. **Link Your Choice:** Use the `argc` command to link your chosen tool as `web_search`. For example, to use `web_search_perplexity.sh`:

    ```sh
    $ argc link-web-search web_search_perplexity.sh
    ```

    This command creates a symbolic link, making `web_search.sh` point to your selected `web_search_perplexity.sh` tool. 

Now there is a `web_search.sh` ready to be added to your `./tools.txt`.

</details>

#### II. Create a `./agents.txt` file with each agent name on a new line.

```
coder
todo
```

#### III. Build `bin` and `functions.json`

```sh
argc build
```

### 3. Install to AIChat

Symlink this repo directory to AIChat's **functions_dir**:

```sh
ln -s "$(pwd)" "$(aichat --info | grep -w functions_dir | awk '{$1=""; print substr($0,2)}')"
# OR
argc install
```

### 4. Start using the functions

Done! Now you can use the tools and agents with AIChat.

```sh
aichat --role %functions% what is the weather in Paris?
aichat --agent todo list all my todos
```

## Writing Your Own Tools

Building tools for our platform is remarkably straightforward. You can leverage your existing programming knowledge, as tools are essentially just functions written in your preferred language.

LLM Functions automatically generates the JSON declarations for the tools based on **comments**. Refer to `./tools/demo_tool.{sh,js,py}` for examples of how to use comments for autogeneration of declarations.

### Bash

Create a new bashscript in the [./tools/](./tools/) directory (.e.g. `execute_command.sh`).

```sh
#!/usr/bin/env bash
set -e

# @describe Execute the shell command.
# @option --command! The command to execute.

main() {
    eval "$argc_command" >> "$LLM_OUTPUT"
}

eval "$(argc --argc-eval "$0" "$@")"
```

### Javascript

Create a new javascript in the [./tools/](./tools/) directory (.e.g. `execute_js_code.js`).

```js
/**
 * Execute the javascript code in node.js.
 * @typedef {Object} Args
 * @property {string} code - Javascript code to execute, such as `console.log("hello world")`
 * @param {Args} args
 */
exports.run = function ({ code }) {
  eval(code);
}

```

### Python

Create a new python script in the [./tools/](./tools/) directory (e.g. `execute_py_code.py`).

```py
def run(code: str):
    """Execute the python code.
    Args:
        code: Python code to execute, such as `print("hello world")`
    """
    exec(code)

```

## Writing Your Own Agents

Agent = Prompt + Tools (Function Calling) + Documents (RAG), which is equivalent to OpenAI's GPTs.

The agent has the following folder structure:
```
└── agents
    └── myagent
        ├── functions.json                  # JSON declarations for functions (Auto-generated)
        ├── index.yaml                      # Agent definition
        ├── tools.txt                       # Shared tools
        └── tools.{sh,js,py}                # Agent tools 
```

The agent definition file (`index.yaml`) defines crucial aspects of your agent:

```yaml
name: TestAgent                             
description: This is test agent
version: 0.1.0
instructions: You are a test ai agent to ... 
conversation_starters:
  - What can you do?
variables:
  - name: foo
    description: This is a foo
documents:
  - local-file.txt
  - local-dir/
  - https://example.com/remote-file.txt
```

Refer to [./agents/demo](https://github.com/sigoden/llm-functions/tree/main/agents/demo) for examples of how to implement a agent.


## License

Copyright (c) 2023-2024 aichat-developers.

AIChat is made available under the terms of either the MIT License or the Apache License 2.0, at your option.

See the LICENSE-APACHE and LICENSE-MIT files for license details.
