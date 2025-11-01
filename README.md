# 🤖 Discord Meme Bot using Python

A fun and simple **Discord bot** built using **Python** and the [meme-api](https://meme-api.com) that fetches and sends random meme images directly into your Discord server when you type `$meme`.

---
![Python](https://img.shields.io/badge/python-3.x-blue.svg)
![Discord.py](https://img.shields.io/badge/discord.py-latest-brightgreen.svg)
![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)

---

## 🚀 Features
- Sends **fresh memes** from the internet using the Meme API  
- Simple command: `$meme`
- Safe token management with `.gitignore`
- Built with `discord.py` and `requests`
- Easy to extend with more commands

---

## 🛠️ Tech Stack
- **Language:** Python 3.8+
- **Libraries:**  
  - [discord.py](https://discordpy.readthedocs.io/en/stable/)  
  - [requests](https://pypi.org/project/requests/)
- **API:** [meme-api.com](https://meme-api.com)
- **Hosting:** Local machine, Replit, Render, or any cloud platform

---

## 📦 Installation

### 1️⃣ Clone the repository
```bash
git clone https://github.com/SandeepKoviri/discord-bot-python.git
cd discord-bot-python
2️⃣ Install dependencies

pip install discord.py requests
3️⃣ Add your bot token securely
Create a file named token.txt in the project directory and paste your Discord bot token inside it.

⚠️ Never share this token or upload it to GitHub.

💻 Usage
Run your bot:

python bot.py
When the bot comes online, type:

$meme
It will send a random meme image from the internet to your Discord channel.

⚙️ Example Code (bot.py)

import discord
import requests
import json

def get_meme():
    response = requests.get('https://meme-api.com/gimme')
    json_data = json.loads(response.text)
    return json_data['url']

class MyClient(discord.Client):
    async def on_ready(self):
        print(f'✅ Logged in as {self.user}')

    async def on_message(self, message):
        if message.author == self.user:
            return
        if message.content.startswith('$meme'):
            await message.channel.send(get_meme())

intents = discord.Intents.default()
intents.message_content = True

client = MyClient(intents=intents)

# Securely load the token
with open("token.txt") as f:
    TOKEN = f.read().strip()

client.run(TOKEN)

🔐 .gitignore
Ensure your .gitignore file contains:

token.txt
__pycache__/
.env
This prevents your token from being pushed to GitHub.

🌍 Invite Your Bot
Go to the Discord Developer Portal

Open your bot → OAuth2 → URL Generator

Under Scopes, check bot

Under Bot Permissions, select:

Read Messages

Send Messages

Copy the generated URL, open it in your browser, and invite the bot to your server.

❤️ Contributing
Feel free to fork this project, open issues, or submit pull requests to improve it.

🧑‍💻 Author
Sandeep Koviri
📎 GitHub: SandeepKoviri
