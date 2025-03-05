    pip install discord.py
    import discord
    from discord.ext import commands, tasks
    from datetime import time

    intents = discord.Intens.all()
    bot = commands.Bot("*", intents = intents)

    @bot.event
    async def on_ready():
        mensagem_de_bom_dia.start()
        print("O que você quer?? Eu tava' dormindo!")

    @bot.event
    async def on_message(msg: discord.Message):
        if msg.author.bot:
            return
        bot.process_commans(msg)
        # await msg.reply("Mensagem não enviada, envie novamente")

    @bot.event
    async def on_member_join(menbro: discord.Member):
        canal = bot.get_channel(1346853368936661053)
        await canal.send(f"Mais um para a coleção! Bem vindo {membro.mention}")

    @bot.command():
    async def fala(ctx: commands.Context, *, num1):
        await ctx.send(num1)

    @bot.command():
    async def somar(ctx: commands.Context, num1: float, num2: float)
        resultado = num1 + num2
        await ctx.send(f"Somando esses números, temos: {resultado}")

    @bot.command()
    async def enviar_ember(ctx.commands.Context)
    minha_embed = discord.Embed()
    minha_embed.title = "Bla Bla bla"
    minha_embed.description = "mais bla bla bla" 

    ctx.reply(embed=minha_embled)


    @tasks.loop(time=time(3, 30))
    async def mensagem_de_bom_dia():
        canal = bot.get_channel(1346844970081849395)
        await canal.send("Bom dia!!! Tenham um Bom dia!!")

    bot.run("MTM0Njg0NDI4MTk4NTMwNjY0NA.GqhGL7.DlfshUMFwmptgVXZrIArwygKjeOnUZupdXjeV0")
