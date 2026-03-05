# Inspiro MCP 服务器

Inspiro MCP 服务器提供以下能力：
- 搜索、提取、站点映射、爬取等工具
- 通过 `inspiro_search` 进行实时网页搜索
- 通过 `inspiro_extract` 提取网页内容
- 通过 `inspiro_map` 生成网站结构映射
- 通过 `inspiro_crawl` 对网站进行系统化抓取

## 前置条件

开始前请确保你具备以下环境：
- Inspiro API Key（可在 Inspiro 前端获取）
- [Claude Desktop](https://claude.ai/download) 或 [Cursor](https://cursor.sh)
- [Node.js](https://nodejs.org/)（v20 或更高版本）
- [Git](https://git-scm.com/downloads)（仅在使用 Git 安装方式时需要）

## 使用 NPX 运行

```bash
npx -y github:Ryenlvy/inspiro-mcp
```

## 配置方式

### Claude Desktop / Cursor

```json
{
  "mcpServers": {
    "inspiro-mcp": {
      "command": "npx",
      "args": ["-y", "github:Ryenlvy/inspiro-mcp"],
      "env": {
        "INSPIRO_API_KEY": "your-api-key-here"
      }
    }
  }
}
```

### 连接 Claude Code

```bash
claude mcp add inspiro -- npx -y github:Ryenlvy/inspiro-mcp
```

然后将 `INSPIRO_API_KEY` 环境变量设置为你的 API Key。

### 连接 Codex CLI

```bash
codex mcp add inspiro \
  --env INSPIRO_API_KEY=your-api-key-here \
  -- npx -y github:Ryenlvy/inspiro-mcp
```

可使用 `codex mcp list` 查看是否添加成功。

## 默认参数配置

你可以通过 `DEFAULT_PARAMETERS` 环境变量为 `inspiro_search` 设置默认参数。

### 配置示例

```bash
export DEFAULT_PARAMETERS='{"include_images": true}'
```

### 客户端配置示例

```json
{
  "mcpServers": {
    "inspiro-mcp": {
      "command": "npx",
      "args": ["-y", "github:Ryenlvy/inspiro-mcp"],
      "env": {
        "INSPIRO_API_KEY": "your-api-key-here",
        "DEFAULT_PARAMETERS": "{\"include_images\": true, \"max_results\": 15, \"search_depth\": \"advanced\"}"
      }
    }
  }
}
```

## 可用工具

- **inspiro_search**：实时网页搜索，支持搜索深度、域名过滤、时间范围等参数
- **inspiro_extract**：从指定 URL 提取并处理内容
- **inspiro_crawl**：从起始 URL 开始递归抓取网站页面
- **inspiro_map**：分析网站结构并生成站点映射
- **inspiro_research**：围绕主题进行多来源综合研究

## 致谢

- [Model Context Protocol](https://modelcontextprotocol.io)（MCP 协议规范）
- [Anthropic](https://anthropic.com)（Claude Desktop）
