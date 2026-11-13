# Governing AI-Generated Software for Long-Term Maintainability

*December 2026*

## Project overview

We propose a practical student project exploring how organisations can harness AI coding agents to accelerate software delivery while maintaining the engineering standards, architectural consistency and long-term sustainability required in public sector and healthcare environments.

Public sector organisations operate within particularly demanding technical and regulatory frameworks, including the Government Digital Service (GDS) standards, accessibility requirements, security policies, data protection obligations and established architectural principles. These requirements are essential for delivering secure, reliable and maintainable public services, but they also create challenges when introducing AI-assisted software development at scale.

The project will investigate whether AI coding agents can work effectively within predefined, human-governed engineering frameworks, consistently reusing approved components and following established development standards. It will develop a small, publicly available demonstration comparing different approaches to AI governance, from conventional coding agents to agents supported by explicit engineering standards and automated compliance feedback.

The objective is to establish how organisations might benefit from the speed of AI-assisted development without introducing additional technical debt, architectural fragmentation or long-term maintenance costs.

## Background and opportunity

Public sector and healthcare organisations face a growing challenge in maintaining and modernising complex estates of operational applications, data pipelines and supporting infrastructure. Many systems have evolved over years or decades, often through individual projects responding to immediate operational requirements. The result can be a fragmented technology estate containing duplicated functionality, inconsistent implementation patterns, ageing dependencies and significant accumulated technical debt.

Maintaining these systems increasingly consumes engineering capacity. Teams must balance operational support, security updates, regulatory compliance, infrastructure modernisation and the maintenance of existing applications against demands for new digital services. As technical debt accumulates, a growing proportion of available resources is devoted to sustaining existing systems, reducing the capacity to deliver improvements and respond to emerging public health needs. This challenge is particularly significant in government and healthcare, where software must adhere to established standards and assurance processes. Frameworks such as the GDS Service Standard, Technology Code of Practice and accessibility requirements, alongside organisational security and data governance policies, help ensure that digital services remain secure, accessible, interoperable and sustainable. These requirements cannot simply be bypassed in pursuit of faster software delivery.

Recent advances in AI coding agents offer an opportunity to substantially increase development productivity. However, the ability to generate working software quickly does not necessarily translate into an ability to maintain that software efficiently over time. Without appropriate controls, widespread adoption of AI-generated code could accelerate the accumulation of technical debt by producing numerous independently implemented applications, duplicated functions and inconsistent architectural patterns. The risk is that AI enables organisations to create software faster than their engineering teams can sustainably maintain it. In the public sector, this could exacerbate existing capacity constraints rather than resolve them.

An alternative approach is to establish a governance framework in which experienced engineers define and maintain approved architectures, reusable software components, infrastructure modules and development standards. AI agents would then operate within these established boundaries, rapidly implementing new requirements while being independently assessed against the organisation's engineering policies. This creates an opportunity to shift engineering effort away from repeatedly implementing and maintaining similar solutions towards developing and improving shared, sustainable capabilities. Rather than accumulating hundreds of independently generated applications, organisations could use AI to deliver variations of standardised solutions built on common, well-maintained foundations.

The project builds on emerging academic research into how AI coding agents interact with existing software architectures. In particular, the September 2026 paper [*Do Coding Agents Reuse Existing Code or Reinvent the Wheel?*](https://arxiv.org/pdf/2609.35357) investigates whether coding agents identify and reuse existing functionality or unnecessarily introduce duplicate implementations [1]. This provides a direct foundation for the proposed research, which will extend the question to examine whether explicit engineering standards and automated governance can improve code reuse, architectural consistency and long-term maintainability.

The proposed research will explore whether this approach can be demonstrated and measured through a controlled experiment. It draws on emerging work in agent orchestration, automated software evaluation and independent validation, including [Cloudflare's development of model-independent agent harnesses](https://blog.cloudflare.com/build-your-own-vulnerability-harness) that separate AI-generated outputs from the systems responsible for verifying them [2].

The longer-term ambition is to enable public sector organisations to increase the pace of digital delivery without proportionately increasing the complexity, cost and maintenance burden of their technology estates.

## Research aim

To investigate whether lightweight engineering standards and automated feedback can improve code reuse and architectural consistency in AI-generated Python data engineering software, without materially reducing the correctness or speed of delivery.

Indicative questions for the student to investigate:

- Does a capable coding agent naturally reuse existing approved functions, even without explicit instructions?

- Do repository-level standards, such as `AGENTS.md`, improve reuse and reduce unnecessary new code?

- Does independent validation with corrective feedback produce a further measurable improvement?

- How do these approaches compare on functional correctness, development effort and subsequent maintainability?

## Illustrative experimental approach

A possible experiment would begin with a small approved Python pipeline framework. It might provide reusable capabilities for reading, validating, transforming and writing files, plus a pipeline entry point. A coding agent would then receive approximately 50 related requests to implement variations of a data pipeline. Requests would differ in configuration, such as virtual file paths, filenames, delimiters, schema identifiers or output settings, while remaining achievable through the existing framework.

Three comparison groups could be evaluated, each using the same model, starting point and sequence of requests:

| **Approach**           | **Description**                                                                                                                      |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Baseline               | AI coding agent with access to the existing codebase but no additional governance instructions.                                      |
| Documented standards   | Same agent and tasks, with explicit engineering guidance and approved component rules.                                               |
| Standards and feedback | Documented standards plus an independent checker that returns actionable findings and allows the agent to revise its implementation. |

## Evaluation and demonstration

The principal output would be a simple evaluation dashboard showing how each codebase evolves over the sequence of requests. A line chart of cumulative Python function definitions after each task could provide an accessible visual, supported by measures that distinguish useful new functionality from avoidable duplication.

Potential measures include:

- Growth in function definitions and instances of duplicated capability.

- Use of approved functions, libraries and architectural patterns.

- Proportion of requests passing independent functional and structural checks.

- Number of correction attempts, elapsed time and, where available, model usage cost.

- Effort required to apply a common maintenance change across the resulting implementations.

The maintenance comparison is particularly relevant. For example, after the repeated requests, all pipelines might need a common change to file handling. The experiment could assess how many separate places require modification and whether existing implementations continue to pass tests. Results should be presented with clear limitations and should not assume that governance necessarily outperforms an unguided model.

## Technical options

Python is proposed as the primary language, with a public GitHub repository for transparent review and reproducibility. The following are options for investigation rather than mandated technologies:

- Coding agent: an accessible hosted model or locally runnable model, selected according to availability and university resources.

- Standards: `AGENTS.md`, Markdown guidance, structured configuration files or a combination.

- Validation: Python abstract syntax tree analysis, pytest, Ruff, and optional policy rules.

- Experiment automation: a lightweight Python runner, with GitHub Actions where useful.

- Visualisation: Streamlit, a notebook or a static interactive report.

No organisational infrastructure, credentials or datasets are required. The demonstration can operate on virtual file paths, configuration-only scenarios and mocked processing interfaces. It will be developed outside any UKHSA technical environment, using only independently created, openly publishable material. No real or synthetic data records need to be processed.

## Expected student deliverables

- A short review of relevant approaches to coding-agent guidance, evaluations and software governance.

- A small reusable Python framework and an illustrative catalogue of pipeline requests.

- A reproducible experiment comparing selected governance approaches.

- A transparent evaluation method and dashboard, including findings and limitations.

- A public repository with setup guidance and a concise technical report identifying possible next steps.

The scope is intended to be achievable as a bounded student project, subject to agreement on duration, available AI access and assessment requirements. A smaller number of tasks or fewer experimental repetitions could be used if necessary. The emphasis should remain on a credible comparison and clear evidence rather than the volume of generated code.

## Future prospects

The student project is envisaged as an initial research step rather than a production platform. If the findings are promising, subsequent work could develop the validation approach into a reusable engineering governance service. Potential directions include persistent multi-stage agent workflows, independent architectural review, shared component discovery, cross-repository compliance assessment and automatic preparation of governed pull requests.

A longer-term ambition is a controlled self-service delivery process in which users describe a data engineering requirement, AI agents propose a change using approved modules, automated checks verify the implementation, and users refine it through acceptance testing. Production changes would remain subject to appropriate human approval and organisational controls. The enduring asset would be the standards, evidence and orchestration framework, rather than dependency on any single AI model.

## References and further reading

[1] Ma, D., Wang, S., Huang, X., Wang, Z., Wang, Y., Si, L., Wei, X. and Zhang, W. (2026) ‘Do Coding Agents Reuse Existing Code or Reinvent the Wheel?’, *arXiv preprint*, arXiv:2609.35357. Available at: <https://doi.org/10.48550/arXiv.2609.35357>

[2] Jones, D., Godoi, A. and Bourzikas, G. (2026). Build your own vulnerability harness. Cloudflare. https://blog.cloudflare.com/build-your-own-vulnerability-harness/

[3] Cloudflare. Security audit skill, public reference implementation. https://github.com/cloudflare/security-audit-skill

[4] Anthropic. Demystifying evals for AI agents. https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents

[5] Python Software Foundation. ast: Abstract Syntax Trees. https://docs.python.org/3/library/ast.html

[6] pytest documentation. https://docs.pytest.org/

[7] Astral. Ruff documentation. https://docs.astral.sh/ruff/

[8] GitHub. Continuous integration with GitHub Actions. https://docs.github.com/en/actions/get-started/continuous-integration

[9] Streamlit. Documentation. https://docs.streamlit.io/
