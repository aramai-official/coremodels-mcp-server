# CoreModels MCP Server

A [Model Context Protocol](https://modelcontextprotocol.io) (MCP) server for managing graph-based data models, schemas, and ontologies with [CoreModels](https://coremodels.io).

## Quick Start

### Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "coremodels": {
      "url": "https://go.coremodels.io/mcp"
    }
  }
}
```

### Cursor / VS Code

Add to `.cursor/mcp.json` or `.vscode/mcp.json`:

```json
{
  "servers": {
    "coremodels": {
      "type": "streamable-http",
      "url": "https://go.coremodels.io/mcp"
    }
  }
}
```

## Authentication

All tools require a `token` parameter. Generate an API key from your CoreModels project settings.

## Available Tools

### Read-Only

| Tool | Description |
|------|-------------|
| `core_models_fetch_nodes` | Fetch nodes with filtering and pagination |
| `core_models_project_content_summary` | Get all types, elements, and taxonomies |
| `core_models_get_mixins_info` | Get mixin definitions |
| `core_models_get_relation_groups_info` | Get available relation groups |

### Write

| Tool | Description |
|------|-------------|
| `core_models_create_node` | Create a new node |
| `core_models_update_node` | Update node label or spaces |
| `core_models_restore_node` | Restore a soft-deleted node |
| `core_models_bulk_create` | Bulk create nodes, relations, and mixins |
| `core_models_create_relation` | Create a relation between nodes |
| `core_models_create_mixin_type` | Create a new mixin type |
| `core_models_create_mixin_value` | Attach mixin values to a node |
| `core_models_import_jsonschema` | Import JSON Schema into a space |

### Destructive (use with caution)

| Tool | Description |
|------|-------------|
| `core_models_remove_node` | Soft-delete a node (restorable via `restore_node`) |
| `core_models_remove_relation` | Permanently remove a relation |
| `core_models_remove_mixin_value` | Remove mixin values from a node |
| `core_models_remove_mixin_type` | **Permanently** delete a mixin type and all its columns |

## Usage Examples

**Explore a project:**
> "List all types and elements in project abc123..."

**Build a data model:**
> "Create a Type node called 'Patient' and an Element node called 'Name', then create an inheritance relation between them."

**Add metadata:**
> "Create a mixin type called 'FHIR Mapping' with columns 'resourceType' and 'path', then attach it to the Patient node."

## Links

- [CoreModels](https://www.aramai.net/products/coremodels)
- [Aramai](https://www.aramai.net/)
