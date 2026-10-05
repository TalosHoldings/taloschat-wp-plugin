# TalosChat AI — WordPress plugin

The WordPress plugin distribution mirror for [TalosChat AI](https://agenttalos.ai/ai): an AI chat assistant that answers your website visitors from your own business knowledge.

## What lives here

**Public release artifacts only.** Each release on this repo carries one or two assets:

- `taloschat-ai-chat-vX.Y.Z.zip` — the versioned plugin zip
- `taloschat-ai-chat.zip` — an unversioned alias of the latest release, so the documented WP-CLI one-liner has a stable URL

## What does NOT live here

**The plugin source code.** The plugin is built and maintained inside the private [TalosHoldings/agency-system](https://github.com/TalosHoldings/agency-system) monorepo at `wp-plugin/taloschat-ai-chat/`. This mirror exists solely to publish the .zip publicly without exposing the rest of the agency-system codebase. Bug reports and feature requests should go to support@agenttalos.ai.

## Install

Three paths, full details in the plugin's own [INSTALL.md](https://github.com/TalosHoldings/agency-system/blob/main/wp-plugin/INSTALL.md):

1. **WordPress admin → Plugins → Add New → Upload Plugin** — download the `.zip` from the [latest release](https://github.com/TalosHoldings/taloschat-wp-plugin/releases/latest).
2. **WP-CLI one-liner:**
   ```bash
   wp plugin install \
     https://github.com/TalosHoldings/taloschat-wp-plugin/releases/latest/download/taloschat-ai-chat.zip \
     --activate \
     && wp option update taloschat_ai_chat_settings \
     '{"client_id":"YOUR_CLIENT_ID","api_base":"https://api.agenttalos.ai","enabled":true}' \
     --format=json
   ```
3. **Manual folder upload** — unzip, drop the `taloschat-ai-chat/` folder into `wp-content/plugins/`, activate from the Plugins page.

Then go to **Settings → TalosChat AI**, paste your `client_id`, check **Enable widget**, save.

## You need

- An [AgentTalos](https://agenttalos.ai) subscription with the TalosChat module enabled
- Your `client_id` (a short slug like `agenttalos`)

The plugin is free and GPL-licensed. The service it loads (the AI assistant, its knowledge base and your operator inbox) is a paid AgentTalos module.

## License

GPLv2-or-later. See [LICENSE](LICENSE).
