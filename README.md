# Cinatra Company Research Skill

The company-research playbook from Cinatra's assistant skill set: to research a company, find decision makers, or enrich a company profile, it checks the workspace database first, enriches from the web only when the company is unknown, finds and enriches key contacts, scores each one for ICP fit, and presents a structured company summary with a decision-maker table and a recommended play. Packaged as its own skill so it registers in the skills catalog and stays independently versionable.

**Install:** Install `@cinatra-ai/company-research-skill` in your Cinatra instance. The bundle registers in the skills catalog at workspace level.

**Usage:** The skill is method prose delivered into a run by whatever mounts it — an assistant configured with it in its skill bundle, or an extension declaring a skill dependency on this package. You do not invoke it directly.

**Configuration:** None. The skill carries no credentials and reads no settings; it relies on whatever search, web, and enrichment tools the mounting surface provides.

**Development:** Clone the repository and run `node extension-kind-gate.mjs --package-root .` to validate the manifest. The bundle lives in `skills/company-research/`.

**Troubleshooting:** If research answers skip the workspace database and go straight to the web, the bundle is not being delivered into the run. If contacts come back without fit ratings, the workspace context defines no ICP for the model to score against.

## Works with

- Cinatra assistants configured with this skill in their bundle
- Any extension declaring a skill dependency on this package

## Capabilities

- Check the workspace database before spending web searches
- Enrich an unknown company with industry, size, and HQ firmographics
- Find key decision makers and enrich them with emails and titles
- Score every contact for ICP fit from the user's workspace context
- Present a company summary, a decision-maker table, and a recommended play
