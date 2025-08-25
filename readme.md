HubSpot MCP Server

The HubSpot MCP Server enables you to build AI integrations for third-party systems and securely interact with HubSpot data via MCP (Model Context Protocol) protocol. This remote MCP server is hosted on HubSpot’s infrastructure available to connect,through compatible MCP clients.

MCP (Model Context Protocol) is an emerging standard that allows AI models to interact with applications through a consistent interface. It acts as an abstraction layer over HTTP, letting AI agents access application functionality without needing to understand specific API protocols.

Data access
HubSpot MCP server allows read-only access to

- contacts,
- companies,
- deals,
- tickets,
- owners,
- carts,
- products,
- orders,
- line items,
- invoices,
- quotes,
- subscriptions

Developers are required to create user-level apps to connect with MCP server endpoint: mcp.hubspot.com

MCP server allows secure connections through OAuth and all server responses respect authenticated user’s permissions inside HubSpot. This is enabled by creating user level apps that are mandatory to access the MCP server.

Get Started

1. Install the latest version of HubSpot CLI using npm install -g @hubspot/cli@latest
2. Clone this user level app template repository
3. Update `user-level-app-hsmeta.json` file with your preferred app’s name, description, and redirect URI as necessary
4. Upload the project using hs project upload
5. Update `user-level-app-hsmeta.json` with crm.objects.ticket.read as a required scope. Add additional scopes from the optionalScopes list below, as needed.

```json
"requiredScopes": [
         "crm.objects.tickets.read"
       ],
       "optionalScopes": [
         "crm.objects.users.read",
         "crm.objects.owners.read",
         "crm.objects.carts.read",
         "crm.objects.products.read",
         "crm.objects.orders.read",
         "crm.objects.invoices.read",
         "crm.objects.quotes.read",
         "crm.objects.line_items.read",
         "crm.objects.subscriptions.read"
       ],
```

Note: it is important to add `crm.objects.tickets.read` scope after first project upload.

6. Upload the project using `hs project upload`.

You can now start using the app’s credentials (Client ID/Client secret) in your preferred MCP client to connect with mcp.hubspot.com.
