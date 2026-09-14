# Details for Claude Code and Cowork

Give your AI taste. Find website references for playful heroes, morphing navigation, and services brought to life with scroll animations. Explore a reference's images and motion, or get reusable components and implementation instructions from the Details Vault.

This plugin connects Claude Code and Cowork to the hosted [Details](https://www.details.so) MCP server at `https://api.details.so/mcp`.

## Account access

A Details account with an eligible plan is required. Pro includes inspiration search and reference inspection. Max, Team, and Lifetime also include the Vault tools. Free accounts cannot connect to the MCP server.

Each tool call consumes the account's applicable usage allowance. Repeated calls and admitted calls that return no match or fail during retrieval also consume allowance. Connections and tool discovery cost no credits. Daily and rate limits also apply. Check your Details account for your current plan and remaining allowance.

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
| `read_inspiration_source` | When source evidence is available, reads a narrow cited line range from a captured public source file listed by `get_inspiration`. |

The four core tools are always available to eligible accounts. `read_inspiration_source` appears when source evidence is enabled for the MCP connection. The tools retrieve content and record usage. They do not edit your project, delete collections, change subscriptions, or make purchases. Any subsequent project edits are performed by Claude Code or Cowork using its own tools and permissions.

## Privacy and support

Details receives the arguments sent to its tools, including search text and optional short project context. For selected inspirations, it may also return a source brief built from publicly accessible source files and runtime observations captured by Details; the optional source-reading tool returns only narrow ranges from files listed in that brief. Inspiration matching uses the OpenAI API for embeddings and Supabase for search, even when the connected assistant is Claude. Catalog media and private source evidence are delivered or stored through bunny.net. Usage records contain account/client identifiers, tool names, timestamps, and allowance information; they do not contain search text, project context, complete tool arguments, response content, or access tokens.

Read the [Privacy Policy](https://www.details.so/legal/privacy) and [Terms of Service](https://www.details.so/legal/terms). For support, contact [legal@details.so](mailto:legal@details.so). You can revoke a connection in your Details account's MCP settings.
