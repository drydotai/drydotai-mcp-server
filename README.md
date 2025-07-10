# dryai-mcp-server

The [Dry.ai](https://dry.ai) Model Context Protocol (MCP) server enables seamless integration between Claude and your Dry smartspaces, turning conversations into persistent, structured data. Currently, you can use this server to create and store memories and query the information in your database (smartspace).

Begin by signing up for our alpha [here](https://dry.ai/getClaudeMemory)

Watch a video of Dry in action [here](https://youtu.be/TW55riZYsZo?si=pgbnrMACYSxk321Q)


## Steps to Configure your User

1. Log in to [Dry.ai](https://dry.ai) and navigate to your **Dry Profile**.
<img width="611" alt="Screenshot 2025-04-11 at 12 15 17 PM" src="https://github.com/user-attachments/assets/462d5e88-97f0-4f87-8e64-1e75c07bb8a8" />


2. You user has a unique **MCP Token** located on your profile. You can copy your claude desktop config from here.
   
<img width="767" height="185" alt="image" src="https://github.com/user-attachments/assets/9770c54c-a72d-4577-83bf-6abb28c2f68a" />

## Steps to Configure a Smartspace for MCP

1. Open the settings for the smartspace that you want to connect. Click the "Chat" tab and enable integration for Claude:
<img width="1029" alt="image" src="https://github.com/user-attachments/assets/dfa4c2c0-d1ac-495f-b2a0-50995b3c2df7" />


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
You can access this by visiting Claude->Settings->Developer and pressing "Edit Config" 

2. Run Claude Desktop - it will connect to Dry and all of your configured smartspaces will appear as tools to ask questions and add items. Every time you create or install new memory types in your Dry space, you'll need to restart your Claude desktop app to sync its tools with the latest state of your Dry smartspace.
