import discord
import asyncio
from discord.ext import tasks, commands

# Setze deinen Token hier ein
TOKEN = 'TOKEN_HIER'
USER_ID = User_ID  # Ersetze dies durch die ID des Users, den du pingen möchtest

# Initialisiere den Bot
intents = discord.Intents.default()
intents.members = True  # Damit der Bot Mitglieder sehen kann, benötigt er diesen Intent
bot = commands.Bot(command_prefix='!', intents=intents)


# Event, wenn der Bot bereit ist
@bot.event
async def on_ready():
    print(f'{bot.user} ist jetzt online!')
    ping_user.start()  # Startet die Ping-Task, wenn der Bot bereit ist


# Die Task, die alle 30 Minuten ausgeführt wird
@tasks.loop(minutes=30)
async def ping_user():
    user = await bot.fetch_user(USER_ID)  # Holt die User-Informationen

    if user:
        try:
            await user.send("**Gehe Live Du Sack**")  # Sendet eine private Nachricht an den User
            print(f'Nachricht an {user.name} gesendet.')
        except Exception as e:
            print(f'Konnte Nachricht nicht senden: {e}')
    else:
        print('User nicht gefunden.')


# Startet den Bot
bot.run(TOKEN)
