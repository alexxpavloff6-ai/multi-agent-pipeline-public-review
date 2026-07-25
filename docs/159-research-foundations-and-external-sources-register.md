# Исследовательские основания и реестр внешней литературы

> **Примечание к публикационной копии.** Внешние источники и связи с
> включёнными документами сохранены. Ссылки на закрытую память, рабочие RUN,
> код и документы вне публикационного комплекта заменены текстовыми
> указателями; соответствующие закрытые файлы не опубликованы.

**Дата среза:** 25 июля 2026 года

**Состояние:** доказательный указатель; не подтверждение истинности каждого внешнего утверждения

**Связанные документы:** [сравнение с Orca](59-orca-comparison.md), [сравнение с oh-my-pi](68-oh-my-pi-comparison.md), критическая оценка многооболочечной схемы, стандарт доказательности.

## 1. Назначение

Документ отвечает на три вопроса:

1. где сохранены исследования Orca и oh-my-pi/OMP;
2. какие внешние публикации, инструкции, репозитории, оценки и обсуждения использовались при разработке;
3. какой доказательный вес допустимо придавать источникам разных видов.

Полная история изучения и замечания о границах каждого источника остаются в `memory/SOURCES.md`. Настоящий файл — самостоятельный указатель для чтения и профессионального обсуждения. Адрес самого публикационного репозитория намеренно исключён из библиографии, поскольку не является внешним основанием проекта.

## 2. Где находятся оценки Orca и OMP

| Предмет | Основной документ | Решение | Источники | Что вошло в проект |
|---|---|---|---|---|
| Orca от Stably AI | [документ 59](59-orca-comparison.md), 22 413 байт, `sha256:e28e51680191020af96ecbfad8e7203fb63f2945c675934e44045ed2ac5dd7e2` | D-215 | S-401–S-418 | внешнее подтверждение детерминированного ядра; уроки по жизненному циклу процессов, аутентификации и изоляции; отдельные идеи точек решения и контроля устаревшего основания |
| oh-my-pi, команда OMP | [документ 68](68-oh-my-pi-comparison.md), 30 756 байт, `sha256:57f97c800a692e04736dc53f2ce5411156d0b18a257fa71f5b484e981940e485` | D-232 | S-701–S-717 | третье внешнее подтверждение детерминированного ядра; уроки по сокращению системного задания, обязательным одобрениям и человеку в контуре; отложенные идеи свёртки контекста и ветвления |

Оба исследования являются сравнением принципов, а не доказательством превосходства текущего проекта. Orca и oh-my-pi решают задачи программирования, тогда как проект ориентирован на доказательные аналитические работы. Их опыт подтверждает отдельные инженерные решения, но не доказывает гипотезу о росте качества от конкретной тройки моделей и оболочек.

## 3. Правила доказательного веса

| Вид источника | Допустимое использование | Что запрещено выводить автоматически |
|---|---|---|
| Рецензированная работа | основание для общего механизма или измеренной закономерности в пределах опыта | перенос результата на другую модель, оболочку, домен и версию без проверки |
| Препринт | рабочая гипотеза и описание опыта с обязательным учётом ограничений | отраслевой стандарт или окончательно установленный факт |
| Официальная инструкция | поведение конкретной версии продукта, интерфейса или поставщика | независимую оценку качества собственного продукта поставщика |
| Исходный код | прямое подтверждение реализованного механизма в исследованной редакции | гарантию поведения будущей версии или полной системы вне прочитанного пути |
| Сообщение об ошибке | существование наблюдаемого случая и материал для воспроизведения | частоту дефекта во всей совокупности пользователей |
| Независимая оценка или набор данных | сравнительный сигнал при известной методике | качество точной связки «модель + поставщик + оболочка + настройки + договор» |
| Блог и обсуждение | поиск рисков, альтернатив и пользовательских симптомов | архитектурное решение без первичного подтверждения |

## 4. Ключевое ядро литературы

### 4.1. Влияние агентной оболочки

- [Harness-Bench](https://arxiv.org/html/2605.27922v1) — измеряет взаимодействие модели и оболочки; основание считать точную связку единицей оценки, а не переносить показатель модели автоматически.
- [Rethinking Harness Evolution](https://arxiv.org/abs/2607.12227) — показывает, что автоматическое усложнение оболочки не обязательно превосходит простые дополнительные попытки и плохо переносится на новые задания.
- [The Context Fails First](https://arxiv.org/abs/2607.14275) — поддерживает качество и структуру контекста как самостоятельный фактор, но не доказывает конкретную архитектуру проекта.
- [Agent-Reactive Bugs](https://arxiv.org/abs/2607.15684) — таксономия отказов на границе модели и оболочки; основание сохранять состояние «причина неизвестна».
- [Phantom Guardrails](https://arxiv.org/abs/2607.13083) — основание не закреплять постоянное правило без доказанного сбоя.

### 4.2. Разные модели, проверяющие и маршрутизация

- [Rethinking Mixture-of-Agents](https://arxiv.org/abs/2502.00674) — сильный контраргумент против общего тезиса «разные модели всегда лучше одной сильной».
- [Single-agent or Multi-agent?](https://arxiv.org/abs/2505.18286) — преимущество многоагентной схемы сокращается с усилением одиночной модели.
- [Small LMs Need Strong Verifiers](https://aclanthology.org/2024.findings-acl.924.pdf) — основание асимметрии «исполнитель + сильный проверяющий».
- [Selection Bottleneck](https://arxiv.org/html/2603.20324) — качество отбора ограничивает пользу от множества кандидатов.
- [Weak-to-Strong Generalization](https://arxiv.org/abs/2312.09390) — концептуальная опора для проверки слабого исполнителя более сильной моделью.
- [RouteLLM](https://arxiv.org/abs/2406.18665) и [FrugalGPT](https://arxiv.org/abs/2305.05176) — основания для маршрутизации по сложности, а не постоянного назначения одной модели на все случаи.
- [Diversity Empowers Intelligence](https://openreview.net/pdf?id=cKlzKs3Nnb) — связывает пользу разнообразия с различием ошибок, а не с числом агентов само по себе.

### 4.3. Управление, безопасность и отказы

- [Anthropic: Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) — внешняя инженерная опора детерминированного управления потоком.
- [Why Do Multi-Agent LLM Systems Fail?](https://arxiv.org/abs/2503.13657) — таксономия режимов отказа многоагентных систем.
- [Setup Complete, Now You Are Compromised](https://arxiv.org/abs/2607.15143) — безопасность установки зависит от пары модели и оболочки.
- [Coercion and Deception](https://arxiv.org/abs/2607.15434) — поддерживает честное состояние отказа вместо ложного сообщения об успехе.
- [Load-Bearing Evidence](https://arxiv.org/abs/2607.12469) — поддерживает восстанавливаемость доказательной цепочки, но не заменяет проверку истинности.

### 4.4. Внешние системы

- [Orca](https://github.com/stablyai/orca) — практический внешний пример детерминированного координатора над готовыми агентными оболочками.
- [oh-my-pi](https://github.com/can1357/oh-my-pi) и [The harness problem](https://blog.can.ac/2026/02/12/the-harness-problem/) — внешний пример конечного автомата оболочки, управления контекстом и связанных рисков.
- [Многоагентная исследовательская система Anthropic](https://www.anthropic.com/engineering/multi-agent-research-system) — пример асимметрии ведущей и более быстрой вспомогательной моделей; не доказательство точной связки проекта.

## 5. Как читать полный указатель

В приложении перечислены 202 уникальных внешних адреса из канонического реестра проекта. Идентификатор S-* связывает адрес с описанием степени изучения в `memory/SOURCES.md`. Одна ссылка может иметь несколько идентификаторов, если использовалась в разных исследованиях.

Классификация выполняет навигационную функцию. Она не заменяет чтение методики конкретной работы. Доступность адресов и текущие версии в этом шаге повторно не проверялись.

## Приложение А. Полный указатель внешних источников

### А.1. Исследовательские публикации

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 1 | aclanthology.org | — | [ссылка](https://aclanthology.org/2024.findings-acl.924.pdf`tS-310`tSmall LMs Need Strong Verifiers (ACL 2024 Findings)) |
| 2 | aclanthology.org | — | [ссылка](https://aclanthology.org/2025.naacl-long.12/`tS-621`truMTEB — русские эмбеддинги) |
| 3 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2305.05176`tS-876,S-881`tДоказательная история замысла и развития проекта / Основания приложения о низовом слое Hermes) |
| 4 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2312.09390`tS-312`tBurns et al. — Weak-to-Strong Generalization (ICML 2024)) |
| 5 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2406.04692`tS-325`tMixture-of-Agents оригинал (Wang et al., ICLR 2025)) |
| 6 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2406.18665`tS-876,S-881`tДоказательная история замысла и развития проекта / Основания приложения о низовом слое Hermes) |
| 7 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2410.05229`tS-614`tGSM-Symbolic — ненадёжность LLM в расчётах) |
| 8 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2501.16794`tS-652`tNLLP 2024 — автоматическая консолидация) |
| 9 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2502.00674`tS-306,S-881`tLi et al. — Rethinking Mixture-of-Agents (ICLR 2025) / Доказательная история замысла и развития проекта) |
| 10 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2503.13657`tS-881`tДоказательная история замысла и развития проекта) |
| 11 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2505.18286`tS-308`tGao et al. — Single-agent or Multi-agent?) |
| 12 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2510.06002`tS-634`tSAT-Graph RAG — темпоральный graph RAG) |
| 13 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2510.22369`tS-622`tGigaEmbeddings — SOTA на ruMTEB) |
| 14 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2605.27922`tS-881`tДоказательная история замысла и развития проекта) |
| 15 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.13643`tS-201`tRecursive Agent Harnesses) |
| 16 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.15874`tS-205`tLLM-as-Code) |
| 17 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.17454`tS-206`tDissecting model behavior through agent trajectories) |
| 18 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.19380`tS-207`tClayBuddy) |
| 19 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.19613`tS-204`tStaminaBench) |
| 20 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.21005`tS-210`tBuilding Agent Harnesses for Scientific Curation) |
| 21 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2606.25189`tS-211`tActPlane) |
| 22 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.00038`tS-209`tStop Hand-Holding Your Coding Agent) |
| 23 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.00053`tS-203`tSWE-Router) |
| 24 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.02598`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 25 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.06906`tS-208`tThe Harness Effect) |
| 26 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.08028`tS-202`tFrom Prompts to Contracts) |
| 27 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.08124`tS-212`tTest-Time Harness Evolution) |
| 28 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.11388`tS-849,S-876`tОснования приложения о низовом слое Hermes / Статьи arXiv W30 об агентных оболочках) |
| 29 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.11399`tS-849,S-876`tОснования приложения о низовом слое Hermes / Статьи arXiv W30 об агентных оболочках) |
| 30 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.11423`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 31 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.11698`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 32 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.12227`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 33 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.12469`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 34 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.12662`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 35 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.13034`tS-849,S-876`tОснования приложения о низовом слое Hermes / Статьи arXiv W30 об агентных оболочках) |
| 36 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.13083`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 37 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.13285`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 38 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.13396`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 39 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.13683`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 40 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.14004`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 41 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.14158`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 42 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.14159`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 43 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.14275`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 44 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.14336`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 45 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.15143`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 46 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.15434`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 47 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.15524`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 48 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.15557`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 49 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.15684`tS-849`tСтатьи arXiv W30 об агентных оболочках) |
| 50 | arxiv.org | — | [ссылка](https://arxiv.org/html/2506.09440v1`tS-663`tGigaChat 2 Max / 3 Ultra) |
| 51 | arxiv.org | — | [ссылка](https://arxiv.org/html/2508.17536v1`tS-313`tDebate or Vote (NeurIPS 2025 Spotlight)) |
| 52 | arxiv.org | — | [ссылка](https://arxiv.org/html/2509.23055v1`tS-314`tHow Sycophancy Shapes Multi-Agent Debate) |
| 53 | arxiv.org | — | [ссылка](https://arxiv.org/html/2603.20324`tS-311`tSelection Bottleneck in MAS Pipelines) |
| 54 | arxiv.org | — | [ссылка](https://arxiv.org/html/2604.02460v1`tS-307`tБюджетно-контролируемое сравнение single vs multi-agent) |
| 55 | arxiv.org | — | [ссылка](https://arxiv.org/html/2605.27922v1`tS-301`tHarness-Bench — измерение harness-эффекта) |
| 56 | arxiv.org | — | [ссылка](https://arxiv.org/pdf/2402.05120`tS-326`tMore Agents Is All You Need (TMLR)) |
| 57 | arxiv.org | — | [ссылка](https://arxiv.org/pdf/2406.18665`tS-315`tRouteLLM (ICLR 2025)) |
| 58 | arxiv.org | — | [ссылка](https://arxiv.org/pdf/2503.13657`tS-318`tWhy Do MAS Fail? (NeurIPS 2025)) |
| 59 | arxiv.org | — | [ссылка](https://arxiv.org/pdf/2607.09600`tS-501`tAgora — аукцион моделей с динамической калибровкой) |
| 60 | dho.stanford.edu | — | [ссылка](https://dho.stanford.edu/wp-content/uploads/Legal_RAG_Hallucinations.pdf`tS-613`tStanford HAI — галлюцинации legal-AI) |
| 61 | dialogue-conf.org | — | [ссылка](https://dialogue-conf.org/wp-content/uploads/2026/06/SadkovskiiFNasyrovaRSorokinA.087.pdf`tS-633`tRusHallu-RAG — детекция галлюцинаций (рус)) |
| 62 | openreview.net | — | [ссылка](https://openreview.net/forum?id=4FWAwZtd2n`tS-327`tSnell et al. — Scaling Test-Time Compute (ICLR 2025 Oral)) |
| 63 | openreview.net | — | [ссылка](https://openreview.net/pdf?id=cKlzKs3Nnb`tS-322`tDEI — Diversity Empowers Intelligence (ICLR 2025)) |
| 64 | scalingintelligence.stanford.edu | — | [ссылка](https://scalingintelligence.stanford.edu/pubs/weaver/`tS-309`tWeaver (NeurIPS 2025)) |

### А.2. Официальные инструкции, стандарты и сайты

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 65 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 66 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/api/create-chat-completion`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 67 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/quick_start/pricing/`tS-113`tОфициальные тарифы и ограничения DeepSeek) |
| 68 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/quick_start/pricing`tS-662`tDeepSeek V4 Pro) |
| 69 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/quick_start/rate_limit/`tS-113`tОфициальные тарифы и ограничения DeepSeek) |
| 70 | api.z.ai | — | [ссылка](https://api.z.ai/api/anthropic`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 71 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/cli-usage`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 72 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/corporate-proxy`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 73 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/devcontainer`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 74 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/env-vars`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 75 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/headless`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 76 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/installation`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 77 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/llm-gateway`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 78 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/third-party-integrations`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 79 | docs.anthropic.com | — | [ссылка](https://docs.anthropic.com/en/docs/claude-code/getting-started`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 80 | docs.docker.com | — | [ссылка](https://docs.docker.com/ai/sandboxes/security/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 81 | docs.docker.com | — | [ссылка](https://docs.docker.com/ai/sandboxes/security/credentials/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 82 | docs.docker.com | — | [ссылка](https://docs.docker.com/ai/sandboxes/security/isolation/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 83 | docs.docker.com | — | [ссылка](https://docs.docker.com/desktop/features/networking/networking-how-tos/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 84 | docs.docker.com | — | [ссылка](https://docs.docker.com/desktop/setup/install/windows-install/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 85 | docs.docker.com | — | [ссылка](https://docs.docker.com/engine/containers/run/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 86 | docs.docker.com | — | [ссылка](https://docs.docker.com/reference/cli/docker/container/run/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 87 | docs.docker.com | — | [ссылка](https://docs.docker.com/reference/cli/docker/container/run`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 88 | docs.docker.com | — | [ссылка](https://docs.docker.com/reference/cli/docker/network/create/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 89 | docs.z.ai | — | [ссылка](https://docs.z.ai/devpack/latest-model`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 90 | docs.z.ai | — | [ссылка](https://docs.z.ai/devpack/tool/claude`tS-213,S-889`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology / Установка и первоначальная настройка прототипа R0) |
| 91 | docs.z.ai | — | [ссылка](https://docs.z.ai/devpack/tool/others`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 92 | docs.z.ai | — | [ссылка](https://docs.z.ai/guides/overview/pricing`tS-112`tОфициальные тарифы и статистика Z.ai) |
| 93 | git-scm.com | — | [ссылка](https://git-scm.com/download/win`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 94 | hermes-agent.nousresearch.com | — | [ссылка](https://hermes-agent.nousresearch.com/docs/getting-started/installation/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 95 | hermes-agent.nousresearch.com | — | [ссылка](https://hermes-agent.nousresearch.com/docs/user-guide/profiles/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 96 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/docs/agent-configuration/agents-md`tS-884`tПаспорта пяти основных частей продукта) |
| 97 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/docs/app`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 98 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/docs/config-file/config-basic`tS-884`tПаспорта пяти основных частей продукта) |
| 99 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/guides/best-practices.md`tS-884`tПаспорта пяти основных частей продукта) |
| 100 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/single-agent-multiple-agents`tS-317`tMicrosoft Learn — Single-agent or Multi-agent) |
| 101 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.localaccounts/new-localuser`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 102 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.localaccounts/remove-localuser`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 103 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/powershell/module/netsecurity/new-netfirewallrule`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 104 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/rules`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 105 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/troubleshooting-uwp-firewall`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 106 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-updateprocthreadattribute`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 107 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/api/userenv/nf-userenv-createappcontainerprofile`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 108 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/api/winbase/nf-winbase-createprocesswithlogonw`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 109 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/fwp/filtering-conditions-available-at-each-filtering-layer`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 110 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/fwp/monitoring-filter-changes`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 111 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/procthread/job-objects`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 112 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/secauthz/createprocessinsandbox`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 113 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/secauthz/implementing-an-appcontainer`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 114 | linear.app | — | [ссылка](https://linear.app/changelog/2026-03-24-introducing-linear-agent`tS-641`tLinear Agent — публичная бета) |
| 115 | macaron.im | — | [ссылка](https://macaron.im/blog/deepseek-v4-benchmarks`tS-662`tDeepSeek V4 Pro) |
| 116 | martinfowler.com | — | [ссылка](https://martinfowler.com/articles/bitemporal-history.html`tS-653`tMartin Fowler — Bitemporal History) |
| 117 | martinfowler.com | — | [ссылка](https://martinfowler.com/articles/harness-engineering.html`tS-103`tMartin Fowler — направляющие механизмы и обратная связь) |
| 118 | openai.com | — | [ссылка](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/`tS-876,S-881`tДоказательная история замысла и развития проекта / Основания приложения о низовом слое Hermes) |
| 119 | openai.com | — | [ссылка](https://openai.com/index/harness-engineering/`tS-101`tOpenAI — проектирование оболочки Codex) |
| 120 | openrouter.ai | — | [ссылка](https://openrouter.ai/rankings`tS-506`tOpenRouter Rankings — реальное использование через API) |
| 121 | platform.claude.com | — | [ссылка](https://platform.claude.com/docs/en/api/messages/count_tokens`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 122 | platform.claude.com | — | [ссылка](https://platform.claude.com/docs/en/api/messages/create`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 123 | platform.claude.com | — | [ссылка](https://platform.claude.com/docs/en/build-with-claude/citations`tS-632`tAnthropic Citations API) |
| 124 | satgate.io | — | [ссылка](https://satgate.io/ai-agent-cost-control`tS-321`tSatGate — AI Agent Cost Control) |
| 125 | vercel.com | — | [ссылка](https://vercel.com/go/vercel-d0-agent`tS-110`tVercel — сокращение набора инструментов) |
| 126 | www.anthropic.com | — | [ссылка](https://www.anthropic.com/engineering/building-effective-agents`tS-316,S-881`tAnthropic — Building Effective Agents / Доказательная история замысла и развития проекта) |
| 127 | www.anthropic.com | — | [ссылка](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents`tS-102`tAnthropic — длительно работающие агенты) |
| 128 | www.anthropic.com | — | [ссылка](https://www.anthropic.com/engineering/multi-agent-research-system`tS-876`tОснования приложения о низовом слое Hermes) |
| 129 | www.atlassian.com | — | [ссылка](https://www.atlassian.com/blog/announcements/atlassian-rovo-mcp-ga`tS-642`tAtlassian Rovo MCP — GA) |
| 130 | www.databricks.com | — | [ссылка](https://www.databricks.com/blog/ai-harness`tS-108`tDatabricks — определение агентной оболочки) |
| 131 | www.langchain.com | — | [ссылка](https://www.langchain.com/blog/improving-deep-agents-with-harness-engineering`tS-105,S-303`tLangChain — Terminal-Bench 2.0 и системный промпт / LangChain — измеримое влияние оболочки) |
| 132 | www.oasis-open.org | — | [ссылка](https://www.oasis-open.org/standard/akn-v1-0/`tS-651`tAkoma Ntoso (OASIS) — стандарт правовых документов) |
| 133 | www.openproject.org | — | [ссылка](https://www.openproject.org/docs/user-guide/gantt-chart/gantt-chart-faq/`tS-643`tOpenProject Gantt FAQ — отсутствие CPM) |
| 134 | www.postgresql.org | — | [ссылка](https://www.postgresql.org/docs/19/ddl-temporal-tables.html`tS-654`tPostgreSQL Temporal Tables) |
| 135 | www.python.org | — | [ссылка](https://www.python.org/downloads/windows/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 136 | www.sberbank.ru | — | [ссылка](https://www.sberbank.ru/en/press_center/all/article?newsID=2f4dadd5-df7a-44d5-a68f-8be655c81249`tS-663`tGigaChat 2 Max / 3 Ultra) |
| 137 | www.solo.io | — | [ссылка](https://www.solo.io/blog/building-real-time-ai-cost-controls-with-agentgateway`tS-320`tSolo.io — Real-Time AI Cost Controls with agentgateway) |
| 138 | www.stackai.com | — | [ссылка](https://www.stackai.com/blog/llm-leaderboard-which-llms-are-best-for-which-tasks`tS-504`tStackAI Leaderboard — ранжирование по real-world use cases) |
| 139 | www.tbench.ai | — | [ссылка](https://www.tbench.ai/leaderboard/terminal-bench/2.0?models=Claude+Opus+4.7%2CClaude+Opus+4.6`tS-109`tTerminal-Bench 2.0) |
| 140 | www.trychroma.com | — | [ссылка](https://www.trychroma.com/research/context-rot`tS-104`tChroma — деградация длинного контекста) |
| 141 | www.vellum.ai | — | [ссылка](https://www.vellum.ai/llm-leaderboard`tS-503`tVellum LLM Leaderboard — бенчмарки по типам задач) |
| 142 | www.ycombinator.com | — | [ссылка](https://www.ycombinator.com/companies/stably-ai-orca`tS-418`tYC-страница Stably AI) |
| 143 | zcode.z.ai | — | [ссылка](https://zcode.z.ai/cn/docs/usage-stats`tS-112`tОфициальные тарифы и статистика Z.ai) |

### А.3. Репозитории, исходный код и внешние проекты

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 144 | blog.can.ac | — | [ссылка](https://blog.can.ac/2026/02/12/the-harness-problem/`tS-713`tБлог автора «The harness problem») |
| 145 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi/blob/main/CONTRIBUTING.md`tS-712`tVouch-система) |
| 146 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi`tS-701`tРепозиторий oh-my-pi) |
| 147 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/examples/extensions/plan-mode/README.md`tS-709`tPlan Mode) |
| 148 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/examples/extensions/sandbox/index.ts`tS-706`tSandbox) |
| 149 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/src/core/agent-session.ts`tS-705`tCompaction) |
| 150 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/src/core/tools/bash.ts`tS-707`tBash-инструмент) |
| 151 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/pi/packages/agent/docs/agent-harness.md`tS-703`tАрхитектура AgentHarness (наследие Pi)) |
| 152 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/pi/packages/agent/src/agent-loop.ts`tS-704`tЦикл agentLoop) |
| 153 | github.com | — | [ссылка](https://github.com/irlcode/RusLawOD/`tS-603`tRusLawOD — открытый корпус НПА РФ) |
| 154 | github.com | — | [ссылка](https://github.com/nicobailon/pi-subagents`tS-708`tSubagents (расширение)) |
| 155 | github.com | — | [ссылка](https://github.com/nousresearch/hermes-agent/blob/main/tools/code_execution_tool.py`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 156 | github.com | — | [ссылка](https://github.com/nousresearch/hermes-agent/blob/main/website/docs/developer-guide/model-provider-plugin.md`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 157 | github.com | — | [ссылка](https://github.com/nousresearch/hermes-agent/blob/main/website/docs/developer-guide/programmatic-integration.md`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 158 | github.com | — | [ссылка](https://github.com/NVIDIA/RULER`tS-612`tRULER — реальная длина контекста) |
| 159 | github.com | — | [ссылка](https://github.com/openai/agents.md`tS-111`tОткрытый формат AGENTS.md) |
| 160 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/docs/droid-orchestration-group.md`tS-409`tДизайн-док маршрутизации Orca) |
| 161 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/pty-exhaustion-agent-session-leak.md`tS-410`tДокумент об утечке PTY (P0)) |
| 162 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/skill-guides/orchestration.md`tS-408`tДокументация оркестрации Orca) |
| 163 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/coordinator.ts`tS-402`tЯдро оркестрации Orca — coordinator.ts) |
| 164 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/db.ts`tS-406`tСлой SQLite Orca — db.ts) |
| 165 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/groups.ts`tS-404`tГрупповая маршрутизация Orca — groups.ts) |
| 166 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/lifecycle-reconciliation.ts`tS-405`tLifecycle-полномочия Orca) |
| 167 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/types.ts`tS-403`tТипы и роли Orca — types.ts) |
| 168 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/shared/tui-agent-config.ts`tS-407`tКаталог поддерживаемых агентов Orca) |
| 169 | github.com | — | [ссылка](https://github.com/stablyai/orca`tS-401`tРепозиторий Orca) |
| 170 | omp.sh | — | [ссылка](https://omp.sh/`tS-702`tСайт oh-my-pi) |

### А.4. Оценки, наборы данных и измерительные материалы

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 171 | artificialanalysis.ai | — | [ссылка](https://artificialanalysis.ai/`tS-502,S-661`tArtificial Analysis — независимые лидерборды / Artificial Analysis — Парето-фронты моделей) |
| 172 | artificialanalysis.ai | — | [ссылка](https://artificialanalysis.ai/evaluations/omniscience`tS-611`tAA-Omniscience — галлюцинации моделей) |
| 173 | chat.chatbotarena.com`ts-507`tvellum chatbot arena — слепое голосование людей | — | [ссылка](https://chat.chatbotarena.com`tS-507`tVellum Chatbot Arena — слепое голосование людей) |
| 174 | docs.ragas.io | — | [ссылка](https://docs.ragas.io/`tS-631`tRAGAS — метрики RAG) |
| 175 | huggingface.co | — | [ссылка](https://huggingface.co/datasets/FractalGPT/RRNCBFinalPublic`tS-623`tRRNCB — российский RAG-бенчмарк по нормативке) |
| 176 | lexometrica.com | — | [ссылка](https://lexometrica.com/bench/`tS-602`tLexometrica Ground Truth — РФ-право) |
| 177 | llm-stats.com | — | [ссылка](https://llm-stats.com/benchmarks`tS-508`tllm-stats.com — технические бенчмарки) |
| 178 | mera.a-ai.ru | — | [ссылка](https://mera.a-ai.ru/en`tS-601`tMERA — русскоязычный бенчмарк) |
| 179 | www.synopticonresearch.com | — | [ссылка](https://www.synopticonresearch.com/articles/harness-effect/`tS-302`tSynopticon Research — The Harness Moves the Score) |

### А.5. Сообщения об ошибках и обсуждения

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 180 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi/issues/1734`tS-711`tРаздутый системный промпт (issue #1734)) |
| 181 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi/issues/3293`tS-710`tБезопасность — отсутствие одобрений (issue #3293)) |
| 182 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/1099`tS-413`tТоп feature-запрос — multi-repo (issue #1099)) |
| 183 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/5370`tS-411`t«Война токенов» Codex (issue #5370)) |
| 184 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/6144`tS-415`tЛагающий скролл терминала (issue #6144)) |
| 185 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/6234`tS-412`tРе-аутентификация Claude (issue #6234)) |
| 186 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/6364`tS-416`tПастинг картинок в Remote Host (issue #6364)) |
| 187 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/8539`tS-414`tБлокировка рендерера на 87 секунд (issue #8539)) |

### А.6. Вторичный анализ и обсуждения

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 188 | addyosmani.com | — | [ссылка](https://addyosmani.com/blog/agent-harness-engineering/`tS-106`tAddy Osmani — обзор проектирования агентных оболочек) |
| 189 | cobusgreyling.medium.com | — | [ссылка](https://cobusgreyling.medium.com/the-harness-model-relationship-ab285a8992a7`tS-304`tCobus Greyling — Agent = Model + Harness) |
| 190 | galileo.ai | — | [ссылка](https://galileo.ai/blog/multi-agent-ai-failures-prevention`tS-323`tGalileo AI — Multi-Agent AI Failures Prevention) |
| 191 | ianlpaterson.com | — | [ссылка](https://ianlpaterson.com/blog/llm-benchmark-2026-38-actual-tasks-15-models-for-2-29/`tS-505`t38 Real Tasks Benchmark — реальные задачи, 15 моделей) |
| 192 | news.ycombinator.com | — | [ссылка](https://news.ycombinator.com/item?id=47143754`tS-714`tHackerNews — главный тред Pi/omp) |
| 193 | news.ycombinator.com | — | [ссылка](https://news.ycombinator.com/item?id=48849068`tS-715`tHackerNews — OMP-бот и vouch-критика) |
| 194 | news.ycombinator.com | — | [ссылка](https://news.ycombinator.com/item?id=48865001`tS-715`tHackerNews — OMP-бот и vouch-критика) |
| 195 | vibecodinghub.org | — | [ссылка](https://vibecodinghub.org/blog/orca-review`tS-417`tОбзор VibeCodingHub) |
| 196 | www.augmentcode.com | — | [ссылка](https://www.augmentcode.com/guides/multi-agent-cost-compounding`tS-319`tAugment Code — Multi-Agent Cost Compounding) |
| 197 | www.devclass.com | — | [ссылка](https://www.devclass.com/ai-ml/2025/11/27/ocaml-maintainers-reject-massive-ai-generated-pull-request/1728083`tS-717`tФактчек DWARF/OCaml) |
| 198 | www.mindstudio.ai | — | [ссылка](https://www.mindstudio.ai/blog/reliability-compounding-problem-ai-agent-stacks`tS-305`tMindStudio — reliability compounding) |
| 199 | www.philschmid.de | — | [ссылка](https://www.philschmid.de/agent-harness-2026`tS-107`tPhilipp Schmid — роль оболочки в 2026 году) |
| 200 | www.reddit.com | — | [ссылка](https://www.reddit.com/r/LocalLLaMA/comments/1umokm3/built_a_harness_for_myself_using_pi_selfhosted/`tS-716`tReddit — позитив low-level сообщества) |
| 201 | www.reddit.com | — | [ссылка](https://www.reddit.com/r/OnlyAICoding/comments/1ry7iyf/any_thoughts_about_ohmypi_coding_agent/`tS-716`tReddit — позитив low-level сообщества) |
| 202 | www.zartis.com | — | [ссылка](https://www.zartis.com/the-compounding-errors-problem-why-multi-agent-systems-fail-and-the-architecture-that-fixes-it/`tS-324`tZartis — Compounding Errors Problem) |

## 6. Ограничения реестра

1. Наличие адреса означает использование или рассмотрение источника, но не автоматическое принятие его выводов.
2. Большая часть публикаций 2026 года является препринтами и могла не пройти независимое рецензирование.
3. Показатели звёзд, версии, цены и доступность моделей меняются; они действительны только на дату соответствующего исследования.
4. Сообщения GitHub, Hacker News и Reddit используются для поиска воспроизводимых рисков, а не как статистика распространённости.
5. Рекомендации поставщиков полезны для настройки их продуктов, но не являются независимым сравнением качества.
6. Точная конфигурация проекта должна проверяться по D-150; библиография не заменяет опыт.

## 7. Статус

Документ не разрешает новый RUN, модельный или сетевой вызов и не меняет рабочую архитектуру. Он восстанавливает происхождение решений и служит основанием для отдельной формулировки проверяемой гипотезы о качестве многооболочечной многомодельной схемы.
