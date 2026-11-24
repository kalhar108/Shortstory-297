# Short Story: Agent Engineering, Evaluation and Safety in 2026 LLM Surveys
Individual assignment: survey-paper short story on generative AI.
## Links (fill in before submitting)
| Item | Link |
|------|------|
| Medium article | `https://medium.com/@kalharpatel2002/the-model-is-only-half-the-agent-what-six-research-surveys-reveal-about-the-future-of-ai-agents-22816f6da053` |
| SlideShare deck | `https://docs.google.com/presentation/d/18FEoJzY3JHtI7TLu8ED2uvXkNrht5Zg8/edit?usp=drivesdk&ouid=105334028618397780218&rtpof=true&sd=true` |
| YouTube video 1 |https://youtu.be/47dD_ZCoBHQ?is=7kR8eHJqIHXAJStB|

## Topic
How the 2026 survey literature reframes LLM agents as **model + harness**, and what it says about evaluation, safety/isolation, assurance and operations.
## Surveys covered (published roughly May to Aug 2026)
| # | Paper | Venue / ID | Date | Why it was chosen |
|---|-------|-----------|------|-------------------|
| 1 | From Question Answering to Task Completion: A Survey on Agent System and Harness Design (Guo, Hao, Wang, ..., Chang Xu, Yunhe Wang) | arXiv 2606.20683 | 14 Jun 2026 | Core paper: agent engineering, harness anatomy, SWE-bench evidence |
| 2 | A Survey on Evaluation of LLM-based Agents (Yehudai, Eden, Li, Uziel, Zhao, Bar-Haim, Cohan, Shmueli-Scheuer) | Findings of ACL 2026 | Jul 2026 | Evaluation taxonomy and frameworks (arXiv preprint dates from Mar 2025) |
| 3 | Towards Trustworthy Agentic AI (Qi et al., incl. Irwin King, Zenglin Xu) | arXiv 2605.23989 | 17 May 2026 | Safety, robustness, privacy, system security |
| 4 | Isolation as a First-Class Principle for LLM-Agent System Safety (Jing et al., incl. Yangqiu Song) | arXiv 2607.12406 | 14 Jul 2026 | Boundary-based safety taxonomy |
| 5 | Engineering Trustworthy Agentic AI for Critical Systems (Al-Refai et al.) | arXiv 2607.18548 | 20 Jul 2026 | Assurance, metrics, critical infrastructure |
| 6 | LLMs for Agentic NetOps and AIOps (Bilal, Crowcroft, Wang, Xu, Dustdar) | arXiv 2605.12729 (v2) | 15 Jun 2026 | Operations / LLMOps angle |
**Date-window note:** the assignment asks for surveys from the last 3 to 6 months (about mid-May to mid-Nov 2026). Paper 2's preprint is older but its peer-reviewed version is from July 2026. Memory-focused surveys I found (Jan to Mar 2026) fall outside the window, so they are not included. Verify every date on arXiv before submitting.
## Main taxonomy (summary)
- **Four paradigms of agent engineering:** prompt engineering, workflow/context engineering, harness engineering, agent-native training and co-evolution.
- **Six harness components:** observation, context, control loop, action, state/artifacts, verification and governance.
- **Evaluation (five perspectives):** capabilities, application benchmarks, generalist agents, benchmark dimensions, frameworks.
- **Safety:** trustworthiness axes (safety/robustness, privacy/security), isolation boundaries (inputs, tools, execution, inter-agent, environment context), graded assurance.
## Key technique and leaderboard evidence
SWE-bench Verified results compiled in survey 1 show large spreads for the same model under different scaffolds (for example Claude 3.5 Sonnet from 33.6% to 53.6%). See `article.md` for the table.
## Repository layout
```
/README.md
/article/article.md        Medium article draft
/slides/slides.pdf         Slide deck (export from your tool of choice)
/video/script.md           Video script
/video/video.mp4           Recording (or link to YouTube)
/figures/                  Diagrams used in article and slides
```

## References
See the reference list at the end of `article.md`.
