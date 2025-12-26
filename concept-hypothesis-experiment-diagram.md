# Concept-Hypothesis-Experiment Diagram

```mermaid
flowchart TD
    title 相伴AI应对未知问题的"概念-假设-实验"（Concept-Hypothesis-Experiment）策略图
    
    Start([开始：遇到问题]) --> Q1{Q1: 我自信掌握了<br/>这个问题的大部分<br/>相关知识？}

    Q1 -->|是| Q2{Q2: 这是否是简单问题？<br/>单一主要因素、<br/>因果关系明确}

    Q2 -->|是| RABPOC[使用 RABPOC 风格提示词<br/>让 AI 直接解决<br/><br/>Role - Audience - Behavior<br/>Purpose - Output - Concern]

    RABPOC --> Q3{Q3: AI 生成的<br/>内容是否满意？}

    Q3 -->|是| End([结束])
    Q3 -->|否<br/>存在认知盲区| Q1

    Q2 -->|否<br/>复杂问题：<br/>多因素交织、<br/>因果关系不明| Complex1["使用 pause-and-clarify<br/>风格提示词<br/><br/>让 AI 将问题拆解为<br/>一系列小假设<br/>并提供实验方案<br/>通过实验数据指导下一步行动"]

    Complex1 --> Loop1["针对每个小假设<br/>及其实验<br/>重新评估"] --> Q1

    Q1 -->|否<br/>对掌握知识<br/>不够自信| AIJudge["使用 pause-and-clarify<br/>风格提示词<br/><br/>让 AI 判断：<br/>对专家而言<br/>这是否是简单问题？"]

    AIJudge -->|是<br/>对专家是<br/>简单问题| Explain1["使用 pause-and-clarify<br/>风格提示词<br/><br/>让 AI 解释我不理解的<br/>概念并帮我解决问题"]

    Explain1 --> Q3

    AIJudge -->|否<br/>对专家也是<br/>复杂问题| Complex1

    Signature["大厨程序员吾真本，2025-12-26"]

    style Start fill:#e1f5e1,stroke:#2d5c2d,stroke-width:3px
    style End fill:#ffe1e1,stroke:#8b0000,stroke-width:3px
    style Q1 fill:#fff9e1,stroke:#d4a017,stroke-width:2px
    style Q2 fill:#fff9e1,stroke:#d4a017,stroke-width:2px
    style Q3 fill:#fff9e1,stroke:#d4a017,stroke-width:2px
    style AIJudge fill:#e1f0ff,stroke:#1e4d8b,stroke-width:2px
    style RABPOC fill:#f0e1ff,stroke:#6b2d8b,stroke-width:2px
    style Complex1 fill:#f0e1ff,stroke:#6b2d8b,stroke-width:2px
    style Explain1 fill:#f0e1ff,stroke:#6b2d8b,stroke-width:2px
    style Loop1 fill:#ffe1f0,stroke:#8b2d5c,stroke-width:2px
    style Signature fill:#ffffff,stroke:#cccccc,stroke-width:1px,color:#666666

```