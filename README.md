<div align="center">
  <a href="https://ollama.com">
    <img alt="ollama" height="200px" src="https://github.com/ollama/ollama/assets/3325447/0d0b44e2-8f4a-4e99-9b52-a5c1c741c8f7">
  </a>
</div>

# Ollama

[English] This project is for my personal customization and use. Please check the original project directly.
[한국어] 이 프로젝트는 나 나름대로 커스터마이징 하여 사용하기 위함임. 원본은 해당 프로젝트에서 직접 확인하기 바람.

### Docker

[English] The official [Ollama Docker image](https://hub.docker.com/r/ollama/ollama) `ollama/ollama` is available on Docker Hub.
[한국어] 공식 [Ollama Docker 이미지](https://hub.docker.com/r/ollama/ollama) `ollama/ollama`가 Docker Hub에서 사용 가능합니다.

### Libraries | 라이브러리

- [ollama-python](https://github.com/ollama/ollama-python)
- [ollama-js](https://github.com/ollama/ollama-js)

### Community | 커뮤니티

- [Discord](https://discord.gg/ollama)
- [Reddit](https://reddit.com/r/ollama)

## Quick Start | 빠른 시작

[English] To chat with [Llama 3.2](https://ollama.com/library/llama3.2):
[한국어] [Llama 3.2](https://ollama.com/library/llama3.2)와 대화하려면:

```shell
ollama run llama3.2
```

## Model Library | 모델 라이브러리

[English] Ollama supports a list of models available at [ollama.com/library](https://ollama.com/library 'ollama model library').
[한국어] Ollama는 [ollama.com/library](https://ollama.com/library 'ollama 모델 라이브러리')에서 사용 가능한 모델 목록을 지원합니다.

[English] Here are some example models you can download:
[한국어] 다음은 다운로드할 수 있는 예시 모델들입니다:

| Model | Parameters | Size | Download |
|-------|------------|------|----------|
| 모델 | 파라미터 | 크기 | 다운로드 |

| Gemma 3 | 1B | 815MB | `ollama run gemma3:1b` |
| Gemma 3 | 4B | 3.3GB | `ollama run gemma3` |
| Gemma 3 | 12B | 8.1GB | `ollama run gemma3:12b` |
| Gemma 3 | 27B | 17GB | `ollama run gemma3:27b` |
| QwQ | 32B | 20GB | `ollama run qwq` |
| DeepSeek-R1 | 7B | 4.7GB | `ollama run deepseek-r1` |
| DeepSeek-R1 | 671B | 404GB | `ollama run deepseek-r1:671b` |
| Llama 4 | 109B | 67GB | `ollama run llama4:scout` |
| Llama 4 | 400B | 245GB | `ollama run llama4:maverick` |
| Llama 3.3 | 70B | 43GB | `ollama run llama3.3` |
| Llama 3.2 | 3B | 2.0GB | `ollama run llama3.2` |
| Llama 3.2 | 1B | 1.3GB | `ollama run llama3.2:1b` |
| Llama 3.2 Vision | 11B | 7.9GB | `ollama run llama3.2-vision` |
| Llama 3.2 Vision | 90B | 55GB | `ollama run llama3.2-vision:90b` |
| Llama 3.1 | 8B | 4.7GB | `ollama run llama3.1` |
| Llama 3.1 | 405B | 231GB | `ollama run llama3.1:405b` |
| Phi 4 | 14B | 9.1GB | `ollama run phi4` |
| Phi 4 Mini | 3.8B | 2.5GB | `ollama run phi4-mini` |
| Mistral | 7B | 4.1GB | `ollama run mistral` |
| Moondream 2 | 1.4B | 829MB | `ollama run moondream` |
| Neural Chat | 7B | 4.1GB | `ollama run neural-chat` |
| Starling | 7B | 4.1GB | `ollama run starling-lm` |
| Code Llama | 7B | 3.8GB | `ollama run codellama` |
| Llama 2 Uncensored | 7B | 3.8GB | `ollama run llama2-uncensored` |
| LLaVA | 7B | 4.5GB | `ollama run llava` |
| Granite-3.3 | 8B | 4.9GB | `ollama run granite3.3` |

> [!NOTE]
> [English] 7B models require at least 8GB of RAM, 13B models require 16GB, and 33B models require 32GB of RAM.
> [한국어] 7B 모델을 실행하려면 최소 8GB의 RAM이 필요하고, 13B 모델은 16GB, 33B 모델은 32GB의 RAM이 필요합니다.

## Model Customization | 모델 커스터마이징

### Importing from GGUF | GGUF에서 가져오기

[English] Ollama supports importing GGUF models in the Modelfile:
[한국어] Ollama는 Modelfile에서 GGUF 모델 가져오기를 지원합니다:

1. [English] Create a file named `Modelfile` with the local file path of the model you want to import in the `FROM` directive.
   [한국어] 가져오려는 모델의 로컬 파일 경로를 `FROM` 지시문으로 지정하여 `Modelfile`이라는 파일을 생성합니다.

   ```
   FROM ./vicuna-33b.Q4_0.gguf
   ```

2. [English] Create the model in Ollama
   [한국어] Ollama에서 모델 생성

   ```shell
   ollama create example -f Modelfile
   ```

3. [English] Run the model
   [한국어] 모델 실행

   ```shell
   ollama run example
   ```

### Importing from Safetensors | Safetensors에서 가져오기

[English] See the [import guide](docs/import.md) for more information.
[한국어] 자세한 정보는 [가져오기 가이드](docs/import.md)를 참조하세요.

### Prompt Customization | 프롬프트 커스터마이징

[English] Models in the Ollama library can be customized with prompts. For example, to customize the `llama3.2` model:
[한국어] Ollama 라이브러리의 모델은 프롬프트로 커스터마이징할 수 있습니다. 예를 들어, `llama3.2` 모델을 커스터마이징하려면:

```shell
ollama pull llama3.2
```

[English] Create a `Modelfile`:
[한국어] `Modelfile` 생성:

```
FROM llama3.2

# Set temperature to 1 [higher is more creative, lower is more consistent]
# 온도를 1로 설정 [높을수록 더 창의적이고, 낮을수록 더 일관성 있음]
PARAMETER temperature 1

# Set system message
# 시스템 메시지 설정
SYSTEM """
당신은 슈퍼 마리오 브라더스의 마리오입니다. 마리오로서만 답변하세요.
"""
```

[English] Next, create and run the model:
[한국어] 다음으로, 모델을 생성하고 실행합니다:

```
ollama create mario -f ./Modelfile
ollama run mario
>>> 안녕하세요
안녕하세요! 당신의 친구 마리오입니다.
```

[English] See the [Modelfile](docs/modelfile.md) documentation for more information about working with Modelfiles.
[한국어] Modelfile 작업에 대한 자세한 정보는 [Modelfile](docs/modelfile.md) 문서를 참조하세요.

## CLI Reference | CLI 참조

### Model Creation | 모델 생성

[English] `ollama create` is used to create a model from a Modelfile.
[한국어] `ollama create`는 Modelfile에서 모델을 생성하는 데 사용됩니다.

```shell
ollama create mymodel -f ./Modelfile
```

### Model Pull | 모델 가져오기

```shell
ollama pull llama3.2
```

> [English] This command can also be used to update local models. Only the differences are pulled.
> [한국어] 이 명령은 로컬 모델을 업데이트하는 데도 사용할 수 있습니다. 차이점만 가져옵니다.

### Model Removal | 모델 제거

```shell
ollama rm llama3.2
```

### Model Copy | 모델 복사

```shell
ollama cp llama3.2 my-model
```

### Multi-line Input | 여러 줄 입력

[English] You can wrap text in `"""` for multi-line input:
[한국어] 여러 줄 입력을 위해 텍스트를 `"""`로 감쌀 수 있습니다:

```
>>> """안녕하세요,
... 세상!
... """
저는 "안녕하세요, 세상!"이라는 유명한 메시지를 콘솔에 출력하는 기본 프로그램입니다.
```

### Multimodal Models | 멀티모달 모델

```
ollama run llava "이 이미지에 무엇이 있나요? /Users/jmorgan/Desktop/smile.png"
```

> [English] **Output**: The image contains a yellow smiley face, which appears to be the central element of the photo.
> [한국어] **출력**: 이미지에는 노란색 웃는 얼굴이 있으며, 이는 아마도 사진의 중심이 되는 요소일 것입니다.

### Passing Prompts as Arguments | 인자로 프롬프트 전달

```shell
ollama run llama3.2 "이 파일을 요약해주세요: $(cat README.md)"
```

> [English] **Output**: Ollama is a lightweight, extensible framework for building and running language models on your local machine. It provides a simple API for creating, running, and managing models, and a library of pre-built models that can be easily used in various applications.
> [한국어] **출력**: Ollama는 로컬 머신에서 언어 모델을 구축하고 실행하기 위한 가볍고 확장 가능한 프레임워크입니다. 모델 생성, 실행 및 관리를 위한 간단한 API와 다양한 애플리케이션에서 쉽게 사용할 수 있는 사전 구축된 모델 라이브러리를 제공합니다.

### Show Model Information | 모델 정보 표시

```shell
ollama show llama3.2
```

### List Models on Computer | 컴퓨터의 모델 목록 표시

```shell
ollama list
```

### Show Currently Loaded Models | 현재 로드된 모델 목록 표시

```shell
ollama ps
```

### Stop Running Models | 실행 중인 모델 중지

```shell
ollama stop llama3.2
```

### Start Ollama | Ollama 시작

[English] `ollama serve` is used when you want to start ollama without running the desktop application.
[한국어] `ollama serve`는 데스크톱 애플리케이션을 실행하지 않고 ollama를 시작하고 싶을 때 사용됩니다.

## Building | 빌드

[English] See the [developer guide](https://github.com/ollama/ollama/blob/main/docs/development.md)
[한국어] [개발자 가이드](https://github.com/ollama/ollama/blob/main/docs/development.md)를 참조하세요.

### Running Local Builds | 로컬 빌드 실행하기

[English] Next, start the server:
[한국어] 다음으로, 서버를 시작합니다:

```shell
./ollama serve
```

[English] Finally, in a separate shell, run a model:
[한국어] 마지막으로, 별도의 셸에서 모델을 실행합니다:

```shell
./ollama run llama3.2
```

## REST API

[English] Ollama has a REST API for running and managing models.
[한국어] Ollama는 모델을 실행하고 관리하기 위한 REST API를 제공합니다.

### Generate a Response | 응답 생성하기

```shell
curl http://localhost:11434/api/generate -d '{
  "model": "llama3.2",
  "prompt":"하늘이 왜 파란가요?"
}'
```

### Chat with a Model | 모델과 대화하기

```shell
curl http://localhost:11434/api/chat -d '{
  "model": "llama3.2",
  "messages": [
    { "role": "user", "content": "하늘이 왜 파란가요?" }
  ]
}'
```

[English] See the [API documentation](./docs/api.md) for all endpoints.
[한국어] 모든 엔드포인트에 대해서는 [API 문서](./docs/api.md)를 참조하세요.

## Community Integrations | 커뮤니티 통합

### Web & Desktop | 웹 & 데스크톱

- [Open WebUI](https://github.com/open-webui/open-webui)
- [SwiftChat (macOS with ReactNative)](https://github.com/aws-samples/swift-chat)
- [Enchanted (macOS native)](https://github.com/AugustDev/enchanted)
- [Hollama](https://github.com/fmaclen/hollama)
- [Lollms-Webui](https://github.com/ParisNeo/lollms-webui)
- [LibreChat](https://github.com/danny-avila/LibreChat)
- [Bionic GPT](https://github.com/bionic-gpt/bionic-gpt)
- [HTML UI](https://github.com/rtcfirefly/ollama-ui)
- [Saddle](https://github.com/jikkuatwork/saddle)
- [TagSpaces](https://www.tagspaces.org) (파일 기반 앱을 위한 플랫폼, [Ollama 활용](https://docs.tagspaces.org/ai/)으로 태그와 설명 생성)
- [Chatbot UI](https://github.com/ivanfioravanti/chatbot-ollama)
- [Chatbot UI v2](https://github.com/mckaywrigley/chatbot-ui)
- [Typescript UI](https://github.com/ollama-interface/Ollama-Gui?tab=readme-ov-file)
- [Minimalistic React UI for Ollama Models](https://github.com/richawo/minimal-llm-ui)
- [Ollamac](https://github.com/kevinhermawan/Ollamac)
- [big-AGI](https://github.com/enricoros/big-AGI)
- [Cheshire Cat assistant framework](https://github.com/cheshire-cat-ai/core)
- [Amica](https://github.com/semperai/amica)
- [chatd](https://github.com/BruceMacD/chatd)
- [Ollama-SwiftUI](https://github.com/kghandour/Ollama-SwiftUI)
- [Dify.AI](https://github.com/langgenius/dify)
- [MindMac](https://mindmac.app)
- [NextJS Web Interface for Ollama](https://github.com/jakobhoeg/nextjs-ollama-llm-ui)
- [Msty](https://msty.app)
- [Chatbox](https://github.com/Bin-Huang/Chatbox)
- [WinForm Ollama Copilot](https://github.com/tgraupmann/WinForm_Ollama_Copilot)
- [NextChat](https://github.com/ChatGPTNextWeb/ChatGPT-Next-Web) with [Get Started Doc](https://docs.nextchat.dev/models/ollama)
- [Alpaca WebUI](https://github.com/mmo80/alpaca-webui)
- [OllamaGUI](https://github.com/enoch1118/ollamaGUI)
- [OpenAOE](https://github.com/InternLM/OpenAOE)
- [Odin Runes](https://github.com/leonid20000/OdinRunes)
- [LLM-X](https://github.com/mrdjohnson/llm-x) (Progressive Web App)
- [AnythingLLM (Docker + MacOs/Windows/Linux native app)](https://github.com/Mintplex-Labs/anything-llm)
- [Ollama Basic Chat: Uses HyperDiv Reactive UI](https://github.com/rapidarchitect/ollama_basic_chat)
- [Ollama-chats RPG](https://github.com/drazdra/ollama-chats)
- [IntelliBar](https://intellibar.app/) (AI-powered assistant for macOS)
- [Jirapt](https://github.com/AliAhmedNada/jirapt) (Jira Integration to generate issues, tasks, epics)
- [QA-Pilot](https://github.com/reid41/QA-Pilot) (Interactive chat tool that can leverage Ollama models for rapid understanding and navigation of GitHub code repositories)
- [ChatOllama](https://github.com/sugarforever/chat-ollama) (Open Source Chatbot based on Ollama with Knowledge Bases)
- [CRAG Ollama Chat](https://github.com/Nagi-ovo/CRAG-Ollama-Chat) (Simple Web Search with Corrective RAG)
- [RAGFlow](https://github.com/infiniflow/ragflow) (Open-source Retrieval-Augmented Generation engine based on deep document understanding)
- [StreamDeploy](https://github.com/StreamDeploy-DevRel/streamdeploy-llm-app-scaffold) (LLM Application Scaffold)
- [chat](https://github.com/swuecho/chat) (chat web app for teams)
- [Lobe Chat](https://github.com/lobehub/lobe-chat) with [Integrating Doc](https://lobehub.com/docs/self-hosting/examples/ollama)
- [Ollama RAG Chatbot](https://github.com/datvodinh/rag-chatbot.git) (Local Chat with multiple PDFs using Ollama and RAG)
- [BrainSoup](https://www.nurgo-software.com/products/brainsoup) (Flexible native client with RAG & multi-agent automation)
- [macai](https://github.com/Renset/macai) (macOS client for Ollama, ChatGPT, and other compatible API back-ends)
- [RWKV-Runner](https://github.com/josStorer/RWKV-Runner) (RWKV offline LLM deployment tool, also usable as a client for ChatGPT and Ollama)
- [Ollama Grid Search](https://github.com/dezoito/ollama-grid-search) (app to evaluate and compare models)
- [Olpaka](https://github.com/Otacon/olpaka) (User-friendly Flutter Web App for Ollama)
- [Casibase](https://casibase.org) (An open source AI knowledge base and dialogue system combining the latest RAG, SSO, ollama support, and multiple large language models.)
- [OllamaSpring](https://github.com/CrazyNeil/OllamaSpring) (Ollama Client for macOS)
- [LLocal.in](https://github.com/kartikm7/llocal) (Easy to use Electron Desktop Client for Ollama)
- [Shinkai Desktop](https://github.com/dcSpark/shinkai-apps) (Two click install Local AI using Ollama + Files + RAG)
- [AiLama](https://github.com/zeyoyt/ailama) (A Discord User App that allows you to interact with Ollama anywhere in Discord)
- [Ollama with Google Mesop](https://github.com/rapidarchitect/ollama_mesop/) (Mesop Chat Client implementation with Ollama)
- [R2R](https://github.com/SciPhi-AI/R2R) (Open-source RAG engine)
- [Ollama-Kis](https://github.com/elearningshow/ollama-kis) (A simple easy-to-use GUI with sample custom LLM for Drivers Education)
- [OpenGPA](https://opengpa.org) (Open-source offline-first Enterprise Agentic Application)
- [Painting Droid](https://github.com/mateuszmigas/painting-droid) (Painting app with AI integrations)
- [Kerlig AI](https://www.kerlig.com/) (AI writing assistant for macOS)
- [AI Studio](https://github.com/MindWorkAI/AI-Studio)
- [Sidellama](https://github.com/gyopak/sidellama) (browser-based LLM client)
- [LLMStack](https://github.com/trypromptly/LLMStack) (No-code multi-agent framework to build LLM agents and workflows)
- [BoltAI for Mac](https://boltai.com) (AI Chat Client for Mac)
- [Harbor](https://github.com/av/harbor) (Containerized LLM Toolkit with Ollama as default backend)
- [PyGPT](https://github.com/szczyglis-dev/py-gpt) (AI desktop assistant for Linux, Windows, and Mac)
- [Alpaca](https://github.com/Jeffser/Alpaca) (An Ollama client application for Linux and macOS made with GTK4 and Adwaita)
- [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT/blob/master/docs/content/platform/ollama.md) (AutoGPT Ollama integration)
- [Go-CREW](https://www.jonathanhecl.com/go-crew/) (Powerful Offline RAG in Golang)
- [PartCAD](https://github.com/openvmp/partcad/) (CAD model generation with OpenSCAD and CadQuery)
- [Ollama4j Web UI](https://github.com/ollama4j/ollama4j-web-ui) - Java-based Web UI for Ollama built with Vaadin, Spring Boot, and Ollama4j
- [PyOllaMx](https://github.com/kspviswa/pyOllaMx) - macOS application capable of chatting with both Ollama and Apple MLX models.
- [Cline](https://github.com/cline/cline) - Formerly known as Claude Dev is a VSCode extension for multi-file/whole-repo coding
- [Cherry Studio](https://github.com/kangfenmao/cherry-studio) (Desktop client with Ollama support)
- [ConfiChat](https://github.com/1runeberg/confichat) (Lightweight, standalone, multi-platform, and privacy-focused LLM chat interface with optional encryption)
- [Archyve](https://github.com/nickthecook/archyve) (RAG-enabling document library)
- [crewAI with Mesop](https://github.com/rapidarchitect/ollama-crew-mesop) (Mesop Web Interface to run crewAI with Ollama)
- [Tkinter-based client](https://github.com/chyok/ollama-gui) (Python tkinter-based Client for Ollama)
- [LLMChat](https://github.com/trendy-design/llmchat) (Privacy focused, 100% local, intuitive all-in-one chat interface)
- [Local Multimodal AI Chat](https://github.com/Leon-Sander/Local-Multimodal-AI-Chat) (Ollama-based LLM Chat with support for multiple features, including PDF RAG, voice chat, image-based interactions, and integration with OpenAI.)
- [ARGO](https://github.com/xark-argo/argo) (Locally download and run Ollama and Huggingface models with RAG on Mac/Windows/Linux)
- [OrionChat](https://github.com/EliasPereirah/OrionChat) - OrionChat is a web interface for chatting with different AI providers
- [G1](https://github.com/bklieger-groq/g1) (Prototype of using prompting strategies to improve the LLM's reasoning through o1-like reasoning chains.)
- [Web management](https://github.com/lemonit-eric-mao/ollama-web-management) (Web management page)
- [Promptery](https://github.com/promptery/promptery) (desktop client for Ollama.)
- [Ollama App](https://github.com/JHubi1/ollama-app) (Modern and easy-to-use multi-platform client for Ollama)
- [chat-ollama](https://github.com/annilq/chat-ollama) (a React Native client for Ollama)
- [SpaceLlama](https://github.com/tcsenpai/spacellama) (Firefox and Chrome extension to quickly summarize web pages with ollama in a sidebar)
- [YouLama](https://github.com/tcsenpai/youlama) (Webapp to quickly summarize any YouTube video, supporting Invidious as well)
- [DualMind](https://github.com/tcsenpai/dualmind) (Experimental app allowing two models to talk to each other in the terminal or in a web interface)
- [ollamarama-matrix](https://github.com/h1ddenpr0cess20/ollamarama-matrix) (Ollama chatbot for the Matrix chat protocol)
- [ollama-chat-app](https://github.com/anan1213095357/ollama-chat-app) (Flutter-based chat app)
- [Perfect Memory AI](https://www.perfectmemory.ai/) (Productivity AI assists personalized by what you have seen on your screen, heard, and said in the meetings)
- [Hexabot](https://github.com/hexastack/hexabot) (A conversational AI builder)
- [Reddit Rate](https://github.com/rapidarchitect/reddit_analyzer) (Search and Rate Reddit topics with a weighted summation)
- [OpenTalkGpt](https://github.com/adarshM84/OpenTalkGpt) (Chrome Extension to manage open-source models supported by Ollama, create custom models, and chat with models from a user-friendly UI)
- [VT](https://github.com/vinhnx/vt.ai) (A minimal multimodal AI chat app, with dynamic conversation routing. Supports local models via Ollama)
- [Nosia](https://github.com/nosia-ai/nosia) (Easy to install and use RAG platform based on Ollama)
- [Witsy](https://github.com/nbonamy/witsy) (An AI Desktop application available for Mac/Windows/Linux)
- [Abbey](https://github.com/US-Artificial-Intelligence/abbey) (A configurable AI interface server with notebooks, document storage, and YouTube support)
- [Minima](https://github.com/dmayboroda/minima) (RAG with on-premises or fully local workflow)
- [aidful-ollama-model-delete](https://github.com/AidfulAI/aidful-ollama-model-delete) (User interface for simplified model cleanup)
- [Perplexica](https://github.com/ItzCrazyKns/Perplexica) (An AI-powered search engine & an open-source alternative to Perplexity AI)
- [Ollama Chat WebUI for Docker ](https://github.com/oslook/ollama-webui) (Support for local docker deployment, lightweight ollama webui)
- [AI Toolkit for Visual Studio Code](https://aka.ms/ai-tooklit/ollama-docs) (Microsoft-official VSCode extension to chat, test, evaluate models with Ollama support, and use them in your AI applications.)
- [MinimalNextOllamaChat](https://github.com/anilkay/MinimalNextOllamaChat) (Minimal Web UI for Chat and Model Control)
- [Chipper](https://github.com/TilmanGriesel/chipper) AI interface for tinkerers (Ollama, Haystack RAG, Python)
- [ChibiChat](https://github.com/CosmicEventHorizon/ChibiChat) (Kotlin-based Android app to chat with Ollama and Koboldcpp API endpoints)
- [LocalLLM](https://github.com/qusaismael/localllm) (Minimal Web-App to run ollama models on it with a GUI)
- [Ollamazing](https://github.com/buiducnhat/ollamazing) (Web extension to run Ollama models)
- [OpenDeepResearcher-via-searxng](https://github.com/benhaotang/OpenDeepResearcher-via-searxng) (A Deep Research equivalent endpoint with Ollama support for running locally)
- [AntSK](https://github.com/AIDotNet/AntSK) (Out-of-the-box & Adaptable RAG Chatbot)
- [MaxKB](https://github.com/1Panel-dev/MaxKB/) (Ready-to-use & flexible RAG Chatbot)
- [yla](https://github.com/danielekp/yla) (Web interface to freely interact with your customized models)
- [LangBot](https://github.com/RockChinQ/LangBot) (LLM-based instant messaging bots platform, with Agents, RAG features, supports multiple platforms)
- [1Panel](https://github.com/1Panel-dev/1Panel/) (Web-based Linux Server Management Tool)
- [AstrBot](https://github.com/Soulter/AstrBot/) (User-friendly LLM-based multi-platform chatbot with a WebUI, supporting RAG, LLM agents, and plugins integration)
- [Reins](https://github.com/ibrahimcetin/reins) (Easily tweak parameters, customize system prompts per chat, and enhance your AI experiments with reasoning model support.)
- [Flufy](https://github.com/Aharon-Bensadoun/Flufy) (A beautiful chat interface for interacting with Ollama's API. Built with React, TypeScript, and Material-UI.)
- [Ellama](https://github.com/zeozeozeo/ellama) (Friendly native app to chat with an Ollama instance)
- [screenpipe](https://github.com/mediar-ai/screenpipe) Build agents powered by your screen history
- [Ollamb](https://github.com/hengkysteen/ollamb) (Simple yet rich in features, cross-platform built with Flutter and designed for Ollama. Try the [web demo](https://hengkysteen.github.io/demo/ollamb/).)
- [Writeopia](https://github.com/Writeopia/Writeopia) (Text editor with integration with Ollama)
- [AppFlowy](https://github.com/AppFlowy-IO/AppFlowy) (AI collaborative workspace with Ollama, cross-platform and self-hostable)
- [Lumina](https://github.com/cushydigit/lumina.git) (A lightweight, minimal React.js frontend for interacting with Ollama servers)

### Cloud | 클라우드

- [Google Cloud](https://cloud.google.com/run/docs/tutorials/gpu-gemma2-with-ollama)
- [Fly.io](https://fly.io/docs/python/do-more/add-ollama/)
- [Koyeb](https://www.koyeb.com/deploy/ollama)

### Mobile | 모바일

- [SwiftChat](https://github.com/aws-samples/swift-chat) (Android, iOS, iPad를 위한 빠른 크로스 플랫폼 AI 채팅 앱)
- [Enchanted](https://github.com/AugustDev/enchanted)
- [Maid](https://github.com/Mobile-Artificial-Intelligence/maid)
- [Ollama App](https://github.com/JHubi1/ollama-app) (Ollama를 위한 현대적이고 사용하기 쉬운 멀티플랫폼 클라이언트)
- [ConfiChat](https://github.com/1runeberg/confichat) (선택적 암호화가 포함된 가벼운 독립형 멀티플랫폼 프라이버시 중심 LLM 채팅 인터페이스)
- [Ollama Android Chat](https://github.com/sunshine0523/OllamaServer) (Termux가 필요 없이 Android 기기에서 원클릭으로 Ollama 서비스 시작)
- [Reins](https://github.com/ibrahimcetin/reins) (파라미터를 쉽게 조정하고, 채팅별 시스템 프롬프트를 커스터마이징하며, 추론 모델 지원으로 AI 실험을 향상시킬 수 있습니다)

### Extensions & Plugins | 확장 프로그램 & 플러그인

- [Raycast extension](https://github.com/MassimilianoPasquini97/raycast_ollama)
- [Discollama](https://github.com/mxyng/discollama) (Ollama 디스코드 채널 내의 디스코드 봇)
- [Continue](https://github.com/continuedev/continue)
- [Vibe](https://github.com/thewh1teagle/vibe) (Ollama로 회의 내용을 기록하고 분석)
- [Obsidian Ollama plugin](https://github.com/hinterdupfinger/obsidian-ollama)
- [Logseq Ollama plugin](https://github.com/omagdy7/ollama-logseq)
- [NotesOllama](https://github.com/andersrex/notesollama) (Apple Notes Ollama 플러그인)

### Terminal | 터미널

- [oterm](https://github.com/ggozad/oterm)
- [Ellama Emacs 클라이언트](https://github.com/s-kostyaev/ellama)
- [Emacs 클라이언트](https://github.com/zweifisch/ollama)
- [neollama](https://github.com/paradoxical-dev/neollama) Neovim 내에서 모델과 상호작용하기 위한 UI 클라이언트
- [gen.nvim](https://github.com/David-Kunz/gen.nvim)
- [ollama.nvim](https://github.com/nomnivore/ollama.nvim)
- [ollero.nvim](https://github.com/marco-souza/ollero.nvim)
- [ollama-chat.nvim](https://github.com/gerazov/ollama-chat.nvim)
- [ogpt.nvim](https://github.com/huynle/ogpt.nvim)
- [gptel Emacs 클라이언트](https://github.com/karthink/gptel)
- [Oatmeal](https://github.com/dustinblackman/oatmeal)
- [cmdh](https://github.com/pgibler/cmdh)
- [ooo](https://github.com/npahlfer/ooo)
- [shell-pilot](https://github.com/reid41/shell-pilot)(Linux나 macOS에서 순수 셸 스크립트를 통해 모델과 상호작용)
- [tenere](https://github.com/pythops/tenere)
- [llm-ollama](https://github.com/taketwo/llm-ollama) [Datasette의 LLM CLI](https://llm.datasette.io/en/stable/)용
- [typechat-cli](https://github.com/anaisbetts/typechat-cli)
- [ShellOracle](https://github.com/djcopley/ShellOracle)
- [tlm](https://github.com/yusufcanb/tlm)
- [podman-ollama](https://github.com/ericcurtin/podman-ollama)
- [gollama](https://github.com/sammcj/gollama)
- [ParLlama](https://github.com/paulrobello/parllama)
- [Ollama eBook Summary](https://github.com/cognitivetech/ollama-ebook-summary/)
- [Ollama Mixture of Experts (MOE) in 50 lines of code](https://github.com/rapidarchitect/ollama_moe)
- [vim-intelligence-bridge](https://github.com/pepo-ec/vim-intelligence-bridge) Vim 에디터와 "Ollama"의 간단한 상호작용
- [x-cmd ollama](https://x-cmd.com/mod/ollama)
- [bb7](https://github.com/drunkwcodes/bb7)
- [SwollamaCLI](https://github.com/marcusziade/Swollama) Swollama Swift 패키지와 함께 번들로 제공. [데모](https://github.com/marcusziade/Swollama?tab=readme-ov-file#cli-usage)
- [aichat](https://github.com/sigoden/aichat) OpenAI, Claude, Gemini, Ollama, Groq 등에 접근할 수 있는 셸 어시스턴트, 채팅-REPL, RAG, AI 도구 및 에이전트를 갖춘 올인원 LLM CLI 도구
- [PowershAI](https://github.com/rrg92/powershai) Ollama 지원을 포함하여 Windows의 터미널에 AI를 제공하는 PowerShell 모듈
- [DeepShell](https://github.com/Abyss-c0re/deepshell) 자체 호스팅 AI 어시스턴트. 대화형 셸, 파일 및 폴더 분석
- [orbiton](https://github.com/xyproto/orbiton) Ollama를 통한 탭 완성을 지원하는 설정이 필요 없는 텍스트 에디터 및 IDE
- [orca-cli](https://github.com/molbal/orca-cli) Ollama 레지스트리 CLI 애플리케이션 - 터미널에서 Ollama 레지스트리의 모델을 탐색, 가져오기 및 다운로드
- [GGUF-to-Ollama](https://github.com/jonathanhecl/gguf-to-ollama) - GGUF를 Ollama로 쉽게 가져오기 (멀티플랫폼)

### Apple Vision Pro

- [SwiftChat](https://github.com/aws-samples/swift-chat) ("iPad용으로 설계"를 통해 Apple Vision Pro를 지원하는 크로스 플랫폼 AI 채팅 앱)
- [Enchanted](https://github.com/AugustDev/enchanted)

### Database | 데이터베이스

- [pgai](https://github.com/timescale/pgai) - 벡터 데이터베이스로서의 PostgreSQL (pgvector를 사용하여 Ollama 모델에서 임베딩 생성 및 검색)
   - [시작 가이드](https://github.com/timescale/pgai/blob/main/docs/vectorizer-quick-start.md)
- [MindsDB](https://github.com/mindsdb/mindsdb/blob/staging/mindsdb/integrations/handlers/ollama_handler/README.md) (Ollama 모델을 거의 200개의 데이터 플랫폼 및 앱과 연결)
- [chromem-go](https://github.com/philippgille/chromem-go/blob/v0.5.0/embed_ollama.go) [예제](https://github.com/philippgille/chromem-go/tree/v0.5.0/examples/rag-wikipedia-ollama) 포함
- [Kangaroo](https://github.com/dbkangaroo/kangaroo) (인기 있는 데이터베이스를 위한 AI 기반 SQL 클라이언트 및 관리 도구)

### Package Managers | 패키지 관리자

- [Pacman](https://archlinux.org/packages/extra/x86_64/ollama/)
- [Gentoo](https://github.com/gentoo/guru/tree/master/app-misc/ollama)
- [Homebrew](https://formulae.brew.sh/formula/ollama)
- [Helm Chart](https://artifacthub.io/packages/helm/ollama-helm/ollama)
- [Guix channel](https://codeberg.org/tusharhero/ollama-guix)
- [Nix package](https://search.nixos.org/packages?show=ollama&from=0&size=50&sort=relevance&type=packages&query=ollama)
- [Flox](https://flox.dev/blog/ollama-part-one)

### Libraries | 라이브러리

- [LangChain](https://python.langchain.com/docs/integrations/chat/ollama/) 및 [LangChain.js](https://js.langchain.com/docs/integrations/chat/ollama/) [예제](https://js.langchain.com/docs/tutorials/local_rag/) 포함
- [Firebase Genkit](https://firebase.google.com/docs/genkit/plugins/ollama)
- [crewAI](https://github.com/crewAIInc/crewAI)
- [Yacana](https://remembersoftwares.github.io/yacana/) (내장된 도구 통합으로 미리 정의된 흐름을 브레인스토밍하고 실행하기 위한 사용자 친화적인 멀티 에이전트 프레임워크)
- [Spring AI](https://github.com/spring-projects/spring-ai) [참조](https://docs.spring.io/spring-ai/reference/api/chat/ollama-chat.html) 및 [예제](https://github.com/tzolov/ollama-tools) 포함

### Observability | 관찰 가능성

- [Opik](https://www.comet.com/docs/opik/cookbook/ollama)은 포괄적인 추적, 자동화된 평가 및 프로덕션 준비된 대시보드로 LLM 애플리케이션, RAG 시스템 및 에이전트 워크플로우를 디버그, 평가 및 모니터링하기 위한 오픈소스 플랫폼입니다. Opik은 Ollama와의 네이티브 통합을 지원합니다.
- [Lunary](https://lunary.ai/docs/integrations/ollama)는 선도적인 오픈소스 LLM 관찰 가능성 플랫폼입니다. 실시간 분석, 프롬프트 템플릿 관리, PII 마스킹 및 포괄적인 에이전트 추적과 같은 다양한 엔터프라이즈급 기능을 제공합니다.
- [OpenLIT](https://github.com/openlit/openlit)은 추적과 메트릭을 사용하여 Ollama 애플리케이션 및 GPU를 모니터링하기 위한 OpenTelemetry 네이티브 도구입니다.
- [HoneyHive](https://docs.honeyhive.ai/integrations/ollama)는 AI 에이전트를 위한 AI 관찰 가능성 및 평가 플랫폼입니다. HoneyHive를 사용하여 에이전트 성능을 평가하고, 실패를 조사하며, 프로덕션에서 품질을 모니터링할 수 있습니다.
- [Langfuse](https://langfuse.com/docs/integrations/ollama)는 팀이 AI 애플리케이션을 협업적으로 모니터링, 평가 및 디버그할 수 있게 해주는 오픈소스 LLM 관찰 가능성 플랫폼입니다.
- [MLflow Tracing](https://mlflow.org/docs/latest/llms/tracing/index.html#automatic-tracing)은 편리한 API로 추적을 기록하고 시각화하여 GenAI 애플리케이션을 쉽게 디버그하고 평가할 수 있게 해주는 오픈소스 LLM 관찰 가능성 도구입니다.
