# Agent MCP 安装配置指南

## 📋 前置要求

- **Python**: 3.8 或更高版本
- **Node.js**: 16.0 或更高版本  
- **Cursor 编辑器**: 最新版本
- **Git**: 用于版本控制

## 🚀 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/dxx092224/agent-mcp.git
cd agent-mcp
```

### 2. 配置 MCP Servers

在 Cursor 编辑器中，创建或编辑 `mcp.json` 配置文件：

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

### 3. 验证配置

重启 Cursor 编辑器，然后测试 MCP 功能：

```python
# 在 Cursor 中测试
# 尝试获取抖音热搜
```

## 🔧 详细配置

### 文件系统服务器

用于文件操作功能：

```json
"filesystem": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-filesystem"],
  "env": {
    "MCP_SERVER_FILESYSTEM_ROOT": "."
  }
}
```

### 趋势中心服务器

用于获取各种平台的热搜数据：

```json
"trends-hub": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-trends-hub"]
}
```

支持的平台：
- 微博热搜
- 知乎热榜
- 抖音热搜
- B站排行榜
- 今日头条热榜
- 网易新闻
- 腾讯新闻
- 澎湃新闻
- 36氪热榜
- 豆瓣榜单
- 微信读书
- 什么值得买
- 少数派热榜
- BBC新闻
- 纽约时报
- The Verge
- 9to5Mac
- InfoQ
- 掘金文章榜
- 爱范儿
- 机核网

### DuckDuckGo 搜索服务器

用于网络搜索功能：

```json
"duckduckgo": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-duckduckgo"]
}
```

## 🧪 测试功能

### 1. 运行示例

```bash
cd examples
python trends_demo.py
```

### 2. 验证 MCP 连接

在 Cursor 中尝试以下操作：
- 获取抖音热搜
- 获取知乎热榜
- 搜索网络内容
- 文件操作

## 🔍 故障排除

### 常见问题

1. **MCP 服务器连接失败**
   - 检查 Node.js 版本
   - 确认网络连接
   - 验证配置文件格式

2. **权限问题**
   - 确保有足够的文件系统权限
   - 检查防火墙设置

3. **API 限制**
   - 某些平台可能有访问频率限制
   - 考虑使用代理或 VPN

### 日志查看

在 Cursor 的开发者工具中查看 MCP 相关日志。

## 📚 更多资源

- [Model Context Protocol 官方文档](https://modelcontextprotocol.io/)
- [Cursor 编辑器文档](https://cursor.sh/docs)
- [GitHub 仓库](https://github.com/dxx092224/agent-mcp)

## 🤝 获取帮助

如果遇到问题，请：

1. 查看 [Issues](https://github.com/dxx092224/agent-mcp/issues)
2. 创建新的 Issue 描述问题
3. 提供详细的错误信息和环境信息