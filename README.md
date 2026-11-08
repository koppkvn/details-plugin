# Details for Claude Code and Cowork

Give your AI taste. Find website references for playful heroes, morphing navigation, and services brought to life with scroll animations. Explore a reference's images and motion, or get reusable components and implementation instructions from the Details Vault.

This plugin connects Claude Code and Cowork to the hosted [Details](https://www.details.so) MCP server at `https://api.details.so/mcp`. Its [design reference skill](skills/details-design/SKILL.md) covers choosing an inspiration, inspecting its evidence, and retrieving a reusable component.

## Account access

A Details account with eligible access is required. Pro includes inspiration search and reference inspection. Max, Team, and Lifetime also include the Vault tools. See the [MCP guide](https://www.details.so/mcp) for current access.

Tool calls record account usage. Admitted searches and inspections consume credits, including repeated calls, searches with no matches and retrieval failures. Connections and tool discovery cost no credits. Daily and rate limits also apply. Check your Details account for your current plan and remaining allowance.

## Try the plugin locally

Clone or download this plugin repository. From its root, launch:

```sh
claude --plugin-dir .
```

In Claude Code, open `/mcp`, select the Details server provided by this plugin, and choose **Authenticate**. Sign in to Details in the browser, approve access, and return to Claude Code.

If you already connected Details manually, use one connection for your test so the assistant does not see duplicate tool registrations.

## Try asking

- Give me some inspiration for a morphing navigation.
- Show me some playful hero sections.
- I want to showcase my services with a pinned scroll animation. Any ideas?
- Find an accordion in the Details Vault.

## Available tools

| Tool | What it does |
| --- | --- |
| `search_inspirations` | Finds curated website references with previews and Details links. |
| `get_inspiration` | Retrieves an individual reference's image or ordered video frames and supporting information. |
| `search_vault` | Finds relevant reusable resources in the Details Vault. |
| `get_vault_resource` | Retrieves a selected resource's implementation instructions or supporting documentation. |
| `read_inspiration_source` | Reads a cited range in captured source or a page from a listed evidence file. |
| `read_inspiration_bundle` | Reads or transfers a page of a versioned evidence file for a selected inspiration. |

The available tools depend on the connected account. They retrieve content and record usage. Any subsequent project edits are performed by your assistant using its own tools and permissions.

## Privacy and support

Details receives the arguments sent to its tools, including search text and optional short project context. For selected inspirations, it may also return a source brief built from publicly accessible source files and runtime observations captured by Details; its source readers return listed evidence as line ranges or versioned file pages, with a transfer option for the bundle. Inspiration matching uses the OpenAI API for embeddings and Supabase for search, even when the connected assistant is Claude. Catalog media and private source evidence are delivered or stored through bunny.net. Usage records contain account/client identifiers, tool names, timestamps, and allowance information; they do not contain search text, project context, complete tool arguments, response content, or access tokens.

Read the [Privacy Policy](https://www.details.so/legal/privacy) and [Terms of Service](https://www.details.so/legal/terms). For support, contact [legal@details.so](mailto:legal@details.so). You can revoke a connection in your Details account's MCP settings.

## Package license

The [MIT license](LICENSE) covers the files in this plugin package. The hosted service, catalog content and Vault resources are governed by the [Details terms](https://www.details.so/legal/terms).
