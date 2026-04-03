# Pika Product Skills — Project Instructions

## What This Repo Is

This is a PM skill workspace for Pika, a B2C EdTech product for children in Vietnam. It contains 109 PM skills organized into 14 plugins, with a master orchestrator.

## How to Use Skills

When the user asks you to run a skill or command, read the corresponding file and follow its instructions:

### Core Commands
- When user says `/pm` → Read and follow `pm-orchestrator/commands/pm.md`
- When user says `/discover` → Read and follow `pm-product-discovery/commands/discover.md`
- When user says `/strategy` → Read and follow `pm-product-strategy/commands/strategy.md`
- When user says `/write-prd` → Read and follow `pm-execution/commands/write-prd.md`
- When user says `/plan-okrs` → Read and follow `pm-execution/commands/plan-okrs.md`
- When user says `/sprint` → Read and follow `pm-execution/commands/sprint.md`
- When user says `/interview` → Read and follow `pm-product-discovery/commands/interview.md`
- When user says `/brainstorm` → Read and follow `pm-product-discovery/commands/brainstorm.md`
- When user says `/research-users` → Read and follow `pm-market-research/commands/research-users.md`
- When user says `/competitive-analysis` → Read and follow `pm-market-research/commands/competitive-analysis.md`
- When user says `/analyze-feedback` → Read and follow `pm-market-research/commands/analyze-feedback.md`
- When user says `/business-model` → Read and follow `pm-product-strategy/commands/business-model.md`
- When user says `/value-proposition` → Read and follow `pm-product-strategy/commands/value-proposition.md`
- When user says `/pricing` → Read and follow `pm-product-strategy/commands/pricing.md`
- When user says `/market-scan` → Read and follow `pm-product-strategy/commands/market-scan.md`
- When user says `/plan-launch` → Read and follow `pm-go-to-market/commands/plan-launch.md`
- When user says `/growth-strategy` → Read and follow `pm-go-to-market/commands/growth-strategy.md`
- When user says `/battlecard` → Read and follow `pm-go-to-market/commands/battlecard.md`
- When user says `/north-star` → Read and follow `pm-marketing-growth/commands/north-star.md`
- When user says `/market-product` → Read and follow `pm-marketing-growth/commands/market-product.md`
- When user says `/write-query` → Read and follow `pm-data-analytics/commands/write-query.md`
- When user says `/analyze-cohorts` → Read and follow `pm-data-analytics/commands/analyze-cohorts.md`
- When user says `/analyze-test` → Read and follow `pm-data-analytics/commands/analyze-test.md`
- When user says `/write-stories` → Read and follow `pm-execution/commands/write-stories.md`
- When user says `/test-scenarios` → Read and follow `pm-execution/commands/test-scenarios.md`
- When user says `/pre-mortem` → Read and follow `pm-execution/commands/pre-mortem.md`
- When user says `/stakeholder-map` → Read and follow `pm-execution/commands/stakeholder-map.md`
- When user says `/transform-roadmap` → Read and follow `pm-execution/commands/transform-roadmap.md`
- When user says `/meeting-notes` → Read and follow `pm-execution/commands/meeting-notes.md`
- When user says `/generate-data` → Read and follow `pm-execution/commands/generate-data.md`
- When user says `/triage-requests` → Read and follow `pm-product-discovery/commands/triage-requests.md`
- When user says `/setup-metrics` → Read and follow `pm-product-discovery/commands/setup-metrics.md`
- When user says `/proofread` → Read and follow `pm-toolkit/commands/proofread.md`
- When user says `/draft-nda` → Read and follow `pm-toolkit/commands/draft-nda.md`
- When user says `/privacy-policy` → Read and follow `pm-toolkit/commands/privacy-policy.md`
- When user says `/review-resume` → Read and follow `pm-toolkit/commands/review-resume.md`
- When user says `/tailor-resume` → Read and follow `pm-toolkit/commands/tailor-resume.md`

### People Management Commands
- When user says `/people-plan` → Read and follow `pm-people-management/commands/people-plan.md`
- When user says `/people-hire` → Read and follow `pm-people-management/commands/people-hire.md`
- When user says `/people-grow` → Read and follow `pm-people-management/commands/people-grow.md`
- When user says `/people-health` → Read and follow `pm-people-management/commands/people-health.md`

### AI Product Commands
- When user says `/ai-discover` → Read and follow `pm-ai-product/commands/ai-discover.md`
- When user says `/ai-strategy` → Read and follow `pm-ai-product/commands/ai-strategy.md`
- When user says `/ai-design` → Read and follow `pm-ai-product/commands/ai-design.md`
- When user says `/ai-responsible` → Read and follow `pm-ai-product/commands/ai-responsible.md`
- When user says `/ai-evaluate` → Read and follow `pm-ai-product/commands/ai-evaluate.md`

### EdTech Commands (Pika-specific)
- When user says `/learning-design` → Read and follow `pm-learning-design/commands/learning-design.md`
- When user says `/child-safety` → Read and follow `pm-child-safety/commands/child-safety.md`
- When user says `/engagement-design` → Read and follow `pm-engagement-design/commands/engagement-design.md`

### Product Coaching Commands
- When user says `/coach` → Read and follow `pm-product-coach/commands/coach.md`

## Skill Graph & Orchestrator

The orchestrator (`/pm`) uses `pm-orchestrator/skill-graph.yaml` to understand dependencies between skills. When running the orchestrator:

1. Read the skill graph to understand phase ordering and skill dependencies
2. Check for `project-state.md` in the workspace for current project state
3. Look in `Project Context/production-version/product-docs/` for existing artifacts and data

## Project Context

Real Pika product data lives in `Project Context/production-version/product-docs/`:
- `overview/` — Product direction and user journey
- `insight hub/user-feedback/` — User feedback CSVs and analysis
- `insight hub/market-research/` — Survey and interview data
- `insight hub/feature-report/` — Feature performance reports
- `insight hub/insight/` — Strategic documents (OST, prioritization, OKRs)
- `insight hub/proposals/` — Feature proposals and roadmaps

When running any skill, check this directory for relevant context to inject.

## Output Convention

Save skill outputs as markdown files. Use the naming convention specified in each skill's output format section (e.g., `learning-objectives-[feature].md`, `compliance-audit-[product].md`).
