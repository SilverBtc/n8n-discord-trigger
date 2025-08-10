# n8n-discord-trigger

![n8n.io - Workflow Automation](https://raw.githubusercontent.com/n8n-io/n8n/master/assets/n8n-logo.png)

[n8n](https://www.n8n.io) nodes to trigger workflows from Discord messages.


This node utilizes a Discord bot to transmit or receive data from child processes when a node is executed.


[n8n](https://n8n.io/) is a [fair-code licensed](https://docs.n8n.io/reference/license/) workflow automation platform.

[Installation](#installation)  
[Bot Setup](#bot-setup)  
[Operations](#operations)  
[Credentials](#credentials)  <!-- delete if no auth needed -->  
[Compatibility](#compatibility)  
[Usage](#usage)  <!-- delete if not using this section -->  
[Version history](#version-history)  <!-- delete if not using this section -->  

## Bot Setup

To send, listen to messages, or fetch the list of channels or roles, you need to set up a bot using the [Discord Developer Portal](https://discord.com/developers/applications).

1. Create a new application and set it up as a bot.
2. Enable the **Privileged Gateway Intents** for Message Intent.
3. Add the bot to your server with at least **read channel permissions**.



## Installation

Quick install guide

1) Install the package in n8n (Community Nodes)
- In n8n, go to Settings > Community Nodes > Install.
- Search the npm package: `n8n-nodes-trigger-discord` (or your custom name) and install it.

2) Create the “Discord Bot Trigger API” credentials
- Settings > Credentials > New > “Discord Bot Trigger API”.
- Fill in:
	- Client ID: your Discord application client ID.
	- Bot Token: your Discord bot token.
	- n8n API key: from Settings > Personal Access Tokens in n8n.
	- Base URL: your n8n API URL, e.g. `http://localhost:5678/api/v1` or `https://your-domain.tld/api/v1`.

3) Add the node and test
- In a workflow, add “Discord Trigger”.
- Choose “message” (or “direct-message”) and configure the text/pattern, server, channels, and roles.
- Run in test mode or activate the workflow, then send a matching message to trigger it.

Notes
- If you see ENOTFOUND on stop/deactivation, verify the credentials’ Base URL is resolvable and ends with `/api/v1`.
- The bot must be added to your Discord server with the required intents/permissions (see Bot Setup below).


## Usage

To use this node:
1. Install it as a community node in your n8n instance.
2. Configure the required credentials.
3. Set up triggers for Discord messages based on your use case.

For more help on setting up n8n workflows, check the [Try it out documentation](https://docs.n8n.io/try-it-out/).


## Version history

- **v0.8.0**: Add GuildMemberUpdate trigger, add option to rename confirm button choices.
- **v0.7.0**: Add multiclient support. Multiple credentials across multiple workflows are now possible.
- **v0.6.0**: Add direct message support (Thank you [Fank](https://github.com/Fank)) 
- **v0.5.1**: Add additional timeout field for confirmation message
- **v0.5.0**: Add a reaction trigger on messages, add attachments to message
- **v0.4.0**: Introduce additional trigger options, such as User joins guild, User leaves guild, Role created, Role deleted or Role updated. 
- **v0.3.2**: Update for multiple simultaneous trigger nodes with one bot.
- **v0.3.1**: Added additional option to trigger node to trigger on other bot messages
- **v0.3.0**: Added option to require a reference message in order to trigger the node. Enhance interaction node with a confirmation node
- **v0.2.9**: Bug fix, where a message won't trigger when multiple trigger nodes are included.
- **v0.2.8**: Multiple trigger nodes are now supported.
- **v0.2.7**: A second node Discord Interaction is added to send a message with the same credentials. Additionally roles of users can be added or removed based on interaction.
- **v0.1.5**: Initial release with message triggers and channel/role fetching capabilities.

