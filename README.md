# zeusz_dc_bot

```python


import discord
import random
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True  # Kell, ha !parancsokat akarsz olvasni

bot = commands.Bot(command_prefix="!", intents=intents)

@bot.event
async def on_ready():
    print(f"Bejelentkezve mint {bot.user}")

@bot.event
async def on_member_join(member):
    print(f"Üdvüzlünk a szerveren! {member.name}")

@bot.command()
async def ping(ctx):
    await ctx.send("pong!")

@bot.command()
async def hello(ctx):
    await ctx.send("Hello Zeusz vagyok a helyi lokális isten!")

@bot.command()
async def dice(ctx):
    await ctx.send(f"Dobókockával ennyit dobtam: {random.randint(1,6)}")

@bot.command()
async def quotes(ctx):
    lista = ["BME avagy bemész, megirod, egyes","In medium res, deus ex machine","Ugye diplomához nem kell nyelvizsga?","Cuius regio, eius religio!","Panem et circenses","Acta est fabula","Ave Caesar, morituri te salutant!","Carpe diem!","Cogito, ergo sum","Divide et impera","Dum spiro, spero","Lupus in fabula.","Nomen est omen","Veni, vidi, vici!"]
    await ctx.send(f"*{random.choice(lista)}*")

bot.run(TOKEN)

```
