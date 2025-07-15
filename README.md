# drydotai-mcp-server

The [Dry.ai](https://dry.ai) Model Context Protocol (MCP) server enables seamless integration between Claude and your Dry smartspaces, turning conversations into persistent, structured data. Currently, you can use this server to create and store memories and query the information in your database (smartspace).

Begin by signing up for our alpha [here](https://dry.ai/getClaudeMemory)

Watch a video of Dry in action [here](https://youtu.be/gsOecudzmFQ?feature=shared)



## Steps to Configure your User

1. Log in to [Dry.ai](https://dry.ai) and go to your Memories for Claude Smartspace. From there you can press the Claude button
<img width="972" height="293" alt="image" src="https://github.com/user-attachments/assets/523d906f-f47e-4e6f-a520-f26930199f22" />



2. You can copy your Claude desktop config or your MCP Server URL from either of these locations.
   
<img width="769" height="473" alt="image" src="https://github.com/user-attachments/assets/e021aeff-b8de-4b82-a188-3e60f3acb9a2" />

## Steps to Configure a Smartspace for MCP

1. Open the settings for the smartspace that you want to connect. Click the "Chat" tab and enable integration for Claude:

<img width="968" height="314" alt="image" src="https://github.com/user-attachments/assets/0b1e2b97-4082-462d-a195-24356d9f3989" />


Note that your very first 'Memories for Claude' smartspace should already be enabled as an integration for Claude.

## Steps to connect Dry to Claude Desktop

1. Install Node.js (v22.x or later)
   Download from: https://nodejs.org/
   Verify installation by opening Command Prompt (CMD) and running:
   ```node --version```

2. Modify your `claude_desktop_config.json` file to include the configuration copied from your profile above. It should look similar to the below:
 ```json
   {
      "mcpServers": {
        "dryai": {
         "command": "npx",
         "args": ["-y", "@drydotai/drydotai-mcp-server"],
         "env": {
            "MCP_TOKEN": "<MCP TOKEN>"
         }
      }
      }
   }
   ```
You can access this by visiting Claude -> Settings -> Developer and pressing "Edit Config" 

2. Run Claude Desktop - it will connect to Dry and all of your configured smartspaces will appear as tools to ask questions and add items. Every time you create or install new memory types in your Dry space, you'll need to restart your Claude desktop app to sync its tools with the latest state of your Dry smartspace.
