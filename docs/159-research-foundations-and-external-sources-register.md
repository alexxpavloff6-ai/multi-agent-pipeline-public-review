# Исследовательские основания и реестр внешней литературы

> **Обновление от 12 октября 2026 года.** По материалам еженедельного
> мониторинга внешних публикаций (июль — октябрь 2026) в приложение А.1
> приняты 158 статей arXiv с идентификаторами S-909–S-1066. Все они имеют
> статус рабочих гипотез: монитор рассматривал абстракты, а не полные
> тексты, и перенос выводов на связки проекта запрещён. Дубли блока W30
> (свод S-849 / S-876) повторно не вносились.

> **Примечание к публикационной копии.** Внешние источники и связи с
> включёнными документами сохранены. Ссылки на закрытую память, рабочие RUN,
> код и документы вне публикационного комплекта заменены текстовыми
> указателями; соответствующие закрытые файлы не опубликованы.

**Дата среза:** 25 июля 2026 года

**Обновлено:** 13 октября 2026 года

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

В приложении перечислены 366 уникальных внешних адресов из канонического реестра проекта. Идентификатор S-* связывает адрес с описанием степени изучения в `memory/SOURCES.md`. Одна ссылка может иметь несколько идентификаторов, если использовалась в разных исследованиях.

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
| 65 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.19899`tS-909`tСходимость ошибок усиленных моделей) |
| 66 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.21268`tS-910`tГейты и человек в контуре, экономическая теория) |
| 67 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.21920`tS-911`tПерекрёстная проверка в систематических обзорах) |
| 68 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.20216`tS-912`tОркестрация малых моделей, узкий домен) |
| 69 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.21419`tS-913`tКарточки свидетельств для слабой роли) |
| 70 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.21461`tS-914`tПроверка вынесена в отдельный контур) |
| 71 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.28576`tS-915`tПовторные попытки бьют рефлексию при равном бюджете) |
| 72 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.28871`tS-916`t46% зелёных проверок не различают дефект) |
| 73 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.28908`tS-917`tСамопроверка даёт почти ноль) |
| 74 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.28317`tS-918`tУверенность модели бесполезна для аудита) |
| 75 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.22448`tS-919`tДевять слоёв потери фактов) |
| 76 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.29433`tS-920`tПравило видно, но не применено) |
| 77 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.09553`tS-921`tСостав описания задачи решает успех следующей роли) |
| 78 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.02436`tS-922`tУровень модели доминирует над инструментами) |
| 79 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.02507`tS-923`tПубличный и скрытый ответ агента расходятся до 40%) |
| 80 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.19865`tS-924`tОтказы в документных операциях) |
| 81 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.22520`tS-925`tНавыки могут ухудшать агента) |
| 82 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.02514`tS-926`tНи один монитор не держит оба типа распределённой атаки) |
| 83 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.28802`tS-927`tТаксономия сбоя: модель или обвязка, 41 режим) |
| 84 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.28037`tS-928`tОценка результата и процесса вместе) |
| 85 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.22368`tS-929`tАудит вздутия оценок) |
| 86 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.27994`tS-930`tГраница применимости: открытые задачи) |
| 87 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.25890`tS-931`tАгентный контур OWASP) |
| 88 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.29167`tS-932`tПроисхождение памяти) |
| 89 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.29254`tS-933`tСпецификации инструментов ослабляют отказ) |
| 90 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2607.26922`tS-934`tДва вызова бьют пять агентов на слабой модели) |
| 91 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.00718`tS-935`tВраждебный текст идёт по конвейеру как доверенный) |
| 92 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.03836`tS-936`tКонтракт остановки и продолжения, пять каркасов его нарушают) |
| 93 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.04968`tS-937`tЭволюция обвязок без смены весов) |
| 94 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.06301`tS-938`tБенчмарк оптимизации обвязки) |
| 95 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.06477`tS-939`tАтака дробится на безобидные шаги) |
| 96 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.08654`tS-940`tСкаффолд, не интерфейс: разброс стоимости до 139 раз) |
| 97 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.12307`tS-941`tСильная модель строит обвязку для слабой без смены весов) |
| 98 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.08239`tS-942`tПодмена модели в записи переписывает 61–94% действий) |
| 99 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.14380`tS-943`tСогласованные точки отката контекста и окружения) |
| 100 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.13900`tS-944`tАгентные транзакции с гарантиями ACID) |
| 101 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.11274`tS-945`tБезопасность как контракт времени исполнения) |
| 102 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.10218`tS-946`tСамораспространяющиеся идеи между агентами) |
| 103 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.09096`tS-947`tБенчмарк эволюции обвязки) |
| 104 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.13560`tS-948`tМета-оптимизация обвязки) |
| 105 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.13951`tS-949`tКо-эволюция модели и обвязки с прослеживанием источника) |
| 106 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.13228`tS-950`tКомпоненты обвязки расходятся на общем состоянии) |
| 107 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.08793`tS-951`tЖизненный цикл навыков, четыре уровня доказательности) |
| 108 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.13867`tS-952`tОбвязка надёжного кодинг-агента) |
| 109 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.12895`tS-953`tДве копии одной модели со-отказывают на 90%) |
| 110 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.14927`tS-954`tМодель не выбирает окупаемый протокол) |
| 111 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.21208`tS-955`tПереносимость спецификаций между агентами) |
| 112 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.15089`tS-956`tПостоянные состояния и проверяемые переходы) |
| 113 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.17597`tS-957`tБенчмарк безопасности жизненного цикла обвязки) |
| 114 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.21101`tS-958`tМногоуровневый монитор безопасности) |
| 115 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.19013`tS-959`tОбновление обвязки ломает ранее надёжное поведение) |
| 116 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.20622`tS-960`tНавыки, хуки и промпты отделены от весов) |
| 117 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.15071`tS-961`tЭволюция обвязки) |
| 118 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.15763`tS-962`tОбвязка эволюционирует в продакшене) |
| 119 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.20169`tS-963`tСовместная эволюция задачи и обвязки) |
| 120 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.17528`tS-964`tОбучение агента без смены каркаса) |
| 121 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.16798`tS-965`tСреда для обучения обвязки) |
| 122 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.17393`tS-966`tОбучение обвязки по частям) |
| 123 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.17433`tS-967`tПодбор обвязки под задачу) |
| 124 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.26218`tS-968`tТа же модель, другая обвязка, другой результат) |
| 125 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.28264`tS-969`tРефлексия только агента-виновника, не всей команды) |
| 126 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27338`tS-970`tНесколько ролей внутри одной модели) |
| 127 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.28363`tS-971`tУлучшающие мутации не проходят проверку отката) |
| 128 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27808`tS-972`t90% провалов заканчивались ложным успехом) |
| 129 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27086`tS-973`tЧетыре контрактных объекта ответственности) |
| 130 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27299`tS-974`tСборка контекста повышает привилегии) |
| 131 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.25091`tS-975`tНавык описывает поведение, допустимость оставлена модели) |
| 132 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.25593`tS-976`tОбвязка чинится под задачу на лету) |
| 133 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.24804`tS-977`tЭволюция обвязки при замороженных весах) |
| 134 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27790`tS-978`tНайденные программы обвязки непрозрачны) |
| 135 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.23041`tS-979`tАвтоматическая подгонка обвязки) |
| 136 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27311`tS-980`tПроверка обвязки) |
| 137 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.28281`tS-981`tСравнение петель) |
| 138 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.23953`tS-982`tРазделение слоёв агентной инженерии) |
| 139 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.27969`tS-983`tОткрытый каркас агентов) |
| 140 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.23541`tS-984`tЦена взаимодействия) |
| 141 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.24794`tS-985`tОценка агентных систем) |
| 142 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.26530`tS-986`tЧеловек в контуре) |
| 143 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2608.28553`tS-987`tНаблюдаемость агента) |
| 144 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.04270`tS-988`tЧужой ревьюер против самопроверки) |
| 145 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.04518`tS-989`tОбвязка двигает результат сильнее рецепта обучения, перенос около нуля) |
| 146 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.05279`tS-990`tЗамена роли поднимает коммуникацию на 16–63%) |
| 147 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.00621`tS-991`tУправление и данные разведены) |
| 148 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.00050`tS-992`tПрогресс гейтится машинно проверяемыми доказательствами) |
| 149 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.03884`tS-993`tХуки рантайма компрометируют 7 из 7 обвязок) |
| 150 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.01481`tS-994`tНадстройка поверх обвязок, +52% в среднем) |
| 151 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.04280`tS-995`tБенчмарк эволюции обвязки и её забывание) |
| 152 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.01600`tS-996`tЖизненные циклы компонентов, ссылка дешевле рассуждения) |
| 153 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.03920`tS-997`tАрхитектуры, сохраняющие ценность) |
| 154 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.01222`tS-998`tПовышение привилегий через контекст) |
| 155 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.00453`tS-999`tНавыки) |
| 156 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.02094`tS-1000`tНавыки для нескольких агентов) |
| 157 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.04865`tS-1001`tСовместные навыки) |
| 158 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.11987`tS-1002`tРодная обвязка вендора не даёт средней выгоды) |
| 159 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.08472`tS-1003`tПолномочие живёт вне рабочей области) |
| 160 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.04665`tS-1004`tМонитор на хуках ловит взлом награды) |
| 161 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.08175`tS-1005`tГенерация правки и её сертификация разведены) |
| 162 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.11677`tS-1006`tДефект обвязки отделён от подгонки под модель) |
| 163 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.09646`tS-1007`tПоиск правки обвязки от сохранённых снимков) |
| 164 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.09134`tS-1008`tОбучение слабой модели на траекториях сильной ломает согласованность) |
| 165 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.12742`tS-1009`tЧестный потолок навыков на уровне шума) |
| 166 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.08919`tS-1010`tБыстрое текстовое состояние и медленное закрепление в политике) |
| 167 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.07247`tS-1011`tКогда остановить, а не как масштабировать) |
| 168 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.20804`tS-1012`tПокомпонентный замер обвязки, 176 конфигураций) |
| 169 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.14857`tS-1013`tПять модулей обвязки эволюционируют независимо и переносятся) |
| 170 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.20519`tS-1014`tСамоулучшение меряют в токенах, не только в качестве) |
| 171 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.20474`tS-1015`tВклад плана и выпускающего контроля разведены) |
| 172 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.19519`tS-1016`tНепрерывность живёт в обвязке, не в модели) |
| 173 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.15293`tS-1017`tАудит без пути к действию бесполезен) |
| 174 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.20625`tS-1018`tЗапись границ, инцидент становится регрессионным тестом) |
| 175 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.17320`tS-1019`tУгроза жила в памяти агентов до 46 часов) |
| 176 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.19759`tS-1020`tБольше агентов выигрывает только на длинных редких задачах) |
| 177 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.18304`tS-1021`tОткат мира, рефлексия сохраняется) |
| 178 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.15309`tS-1022`tАгенты замедляются) |
| 179 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.16268`tS-1023`tЛожное использование инструментов) |
| 180 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.20301`tS-1024`tПрофилирование агента) |
| 181 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.15983`tS-1025`tСреда сравнения агентов) |
| 182 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.22068`tS-1026`tКодинг-агент) |
| 183 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30813`tS-1027`tПересказ чужого убеждения не считается независимым подтверждением) |
| 184 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30734`tS-1028`tВклад стадий конвейера оценивается контрфактически) |
| 185 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30662`tS-1029`tАгент продолжает действовать после цели, нужен внешний контур) |
| 186 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30293`tS-1030`tКарточки инструментов подписаны оператором) |
| 187 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30967`tS-1031`tОбвязка оптимизируется по точности, безопасности и токенам сразу) |
| 188 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.31395`tS-1032`tКлюч-значение действий) |
| 189 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.31047`tS-1033`tДинамическое ветвление) |
| 190 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.31076`tS-1034`tЛестница абстракций) |
| 191 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.31590`tS-1035`tСреда агентов) |
| 192 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30289`tS-1036`tПамять не равноценна) |
| 193 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.31318`tS-1037`tЭксплуатация агента) |
| 194 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30383`tS-1038`tСовместный вред при раздельной маскировке) |
| 195 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.30604`tS-1039`tТрудная часть после поиска) |
| 196 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.38912`tS-1040`tОбвязка собирается из примитивов, не пишется заново) |
| 197 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.38147`tS-1041`tКонтроллер отдельно от воркеров, выигрыш зависит от модели) |
| 198 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.34017`tS-1042`tПроверка передачи без модели в пути, и ложные остановки валидатора) |
| 199 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.39228`tS-1043`tДетерминированный валидатор улик аудита) |
| 200 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.00948`tS-1044`tОбвязка эволюционирует при замороженной модели и переносится) |
| 201 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.39154`tS-1045`tГраф задач растёт по сигналам уверенности) |
| 202 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.26891`tS-1046`tМинимальная петля обходит отдельный слой памяти) |
| 203 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2609.38137`tS-1047`tОдна модель даёт заметно разную эффективность в разных обвязках; наборы насыщены) |
| 204 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.10961`tS-1048`tКонтракт ревью: разные пулы, урезанные права проверяющего) |
| 205 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.11464`tS-1049`tСчёт агента не сертифицирует судью) |
| 206 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.11678`tS-1050`tПовторные прогоны переворачивают 15–36% исходов) |
| 207 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.07625`tS-1051`tСостояние вынесено из разговора) |
| 208 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.12813`tS-1052`tМодель предлагает патч, верификатор принимает) |
| 209 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.07639`tS-1053`tАвто-approve поднимает успех атаки до 95,6%) |
| 210 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.07832`tS-1054`tАртефакты репозитория как исполнимые примитивы) |
| 211 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.11655`tS-1055`tЭволюция обвязки упирается в потолок, дальше веса) |
| 212 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.13025`tS-1056`tКо-эволюция эволюционера) |
| 213 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.10426`tS-1057`tТраектория ценна только под своей обвязкой) |
| 214 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.13494`tS-1058`tС ростом модели выигрыш кастомной обвязки схлопывается) |
| 215 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.09264`tS-1059`tИнъекция в общий файл правил) |
| 216 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.02616`tS-1060`tСамоэволюция оптимизатора без проверки по исполнению не улучшает результат) |
| 217 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.02920`tS-1061`tОбвязка эволюционирует против новых атак) |
| 218 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.10629`tS-1062`tОбвязка как единственная изменяемая поверхность, симуляция) |
| 219 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.11188`tS-1063`tДопуск в память решает детерминированная политика) |
| 220 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.09021`tS-1064`tНе каждый вызов требует фронтирной модели, чужой домен) |
| 221 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.10126`tS-1065`tСбои передачи, использования и проверки различаются по структуре связи) |
| 222 | arxiv.org | — | [ссылка](https://arxiv.org/abs/2610.11050`tS-1066`tСудьи-агенты плохо отличают выполненную задачу от нарушающей ограничения) |

### А.2. Официальные инструкции, стандарты и сайты

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 223 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 224 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/api/create-chat-completion`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 225 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/quick_start/pricing/`tS-113`tОфициальные тарифы и ограничения DeepSeek) |
| 226 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/quick_start/pricing`tS-662`tDeepSeek V4 Pro) |
| 227 | api-docs.deepseek.com | — | [ссылка](https://api-docs.deepseek.com/quick_start/rate_limit/`tS-113`tОфициальные тарифы и ограничения DeepSeek) |
| 228 | api.z.ai | — | [ссылка](https://api.z.ai/api/anthropic`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 229 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/cli-usage`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 230 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/corporate-proxy`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 231 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/devcontainer`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 232 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/env-vars`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 233 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/headless`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 234 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/installation`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 235 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/llm-gateway`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 236 | code.claude.com | — | [ссылка](https://code.claude.com/docs/en/third-party-integrations`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 237 | docs.anthropic.com | — | [ссылка](https://docs.anthropic.com/en/docs/claude-code/getting-started`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 238 | docs.docker.com | — | [ссылка](https://docs.docker.com/ai/sandboxes/security/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 239 | docs.docker.com | — | [ссылка](https://docs.docker.com/ai/sandboxes/security/credentials/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 240 | docs.docker.com | — | [ссылка](https://docs.docker.com/ai/sandboxes/security/isolation/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 241 | docs.docker.com | — | [ссылка](https://docs.docker.com/desktop/features/networking/networking-how-tos/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 242 | docs.docker.com | — | [ссылка](https://docs.docker.com/desktop/setup/install/windows-install/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 243 | docs.docker.com | — | [ссылка](https://docs.docker.com/engine/containers/run/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 244 | docs.docker.com | — | [ссылка](https://docs.docker.com/reference/cli/docker/container/run/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 245 | docs.docker.com | — | [ссылка](https://docs.docker.com/reference/cli/docker/container/run`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 246 | docs.docker.com | — | [ссылка](https://docs.docker.com/reference/cli/docker/network/create/`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 247 | docs.z.ai | — | [ссылка](https://docs.z.ai/devpack/latest-model`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 248 | docs.z.ai | — | [ссылка](https://docs.z.ai/devpack/tool/claude`tS-213,S-889`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology / Установка и первоначальная настройка прототипа R0) |
| 249 | docs.z.ai | — | [ссылка](https://docs.z.ai/devpack/tool/others`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 250 | docs.z.ai | — | [ссылка](https://docs.z.ai/guides/overview/pricing`tS-112`tОфициальные тарифы и статистика Z.ai) |
| 251 | git-scm.com | — | [ссылка](https://git-scm.com/download/win`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 252 | hermes-agent.nousresearch.com | — | [ссылка](https://hermes-agent.nousresearch.com/docs/getting-started/installation/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 253 | hermes-agent.nousresearch.com | — | [ссылка](https://hermes-agent.nousresearch.com/docs/user-guide/profiles/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 254 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/docs/agent-configuration/agents-md`tS-884`tПаспорта пяти основных частей продукта) |
| 255 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/docs/app`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 256 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/docs/config-file/config-basic`tS-884`tПаспорта пяти основных частей продукта) |
| 257 | learn.chatgpt.com | — | [ссылка](https://learn.chatgpt.com/guides/best-practices.md`tS-884`tПаспорта пяти основных частей продукта) |
| 258 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/single-agent-multiple-agents`tS-317`tMicrosoft Learn — Single-agent or Multi-agent) |
| 259 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.localaccounts/new-localuser`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 260 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.localaccounts/remove-localuser`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 261 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/powershell/module/netsecurity/new-netfirewallrule`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 262 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/rules`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 263 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/troubleshooting-uwp-firewall`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 264 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-updateprocthreadattribute`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 265 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/api/userenv/nf-userenv-createappcontainerprofile`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 266 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/api/winbase/nf-winbase-createprocesswithlogonw`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 267 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/fwp/filtering-conditions-available-at-each-filtering-layer`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 268 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/fwp/monitoring-filter-changes`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 269 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/procthread/job-objects`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 270 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/secauthz/createprocessinsandbox`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 271 | learn.microsoft.com | — | [ссылка](https://learn.microsoft.com/en-us/windows/win32/secauthz/implementing-an-appcontainer`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 272 | linear.app | — | [ссылка](https://linear.app/changelog/2026-03-24-introducing-linear-agent`tS-641`tLinear Agent — публичная бета) |
| 273 | macaron.im | — | [ссылка](https://macaron.im/blog/deepseek-v4-benchmarks`tS-662`tDeepSeek V4 Pro) |
| 274 | martinfowler.com | — | [ссылка](https://martinfowler.com/articles/bitemporal-history.html`tS-653`tMartin Fowler — Bitemporal History) |
| 275 | martinfowler.com | — | [ссылка](https://martinfowler.com/articles/harness-engineering.html`tS-103`tMartin Fowler — направляющие механизмы и обратная связь) |
| 276 | openai.com | — | [ссылка](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/`tS-876,S-881`tДоказательная история замысла и развития проекта / Основания приложения о низовом слое Hermes) |
| 277 | openai.com | — | [ссылка](https://openai.com/index/harness-engineering/`tS-101`tOpenAI — проектирование оболочки Codex) |
| 278 | openrouter.ai | — | [ссылка](https://openrouter.ai/rankings`tS-506`tOpenRouter Rankings — реальное использование через API) |
| 279 | platform.claude.com | — | [ссылка](https://platform.claude.com/docs/en/api/messages/count_tokens`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 280 | platform.claude.com | — | [ссылка](https://platform.claude.com/docs/en/api/messages/create`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 281 | platform.claude.com | — | [ссылка](https://platform.claude.com/docs/en/build-with-claude/citations`tS-632`tAnthropic Citations API) |
| 282 | satgate.io | — | [ссылка](https://satgate.io/ai-agent-cost-control`tS-321`tSatGate — AI Agent Cost Control) |
| 283 | vercel.com | — | [ссылка](https://vercel.com/go/vercel-d0-agent`tS-110`tVercel — сокращение набора инструментов) |
| 284 | www.anthropic.com | — | [ссылка](https://www.anthropic.com/engineering/building-effective-agents`tS-316,S-881`tAnthropic — Building Effective Agents / Доказательная история замысла и развития проекта) |
| 285 | www.anthropic.com | — | [ссылка](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents`tS-102`tAnthropic — длительно работающие агенты) |
| 286 | www.anthropic.com | — | [ссылка](https://www.anthropic.com/engineering/multi-agent-research-system`tS-876`tОснования приложения о низовом слое Hermes) |
| 287 | www.atlassian.com | — | [ссылка](https://www.atlassian.com/blog/announcements/atlassian-rovo-mcp-ga`tS-642`tAtlassian Rovo MCP — GA) |
| 288 | www.databricks.com | — | [ссылка](https://www.databricks.com/blog/ai-harness`tS-108`tDatabricks — определение агентной оболочки) |
| 289 | www.langchain.com | — | [ссылка](https://www.langchain.com/blog/improving-deep-agents-with-harness-engineering`tS-105,S-303`tLangChain — Terminal-Bench 2.0 и системный промпт / LangChain — измеримое влияние оболочки) |
| 290 | www.oasis-open.org | — | [ссылка](https://www.oasis-open.org/standard/akn-v1-0/`tS-651`tAkoma Ntoso (OASIS) — стандарт правовых документов) |
| 291 | www.openproject.org | — | [ссылка](https://www.openproject.org/docs/user-guide/gantt-chart/gantt-chart-faq/`tS-643`tOpenProject Gantt FAQ — отсутствие CPM) |
| 292 | www.postgresql.org | — | [ссылка](https://www.postgresql.org/docs/19/ddl-temporal-tables.html`tS-654`tPostgreSQL Temporal Tables) |
| 293 | www.python.org | — | [ссылка](https://www.python.org/downloads/windows/`tS-889`tУстановка и первоначальная настройка прототипа R0) |
| 294 | www.sberbank.ru | — | [ссылка](https://www.sberbank.ru/en/press_center/all/article?newsID=2f4dadd5-df7a-44d5-a68f-8be655c81249`tS-663`tGigaChat 2 Max / 3 Ultra) |
| 295 | www.solo.io | — | [ссылка](https://www.solo.io/blog/building-real-time-ai-cost-controls-with-agentgateway`tS-320`tSolo.io — Real-Time AI Cost Controls with agentgateway) |
| 296 | www.stackai.com | — | [ссылка](https://www.stackai.com/blog/llm-leaderboard-which-llms-are-best-for-which-tasks`tS-504`tStackAI Leaderboard — ранжирование по real-world use cases) |
| 297 | www.tbench.ai | — | [ссылка](https://www.tbench.ai/leaderboard/terminal-bench/2.0?models=Claude+Opus+4.7%2CClaude+Opus+4.6`tS-109`tTerminal-Bench 2.0) |
| 298 | www.trychroma.com | — | [ссылка](https://www.trychroma.com/research/context-rot`tS-104`tChroma — деградация длинного контекста) |
| 299 | www.vellum.ai | — | [ссылка](https://www.vellum.ai/llm-leaderboard`tS-503`tVellum LLM Leaderboard — бенчмарки по типам задач) |
| 300 | www.ycombinator.com | — | [ссылка](https://www.ycombinator.com/companies/stably-ai-orca`tS-418`tYC-страница Stably AI) |
| 301 | zcode.z.ai | — | [ссылка](https://zcode.z.ai/cn/docs/usage-stats`tS-112`tОфициальные тарифы и статистика Z.ai) |
| 302 | onorca.dev | — | [ссылка](https://onorca.dev/`tS-1069`tОфициальный сайт Orca — среда разработки агентов) |

### А.3. Репозитории, исходный код и внешние проекты

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 303 | blog.can.ac | — | [ссылка](https://blog.can.ac/2026/02/12/the-harness-problem/`tS-713`tБлог автора «The harness problem») |
| 304 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi/blob/main/CONTRIBUTING.md`tS-712`tVouch-система) |
| 305 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi`tS-701`tРепозиторий oh-my-pi) |
| 306 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/examples/extensions/plan-mode/README.md`tS-709`tPlan Mode) |
| 307 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/examples/extensions/sandbox/index.ts`tS-706`tSandbox) |
| 308 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/src/core/agent-session.ts`tS-705`tCompaction) |
| 309 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/src/core/tools/bash.ts`tS-707`tBash-инструмент) |
| 310 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/pi/packages/agent/docs/agent-harness.md`tS-703`tАрхитектура AgentHarness (наследие Pi)) |
| 311 | github.com | — | [ссылка](https://github.com/earendil-works/pi/blob/main/pi/packages/agent/src/agent-loop.ts`tS-704`tЦикл agentLoop) |
| 312 | github.com | — | [ссылка](https://github.com/irlcode/RusLawOD/`tS-603`tRusLawOD — открытый корпус НПА РФ) |
| 313 | github.com | — | [ссылка](https://github.com/nicobailon/pi-subagents`tS-708`tSubagents (расширение)) |
| 314 | github.com | — | [ссылка](https://github.com/nousresearch/hermes-agent/blob/main/tools/code_execution_tool.py`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 315 | github.com | — | [ссылка](https://github.com/nousresearch/hermes-agent/blob/main/website/docs/developer-guide/model-provider-plugin.md`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 316 | github.com | — | [ссылка](https://github.com/nousresearch/hermes-agent/blob/main/website/docs/developer-guide/programmatic-integration.md`tS-213`tEvaluating Agentic Harness Systems for Autonomous Computational Pathology) |
| 317 | github.com | — | [ссылка](https://github.com/NVIDIA/RULER`tS-612`tRULER — реальная длина контекста) |
| 318 | github.com | — | [ссылка](https://github.com/openai/agents.md`tS-111`tОткрытый формат AGENTS.md) |
| 319 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/docs/droid-orchestration-group.md`tS-409`tДизайн-док маршрутизации Orca) |
| 320 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/pty-exhaustion-agent-session-leak.md`tS-410`tДокумент об утечке PTY (P0)) |
| 321 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/skill-guides/orchestration.md`tS-408`tДокументация оркестрации Orca) |
| 322 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/coordinator.ts`tS-402`tЯдро оркестрации Orca — coordinator.ts) |
| 323 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/db.ts`tS-406`tСлой SQLite Orca — db.ts) |
| 324 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/groups.ts`tS-404`tГрупповая маршрутизация Orca — groups.ts) |
| 325 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/lifecycle-reconciliation.ts`tS-405`tLifecycle-полномочия Orca) |
| 326 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/main/runtime/orchestration/types.ts`tS-403`tТипы и роли Orca — types.ts) |
| 327 | github.com | — | [ссылка](https://github.com/stablyai/orca/blob/main/src/shared/tui-agent-config.ts`tS-407`tКаталог поддерживаемых агентов Orca) |
| 328 | github.com | — | [ссылка](https://github.com/stablyai/orca`tS-401`tРепозиторий Orca) |
| 329 | omp.sh | — | [ссылка](https://omp.sh/`tS-702`tСайт oh-my-pi) |

### А.4. Оценки, наборы данных и измерительные материалы

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 330 | artificialanalysis.ai | — | [ссылка](https://artificialanalysis.ai/`tS-502,S-661`tArtificial Analysis — независимые лидерборды / Artificial Analysis — Парето-фронты моделей) |
| 331 | artificialanalysis.ai | — | [ссылка](https://artificialanalysis.ai/evaluations/omniscience`tS-611`tAA-Omniscience — галлюцинации моделей) |
| 332 | chat.chatbotarena.com`ts-507`tvellum chatbot arena — слепое голосование людей | — | [ссылка](https://chat.chatbotarena.com`tS-507`tVellum Chatbot Arena — слепое голосование людей) |
| 333 | docs.ragas.io | — | [ссылка](https://docs.ragas.io/`tS-631`tRAGAS — метрики RAG) |
| 334 | huggingface.co | — | [ссылка](https://huggingface.co/datasets/FractalGPT/RRNCBFinalPublic`tS-623`tRRNCB — российский RAG-бенчмарк по нормативке) |
| 335 | lexometrica.com | — | [ссылка](https://lexometrica.com/bench/`tS-602`tLexometrica Ground Truth — РФ-право) |
| 336 | llm-stats.com | — | [ссылка](https://llm-stats.com/benchmarks`tS-508`tllm-stats.com — технические бенчмарки) |
| 337 | mera.a-ai.ru | — | [ссылка](https://mera.a-ai.ru/en`tS-601`tMERA — русскоязычный бенчмарк) |
| 338 | www.synopticonresearch.com | — | [ссылка](https://www.synopticonresearch.com/articles/harness-effect/`tS-302`tSynopticon Research — The Harness Moves the Score) |

### А.5. Сообщения об ошибках и обсуждения

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 339 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi/issues/1734`tS-711`tРаздутый системный промпт (issue #1734)) |
| 340 | github.com | — | [ссылка](https://github.com/can1357/oh-my-pi/issues/3293`tS-710`tБезопасность — отсутствие одобрений (issue #3293)) |
| 341 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/1099`tS-413`tТоп feature-запрос — multi-repo (issue #1099)) |
| 342 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/5370`tS-411`t«Война токенов» Codex (issue #5370)) |
| 343 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/6144`tS-415`tЛагающий скролл терминала (issue #6144)) |
| 344 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/6234`tS-412`tРе-аутентификация Claude (issue #6234)) |
| 345 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/6364`tS-416`tПастинг картинок в Remote Host (issue #6364)) |
| 346 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/8539`tS-414`tБлокировка рендерера на 87 секунд (issue #8539)) |
| 347 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/14854`tS-1070`tКоординатор не отличает заблокированного агента от работающего) |
| 348 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/17741`tS-1071`tПотерянный запрос заявлен как успех) |
| 349 | github.com | — | [ссылка](https://github.com/stablyai/orca/issues/19025`tS-1072`tВорота уведомлений теряют сообщения) |

### А.6. Вторичный анализ и обсуждения

| № | Источник | Идентификаторы | Адрес |
|---:|---|---|---|
| 350 | addyosmani.com | — | [ссылка](https://addyosmani.com/blog/agent-harness-engineering/`tS-106`tAddy Osmani — обзор проектирования агентных оболочек) |
| 351 | cobusgreyling.medium.com | — | [ссылка](https://cobusgreyling.medium.com/the-harness-model-relationship-ab285a8992a7`tS-304`tCobus Greyling — Agent = Model + Harness) |
| 352 | galileo.ai | — | [ссылка](https://galileo.ai/blog/multi-agent-ai-failures-prevention`tS-323`tGalileo AI — Multi-Agent AI Failures Prevention) |
| 353 | ianlpaterson.com | — | [ссылка](https://ianlpaterson.com/blog/llm-benchmark-2026-38-actual-tasks-15-models-for-2-29/`tS-505`t38 Real Tasks Benchmark — реальные задачи, 15 моделей) |
| 354 | news.ycombinator.com | — | [ссылка](https://news.ycombinator.com/item?id=47143754`tS-714`tHackerNews — главный тред Pi/omp) |
| 355 | news.ycombinator.com | — | [ссылка](https://news.ycombinator.com/item?id=48849068`tS-715`tHackerNews — OMP-бот и vouch-критика) |
| 356 | news.ycombinator.com | — | [ссылка](https://news.ycombinator.com/item?id=48865001`tS-715`tHackerNews — OMP-бот и vouch-критика) |
| 357 | vibecodinghub.org | — | [ссылка](https://vibecodinghub.org/blog/orca-review`tS-417`tОбзор VibeCodingHub) |
| 358 | www.augmentcode.com | — | [ссылка](https://www.augmentcode.com/guides/multi-agent-cost-compounding`tS-319`tAugment Code — Multi-Agent Cost Compounding) |
| 359 | www.devclass.com | — | [ссылка](https://www.devclass.com/ai-ml/2025/11/27/ocaml-maintainers-reject-massive-ai-generated-pull-request/1728083`tS-717`tФактчек DWARF/OCaml) |
| 360 | www.mindstudio.ai | — | [ссылка](https://www.mindstudio.ai/blog/reliability-compounding-problem-ai-agent-stacks`tS-305`tMindStudio — reliability compounding) |
| 361 | www.philschmid.de | — | [ссылка](https://www.philschmid.de/agent-harness-2026`tS-107`tPhilipp Schmid — роль оболочки в 2026 году) |
| 362 | www.reddit.com | — | [ссылка](https://www.reddit.com/r/LocalLLaMA/comments/1umokm3/built_a_harness_for_myself_using_pi_selfhosted/`tS-716`tReddit — позитив low-level сообщества) |
| 363 | www.reddit.com | — | [ссылка](https://www.reddit.com/r/OnlyAICoding/comments/1ry7iyf/any_thoughts_about_ohmypi_coding_agent/`tS-716`tReddit — позитив low-level сообщества) |
| 364 | www.zartis.com | — | [ссылка](https://www.zartis.com/the-compounding-errors-problem-why-multi-agent-systems-fail-and-the-architecture-that-fixes-it/`tS-324`tZartis — Compounding Errors Problem) |
| 365 | evomap.ai | — | [ссылка](https://evomap.ai/`tS-1067`tОбзор Orca: параллельное кодирование и изоляция ворктри) |
| 366 | desty.github.io | — | [ссылка](https://desty.github.io/`tS-1068`tОбзор Orca: неподтверждённые заявления продуктивности) |

## 6. Ограничения реестра

1. Наличие адреса означает использование или рассмотрение источника, но не автоматическое принятие его выводов.
2. Большая часть публикаций 2026 года является препринтами и могла не пройти независимое рецензирование.
3. Показатели звёзд, версии, цены и доступность моделей меняются; они действительны только на дату соответствующего исследования.
4. Сообщения GitHub, Hacker News и Reddit используются для поиска воспроизводимых рисков, а не как статистика распространённости.
5. Рекомендации поставщиков полезны для настройки их продуктов, но не являются независимым сравнением качества.
6. Точная конфигурация проекта должна проверяться по D-150; библиография не заменяет опыт.
7. Статьи, добавленные по результатам мониторинга внешних публикаций (июль — октябрь 2026, идентификаторы S-909–S-1066), рассмотрены по абстрактам и имеют статус рабочих гипотез до независимой проверки; перенос их выводов на связки проекта запрещён.

## 7. Статус

Документ не разрешает новый RUN, модельный или сетевой вызов и не меняет рабочую архитектуру. Он восстанавливает происхождение решений и служит основанием для отдельной формулировки проверяемой гипотезы о качестве многооболочечной многомодельной схемы.
