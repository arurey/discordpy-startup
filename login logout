from discord.ext import commands
import os
import traceback

bot = commands.Bot(command_prefix='/')
token = os.environ['DISCORD_BOT_TOKEN']

import discord
from datetime import datetime, timedelta

client = discord.Client()

@client.event
async def on_voice_state_update(member, before, after): 
    if member.guild.id == 589164084654637085 and (before.channel != after.channel):
        now = datetime.utcnow() + timedelta(hours=9)
        alert_channel = client.get_channel(589164084667220149)
        if before.channel is None: 
            msg = f'{now:%m/%d-%H:%M} に {member.name} が {after.channel.name} に参加しました。'
            await alert_channel.send(msg)
        elif after.channel is None: 
            msg = f'{now:%m/%d-%H:%M} に {member.name} が {before.channel.name} から退出しました。'
            await alert_channel.send(msg)

client.run("NTk1NjAyNTc4Nzg0NjQ5MjE2.XRt4Eg.Yj7Fm0WJjo3e3dCcPzkLAfb6_gU")
