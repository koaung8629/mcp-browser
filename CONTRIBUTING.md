# Contributing to MCP Browser

Thanks for your interest in contributing!

## Getting Started

```bash
git clone https://github.com/wgarrido/mcp-browser.git
cd mcp-browser
npm install
npm run dev    # Run with hot reload
```

## Development Workflow

1. Fork the repo and create a branch from `main`
2. Make your changes
3. Run `npm run build` to ensure it compiles
4. Test manually by adding the local build to your MCP client:
   ```json
   {
     "mcpServers": {
       "browser": {
         "command": "node",
         "args": ["/path/to/mcp-browser/dist/index.js"],
         "env": { "CHROME_HEADLESS": "true" }
       }
     }
   }
   ```
5. Open a Pull Request

## Project Structure

```
src/
  index.ts           # Entry point, MCP server setup
  browser.ts         # Chrome/CDP connection manager
  session.ts         # Persistent tab sessions
  monitor.ts         # Page change monitoring
  config.ts          # Configuration & logging
  tools/             # One file per MCP tool
  utils/             # Shared utilities (DOM cleaning, caching, etc.)
```

## Adding a New Tool

1. Create `src/tools/your-tool.ts`
2. Export a `register(server, browser, ctx)` function
3. Use Zod schemas for parameter validation
4. Import and call `register()` in `src/index.ts`

## Code Style

- TypeScript strict mode
- ESM imports (`.js` extensions in imports)
- No unnecessary abstractions — keep it simple

## Reporting Bugs

Use [GitHub Issues](https://github.com/wgarrido/mcp-browser/issues) with the bug report template.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
