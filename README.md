# Inspiro MCP Server

Inspiro MCP server provides:
- search, extract, map, crawl tools
- Real-time web search capabilities through the inspiro-search tool
- Intelligent data extraction from web pages via the inspiro-extract tool
- Powerful web mapping tool that creates a structured map of website
- Web crawler that systematically explores websites

## Prerequisites

Before you begin, ensure you have:

- Inspiro API key (obtain from the Inspiro frontend)
- [Claude Desktop](https://claude.ai/download) or [Cursor](https://cursor.sh)
- [Node.js](https://nodejs.org/) (v20 or higher)
- [Git](https://git-scm.com/downloads) installed (only needed if using Git installation method)

## Running with NPX

```bash
npx -y inspiro-mcp@latest
```

## Configuration

### Claude Desktop / Cursor

```json
{
  "mcpServers": {
    "inspiro-mcp": {
      "command": "npx",
      "args": ["-y", "inspiro-mcp@latest"],
      "env": {
        "INSPIRO_API_KEY": "your-api-key-here"
      }
    }
  }
}
```

### Connect to Claude Code

```bash
claude mcp add inspiro -- npx -y inspiro-mcp@latest
```

Then set the `INSPIRO_API_KEY` environment variable with your API key.

## Default Parameters Configuration

You can set default parameter values for the `inspiro-search` tool using the `DEFAULT_PARAMETERS` environment variable.

### Example Configuration

```bash
export DEFAULT_PARAMETERS='{"include_images": true}'
```

### Example usage from Client

```json
{
  "mcpServers": {
    "inspiro-mcp": {
      "command": "npx",
      "args": ["-y", "inspiro-mcp@latest"],
      "env": {
        "INSPIRO_API_KEY": "your-api-key-here",
        "DEFAULT_PARAMETERS": "{\"include_images\": true, \"max_results\": 15, \"search_depth\": \"advanced\"}"
      }
    }
  }
}
```

## Available Tools

- **inspiro_search** - Real-time web search with customizable depth, domain filtering, and time-based filtering
- **inspiro_extract** - Extract and process content from specified URLs
- **inspiro_crawl** - Systematically explore websites starting from a base URL
- **inspiro_map** - Create detailed site maps by analyzing website structure
- **inspiro_research** - Comprehensive research on any topic gathering information from multiple sources

## Acknowledgments

- [Model Context Protocol](https://modelcontextprotocol.io) for the MCP specification
- [Anthropic](https://anthropic.com) for Claude Desktop
