The Model Is Only Half the Agent: Agent Engineering, Evaluation, and Safety in 2026

A Research Survey and Technical Synthesis of Six Studies on LLM-Based Agent Systems

Individual Assignment | Generative AI | Research Survey | 2026

Research Areas: Large Language Models, Agentic AI, Harness Engineering, LLM Evaluation, AI Safety, Trustworthy AI, Multi-Agent Systems, AIOps, and Software Engineering

---

1. Project Overview

Large Language Models (LLMs) have evolved significantly from systems primarily designed to answer questions and generate text into autonomous and semi-autonomous agents capable of planning, reasoning, interacting with external tools, executing code, maintaining memory, and completing complex tasks over extended periods.

However, this evolution raises an important engineering question:

Is the performance of an AI agent determined primarily by the underlying language model, or by the system designed around that model?

This project investigates that question through a detailed comparative analysis of six research surveys published or formally updated during 2026.

The central argument emerging from these surveys is that an AI agent should not be evaluated as an isolated language model. Instead, it should be understood as an integrated engineering system consisting of a foundation model and an execution harness.

The foundation model provides capabilities such as reasoning, language understanding, planning, and decision-making. The execution harness determines how these capabilities interact with real-world environments through tool execution, context management, memory, feedback, verification, and operational constraints.

The effectiveness of an agent therefore depends not only on the intelligence of the model but also on how reliably its surrounding infrastructure converts reasoning into successful actions.

This repository presents a unified synthesis of six surveys covering the following areas:

1. Agent Engineering: How execution harnesses and runtime architectures transform language models into task-completing agents.
2. Agent Evaluation: Why traditional language-model benchmarks are insufficient for measuring multi-step autonomous behavior.
3. Trustworthy Agentic AI: How safety, robustness, privacy, and system security become more challenging as agents gain autonomy.
4. Isolation-Based Safety: Why separating trust boundaries is essential for preventing unsafe interactions between agents, tools, and environments.
5. Critical-System Assurance: How agent systems can become verifiable, auditable, and sufficiently reliable for high-consequence applications.
6. Agentic Operations: How these principles apply to network operations, incident management, infrastructure automation, and AIOps.

Rather than treating these topics independently, this project identifies the connections between them and develops a unified perspective on reliable agent engineering.

The outcome is a research-driven technical story presented through a Medium article, an accompanying slide presentation, and a recorded video explanation.

---

2. Published Project Resources

The major deliverables associated with this research are available through the following links.

Deliverable| Description| Access
Medium Article| Detailed research story synthesizing six surveys on agent engineering, evaluation, and safety| "Read on Medium" (https://medium.com/@kalharpatel2002/the-model-is-only-half-the-agent-what-six-research-surveys-reveal-about-the-future-of-ai-agents-22816f6da053)
Presentation| Visual explanation of model–harness architecture, agent performance, safety mechanisms, and the proposed engineering framework| "View Presentation" (https://docs.google.com/presentation/d/18FEoJzY3JHtI7TLu8ED2uvXkNrht5Zg8/edit?usp=drivesdk&ouid=105334028618397780218&rtpof=true&sd=true)
YouTube Video| Recorded explanation of the research findings and their engineering implications| "Watch on YouTube" (https://youtu.be/47dD_ZCoBHQ?is=7kR8eHJqIHXAJStB)
Research References| Original academic surveys used in this project| "Jump to References" (#16-references)

Suggested Reading Order

Readers unfamiliar with agent engineering can begin with the Medium article for an accessible explanation of the research. The presentation provides a more visual treatment of the architectural concepts, benchmark comparisons, and safety challenges.

The reference section links to the original academic publications for readers who want to examine the technical taxonomies, experimental evidence, and proposed research directions.

---

3. Research Motivation

3.1 From Language Generation to Autonomous Task Completion

Traditional LLM applications generally follow a relatively straightforward interaction pattern:

User Input → Language Model → Generated Response

The model receives a prompt and produces an answer. Its performance is typically measured through answer accuracy, reasoning quality, factual correctness, or instruction-following ability.

Modern agentic systems operate differently.

An autonomous coding agent, for example, may need to inspect a repository, locate a defect, modify source code, execute tests, interpret failures, revise its implementation, and determine whether the task has been completed successfully.

An infrastructure operations agent may need to inspect telemetry, identify a service degradation, examine system logs, propose a configuration change, simulate the change, and obtain authorization before deployment.

These tasks cannot be reliably completed through a single model invocation.

Instead, they require a continuous interaction cycle:

Observe → Reason → Plan → Act → Verify → Update State → Repeat

Each step introduces engineering decisions that are external to the foundation model itself.

These decisions include:

- Which information should be retrieved from the environment?
- How much previous context should be retained?
- Which tools should the agent be allowed to call?
- How should execution failures be detected?
- When should an agent retry or revise its plan?
- Which actions require human authorization?
- How should unsafe instructions or external data be isolated?
- How can the system determine whether the final outcome is correct?

Consequently, the research focus is shifting from improving standalone model capabilities toward engineering the complete agent system.

3.2 Why Larger Models Are Not Always Sufficient

Improving model quality is valuable, but it does not automatically resolve every limitation encountered during autonomous task execution.

An agent may fail because it retrieves incorrect information, uses an inappropriate tool, loses important context, repeats an unsuccessful action, or incorrectly assumes that its task is finished.

Even a capable language model can produce unreliable outcomes when its runtime environment does not provide adequate feedback and verification.

The surveys examined in this project suggest that model improvements and harness improvements are complementary.

A stronger model may make better decisions, while a better harness can improve the quality of observations, constrain actions, preserve relevant context, and detect mistakes.

The central research question is therefore not simply which language model is strongest, but which combination of model, harness, evaluation methodology, and operational safeguards produces dependable task completion.

---

4. Research Objectives

The primary objective of this project is to investigate the engineering foundations required to build reliable LLM-based agents.

The study addresses several interconnected questions.

4.1 Understanding Agent Architecture

How do modern agent systems differ from conventional LLM applications?

This includes examining execution loops, external tool interfaces, context management, persistent state, and the relationship between model reasoning and environmental feedback.

4.2 Investigating Harness Engineering

What responsibilities should be handled by the execution infrastructure surrounding an LLM?

The project examines how observation, planning control, action execution, state management, and verification interact to support long-running tasks.

4.3 Evaluating Agent Performance

Why can the same foundation model achieve different results under different agent scaffolds?

This objective focuses on the role of benchmark design, execution environments, testing mechanisms, and evaluation procedures.

4.4 Understanding Trustworthiness

What risks emerge when agents acquire the ability to access tools, modify files, communicate with other agents, or interact with external environments?

The study considers safety, privacy, robustness, prompt injection, tool misuse, and the propagation of failures across system boundaries.

4.5 Connecting Research to Practical Deployment

How can theoretical research on agent architecture and trustworthiness guide the engineering of production systems?

The project explores practical implications for software development, infrastructure management, research workflows, and other high-consequence environments.

---

5. Research Methodology and Paper Selection

5.1 Research Approach

This project uses a qualitative, comparative literature-synthesis methodology.

Six research surveys were selected because they address complementary aspects of LLM-based agent development.

The papers were examined with particular attention to their research questions, proposed taxonomies, architectural frameworks, evaluation approaches, security considerations, and identified research gaps.

The objective was not merely to summarize each paper independently.

Instead, the analysis sought to identify common patterns and relationships across the literature and explain how they contribute to a coherent understanding of agent engineering.

The research was organized around five themes:

Research Theme| Main Question
Architecture| How should agent systems be constructed?
Evaluation| How should their capabilities and failures be measured?
Safety| How should dangerous interactions be prevented?
Assurance| How can the system provide evidence of trustworthy behavior?
Operations| How can agent autonomy be managed in real environments?

The resulting synthesis connects these themes into a common engineering perspective.

5.2 Publication Window

The assignment focuses on recent survey literature from approximately the three- to six-month period preceding November 2026.

Most papers were initially published between May and July 2026.

There are several relevant publication-history distinctions:

- The agent evaluation survey appeared as an earlier arXiv preprint but was published in the peer-reviewed Findings of ACL 2026 proceedings in July 2026.
- The isolation survey was submitted to arXiv in July 2026 and later appeared in Findings of EMNLP 2026 in October.
- The NetOps/AIOps survey was initially submitted on May 12, 2026, and received an updated second version on June 15, 2026.

These distinctions are important because a paper's initial preprint date, revision date, and formal publication date are not necessarily identical.

5.3 Selected Research Papers

No.| Paper| Authors| Publication Information| Research Focus
1| From Question Answering to Task Completion: A Survey on Agent System and Harness Design| Guo et al.| arXiv:2606.20683, June 14, 2026| Agent systems, harness engineering, runtime design
2| A Survey on Evaluation of LLM-based Agents| Yehudai et al.| Findings of ACL 2026, July 2026| Agent benchmarks, evaluation dimensions, frameworks
3| Towards Trustworthy Agentic AI| Qi et al.| arXiv:2605.23989, May 17, 2026| Safety, robustness, privacy, system security
4| Isolation as a First-Class Principle for LLM-Agent System Safety| Jing et al.| arXiv:2607.12406, July 14, 2026; Findings of EMNLP 2026| Isolation boundaries and system-level safety
5| Engineering Trustworthy Agentic AI for Critical Systems| Al-Refai et al.| arXiv:2607.18548, July 20, 2026| Critical systems, verification, assurance
6| Large Language Models for Agentic NetOps and AIOps| Bilal et al.| arXiv:2605.12729, revised June 15, 2026| Autonomous operations, reliability, governance

5.4 Scope of the Survey

The work primarily investigates the software-engineering and systems-design aspects of LLM agents.

It does not attempt to provide an exhaustive review of every agent architecture, benchmark, memory mechanism, or training method introduced during 2026.

Instead, it prioritizes six complementary surveys that collectively explain how intelligent agent behavior can be translated into reliable, observable, and controlled execution.

This is a thematic literature synthesis rather than a formal systematic review or a new experimental benchmark study.

---

6. Detailed Review of the Six Surveys

Paper 1: From Question Answering to Task Completion — Agent System and Harness Design

Authors: Jianyuan Guo et al.
Publication: June 14, 2026
Reference: "arXiv:2606.20683" (https://arxiv.org/abs/2606.20683)

This survey forms the architectural foundation of the project.

Its central contribution is the idea that an agent should be understood as a foundation model integrated with an execution harness.

The language model supplies the reasoning engine, but the harness coordinates how that reasoning is translated into actions.

The survey identifies four major paradigms in the evolution of agent engineering:

1. Prompt Engineering

Early agent systems primarily relied on carefully constructed prompts to influence model behavior.

Techniques such as role instructions, chain-of-thought prompting, and structured output formats improved reasoning and task execution without fundamentally changing the surrounding infrastructure.

However, prompt engineering alone provided limited support for persistent state, complex tool interactions, and reliable error recovery.

2. Workflow and Context Engineering

The next stage introduced structured pipelines, external retrieval systems, tool integrations, and context-management techniques.

These approaches made it possible to organize complex tasks into smaller operations and provide models with relevant information at different stages.

Nevertheless, static workflows were often insufficient for dynamic tasks where the correct sequence of actions could not be determined in advance.

3. Harness Engineering

Harness engineering focuses on building a reusable execution environment capable of coordinating agent behavior over multiple steps.

A well-designed harness provides tool interfaces, action control, memory handling, observation mechanisms, validation procedures, and recovery strategies.

The key idea is that successful autonomy depends on the runtime infrastructure as well as the reasoning model.

4. Agent-Native Training and Co-Evolution

The most advanced paradigm investigates how models and execution harnesses can be designed and improved together.

Rather than treating the harness as a fixed wrapper, the model and its runtime environment are considered interdependent components.

Training objectives, evaluation settings, tool interfaces, and execution mechanisms may evolve together to improve overall agent performance.

Main Finding

Agent performance emerges from the interaction between the model, execution harness, task characteristics, and evaluation environment.

The survey also presents evidence that different harness configurations can produce substantial differences in task-completion performance, even when the underlying model family remains the same.

Importance to This Project

This paper provides the central model–harness perspective around which the remaining surveys are organized.

It explains how agents are built and establishes the architectural foundation for studying their evaluation, safety, and operation.

---

Paper 2: A Survey on Evaluation of LLM-based Agents

Authors: Asaf Yehudai, Lilach Eden, Alan Li, Guy Uziel, Yilun Zhao, Roy Bar-Haim, Arman Cohan, and Michal Shmueli-Scheuer
Publication: Findings of ACL 2026, July 2026
Reference: "ACL Anthology" (https://aclanthology.org/2026.findings-acl.1330/)

This survey examines the rapidly developing field of LLM-agent evaluation.

Traditional language-model benchmarks commonly assess individual responses to predefined questions.

However, autonomous agents operate through sequences of decisions, tool invocations, observations, and actions.

A system may produce a plausible answer while failing to accomplish its actual objective.

For example, a coding agent may generate syntactically valid code that does not pass the required tests. Similarly, a web agent may complete several navigation steps but fail to submit the requested information correctly.

These examples illustrate why evaluating only the final text response is insufficient.

The paper organizes agent evaluation into five perspectives.

1. Core Agent Capabilities

Evaluation of capabilities required for agentic workflows, including planning, tool use, self-reflection, and memory.

2. Application-Specific Benchmarks

Evaluation within specific domains such as software engineering, web navigation, scientific research, and conversational applications.

3. Generalist-Agent Evaluation

Assessment of systems intended to operate across multiple task categories and environments.

4. Benchmark Dimensions

Analysis of the properties that make an evaluation meaningful, including task structure, interaction requirements, and measurement methodology.

5. Evaluation Frameworks and Tools

Review of tools that support agent testing and performance analysis during development.

Key Research Gap

A successful final outcome does not necessarily imply an efficient or reliable execution process.

Two agents may complete the same task while using very different numbers of tool calls, consuming different amounts of computation, or exposing their environments to different risks.

For this reason, modern evaluation should consider multiple performance dimensions rather than relying on a single success percentage.

Importance to This Project

This paper provides the measurement framework required to determine whether a proposed harness or agent architecture is genuinely effective.

It connects architectural design decisions to measurable results.

---

Paper 3: Towards Trustworthy Agentic AI

Authors: Jinhu Qi et al.
Publication: May 17, 2026
Reference: "arXiv:2605.23989" (https://arxiv.org/abs/2605.23989)

As AI systems become more autonomous, traditional model-level safety mechanisms become insufficient.

A conventional chatbot may generate an incorrect or inappropriate response.

An agent with external tool permissions may be capable of executing actions that affect files, applications, networks, or other systems.

Consequently, the risks associated with agentic systems extend beyond language generation.

This survey organizes trustworthiness around two principal dimensions:

Safety and Robustness

This dimension considers whether an agent behaves reliably under changing conditions, respects constraints, and avoids unsafe outcomes.

Examples include failures in multi-step planning, unexpected environmental changes, and the accumulation of errors across long-running workflows.

Privacy and System Security

This dimension examines risks associated with sensitive information, tool interfaces, external data, memory systems, and execution privileges.

The survey highlights how malicious or untrusted information encountered during an agent workflow can influence subsequent decisions.

Trajectory-Level Failure

One important concern is that unsafe behavior may develop gradually over a sequence of interactions.

An agent might initially perform legitimate actions, encounter misleading information, incorporate that information into its context, and later make an unsafe decision.

The final failure may therefore originate several steps before the harmful action occurs.

This requires safety evaluation that examines the complete execut
