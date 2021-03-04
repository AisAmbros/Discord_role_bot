# Discord_role_bot
Easy bot for giving ranks on message



import discord
import os
from discord.ext import commands

# What prefix does the bot have. In my case its dot
bot = commands.Bot(command_prefix = '.', help_command=None)

# Bot logged in
@bot.event
async def on_ready():
    print('Logged in')

@bot.event
async def on_message(message):
  member = message.author
# Assigning a given function 'roleT' a role 'test1'
  roleT = discord.utils.get(message.guild.roles, name="test1")
# After what message the bot sets the given rank e.g on message 'give' bot gives you a rank 'test1'
  if message.content.startswith('give'):
    await member.add_roles(roleT)
# Bot deletes the sent message
    await message.delete() 
    
# When you write 'give', the bot will give you the 'test1' rank
