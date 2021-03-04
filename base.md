# Discord_role_bot
Easy bot for giving ranks on message


import discord
import os
from discord.ext import commands

bot = commands.Bot(command_prefix = '.', help_command=None)

@bot.event
async def on_ready():
    print('Logged in')

@bot.event
async def on_message(message):
  member = message.author
  roleT = discord.utils.get(message.guild.roles, name="test1")
  if message.content.startswith('give'):
    await member.add_roles(roleT)
    await message.delete() 
    
# When you write 'give' bot give you the 'test1' rank. After all bot deletes message.
