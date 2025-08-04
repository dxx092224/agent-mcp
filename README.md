# Agent MCP (Model Context Protocol)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![MCP](https://img.shields.io/badge/MCP-Protocol-green.svg)](https://modelcontextprotocol.io/)

## 📖 项目简介

Agent MCP 是一个基于 Model Context Protocol (MCP) 的项目，用于扩展 AI 助手的能力，使其能够与外部服务和数据源进行交互。

## 🚀 主要功能

- **文件系统操作**: 读取、写入、编辑文件
- **趋势数据获取**: 微博、知乎、抖音等平台热搜
- **网络搜索**: DuckDuckGo 搜索功能
- **GitHub 集成**: 仓库管理、代码操作
- **新闻资讯**: 多平台新闻聚合

## 🛠️ 安装配置

### MCP 服务器配置

在 Cursor 中配置 `mcp.json`:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "MCP_SERVER_FILESYSTEM_ROOT": "."
      }
    },
    "trends-hub": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-trends-hub"]
    },
    "duckduckgo": {
      "command": "npx", 
      "args": ["-y", "@modelcontextprotocol/server-duckduckgo"]
    }
  }
}
```

## 📚 使用示例

### 获取热搜数据

```python
# 获取抖音热搜
from mcp_trends_hub import get_douyin_trending
trends = get_douyin_trending()

# 获取知乎热榜
from mcp_trends_hub import get_zhihu_trending
zhihu_trends = get_zhihu_trending(limit=10)
```

## 📁 项目结构

```
agent-mcp/
├── README.md              # 项目说明
├── mcp_config_example.json # MCP 配置示例
├── examples/              # 使用示例
└── docs/                  # 文档
```

## 📄 许可证

本项目采用 MIT 许可证。

## 🙏 致谢

- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Cursor](https://cursor.sh/)

---

⭐ 如果这个项目对您有帮助，请给它一个星标！