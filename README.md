# 星座 MCP 服务 

一个功能完整的星座 MCP (Model Context Protocol) 服务，提供星座信息查询、运势分析、配对测试等功能。
A fully functional constellation MCP (Model Context Protocol) service, providing functions such as constellation information query, fortune analysis, and matching test.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| get_zodiac_info | 获取指定星座的详细信息，包括性格特征、守护星、元素等 |
| get_daily_horoscope | 获取指定星座的今日运势 |
| get_compatibility | 获取两个星座的配对指数和关系分析 |
| get_all_zodiacs | 获取所有星座的基本信息列表 |
| get_zodiac_by_date | 根据出生日期确定星座 |
| get_rising_sign | 计算上升星座，需要出生时间、地点和日期 |
| get_rising_sign_info | 获取指定上升星座的详细信息 |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659203075](https://mcp.xiaobenyang.com/inspector/1777316659203075)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659203075](https://mcp.xiaobenyang.com/inspector/1777316659203075)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "星座 MCP 服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659203075/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "星座 MCP 服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659203075/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "星座 MCP 服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659203075",
          },
          "transport": "stdio"
        }
      }
}

```
