# Trilha de Aprendizado em Engenharia de IA com .NET & C#

> **Construindo Sistemas de Inteligência Artificial Corporativos, Resilientes e Escaláveis sob a Ótica da Engenharia de Software.**

---

## Sumário

- [0. Introdução: O Papel da Engenharia de Software em IA com .NET](#0-introdução-o-papel-da-engenharia-de-software-em-ia-com-net)
  - [0.1 Contexto e Justificativa do Currículo](#01-contexto-e-justificativa-do-currículo)
  - [0.2 Pilares Arquiteturais do Currículo](#02-pilares-arquiteturais-do-currículo)
- [1. Programa dos Módulos e Capstone Projects](#1-programa-dos-módulos-e-capstone-projects)
  - [Módulo 01: Fundamentos de Conectividade e Abstração Unificada com `Microsoft.Extensions.AI`](#módulo-01-fundamentos-de-conectividade-e-abstração-unificada-com-microsoftextensionsai)
  - [Módulo 02: Gateway Unificado de Modelos, Roteamento Dinâmico e OpenRouter](#módulo-02-gateway-unificado-de-modelos-roteamento-dinâmico-e-openrouter)
  - [Módulo 03: LangChain em C# (LangChain.NET) vs. Ecossistema Oficial da Microsoft: Revisão Crítica e Engenharia Comparativa](#módulo-03-langchain-em-c-langchainnet-vs-ecossistema-oficial-da-microsoft-revisão-crítica-e-engenharia-comparativa)
  - [Módulo 04: Sessões de Usuário, Histórico Resiliente e Gerenciamento de Memória de Agentes](#módulo-04-sessões-de-usuário-histórico-resiliente-e-gerenciamento-de-memória-de-agentes)
  - [Módulo 05: RAG Corporativo: Arquitetura Avançada, Busca Híbrida, GraphRAG e Evals](#módulo-05-rag-corporativo-arquitetura-avançada-busca-híbrida-graphrag-e-evals)
  - [Módulo 06: IA Local Soberana com Ollama vs. Cloud: Análise de Trade-offs e Estratégia Híbrida](#módulo-06-ia-local-soberana-com-ollama-vs-cloud-análise-de-trade-offs-e-estratégia-híbrida)
  - [Módulo 07: Engenharia Avançada de Prompts, Notações Estruturadas (JSON/YAML/TON) e Multimodalidade](#módulo-07-engenharia-avançada-de-prompts-notações-estruturadas-jsonyamlton-e-multimodalidade)
  - [Módulo 08: Governança, Contratos de Uso, Privacidade e Zero Data Retention](#módulo-08-governança-contratos-de-uso-privacidade-e-zero-data-retention)
  - [Módulo 09: Observabilidade Transversal, FinOps de Tokens e Dashboards com OpenTelemetry](#módulo-09-observabilidade-transversal-finops-de-tokens-e-dashboards-com-opentelemetry)
  - [Módulo 10: Segurança Ofensiva e Defensiva: OWASP Top 10 for LLMs, Prompt Injection e Guardrails](#módulo-10-segurança-ofensiva-e-defensiva-owasp-top-10-for-llms-prompt-injection-e-guardrails)
  - [Módulo 11: Machine Learning Clássico com ML.NET: Modelos Preditivos e Hibridização com GenAI](#módulo-11-machine-learning-clássico-com-mlnet-modelos-preditivos-e-hibridização-com-genai)
  - [Módulo 12: Extensibilidade com Model Context Protocol (MCP) em .NET](#módulo-12-extensibilidade-com-model-context-protocol-mcp-em-net)
  - [Módulo 13: Agentes de IA com Microsoft Agent Framework (MAF), Semantic Kernel e Declarative Agents](#módulo-13-agentes-de-ia-com-microsoft-agent-framework-maf-semantic-kernel-e-declarative-agents)
  - [Módulo 14: Orquestração Multiagente Avançada: Workflows em Grafo, Máquinas de Estado e Execução Paralela/Sequencial](#módulo-14-orquestração-multiagente-avançada-workflows-em-grafo-máquinas-de-estado-e-execução-paralelasequencial)
  - [Módulo 15: Design by Contract (DbC) para Agentes Autônomos em C#](#módulo-15-design-by-contract-dbc-para-agentes-autônomos-em-c)
  - [Módulo 16: Grand Master Capstone — A Plataforma Agêntica Corporativa](#módulo-16-grand-master-capstone--a-plataforma-agêntica-corporativa)
- [2. Como Utilizar este Repositório](#2-como-utilizar-este-repositório)
- [3. Meta-Prompt: Gerador de Guias de Estudo e Especificações Arquiteturais](#3-meta-prompt-gerador-de-guias-de-estudo-e-especificações-arquiteturais)

---

## 0. Introdução: O Papel da Engenharia de Software em IA com .NET

### 0.1 Contexto e Justificativa do Currículo
O ecossistema contemporâneo de Inteligência Artificial Generativa é amplamente dominado por bibliotecas, tutoriais e materiais voltados para Python e JavaScript/TypeScript. Embora essas linguagens se destaquem na prototipagem rápida, experimentação científica e scripting em notebooks, a realidade da **engenharia de produção corporativa em larga escala** introduz desafios substancialmente diferentes:

- **Acoplamento forte (Tight coupling)**: scripts que entrelaçam chamadas diretas de APIs de IA com a lógica de negócios central.
- **Falta de Type Safety**: validação frágil de schemas e falhas em tempo de execução nas respostas de LLMs devido à ausência de tipagem estática em tempo de compilação.
- **Fragilidade operacional**: ausência de políticas robustas de resiliência (retries, fallbacks, circuit breakers) e de injeção de dependência desacoplada.
- **Naive RAG**: implementações supersimplificadas que dependem de chunking arbitrário e buscas vetoriais por similaridade de cosseno que falham em domínios corporativos complexos.
- **Instruções em prosa não estruturada**: prompts monolíticos em texto livre que causam altas taxas de violação de restrições (*Rule Violations*) e consumo descontrolado de tokens.
- **Ausência de Contratos de Execução**: falta de uma fronteira formal separando o runtime de execução dos invariantes de negócio e critérios de aceitação dos agentes.
- **Déficits de governança e segurança**: pipelines sem trilhas de auditoria de dados, telemetria padronizada e proteção contra ameaças emergentes específicas de IA (OWASP Top 10 for LLMs).

O ecossistema **.NET (C#)** é historicamente reconhecido por sua excelência de nível corporativo em sistemas de missão crítica, concorrência assíncrona de alta performance, tipagem forte e design patterns consolidados. Com os investimentos recentes da Microsoft — notadamente **`Microsoft.Extensions.AI` (MEAI)**, **`Microsoft.Extensions.AI.Evaluation`**, o **Microsoft Agent Framework (MAF)**, **Semantic Kernel** e **ML.NET** —, a plataforma .NET oferece uma toolchain unificada e pronta para o ambiente corporativo.

Este repositório estabelece uma jornada progressiva e prática ao longo de **16 Módulos** projetados para capacitar desenvolvedores a atuar como **Engenheiros de IA com .NET**, cobrindo o ciclo de vida completo de desenvolvimento de ponta a ponta, sem atalhos superficiais.

---

### 0.2 Pilares Arquiteturais do Currículo

Todos os módulos e capstone projects deste currículo são construídos sobre quatro pilares de engenharia não negociáveis:

```text
+---------------------------------------------------------------------------------------+
|                                CLEAN ARCHITECTURE / DDD                               |
+--------------------------+---------------------------+--------------------------------+
|     SOLID PRINCIPLES     |      DESIGN PATTERNS      |       TWELVE-FACTOR APP        |
|  - Single Responsibility |  - Decorator / Pipeline   |  - Stateless Processes (VI)    |
|  - Open/Closed           |  - Strategy / Factory     |  - Backing Services (IV)       |
|  - Liskov Substitution   |  - Adapter (MCP)          |  - Streamed Telemetry (XI)     |
|  - Interface Segregation |  - Circuit Breaker (Polly)|  - Config via Environment (III)|
|  - Dependency Inversion  |  - Saga / DAGs (Workflows)|  - Concurrency (VIII)          |
+--------------------------+---------------------------+--------------------------------+
|                              THE TWELVE-FACTOR AGENT                                  |
|  1. Model vs Deterministic Logic Separation      7. Tenant & Credential Isolation     |
|  2. 100% Stateless Agent Runtime                 8. Observability & Traceability      |
|  3. Graph / Event-Driven State Transitions       9. Continuous Evals & Test Suites    |
|  4. Structured I/O & TON/JSON Formats           10. Idempotency & Fault Tolerance     |
|  5. Deterministic Guardrails vs Injection       11. Human-in-the-Loop & Approvals     |
|  6. Tool Abstraction via MCP Protocol           12. Declarative Specifications (DbC)  |
+---------------------------------------------------------------------------------------+
```

1. **Princípios SOLID Aplicados à IA**:
   - **SRP (Single Responsibility Principle)**: Separação estrita entre modelos de inferência, orquestração estruturada de prompts, guardrails defensivos e persistência de histórico de conversação.
   - **OCP (Open/Closed Principle)**: Extensibilidade do pipeline de execução de chat via delegating handlers (chat middlewares) sem modificar os clientes subjacentes.
   - **LSP (Liskov Substitution Principle)**: Troca transparente entre provedores de modelos (Ollama local, OpenAI, Azure OpenAI, Anthropic) preservando os contratos de domínio.
   - **ISP (Interface Segregation Principle)**: Abstrações focadas e de propósito único (`IChatClient`, `IEmbeddingGenerator`, `IToolRegistry`, `IEvaluator`).
   - **DIP (Dependency Inversion Principle)**: A lógica de negócios depende exclusivamente de abstrações .NET, nunca de SDKs proprietários de fornecedores.

2. **Design Patterns Estruturais e Comportamentais**:
   - **Decorator / Chain of Responsibility**: Implementado via pipeline de `DelegatingChatClient` para logs de auditoria, telemetria, caching, rate limiting e moderação.
   - **Strategy & Factory**: Seleção dinâmica e instanciação do modelo ou provedor ideal com base em restrições de custo, latência ou context window.
   - **Adapter**: Integração de sistemas legados e APIs corporativas no formato universal do Model Context Protocol (MCP).
   - **Directed Acyclic Graph (DAG) / Saga**: Coordenação determinística multiagente em workflows com ramificações e ações compensatórias.
   - **Design by Contract (DbC)**: Especificação formal de Pré-condições (Preconditions), Invariantes (Invariants) e Pós-condições/Critérios de Aceitação (Postconditions / Acceptance Criteria) para execução confiável de agentes.

3. **The Twelve-Factor App & The Twelve-Factor Agent**:
   - Adoção de processos stateless, backing services desacoplados (para bancos vetoriais e caches), configuração isolada via variáveis de ambiente e telemetria tratada como fluxos contínuos de eventos.
   - Implementação dos 12 preceitos para agentes autônomos: separação estrita do **Deterministic Control Plane (Finite State Machines / Harel Statecharts)** da execução estocástica do modelo generativo, isolamento de tenant e credenciais, schemas compactos (JSON/TON), idempotência de tools e approval gates explícitos com Human-in-the-Loop (veja **[Módulo 14: Orquestração Multiagente Avançada: Workflows em Grafo, Máquinas de Estado e Execução Paralela/Sequencial](#módulo-14-orquestração-multiagente-avançada-workflows-em-grafo-máquinas-de-estado-e-execução-paralelasequencial)**).

---

## 1. Programa dos Módulos e Capstone Projects

---

### Módulo 01: Fundamentos de Conectividade e Abstração Unificada com `Microsoft.Extensions.AI`
- **Contexto & Objetivos**: Consumir múltiplos provedores de IA (OpenAI, Azure OpenAI, Anthropic, Gemini) sem vendor lock-in; dominar hiperparâmetros de inferência (`Temperature`, `TopK`, `TopP`, `MaxTokens`, `StopSequences`); medir e realizar benchmarking de latência, custo (preço por 1K tokens) e throughput (tokens por segundo).
- **Abstrações & Frameworks**: `Microsoft.Extensions.AI`, `IChatClient`, `ChatOptions`, `ChatResponse`, cliente `OpenAI`, `Azure.AI.OpenAI`.
- **Princípios & Padrões**: Injeção de Dependência (.NET ServiceCollection), Strategy Pattern, Factory Pattern, Single Responsibility Principle (SRP).
- **Referências do Microsoft Learn**:
  - [Conceitos de IChatClient em .NET](https://learn.microsoft.com/dotnet/ai/ichatclient)
  - [Referência de API: IChatClient](https://learn.microsoft.com/dotnet/api/microsoft.extensions.ai.ichatclient)
- **Capstone Project 01**:
  - *Nome*: `AiProviderBenchmarker.Cli`
  - *Caminho*: `src/Module01/AiProviderBenchmarker/` (com uma demo rápida em `src/Module01/SimpleChatDemo/`)
  - *Executar & Testar*:
    - Demo Rápida: `dotnet run --project src/Module01/SimpleChatDemo`
    - CLI Interativa: `dotnet run --project src/Module01/AiProviderBenchmarker/src/AiProviderBenchmarker.Cli`
    - Suíte de Testes: `dotnet test src/Module01/AiProviderBenchmarker/AiProviderBenchmarker.slnx`
  - *Escopo*: Console Application em C# construída com Clean Architecture que injeta uma `IChatClientFactory`. A aplicação despacha um lote idêntico de prompts para múltiplos provedores concorrentemente, renderizando streaming token a token em tempo real e uma tabela comparativa com métricas: TTFT (Time To First Token), total de tokens gerados, latência decorrida e custo estimado de FinOps.

---

### Módulo 02: Gateway Unificado de Modelos, Roteamento Dinâmico e OpenRouter
- **Contexto & Objetivos**: Construir um gateway corporativo de IA utilizando agregadores como OpenRouter em conjunto com roteamento inteligente interno; alternar modelos dinamicamente em runtime com base no tamanho do payload, custo ou limites de latência; implementar failover automatizado com circuit breakers e retries do Polly.
- **Abstrações & Frameworks**: `Microsoft.Extensions.AI`, `DelegatingChatClient`, `Polly` (resiliência em .NET), `System.Net.Http`.
- **Princípios & Padrões**: Decorator Pattern (ChatClient Middleware), Circuit Breaker, Fallback Strategy, Twelve-Factor: Fator IV (Backing Services tratados como recursos anexados).
- **Referências do Microsoft Learn**:
  - [Custom IChatClient Middleware](https://learn.microsoft.com/dotnet/ai/ichatclient#custom-ichatclient-middleware)
  - [Resiliência HTTP em .NET com Polly](https://learn.microsoft.com/dotnet/core/resilience/http-resilience)
- **Capstone Project 02**:
  - *Nome*: `SmartRouter.Gateway`
  - *Caminho*: `src/Module02/SmartRouter/`
  - *Executar & Testar*:
    - Minimal API: `dotnet run --project src/Module02/SmartRouter/src/SmartRouter.Gateway`
    - Suíte de Testes: `dotnet test src/Module02/SmartRouter/SmartRouter.slnx`
  - *Escopo*: ASP.NET Core Minimal API em C# encapsulando um `SmartRoutingChatClient` herdando de `DelegatingChatClient`. O cliente avalia requisições dinamicamente: queries curtas e sensíveis a custo são roteadas para um tier econômico (ex.: OpenRouter / Ollama); em caso de erros de rede, timeouts ou acionamento do circuit breaker, o failover resiliente redireciona chamadas automaticamente para o tier premium de alta disponibilidade (ex.: Azure OpenAI / OpenAI). Inclui streaming SSE e diagnósticos de saúde (health checks).

---

### Módulo 03: LangChain em C# (LangChain.NET) vs. Ecossistema Oficial da Microsoft: Revisão Crítica e Engenharia Comparativa
- **Contexto & Objetivos**: Avaliação rigorosa de engenharia do ecossistema LangChain em .NET (`LangChain.NET` da comunidade tryAGI); mapeamento conceitual de *Prompts*, *Chains*, *Memory*, *Tools* e *Agents* para as abstrações canônicas da Microsoft (`Microsoft.Extensions.AI`, `Semantic Kernel` e `Microsoft Agent Framework`); análise aprofundada de trade-offs arquiteturais, limitações e riscos na adoção de ports comunitários do LangChain em produção (violação de convenções idiomáticas do .NET e princípios SOLID, risco de governança e abandonware, falta de SLAs corporativos, leaky abstractions, overhead de alocação de heap/GC, ausência de integração nativa com OpenTelemetry/.NET Aspire e suporte a Native AOT); matriz de decisão: quando considerar LangChain para prototipagem rápida e por que a tríade oficial da Microsoft deve ser priorizada para produção corporativa.
- **Abstrações & Frameworks**: `LangChain` (tryAGI), `Microsoft.Extensions.AI` (`IChatClient`, `DelegatingChatClient`), `Microsoft.SemanticKernel`, `Microsoft.Agents.AI`, `System.Diagnostics.DiagnosticSource` / `ActivitySource`.
- **Princípios & Padrões**: Interface Segregation Principle (ISP), Dependency Inversion Principle (DIP), Decorator Pattern vs. Monolithic Chains, Padrão de Benchmark & Análise Comparativa, Twelve-Factor Agent: Fator 1 (Lógica Determinística vs Modelo Estocástico) e Fator 8 (Observabilidade Nativa).
- **Referências do Microsoft Learn**:
  - [Visão Geral de IA em .NET](https://learn.microsoft.com/dotnet/ai/)
  - [Abstrações Unificadas com Microsoft.Extensions.AI](https://learn.microsoft.com/dotnet/ai/ichatclient)
  - [Conceitos do Semantic Kernel e Migração de Frameworks](https://learn.microsoft.com/semantic-kernel/overview/)
- **Capstone Project 03**:
  - *Nome*: `FrameworkComparison.Benchmarker`
  - *Caminho*: `src/Module03/FrameworkComparison/`
  - *Executar & Testar*:
    - CLI Comparativa: `dotnet run --project src/Module03/FrameworkComparison/src/FrameworkComparison.Cli`
    - Suíte de Testes: `dotnet test src/Module03/FrameworkComparison/FrameworkComparison.slnx`
  - *Escopo*: Aplicação de benchmark arquitetural e de performance executando a mesma carga de trabalho corporativa (triagem de pedidos com prompt estruturado, pipeline de validação e instrumentação de telemetria) utilizando duas implementações distintas lado a lado: `LangChain.NET` vs. `Microsoft.Extensions.AI`. Gera relatórios comparativos em CLI e Markdown avaliando: tempo de execução, alocação de memória (alocações GC Gen0/Gen1/Gen2 via `GC.GetAllocatedBytesForCurrentThread`), profundidade do call stack, cobertura de tracing OpenTelemetry e conformidade com a Injeção de Dependência do .NET.

---

### Módulo 04: Sessões de Usuário, Histórico Resiliente e Gerenciamento de Memória de Agentes
- **Contexto & Objetivos**: Arquitetura de gerenciamento de estado para agentes conversacionais e sistemas de chat; separação estrita entre working memory de curto prazo e memória episódica de longo prazo; estratégias de compactação de contexto, sliding windows com contagem exata de tokens e sumarização periódica em segundo plano; garantia de agentes 100% stateless persistidos em backing stores externos.
- **Abstrações & Frameworks**: `Microsoft.Extensions.Caching.Distributed`, `StackExchange.Redis`, `System.Text.Json`, `Microsoft.Extensions.AI` (`ChatMessage`, `ChatRole`).
- **Princípios & Padrões**: Repository Pattern, Padrão Outbox/Event-Driven para consolidação de memória, Twelve-Factor: Fator VI (Processos Stateless), Twelve-Factor Agent: Fator 2 (Runtime de Agente Stateless).
- **Referências do Microsoft Learn**:
  - [Gerenciamento de Conversação e Sessão no Agent Framework](https://learn.microsoft.com/agent-framework/concepts/agents/conversations/session)
  - [Distributed Caching no ASP.NET Core](https://learn.microsoft.com/aspnet/core/performance/caching/distributed)
- **Capstone Project 04**:
  - *Nome*: `ResilientMemory.Core`
  - *Caminho*: `src/Module04/ResilientMemory/`
  - *Escopo*: Serviço multitenant de gerenciamento de sessões conversacionais. Emprega um pipeline em segundo plano monitorando os limites de tokens da sessão no Redis: ao atingir 75% da capacidade de contexto do modelo, dispara um job assíncrono de sumarização para condensar turnos mais antigos, preservando a fluidez conversacional, a identidade do usuário e mantendo os custos de prompt delimitados.

---

### Módulo 05: RAG Corporativo: Arquitetura Avançada, Busca Híbrida, GraphRAG e Evals
- **Contexto & Objetivos**: Superando as armadilhas do *Naive RAG*; parsing de documentos corporativos complexos (PDFs com tabelas financeiras, Markdown hierárquico); métodos avançados de chunking (Semantic Chunking, Parent-Document Retriever, Sentence-Window); **Hybrid Search** unindo busca vetorial densa com busca lexical esparsa (BM25/Full-Text) através de Reciprocal Rank Fusion (RRF); **Re-Ranking** com Cross-Encoders para redução de ruído e filtragem de contexto; princípios de **GraphRAG** (Microsoft Research) com extração de grafos de entidades e sumarização de comunidades; avaliação da Tríade de RAG (*Context Relevance*, *Groundedness / Faithfulness*, *Answer Relevance*) utilizando `Microsoft.Extensions.AI.Evaluation`.
- **Abstrações & Frameworks**: `IEmbeddingGenerator<TInput, TEmbedding>`, `Microsoft.Extensions.AI.Evaluation` (`GroundednessEvaluator`, `RelevanceEvaluator`, `RetrievalEvaluator`), `Microsoft.SemanticKernel.Connectors.Qdrant` / `AzureAISearch`, `Testcontainers`.
- **Princípios & Padrões**: Pipeline Pattern, Strategy Pattern para recuperação híbrida, Avaliação Contínua (CI/CD para IA), Twelve-Factor Agent: Fator 9 (Testabilidade & Suítes de Avaliação).
- **Referências do Microsoft Learn**:
  - [As bibliotecas Microsoft.Extensions.AI.Evaluation](https://learn.microsoft.com/dotnet/ai/evaluation/libraries)
  - [Avaliando Groundedness e Segurança em .NET](https://learn.microsoft.com/dotnet/ai/evaluation/evaluate-safety)
  - [Conectores de Vector Store no Semantic Kernel](https://learn.microsoft.com/semantic-kernel/concepts/vector-store-connectors/)
  - [Visão Geral de GraphRAG da Microsoft Research](https://learn.microsoft.com/azure/developer/ai/intro-graphrag)
- **Capstone Project 05**:
  - *Nome*: `EnterpriseKnowledge.AdvancedRag`
  - *Caminho*: `src/Module05/EnterpriseKnowledge/`
  - *Escopo*: Mecanismo corporativo de RAG de nível de produção sobre documentação técnica complexa. Realiza ingestão de documentos hierárquicos (Parent-Child), executa busca híbrida (densa + esparsa) com fusão RRF, aplica um modelo de Cross-Encoder para reordenar as 5 passagens mais relevantes e sintetiza respostas com citações verificadas. Acompanhado por suítes de testes automatizados com `Microsoft.Extensions.AI.Evaluation` para pontuar groundedness e reprovar builds em caso de alucinação.

---

### Módulo 06: IA Local Soberana com Ollama vs. Cloud: Análise de Trade-offs e Estratégia Híbrida
- **Contexto & Objetivos**: Executar LLMs de código aberto locais (Phi-3/4, Llama 3, DeepSeek) via Ollama com integração nativa em .NET; benchmarking comparativo: privacidade estrita de dados e latência local vs. concorrência e capacidade computacional em nuvem; design de arquitetura híbrida (local-first com escalonamento transparente para a nuvem).
- **Abstrações & Frameworks**: `Microsoft.Extensions.AI.Ollama`, API do Ollama, Docker.
- **Princípios & Padrões**: Liskov Substitution Principle (LSP - alternância entre Ollama e Azure sem violar regras de domínio), Interface Segregation.
- **Referências do Microsoft Learn**:
  - [Utilizando um Ollama Chat Client em .NET](https://learn.microsoft.com/dotnet/ai/ichatclient#use-an-ollama-chat-client)
- **Capstone Project 06**:
  - *Nome*: `HybridLocalCloud.Engine`
  - *Caminho*: `src/Module06/HybridLocalCloud/`
  - *Escopo*: Mecanismo de processamento de documentos executado localmente no Ollama (`phi-4` ou `llama3.2`). Quando uma tarefa demanda raciocínio avançado que excede o hardware local, a aplicação solicita aprovação e despacha dados higienizados para provedores em nuvem, gerando um relatório comparativo de telemetria (VRAM/RAM vs tokens faturados).

---

### Módulo 07: Engenharia Avançada de Prompts, Notações Estruturadas (JSON/YAML/TON) e Multimodalidade
- **Contexto & Objetivos**:
  - Técnicas de metaprompting, exemplos Few-Shot, Chain-of-Thought (CoT) e separação estrita de papéis (roles) em mensagens de sistema e de usuário;
  - **Arquitetura de Instruções Estruturadas**: Comparação rigorosa entre Prosa Livre vs Markdown vs Tags XML vs Schemas Estruturados (JSON & YAML);
  - **Token Object Notation (TON)**: Fundamentos de TON como uma notação compacta de dados projetada para maximizar a densidade de informação para LLMs, eliminando delimitadores e colchetes redundantes, reduzindo o uso de tokens em 30%–40% enquanto preserva a hierarquia e a tipagem forte;
  - **Aderência a Restrições Negativas (Negative Constraint Adherence)**: Como formatos estruturados (JSON/YAML/TON) mitigam o desvio de atenção e reforçam a obediência estrita a invariantes de negócio e limites de segurança;
  - **Structured Outputs em .NET**: Geração determinística de saída com `ChatResponseFormat.ForJsonSchema<T>`, validação estrita de schema com `System.Text.Json.Schema` e DTOs fortemente tipados em C#;
  - **Multimodalidade**: Análise multimodal combinando texto, entradas de imagem, transcrição speech-to-text (Whisper) e visão computacional.
- **Abstrações & Frameworks**: `ChatResponseFormat.ForJsonSchema<T>`, `System.Text.Json.Schema`, Azure AI Speech SDK, serializadores customizados de TON/YAML para C#.
- **Princípios & Padrões**: Type Safety, Data Transfer Objects (DTOs) Fortemente Tipados, Twelve-Factor Agent: Fator 4 (I/O Estruturado & Formatos TON/JSON).
- **Referências do Microsoft Learn**:
  - [Saída Estruturada com IChatClient](https://learn.microsoft.com/dotnet/ai/ichatclient#structured-output)
  - [Saídas Estruturadas com Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/how-to/structured-outputs)
- **Capstone Project 07**:
  - *Nome*: `PromptArchitectAndTriage.Service`
  - *Caminho*: `src/Module07/PromptArchitect/`
  - *Escopo*: Serviço de triagem de sinistros corporativos que consome múltiplas entradas (áudios de clientes via Whisper, fotos de evidências via modelos de visão) e gera um relatório pericial de sinistro validado contra um C# `record SinistroReport(...)`. Inclui um benchmark automatizado comparando a execução do System Prompt em Prosa, JSON, YAML e TON, reportando: tokens consumidos, latência e taxa de conformidade em 10 restrições complexas.

---

### Módulo 08: Governança, Contratos de Uso, Privacidade e Zero Data Retention
- **Contexto & Objetivos**: Análise aprofundada dos termos de serviço de provedores (OpenAI Enterprise, Azure OpenAI Data & Privacy, Termos Comerciais da Anthropic); auditoria de trânsito de dados, políticas de retenção efêmera e opt-out de treinamento com dados de clientes (Zero Data Retention / HIPAA / LGPD / GDPR).
- **Abstrações & Frameworks**: Chaves Gerenciadas pelo Cliente do Azure OpenAI (CMK), endpoints privados em Virtual Network (VNet), padrões de DLP (Data Loss Prevention).
- **Princípios & Padrões**: Privacy by Design, Arquitetura Zero Trust, Twelve-Factor: Fator X (Paridade de Segurança Dev/Prod).
- **Referências do Microsoft Learn**:
  - [Dados, Privacidade e Segurança para Azure OpenAI](https://learn.microsoft.com/legal/cognitive-services/openai/data-privacy)
  - [Linha de Base de Segurança do Azure para Serviços de IA](https://learn.microsoft.com/azure/ai-services/openai/concepts/security-baseline)
- **Capstone Project 08**:
  - *Nome*: `DataPrivacyAuditor.Tool`
  - *Caminho*: `src/Module08/DataPrivacyAuditor/`
  - *Escopo*: Ferramenta de auditoria de conformidade que intercepta chamadas de IA via middleware HTTP, inspecionando cabeçalhos de resposta (verificando flags de conformidade de não-retenção), validando que dados sensíveis trafeguem apenas por endpoints e regiões autorizadas, e publicando um relatório de conformidade do Azure Trust Center.

---

### Módulo 09: Observabilidade Transversal, FinOps de Tokens e Dashboards com OpenTelemetry
- **Contexto & Objetivos**: Telemetria ponta a ponta com OpenTelemetry (Métricas, Logs Estruturados, Distributed Traces de GenAI); rastreamento de consumo de tokens (prompt, completion), latência por modelo, contagem de sessões e volume de usuários; exportação de telemetria para o painel do .NET Aspire, Prometheus/Grafana ou Azure Monitor.
- **Abstrações & Frameworks**: `OpenTelemetry`, `Microsoft.Extensions.AI` (`UseOpenTelemetry`), .NET Aspire, `System.Diagnostics.Activity`.
- **Princípios & Padrões**: Observabilidade como Código (Observability as Code), Twelve-Factor: Fator XI (Logs como Fluxos), Twelve-Factor Agent: Fator 8 (Observabilidade Abrangente & Rastreabilidade).
- **Referências do Microsoft Learn**:
  - [Telemetria e Métricas em IChatClient](https://learn.microsoft.com/dotnet/ai/ichatclient#telemetry)
  - [Telemetria no .NET Aspire](https://learn.microsoft.com/dotnet/aspire/fundamentals/telemetry)
- **Capstone Project 09**:
  - *Nome*: `GenAiObservability.Dashboard`
  - *Caminho*: `src/Module09/GenAiObservability/`
  - *Escopo*: Sistema distribuído orquestrado com .NET Aspire utilizando `client.AsBuilder().UseOpenTelemetry().Build()`. Exibe todas as interações com LLMs no Aspire Dashboard, custos acumulados por tenant/usuário, taxas de erro, traces de invocações em cascata de ferramentas (tools) e alertas automatizados de orçamento de FinOps quando limites de gastos diários são atingidos.

---

### Módulo 10: Segurança Ofensiva e Defensiva: OWASP Top 10 for LLMs, Prompt Injection e Guardrails
- **Contexto & Objetivos**: Ameaças clássicas (Direct/Indirect Prompt Injection, Jailbreaking, System Prompt Extraction, Insecure Output Handling); higienização e isolamento estrito de contexto entre prompts de sistema e entradas não confiáveis do usuário; moderação de conteúdo e guardrails programáticos.
- **Abstrações & Frameworks**: Azure AI Content Safety SDK, mecanismos de Guardrails em C#, pré-validadores Semânticos e por Regex.
- **Princípios & Padrões**: Defesa em Profundidade (Defense in Depth), Padrões à Prova de Falhas (Fail-Safe Defaults), Twelve-Factor Agent: Fator 5 (Guardrails Determinísticos vs LLMs Estocásticos).
- **Referências do Microsoft Learn**:
  - [Visão Geral do Azure AI Content Safety](https://learn.microsoft.com/azure/ai-services/content-safety/overview)
  - [Filtragem de Conteúdo no Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/concepts/content-filter)
- **Capstone Project 10**:
  - *Nome*: `AiFirewall.Middleware`
  - *Caminho*: `src/Module10/AiFirewall/`
  - *Escopo*: `DelegatingChatClient` customizado operando como um Web Application Firewall (WAF) para IA. Faz varredura de mensagens recebidas contra assinaturas conhecidas de prompt injection, valida payloads contra a API do Azure Content Safety e intercepta respostas enviadas para mascarar/redigir chaves de API vazadas ou informações de identificação pessoal (PII).

---

### Módulo 11: Machine Learning Clássico com ML.NET: Modelos Preditivos e Hibridização com GenAI
- **Contexto & Objetivos**: Ingestão de dados e pipelines (`IDataView`), treinamento, validação e inferência inteiramente em C# sem runtimes de Python; algoritmos de regressão, classificação multiclasse e detecção de anomalias em logs e documentos; implantação de modelos ML.NET como roteadores de intenção rápidos e econômicos antes da invocação de LLMs.
- **Abstrações & Frameworks**: `Microsoft.ML`, `MLContext`, `ITransformer`, `PredictionEnginePool`.
- **Princípios & Padrões**: Data Pipeline Pattern, Padrão de Pré-filtragem (Early Termination Pattern).
- **Referências do Microsoft Learn**:
  - [Documentação Oficial do ML.NET](https://learn.microsoft.com/dotnet/machine-learning/)
  - [Tutoriais de Modelos Preditivos com ML.NET](https://learn.microsoft.com/dotnet/machine-learning/tutorials/predict-prices)
- **Capstone Project 11**:
  - *Nome*: `SmartSupportTriage.Hybrid`
  - *Caminho*: `src/Module11/SmartSupportTriage/`
  - *Escopo*: Pipeline de triagem de tickets de suporte ao cliente: um modelo on-premises treinado com ML.NET prevê a categoria e a severidade do ticket em microssegundos. Problemas padrão recebem respostas determinísticas pré-elaboradas; tickets complexos ou anômalos são enriquecidos com contexto e escalados para o pipeline de LLM para resolução profunda.

---

### Módulo 12: Extensibilidade com Model Context Protocol (MCP) em .NET
- **Contexto & Objetivos**: O Model Context Protocol (MCP) como um padrão aberto de interoperabilidade para conectar LLMs a bancos de dados corporativos, ferramentas e APIs internas; construção de servidores e clientes MCP nativos em C#; injeção dinâmica de ferramentas em tempo de execução nos pipelines de chat.
- **Abstrações & Frameworks**: Protocolo MCP (JSON-RPC / SSE / stdio), Chamada de Ferramentas / Invocação de Funções de `Microsoft.Extensions.AI`, SDKs de cliente/servidor MCP em C#.
- **Princípios & Padrões**: Adapter Pattern, Inversão de Controle (IoC), Twelve-Factor Agent: Fator 6 (Abstração de Ferramentas & MCP).
- **Referências do Microsoft Learn**:
  - [Ferramentas e Integrações no Agent Framework](https://learn.microsoft.com/agent-framework/agents/tools/)
  - [Invocação de Funções e Ferramentas com IChatClient](https://learn.microsoft.com/dotnet/ai/ichatclient#tool-calling)
- **Capstone Project 12**:
  - *Nome*: `EnterpriseMcpServer.Connector`
  - *Caminho*: `src/Module12/EnterpriseMcpServer/`
  - *Escopo*: Servidor MCP corporativo em .NET expondo recursos de banco de dados SQL e operações de API REST via schemas padronizados. Seguido por um cliente C# utilizando `IChatClient` que consome as ferramentas via SSE, permitindo que a LLM execute consultas analíticas seguras e auditadas com proteção.

---

### Módulo 13: Agentes de IA com Microsoft Agent Framework (MAF), Semantic Kernel e Declarative Agents
- **Contexto & Objetivos**:
  - Definição formal de um Agente (Persona, Ferramentas, Memória, Tomada de Decisão Autônoma);
  - O ecossistema do **Microsoft Agent Framework** (`Microsoft.Agents.AI`) e interoperabilidade com `Microsoft.SemanticKernel.Agents`;
  - **Agentes Declarativos (Declarative Agents)**: Modelagem de agentes seguindo o **Declarative Agent Manifest (especificações em JSON Schema / YAML / TON)** da Microsoft, desacoplando com clareza as especificações comportamentais da lógica de execução em C#;
  - Ciclos de vida de agentes, isolamento de threads e padrões de **Harness Agent** (planejamento autônomo, backlogs de tarefas, compactação de contexto e autorização de ferramentas);
  - Aplicação de governança corporativa com **Human-in-the-Loop (HITL)** para operações sensíveis.
- **Abstrações & Frameworks**: `Microsoft.Agents.AI` (`AIAgent`, `AIProjectClient`), `Microsoft.SemanticKernel.Agents`, Schemas de Manifestos Declarativos (JSON/YAML/TON).
- **Princípios & Padrões**: Padrão de Agente Autônomo, Human-in-the-Loop (HITL), Padrão de Especificação Declarativa, Twelve-Factor Agent: Fator 11 (Human-in-the-Loop & Approval Gates) e Fator 12 (Especificações Declarativas).
- **Referências do Microsoft Learn**:
  - [Visão Geral do Microsoft Agent Framework](https://learn.microsoft.com/agent-framework/overview/)
  - [Conceitos de Harness Agent](https://learn.microsoft.com/agent-framework/concepts/harness)
  - [Schema do Manifesto de Agente Declarativo da Microsoft](https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8)
- **Capstone Project 13**:
  - *Nome*: `AutonomousDevAssistant.Agent`
  - *Caminho*: `src/Module13/AutonomousDevAssistant/`
  - *Escopo*: Agente desenvolvedor inteligente cuja persona, ferramentas e políticas de governança são carregadas dinamicamente a partir de um manifesto declarativo (JSON/YAML/TON). O agente recebe solicitações de engenharia em linguagem natural, constrói planos de execução em memória, inspeciona repositórios e edita arquivos de código via MCP, pausando o runtime de execução para exigir confirmação explícita do desenvolvedor antes de operações de alto risco (ex.: git commit, deployment).

---

### Módulo 14: Orquestração Multiagente Avançada: Workflows em Grafo, Máquinas de Estado e Execução Paralela/Sequencial
- **Contexto & Objetivos**:
  - **Governança Determinística Multiagente**: Superando o "Agent Slop", loops infinitos de raciocínio e desvio de prompt (prompt drift) em sistemas multiagente ao substituir supervisores de prompt não estruturados por grafos de estados explícitos e matematicamente delimitados;
  - **O Paradigma StateFlow (COLM 2024)**: Desacoplando o **Process Grounding** (navegação determinística de estados, lógica de transição, limites de terminação de loop) da **Resolução de Subtarefas (Sub-task Solving)** (geração localizada por LLM dentro dos nós);
  - **Statecharts de David Harel (1987)**: Modelagem de topologias multiagente utilizando **Superestados Hierárquicos (OR-states)** para evitar explosão combinatória de estados, **Regiões Ortogonais (AND-states)** para execução paralela concorrente (fan-out/fan-in) com sincronização por barreira, e **Estados de Histórico ($H$)**;
  - **Verificação de Grafos com MetaAgent (ICML 2025)**: Validação estática de topologias de máquinas de estado em C# para detectar deadlocks, estados inalcançáveis e armadilhas cíclicas (cyclic sink traps) antes da execução em runtime;
  - **Isolamento de Estado & Higienização de Memória**: Prevenção de contaminação cruzada de contexto entre agentes e alucinações em cascata utilizando `IResettableExecutor` no Microsoft Agent Framework;
  - **Sagas Distribuídas**: Persistência de workflows de longa duração com MassTransit Saga State Machines e Redis, suportando checkpoints duráveis de Human-in-the-Loop.
- **Abstrações & Frameworks**: `Microsoft.Agents.AI.Workflows`, `Stateless` (Máquinas de Estado Hierárquicas em .NET), `Microsoft.Extensions.AI`, `IResettableExecutor`, `MassTransit` (Saga State Machines), `System.Diagnostics.ActivitySource`.
- **Princípios & Padrões**: Finite State Machine (FSM) & Hierarchical Statecharts (Harel), Paradigma StateFlow (COLM 2024), Saga Pattern com Ações Compensatórias, Directed Acyclic Graph (DAG), Padrão Barrier / Fan-Out/Fan-In, Twelve-Factor Agent: Fator 1 (Plano de Controle Determinístico), Fator 3 (Transições de Estado por Grafo e Event-Driven) e Fator 11 (Approval Gates com Human-in-the-Loop).
- **Referências Acadêmicas & da Literatura**:
  - [StateFlow: Enhancing LLM Task-Solving through State-Driven Workflows (COLM 2024)](https://arxiv.org/abs/2403.11322)
  - [MetaAgent: Auto-Constructing FSM-based Multi-Agent Systems (ICML 2025)](https://arxiv.org/abs/2410.03816)
  - [Statecharts: A Visual Formalism for Complex Systems (David Harel, 1987)](https://www.sciencedirect.com/science/article/pii/0167642387900359)
  - [Practical UML Statecharts in C/C++: Event-Driven Programming (Miro Samek)](https://www.state-machine.com/psicc2)
- **Referências do Microsoft Learn**:
  - [Isolamento de Estado em Workflows do MAF](https://learn.microsoft.com/agent-framework/concepts/workflows/state)
  - [Orquestração Magentic no Agent Framework](https://learn.microsoft.com/agent-framework/workflows/orchestrations/magentic)
  - [Workflow Builders no Microsoft Agent Framework](https://learn.microsoft.com/agent-framework/workflows/)
- **Guia de Estudos Detalhado**:
  - *Localização*: [`docs/modules/module-14-multi-agent-orchestration-and-state-machines/STUDY_GUIDE.md`](docs/modules/module-14-multi-agent-orchestration-and-state-machines/STUDY_GUIDE.md)
- **Capstone Projects 14**:
  - *Projeto 14.1 (Projeto Inicial de Workflow)*: `EmailApprovalWorkflow.StateMachine`
    - *Caminho*: `src/Module14/EmailApprovalWorkflow/`
    - *Executar & Testar*: `dotnet run --project src/Module14/EmailApprovalWorkflow/src/EmailApprovalWorkflow.Cli`
    - *Escopo*: Workflow fundamental com agente único implementando o paradigma StateFlow com `Stateless` e `Microsoft.Extensions.AI`. Demonstra estados e triggers fortemente tipados (`Drafting`, `AwaitingHumanApproval`, `Dispatching`) com transições protegidas (`PermitIf`), garantindo matematicamente que ações destrutivas não sejam executadas sem aprovação humana explícita.
  - *Projeto 14.2 (Projeto Avançado Multiagente Corporativo)*: `EnterpriseAudit.MultiAgentWorkflow`
    - *Caminho*: `src/Module14/EnterpriseAudit/`
    - *Executar & Testar*:
      - CLI do Orquestrador: `dotnet run --project src/Module14/EnterpriseAudit/src/EnterpriseAudit.Cli`
      - Suíte de Testes: `dotnet test src/Module14/EnterpriseAudit/EnterpriseAudit.slnx`
    - *Escopo*: Orquestrador de statechart hierárquico orientado a StateFlow em C# (.NET 10). Executa uma auditoria de conformidade corporativa através de 3 agentes especializados: *Regulations Researcher*, *Financial Data Analyst* e *Compliance Auditor*. A pesquisa paralela é executada dentro de uma região ortogonal (AND-state) com sincronização por barreira; discrepâncias disparam estados condicionais de remediação delimitados por um contador máximo de transições (prevenindo loops infinitos); sign-offs finais destrutivos exigem um gate de aprovação obrigatório com Human-in-the-Loop com isolamento de estado entre sessões concorrentes.

---

### Módulo 15: Design by Contract (DbC) para Agentes Autônomos em C#
- **Contexto & Objetivos**:
  - Adaptação dos princípios clássicos de **Design by Contract (DbC)** de Bertrand Meyer para arquiteturas de Agentes de IA;
  - Decomposição formal de instruções: **Pré-condições (Preconditions)** (validação de entradas e estado inicial), **Invariantes (Invariants)** (regras estritas de negócio que o agente nunca deve violar) e **Pós-condições / Critérios de Aceitação (Postconditions / Acceptance Criteria)** (*Definition of Done* determinística);
  - Parsing e compilação de contratos declarativos a partir de arquivos Markdown com Frontmatter (`*.agent.md`) utilizando `Markdig` e `YamlDotNet` em records de contrato fortemente tipados em C#;
  - Mecanismo determinístico de validação de pós-condições e loops de autocorreção autônoma (*Self-Correction / Retry Loops*) sempre que as saídas do LLM violarem os critérios de aceitação.
- **Abstrações & Frameworks**: `Markdig` (com `UseYamlFrontMatter`), `YamlDotNet`, `System.Text.Json.Schema`, `Microsoft.Extensions.AI`.
- **Princípios & Padrões**: Design by Contract (DbC), Liskov Substitution Principle (LSP), Open/Closed Principle (OCP), Twelve-Factor Agent: Fator 1 (Lógica Determinística vs Modelo Estocástico) e Fator 5 (Guardrails Determinísticos).
- **Referências do Microsoft Learn**:
  - [Extensibilidade e Injeção de Dependência em .NET](https://learn.microsoft.com/dotnet/core/extensions/dependency-injection)
  - [Conceitos de Validação e Harness Agent](https://learn.microsoft.com/agent-framework/concepts/harness)
- **Capstone Projects 15**:
  - *Projeto 15.1*: `DbcContractParser.Core` — Biblioteca e CLI que faz o parsing de arquivos `*.agent.md`, validando a sintaxe de pré-condições, invariantes e critérios de aceitação em objetos `record AgentContract(...)` fortemente tipados.
  - *Projeto 15.2*: `ContractEnforcer.Runner` — Agente de análise jurídica e tributária cuja execução é delimitada por validação determinística de pós-condições. Se o LLM alucinar ou omitir uma cláusula obrigatória exigida pelo contrato em Markdown, o runtime rejeita a conclusão e reexecuta o passo, injetando a violação contratual como feedback corretivo.

---

### Módulo 16: Grand Master Capstone — A Plataforma Agêntica Corporativa
- **Contexto & Objetivos**:
  - Convergência definitiva de **TODAS as disciplinas do currículo (Módulos 01 a 15)** em uma plataforma corporativa pronta para produção (*Production-Ready Enterprise Platform*);
  - Arquitetura e implementação de uma **Plataforma de Agentes Autônomos** em C# .NET que atua como host agnóstico de microsserviços de IA para toda a organização;
  - Suporte a Hot-reload e Multi-tenancy: publique e atualize agentes em produção simplesmente adicionando novos arquivos de contrato `*.agent.md` ou manifestos de grafo `*.workflow.md` a repositórios Git monitorados, sem necessidade de recompilar código C#;
  - Integração de infraestrutura completa de ponta a ponta:
    - Gateway unificado com resiliência via Polly (Módulos 1 e 2);
    - Análise comparativa de frameworks e benchmarks de performance (Módulo 3);
    - Sessões resilientes de usuário e gerenciamento de memória em Redis (Módulo 4);
    - RAG Híbrido Corporativo com GraphRAG e Evals de Groundedness (Módulo 5);
    - Implantação híbrida com Ollama local + Azure/OpenRouter em nuvem (Módulo 6);
    - Otimização de tokens com notação TON e Saídas Estruturadas (Módulo 7);
    - Auditoria de privacidade de dados e conformidade com Zero Data Retention (Módulo 8);
    - Observabilidade abrangente com OpenTelemetry no painel do .NET Aspire (Módulo 9);
    - WAF para IA e defesa contra Prompt Injection (Módulo 10);
    - Pré-filtragem preditiva com ML.NET (Módulo 11);
    - Ferramentas distribuídas dinamicamente via Model Context Protocol (Módulo 12);
    - Orquestração de agentes MAF e workflows em grafo (Módulos 13 e 14);
    - Governança contratual estrita via Design by Contract (Módulo 15).
- **Abstrações & Frameworks**: Stack completa da plataforma (`Microsoft.Agents.AI`, `Microsoft.Extensions.AI`, `Microsoft.Extensions.AI.Evaluation`, `OpenTelemetry`, `Polly`, `.NET Aspire`, `ML.NET`, `MCP`, `StackExchange.Redis`, `Markdig`).
- **Princípios & Padrões**: The Twelve-Factor App & The Twelve-Factor Agent, Clean Architecture / DDD, Enterprise Integration Patterns, Arquitetura Zero Trust.
- **Capstone Project 16 (Grand Finale Capstone)**:
  - *Nome*: `EnterpriseAgenticPlatform.Host`
  - *Caminho*: `src/Module16/EnterpriseAgenticPlatform/`
  - *Escopo*: A plataforma definitiva de IA corporativa em .NET. Uma solução distribuída orquestrada com .NET Aspire que provisiona um cluster de execução de agentes, disponibiliza um portal web para métricas de FinOps e auditorias de contratos, hospeda um catálogo corporativo de ferramentas MCP e executa workflows de negócio complexos (ex.: *Automated Supplier Onboarding* abrangendo auditorias jurídica, tributária e de segurança) orientados 100% por contratos declarativos em Markdown com garantias matemáticas e determinísticas de conformidade.

---

## 2. Como Utilizar este Repositório

Cada módulo acima inclui limites e metadados claramente definidos para que você possa segui-lo como uma trilha de aprendizagem iterativa e no seu próprio ritmo:

1. **Geração do Guia de Estudos e Especificação**: Utilize o **Meta-Prompt na Seção 3** para gerar uma especificação em Markdown dedicada em `docs/modules/module-XX-<nome>/STUDY_GUIDE.md` para o módulo escolhido. Esse guia fornece teoria aprofundada, checkpoints cognitivos e a especificação arquitetural completa para o capstone project.
2. **Revisão e Validação de Checkpoints**: Leia o guia de estudos gerado, explore os links recomendados do Microsoft Learn e valide cada checkpoint conceitual antes de escrever código.
3. **Construção do Capstone Project**: Siga a especificação arquitetural do guia para implementar o projeto em C# (.NET 10 LTS) dentro do diretório modular correspondente em `src/ModuleXX/<ProjectName>` (por exemplo: `src/Module01/AiProviderBenchmarker/`, `src/Module02/SmartRouter/`). Quaisquer projetos suplementares ou demonstrações didáticas rápidas também devem ser localizados dentro do diretório de seu respectivo módulo (ex.: `src/Module01/SimpleChatDemo/`).
4. **Melhoria Contínua**: Cada capstone project implementa de forma independente testes unitários/integração automatizados, instrumentação de observabilidade e boas práticas de engenharia de software de maneira incremental.

---

## 3. Meta-Prompt: Gerador de Guias de Estudo e Especificações Arquiteturais

Copie e envie o prompt abaixo para sua LLM (ou execute-o dentro desta mesma sessão de IA), especificando o módulo desejado (por exemplo: `"Execute o Meta-Prompt para o Módulo 01"`).

A LLM gerará um guia abrangente em Markdown em `docs/modules/module-XX-<nome>/STUDY_GUIDE.md`, servindo como seu material didático e especificação de engenharia para aquele módulo.

````markdown
# SYSTEM PROMPT: SENIOR SOFTWARE ARCHITECT & AI INSTRUCTOR (.NET / C#)

## ROLE AND OBJECTIVE
Você é um Arquiteto de Software Sênior e Especialista em Inteligência Artificial no ecossistema .NET.
Sua missão é ler o programa de um módulo específico do repositório **MafMastery (README.md)** e gerar um documento Markdown abrangente, exaustivo e tecnicamente rigoroso em:
`docs/modules/module-{{MODULE_NUMBER}}-{{MODULE_NAME}}/STUDY_GUIDE.md`

Este documento NÃO deve conter o código final do projeto implementado, mas sim:
1. Material aprofundado de estudo teórico;
2. Checkpoints cognitivos de autoavaliação;
3. A especificação técnica e arquitetural completa para orientar o desenvolvimento do Capstone Project do módulo.

---

## DESIGN AND ENGINEERING GUIDELINES
Todo o conteúdo deve refletir os quatro pilares do MafMastery:
- **Clean Architecture & DDD**: Separação estrita de responsabilidades (Domain, Application, Infrastructure, Presentation).
- **SOLID Principles**: Demonstrações concretas de como SRP, OCP, LSP, ISP e DIP são aplicados aos componentes de IA neste módulo.
- **Design Patterns Clássicos**: Identificação e especificação de padrões aplicados (ex.: Decorator via DelegatingChatClient, Strategy, Factory, Adapter via MCP, Saga/DAG).
- **The Twelve-Factor App & The Twelve-Factor Agent**: Adoção prática de fatores relevantes (Stateless Runtime, I/O Estruturado com TON/JSON, Backing Services, Observabilidade como Código, Guardrails Determinísticos, Design by Contract).
- **Tecnologia Alvo**: .NET 10 (LTS) e C# moderno, priorizando abstrações oficiais da Microsoft (`Microsoft.Extensions.AI`, `Microsoft.Agents.AI`, `Microsoft.Extensions.AI.Evaluation`, `OpenTelemetry`, etc.).

---

## ESTRUTURA OBRIGATÓRIA DE `STUDY_GUIDE.md`

O documento gerado deve seguir estritamente o seguinte roteiro estruturado:

### # Module {{NUMBER}}: {{MODULE NAME}} — Guia de Estudos e Especificação de Engenharia

#### 1. Visão Geral e Objetivos de Aprendizagem
- Resumo executivo do desafio real de mercado resolvido por este módulo.
- Habilidades práticas de engenharia adquiridas após a conclusão.

#### 2. Fundamentos Teóricos Aprofundados
- Explicação conceitual exaustiva de cada tópico do programa.
- Mergulho profundo nos aspectos internos do runtime .NET e mecânicas de invocação de IA (alocação de memória, concorrência assíncrona com `Task`/`IAsyncEnumerable`, pipelines de streaming de tokens).
- Trade-offs técnicos, vantagens, desvantagens e armadilhas comuns em produção (*Gotchas & Anti-patterns*).

#### 3. Mapeamento de Princípios Arquiteturais e Padrões
- **SOLID neste Módulo**: Tabela ou lista detalhada indicando onde cada um dos 5 princípios atua.
- **Design Patterns Aplicados**: Padrões selecionados e sua justificativa arquitetural.
- **Twelve-Factor App & Agent**: Fatores específicos atendidos e diretrizes de implementação.
- **Diagrama Arquitetural**: Diagrama conceitual em Mermaid (`graph TD` ou `sequenceDiagram`) ilustrando interações entre o domínio, o pipeline de IA e serviços externos.

#### 4. Checkpoints Cognitivos de Aprendizagem
- Lista de 5 a 8 questões conceituais e cenários arquiteturais, completos com gabarito fundamentado para autoavaliação prévia à escrita do código.

#### 5. Leituras Recomendadas & Fundamentação no Microsoft Learn
- Lista curada de links oficiais do Microsoft Learn (documentação de APIs, guias arquiteturais e pacotes NuGet oficiais).

#### 6. Especificação Técnica do Capstone Project
- **Project Name**: Nome padronizado do projeto conforme definido no README.
- **Solution Path**: Caminho padronizado sob o diretório do módulo: `src/Module{{NUMBER}}/{{PROJECT_NAME}}/`.
- **Scope & Business Problem**: Caso de uso corporativo simulado.
- **Functional Requirements (FRs)**: Lista numerada (FR-01, FR-02...) definindo as capacidades exigidas.
- **Non-Functional Requirements (NFRs)**: Restrições de latência, resiliência, observabilidade, desacoplamento e alocação de memória.
- **Project and Directory Structure (Clean Architecture)**:
  - Exemplo: `Domain`, `Application`, `Infrastructure`, `Presentation` sob `src/Module{{NUMBER}}/{{PROJECT_NAME}}/`.
- **Core Interface Contracts and Entities**:
  - Código C# demonstrando apenas contratos fundamentais (interfaces, records, DTOs e assinaturas de métodos), sem implementações de lógica de negócio concreta.
- **Acceptance Criteria & Definition of Done (DoD)**:
  - Checklist formal para considerar o projeto concluído.
- **Minimum Testing Plan**:
  - Cenários de testes unitários obrigatórios (mocking com xUnit/Moq/NSubstitute) e requisitos de testes de integração.

#### 7. Roteiro Passo a Passo de Construção
- Sequência lógica ordenada (Passo 1 ao Passo N) orientando o desenvolvedor a construir o software de forma incremental e testável, incluindo comandos explícitos de terminal para inicialização do projeto, execução (`dotnet run --project ...`) e testes (`dotnet test ...`).
````
