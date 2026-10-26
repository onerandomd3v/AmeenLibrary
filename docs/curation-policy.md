# Curation and verification policy

AmeenLibrary began as a personal toolkit and follows a **hybrid curation model**: resources the maintainer has used form its foundation, while community submissions and useful discoveries are welcome.

## Categories

- **Skills:** Agent skills and reusable task guidance.
- **Tools:** Standalone developer utilities, including tools used alongside agents.
- **MCP Servers:** Connections exposing tools and data to agents.
- **Workflows:** Repeatable processes combining tools, agents, and development practices.
- **Configurations:** Sanitized, reusable settings and instruction templates.

Classify a resource by what it actually is. A tool is not automatically a skill, and an MCP server is not automatically a plugin. A dedicated plugins category can be reconsidered if there is a concrete need.

## Verification labels

- **Personally Verified:** The maintainer confirms firsthand use and evaluation.
- **Community Verified:** A contributor confirms firsthand use and supplies meaningful usage details or reproducible evidence, reviewed by maintainers.
- **Not Yet Verified:** A resource is curated for discovery, but no firsthand evaluation has been established.

**All three statuses may appear in the published library**, with their status visible. Unverified resources must not be presented as tested or endorsed. Maintainers may decline submissions for quality, safety, relevance, or inadequate attribution.

Verification is not a security audit, a guarantee of compatibility, or a promise that a resource still works. A workflow derived from firsthand practice can still contain example commands that have not been executed end-to-end; state this clearly.

## Agent support

Prioritize Codex and Claude Code documentation initially, without excluding other agents. Record compatibility as **Tested**, **Reported**, or **Not evaluated** for each relevant agent. Do not infer compatibility from general claims.

## Documentation and installation

Provide a concise explanation of the purpose, original source and author, verification status, example use, relevant caveats, and the resource's category.

**Link to the official installation instructions by default** to avoid maintaining stale copies. Include a short command only when it adds practical value and has been checked against the upstream documentation. Document notable prerequisites, authentication, and permissions without exposing credentials.

For original workflows and configuration templates, include adoption steps, required placeholders, validation instructions, and explicit limitations. Do not claim an example has been executed unless it was.

## Publishing rules

1. Credit original maintainers and link to canonical sources.
2. State the license when confirmed; otherwise mark it unconfirmed. Do not copy third-party content without appropriate permission.
3. Do not include credentials, private endpoints, personal data, or internal project details.
4. Clearly distinguish firsthand experience from community reports and untested discoveries.
5. Use pull requests for contributions and documentation changes; review before merging.
6. Update verification dates only after a genuine recheck. Do not invent dates or testing evidence.
7. Use [the resource entry template](resource-template.md) where applicable; adapt it for original workflows and configurations.
