# The Model Is Only Half the Agent: Agent Engineering, Evaluation, and Safety in 2026

### A Research Survey and Technical Synthesis of Six Studies on LLM-Based Agent Systems

**Individual Assignment | Generative AI | Research Survey | 2026**

**Research Areas:** Large Language Models, Agentic AI, Harness Engineering, LLM Evaluation, AI Safety, Trustworthy AI, Multi-Agent Systems, AIOps, and Software Engineering

---

## 1. Project Overview

Large Language Models (LLMs) have evolved from systems primarily designed to answer questions and generate text into autonomous and semi-autonomous agents capable of planning, reasoning, interacting with external tools, executing code, maintaining memory, and completing complex tasks over extended periods.

This project investigates a central engineering question: **Is the performance of an AI agent determined primarily by the underlying language model, or by the system designed around that model?**

Through a comparative synthesis of six 2026 research surveys, the project argues that an agent should be understood as an integrated system consisting of a **foundation model and an execution harness**. The model supplies reasoning and decision-making capabilities; the harness coordinates observations, context, tool use, state, verification, and governance.

The research connects six complementary areas:

1. **Agent engineering:** How harnesses transform language models into task-completing systems.
2. **Agent evaluation:** Why single-response benchmarks are insufficient for multi-step autonomy.
3. **Trustworthy agentic AI:** How autonomy creates safety, robustness, privacy, and security challenges.
4. **Isolation-based safety:** How trust boundaries reduce unsafe interactions among agents, tools, and environments.
5. **Critical-system assurance:** How autonomous systems can be verified, audited, and constrained.
6. **Agentic operations:** How these ideas apply to network operations, incident management, and AIOps.

The deliverables include a Medium article, a slide presentation, and a recorded video explanation.

---

## 2. Published Project Resources

| Deliverable | Description | Access |
|---|---|---|
| Medium Article | Research story synthesizing six surveys | [Read on Medium](https://medium.com/@kalharpatel2002/the-model-is-only-half-the-agent-what-six-research-surveys-reveal-about-the-future-of-ai-agents-22816f6da053) |
| Presentation | Visual explanation of model–harness architecture, evaluation, safety, and operations | [View Presentation](https://docs.google.com/presentation/d/18FEoJzY3JHtI7TLu8ED2uvXkNrht5Zg8/edit?usp=drivesdk&ouid=105334028618397780218&rtpof=true&sd=true) |
| YouTube Video | Recorded explanation of the research findings | [Watch on YouTube](https://youtu.be/47dD_ZCoBHQ?is=7kR8eHJqIHXAJStB) |
| Research References | Original academic publications | [Jump to References](#16-references) |

Readers can start with the Medium article, use the presentation for architectural diagrams and benchmark comparisons, and consult the papers for primary technical detail.

---

## 3. Research Motivation

### 3.1 From Language Generation to Autonomous Task Completion

A traditional LLM interaction often resembles:

```text
User Input → Language Model → Generated Response
```

Modern agents operate through an iterative cycle:

```text
Observe → Reason → Plan → Act → Verify → Update State → Repeat
```

For example, a coding agent may inspect a repository, identify a defect, edit files, run tests, interpret failures, and revise its solution. An infrastructure agent may inspect telemetry, investigate service degradation, propose a configuration change, validate the change, and request authorization before deployment.

Such tasks require answers to engineering questions that cannot be settled by model intelligence alone: Which information should be retrieved? What belongs in the context window? Which tools are authorized? When should the agent retry, stop, or escalate? How is success verified? How are unsafe actions prevented?

### 3.2 Why a Stronger Model Is Not Always Enough

An agent can fail because it retrieves irrelevant context, invokes the wrong tool, loses intermediate state, repeats an unsuccessful action, or incorrectly declares completion. Better reasoning helps, but robust execution also depends on infrastructure that supplies feedback, preserves evidence, and enforces restrictions.

**The central question is therefore not merely which model is strongest, but which combination of model, harness, evaluation methodology, and safeguards produces dependable task completion.**

---

## 4. Research Objectives

The project addresses five questions:

1. **Architecture:** How do execution loops, tools, context, and persistent state turn an LLM into an agent?
2. **Harness engineering:** Which responsibilities belong in the runtime system rather than the model prompt?
3. **Evaluation:** Why do systems built on similar models produce different benchmark outcomes?
4. **Trustworthiness:** How do prompt injection, tool misuse, privacy risks, and failure propagation change under autonomy?
5. **Deployment:** What additional assurance and operational controls are needed in real-world environments?

---

## 5. Research Methodology and Paper Selection

### 5.1 Approach

This is a **qualitative comparative literature synthesis**, not a new benchmark experiment or an exhaustive systematic review. Six surveys were chosen for complementary coverage of architecture, evaluation, safety, isolation, assurance, and operations. Each was analyzed for its central question, taxonomy, technical contributions, practical implications, and research gaps.

| Theme | Guiding Question |
|---|---|
| Architecture | How should agent systems be constructed? |
| Evaluation | How should capabilities and failures be measured? |
| Safety | How should dangerous interactions be prevented? |
| Assurance | How can trustworthy behavior be evidenced? |
| Operations | How can autonomy be managed in deployed environments? |

### 5.2 Publication Window and Nuances

The assignment focuses on surveys from approximately mid-May to mid-November 2026. Most selected preprints appeared in May–July 2026. The evaluation survey had an earlier preprint but appeared in peer-reviewed **Findings of ACL 2026** in July. The isolation survey later appeared in **Findings of EMNLP 2026**. The NetOps/AIOps survey was initially submitted on May 12 and revised on June 15, 2026.

### 5.3 Selected Papers

| # | Paper | Venue / Identifier | Main Focus |
|---|---|---|---|
| 1 | *From Question Answering to Task Completion: A Survey on Agent System and Harness Design* — Guo et al. | [arXiv:2606.20683](https://arxiv.org/abs/2606.20683) | Agent architecture and harness engineering |
| 2 | *A Survey on Evaluation of LLM-based Agents* — Yehudai et al. | [Findings of ACL 2026](https://aclanthology.org/2026.findings-acl.1330/) | Evaluation taxonomies and frameworks |
| 3 | *Towards Trustworthy Agentic AI* — Qi et al. | [arXiv:2605.23989](https://arxiv.org/abs/2605.23989) | Safety, robustness, privacy, security |
| 4 | *Isolation as a First-Class Principle for LLM-Agent System Safety* — Jing et al. | [arXiv:2607.12406](https://arxiv.org/abs/2607.12406) | Isolation and trust boundaries |
| 5 | *Engineering Trustworthy Agentic AI for Critical Systems* — Al-Refai et al. | [arXiv:2607.18548](https://arxiv.org/abs/2607.18548) | Assurance and critical systems |
| 6 | *Large Language Models for Agentic NetOps and AIOps* — Bilal et al. | [arXiv:2605.12729](https://arxiv.org/abs/2605.12729) | Operational reliability and governance |

---

## 6. Detailed Review of the Six Surveys

### 6.1 Guo et al. — From Question Answering to Task Completion

**Paper:** https://arxiv.org/abs/2606.20683

This survey supplies the project's architectural foundation: agent performance emerges from the interaction between a model and its execution harness. It describes four broad engineering paradigms:

1. **Prompt engineering:** Structured instructions, roles, and reasoning prompts influence model behavior but provide limited support for persistent execution.
2. **Workflow and context engineering:** Retrieval, pipelines, tool integrations, and context selection organize tasks beyond one prompt.
3. **Harness engineering:** Reusable runtime infrastructure manages observation, tools, state, verification, and recovery across multiple steps.
4. **Agent-native training and co-evolution:** Models and harnesses are jointly adapted instead of optimized in isolation.

The paper's benchmark discussion is particularly useful because reported coding-agent results vary substantially across scaffolds. The implication is that model-only comparisons do not fully describe deployed agent capability.

**Connection to this project:** Establishes the model–harness perspective used to interpret all five remaining surveys.

### 6.2 Yehudai et al. — Evaluation of LLM-Based Agents

**Paper:** https://aclanthology.org/2026.findings-acl.1330/

Traditional benchmarks evaluate isolated answers, while agents generate sequences of decisions, observations, and tool calls. An agent can produce plausible text without actually completing a task; a coding agent can generate syntactically valid code that fails tests; a web agent can navigate correctly but fail to finish a transaction.

The survey organizes evaluation through five perspectives: **core agent capabilities, application-specific benchmarks, generalist-agent evaluation, benchmark dimensions, and evaluation frameworks/tools**.

The distinction between **outcome quality** and **process quality** is especially important. Two agents may both succeed, yet differ dramatically in latency, tool calls, retries, cost, and risk. Meaningful evaluation therefore requires more than a binary pass/fail score.

**Connection to this project:** Provides the measurement layer for assessing whether harness changes produce genuine system improvements.

### 6.3 Qi et al. — Towards Trustworthy Agentic AI

**Paper:** https://arxiv.org/abs/2605.23989

Autonomy creates risks beyond inaccurate text generation. Agents may interact with external files, APIs, memories, and execution environments, so an incorrect decision can become a consequential action.

The survey examines trustworthiness through **safety and robustness** as well as **privacy and system security**. Important risks include misleading environmental observations, unsafe planning, sensitive-data exposure, and malicious instructions introduced through external content.

A critical challenge is **trajectory-level failure**: unsafe behavior may develop gradually. An agent can begin with legitimate steps, incorporate compromised information, and later perform an inappropriate action. Inspecting only the final answer may miss where the failure originated.

**Connection to this project:** Demonstrates why the harness must support monitoring, security controls, and verification throughout execution.

### 6.4 Jing et al. — Isolation as a First-Class Principle

**Paper:** https://arxiv.org/abs/2607.12406  
**Peer-reviewed version:** https://aclanthology.org/2026.findings-emnlp.976/

This survey treats isolation as an architectural requirement rather than an optional safety feature. Its central concern is that systems routinely combine information and operations with different levels of trust.

Five boundaries organize the analysis:

1. **User–agent:** Distinguish legitimate instructions from untrusted material.
2. **Agent–tool:** Restrict available capabilities and validate tool requests.
3. **Agent–execution:** Separate proposed actions from privileged execution environments.
4. **Agent–agent:** Control delegation and information propagation between agents.
5. **System–environment:** Treat external observations and retrieved content according to their trust level.

The central engineering lesson is that telling an LLM to behave safely cannot replace enforceable permissions, sandboxing, validation, and separation of authority.

**Connection to this project:** Shows how the harness can enforce boundaries that model-level instructions alone cannot guarantee.

### 6.5 Al-Refai et al. — Engineering Trustworthy Agentic AI for Critical Systems

**Paper:** https://arxiv.org/abs/2607.18548

High-consequence applications require more than strong average benchmark performance. The survey examines trustworthiness in environments where incorrect decisions may affect infrastructure, physical processes, or essential services.

Its assurance concerns include **safety and constraint satisfaction, robustness and reliability, transparency and interpretability, accountability and auditability, and privacy and security**.

A useful takeaway is **graded assurance**: verification and oversight should reflect the consequences of failure. Drafting documentation and modifying production infrastructure should not carry identical approval requirements. High-risk actions may need independent checks, strict permissions, trace records, and human authorization.

**Connection to this project:** Extends evaluation and safety into evidence-based assurance for consequential applications.

### 6.6 Bilal et al. — Large Language Models for Agentic NetOps and AIOps

**Paper:** https://arxiv.org/abs/2605.12729

Network and IT operations provide a practical setting for agent engineering. Operational systems produce logs, alerts, metrics, incident records, and configuration histories. Agents can help interpret this information, investigate failures, recommend remediation, and coordinate controlled actions.

However, an incorrect configuration change can cause an outage or violate policy. Therefore, operational autonomy requires **bounded tool use, evidence traces, validation, approval mechanisms, monitoring, and rollback-aware execution**.

An illustrative progression of autonomy is: observation → diagnosis → proposal → validation → authorized execution. Each additional level of action authority requires corresponding safeguards.

**Connection to this project:** Demonstrates how the preceding architectural and trustworthiness principles translate into real operational constraints.

---

## 7. Technical Taxonomy: The Agent Execution Harness

A useful conceptual model is:

```text
Agent System = Foundation Model + Execution Harness + Environment Interaction
```

The model proposes decisions and actions. The harness coordinates their controlled execution. The environment returns observations that inform later decisions.

### 7.1 Six Harness Responsibilities

| Component | Responsibility | Example |
|---|---|---|
| Observation | Collect information from the environment | Repository files, logs, API responses |
| Context | Select and organize information for the model | Retrieval, summarization, context compression |
| Control | Manage loops, plans, retries, and stopping conditions | Replan after failed execution |
| Action | Invoke tools through controlled interfaces | Run tests or authorized APIs |
| State | Preserve intermediate results and artifacts | Checkpoints, task history, modified files |
| Verification | Check whether results satisfy requirements | Tests, validators, policy checks |

**Governance** spans these components through permissions, policies, monitoring, and escalation rules.

### 7.2 Example: Repairing a Software Defect

1. **Observe:** Inspect repository files and failing tests.
2. **Construct context:** Retrieve the relevant functions and issue details.
3. **Plan:** Propose a repair strategy.
4. **Act:** Modify files through authorized tools.
5. **Verify:** Run tests and inspect failures.
6. **Update state:** Record changes and execution results.
7. **Recover or complete:** Retry with new evidence, escalate, or finish when requirements are satisfied.

The harness is what makes this a repeatable, inspectable workflow instead of a single code-generation response.

---

## 8. Benchmark Evidence: Why the Harness Matters

### 8.1 SWE-bench Verified

SWE-bench Verified contains 500 human-validated software-engineering issue-resolution tasks. Agents must produce repository-level fixes that satisfy the benchmark's checks.

### 8.2 Reported Model–Harness Comparison

The Guo et al. survey compiles the following results for systems reported using Claude 3.5 Sonnet:

| Model | Harness | Resolved | Resolution Rate |
|---|---|---:|---:|
| Claude 3.5 Sonnet | SWE-agent | 168 / 500 | 33.6% |
| Claude 3.5 Sonnet | SWE-agent + Tools | 245 / 500 | 49.0% |
| Claude 3.5 Sonnet | Agentless | 254 / 500 | 50.8% |
| Claude 3.5 Sonnet | AutoCodeRover | 259 / 500 | 51.8% |
| Claude 3.5 Sonnet | OpenHands + CodeAct 2.1 | 265 / 500 | 53.0% |
| Claude 3.5 Sonnet | PatchPilot | 268 / 500 | 53.6% |

**Source:** Guo et al., [arXiv:2606.20683](https://arxiv.org/abs/2606.20683), SWE-bench Verified comparison.

The spread is **20 percentage points**, corresponding to **100 additional resolved issues** between the lowest and highest reported entries on a 500-task benchmark.

**Interpretation caveat:** These are compiled cross-system results, not necessarily a perfectly controlled harness-only ablation. Model snapshots, execution budgets, prompting, retries, and experimental configurations may differ. The evidence illustrates the importance of system design without proving that harness differences alone explain the entire spread.

### 8.3 Implications

- Record model versions and harness configurations when reporting benchmarks.
- Compare tool interfaces, validation loops, and context handling, not just model names.
- Consider cost, latency, and reliability alongside completion rate.
- Avoid treating one leaderboard score as universal evidence of superiority.

---

## 9. Evaluation Beyond Task Success

A binary success score cannot fully characterize a multi-step agent. A system may finish a task while wasting resources, taking unsafe intermediate actions, or requiring repeated failures before recovery.

| Dimension | What It Measures | Illustrative Metric |
|---|---|---|
| Task success | Completion of the requested objective | Success rate |
| Efficiency | Resources consumed | Tokens, tool calls, latency, cost |
| Reliability | Consistency across similar runs | Repeated-run success |
| Robustness | Behavior under perturbation | Recovery rate |
| Safety | Respect for operational constraints | Constraint violations |
| Process quality | Quality and traceability of the trajectory | Invalid actions, trace completeness |
| Security | Resistance to untrusted inputs and unauthorized access | Unauthorized-action rate |
| Generalization | Performance across tasks and environments | Cross-domain success |

**Outcome metrics** evaluate what was achieved; **process metrics** evaluate how it was achieved. Long-horizon tasks especially require trajectory inspection because an early mistake may affect many later steps.

---

## 10. Safety, Security, and Isolation

Connecting a model to tools changes the consequences of mistakes. Incorrect text may become an incorrect file modification, API call, or infrastructure action.

| Failure Category | Description | Engineering Response |
|---|---|---|
| Prompt injection | Untrusted content attempts to redirect behavior | Separate instructions from data |
| Tool misuse | Inappropriate tool invocation | Permission controls and validation |
| Memory poisoning | Incorrect or malicious information persists | Provenance and state-integrity checks |
| Cross-agent contamination | Unsafe information propagates between agents | Inter-agent isolation |
| Unsafe execution | Proposed actions affect restricted resources | Sandboxing and authorization |
| Context manipulation | Misleading external information affects decisions | Source validation and trust boundaries |

### 10.1 Defense in Depth

No single instruction or safety filter can provide every guarantee. A stronger design combines restricted permissions, sandboxing, action validation, resource limits, monitoring, human 
