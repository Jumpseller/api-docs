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

- [OpenAPI Spec](openapi.json) - Full API specification
- [Live API Reference](https://api.jumpseller.com/support/api) - Interactive documentation
- [OAuth 2 Guide](https://jumpseller.com/support/oauth-2) - For building Jumpseller Apps

## MCP Integration (AI Agents)

Connect the Jumpseller API as native tools in Claude, Cursor, Windsurf, or any MCP-compatible AI agent:

```bash
npx openmcp install https://api.jumpseller.com/swagger.json --client cursor
```

This prompts for your API credentials (login + authtoken) and creates a local config. Replace `cursor` with `claude` or your preferred client.

Once installed, your AI agent can directly call Jumpseller API endpoints — create stores, manage products, process orders, and more — without writing HTTP requests manually.

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
