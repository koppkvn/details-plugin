# Manual verification

Load this plugin in Claude Code and Cowork and authenticate with a Details Max, Team, or Lifetime account. A reviewer account is supplied privately during submission; credentials are never part of this repository.

Run these prompts in a conversation where this plugin is available. These are expected behaviors to verify, not previously recorded Claude test results. Exact search rankings can change as the catalog evolves.

| Prompt | Expected tool and result |
| --- | --- |
| Find editorial portfolio hero references on Details. | `search_inspirations`: up to ten references with previews and numbered Details links; related matches identified honestly. |
| Show the images and motion evidence for Details inspiration aside-20431f. | `get_inspiration`: retrieves Aside directly by its slug, with seven ordered frames or their links and a distinction between observed and inferred behavior. |
| Find an accordion resource in the Details Vault. | `search_vault`: relevant resources including Accordion, with stable IDs and numbered links. |
| Give me the implementation instructions for Details Vault resource vault:accordion. | `get_vault_resource`: implementation content, available content modes, and Details/preview links. The tool itself does not execute that content. |
| Find a quantum tomography control panel in the Details Vault. | `search_vault`: an honest `no_match` response if the catalog has no suitable resource, with no invented item. |

When source evidence is enabled for the connection, also run:

| Show the source brief for Details inspiration aside-20431f, then read the cited lines for its primary interaction. | `get_inspiration`, followed by `read_inspiration_source` with a path and narrow line range copied from the returned source brief. The source tool returns only captured files listed by that brief and never an arbitrary URL. |

Also check requests outside the integration's scope:

- "What will the weather be in Copenhagen tomorrow?" should not call Details.
- "Delete all my saved Details collections." should not call Details retrieval tools or claim deletion.
- "Cancel my Details subscription and refund the last payment." should not call Details retrieval tools or claim a billing change.

Confirm the connection can be revoked from Details account settings. Re-authenticate before supplying the account for review. If your Claude host renders the inspiration gallery, check its images, video, and links; otherwise, confirm the numbered text links remain useful.
