# Jumpseller API Documentation

Official [OpenAPI 3.0.3](https://spec.openapis.org/oas/v3.0.3) specification for the [Jumpseller](https://jumpseller.com) ecommerce platform API.

## API Overview

The Jumpseller API lets you programmatically create and manage online stores. It covers:

- **Stores** - Create, configure, and manage online stores
- **Products** - Full CRUD with variants, images, categories, and custom fields
- **Orders** - Create, update, search, and fulfill orders
- **Customers** - Manage customer accounts and groups
- **Shipping** - Configure shipping methods and rates
- **Payments** - Set up payment gateways
- **Themes** - Apply and customize store themes
- **Webhooks** - Subscribe to store events
- **Pages & Categories** - Manage store content and navigation

## Quick Start

**Base URL:** `https://api.jumpseller.com/v1`

**Authentication:** Basic auth with your login and auth token (found in your Admin Panel > Account).

```bash
curl -u YOUR_LOGIN:YOUR_AUTHTOKEN https://api.jumpseller.com/v1/products.json
```

## Resources

- [OpenAPI Spec](openapi.json) - Full API specification- [OpenAPI Light](openapi-light.json) - Top 30 endpoints, no code samples (for ChatGPT, Copilot, and other AI platforms with endpoint limits)
- [Live API Reference](https://api.jumpseller.com/support/api) - Interactive documentation
- [OAuth 2 Guide](https://jumpseller.com/support/oauth-2) - For building Jumpseller Apps

## MCP Server (AI Agents)

Jumpseller provides a dedicated [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server that exposes 20 store management tools to AI agents like Claude, Cursor, Windsurf, and GitHub Copilot.

**Server URL:** `https://mcp.jumpseller.com`

**Transport:** Streamable HTTP (JSON-RPC over POST, stateless)

**Documentation:** [jumpseller.com/support/mcp-server](https://jumpseller.com/support/mcp-server/)


### Quick Setup

```json
{
  "mcpServers": {
    "jumpseller": {
      "command": "npx",
      "args": [
        "-y", "mcp-remote",
        "https://mcp.jumpseller.com/",
        "--header", "X-LOGIN-KEY:YOUR_LOGIN_KEY",
        "--header", "X-AUTH-TOKEN:YOUR_AUTH_TOKEN"
      ]
    }
  }
}
```

Add this to `claude_desktop_config.json` (Claude), `.cursor/mcp.json` (Cursor), or `~/.codeium/windsurf/mcp_config.json` (Windsurf). Get your credentials from Jumpseller Admin > Settings > API.

### Available Tools

| Area | Tools | Access |
|------|-------|--------|
| **Products** | `list_products`, `get_product`, `search_products`, `create_product`, `update_product`, `delete_product` | read/write |
| **Orders** | `list_orders`, `get_order`, `search_orders`, `update_order` | read/write |
| **Customers** | `list_customers`, `get_customer`, `search_customers` | read |
| **Categories** | `list_categories`, `create_category`, `delete_category` | read/write |
| **Pages** | `list_pages`, `create_page`, `delete_page` | read/write |
| **Store** | `get_store_info` | read |

Product tools support variants (sizes, colors), images, and categories. Tools are auto-discovered via `tools/list`.

### Authentication

- **API Token:** `X-LOGIN-KEY` + `X-AUTH-TOKEN` headers (for store owners)
- **OAuth 2.0:** `Authorization: Bearer <token>` with scoped permissions (for third-party apps). See [OAuth 2 Guide](https://jumpseller.com/support/oauth-2).

### OpenAPI-based MCP (alternative)

You can also connect via the OpenAPI spec for full API coverage (109 endpoints):

```bash
npx openmcp install https://api.jumpseller.com/swagger.json --client cursor
```

## Rate Limits

- 800 requests per minute
- 20 requests per second
- Rate limit headers included in every response

## Branding & Legal

- **Logo:** https://jumpseller.com/images/brand/jumpseller-logo-26.svg
- **Support:** support@jumpseller.com
- **Terms of Service:** https://jumpseller.com/terms/

## License

This documentation is provided by [Jumpseller](https://jumpseller.com) for use by developers and AI agents building integrations with the platform.
