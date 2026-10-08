import discord, os, random
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
print(f'Hai fatto l\'accesso come {bot.user}')

@bot.command()
async def ciao(ctx):
await ctx.send(f'Ciao! Sono un bot {bot.user}!')

@bot.command()
async def heh(ctx, count_heh = 5):
await ctx.send("he" * count_heh)

@bot.command()
async def meme(ctx):
img_name = random.choice(os.listdir("image"))
with open(f"image/{img_name}", "rb") as f:
picture = discord.File(f)
await ctx.send(file=picture)

consigli_utili=["Basta plastica usa e getta: Sostituisci piatti, bicchieri, posate e bottiglie di plastica con borracce, caraffe in vetro e stoviglie lavabili",
"Scegli prodotti sfusi o alla spina: Compra pasta, legumi, detersivi e detergenti nei negozi dedicati per evitare imballaggi superflui.",
"Porta la sporta da casa: Usa borse di tela o sacchetti riutilizzabili ogni volta che vai a fare la spesa.",
"Pianifica i pasti: Fai una lista della spesa mirata per comprare solo ciò che consumi ed evitare gli sprechi di cibo.",
"Pratica il compostaggio: Trasforma gli scarti organici della cucina in concime naturale se hai un giardino o una compostiera domestica.",
"Elimina la carta inutile: Riduci la stampa di documenti e scegli bollette e comunicazioni in formato digitale.",
"Ripara prima di buttare: Aggiusta vestiti, mobili o piccoli elettrodomestici rotti invece di rimpiazzarli subito.",
"Dona ciò che non usi: Partecipa a mercatini dell'usato, scambi o regala oggetti e abiti in buone condizioni.",
"Evita il borotalco e i prodotti di carta usa e getta: Sostituisci i fogli di carta assorbente con canovacci in tessuto lavabili.",
"Impara a dire di no: Rifiuta volantini pubblicitari e piccoli gadget di plastica che finirebbero subito nella spazzatura."
    "
]

@bot.command()
async def ecologia(ctx):
    await ctx.send(f"Eccoti un fatto casuale a tema ecologia: {random.choice(consigli_utili)}")


    bot.run("MTU1MjAwMjcwMzIzMDc2MzAwOQ.GlAdLd.nx7AYLflWXWFVCA1fKQG5Pzq8HoccPgxy0wuSQ")


bot.run("MTU1MjAwMjcwMzIzMDc2MzAwOQ.GlAdLd.nx7AYLflWXWFVCA1fKQG5Pzq8HoccPgxy0wuSQ")
