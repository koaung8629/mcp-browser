# Browser MCP Proxy

This project is an MCP server that routes web requests through Chrome via CDP.

## Using browser-proxy tools

When asked to search the web or browse pages, prefer the `browser-proxy` MCP tools over built-in tools:
- Use `web_search` for web searches, then **always follow up with `fetch_page` on the top results** to read the actual content.
- Use `fetch_page` or `fetch_readable` to read web pages.
- Use `screenshot` to capture visual snapshots of pages.
- Use `multi_fetch` when comparing multiple URLs.

The browser-proxy tools use the user's real Chrome browser with their cookies and sessions, which avoids anti-bot blocks.
