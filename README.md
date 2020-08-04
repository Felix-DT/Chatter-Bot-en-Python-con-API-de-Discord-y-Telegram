# Chatter-Bot-en-Python-con-API-de-Discord-y-Telegram
Chatter Bot en Python con API de Discord y Telegram

from chatterbot import ChatBot
from chatterbot.trainers import ListTrainer
import discord
from discord.ext import commands
import telebot
bot = telebot.TeleBot("1334124982:AAHvnnswrKwX6yDzQ8_mSOERtSLDYzBPilo")
@bot.message_handler(commands=['start', 'help'])
def send_welcome(message):
	bot.reply_to(message, "Hola, ¿Como estas?")

@bot.message_handler(commands=['Bien'])
def send_welcome(message):
   bot.reply_to(message, "Que bueno, Bot Service le asiste, Numero = 1-Asistencia Tecnica y 2-Otros")

@bot.message_handler(commands=['Mal'])
def send_welcome(message):
	bot.reply_to(message, "Que Mal, Bot Service le asiste, Numero = 1-Asistencia Tecnica y 2-Otros")

@bot.message_handler(commands=['1'])
def send_welcome(message):
	bot.reply_to(message, "Desconecte el modem de la energia electrica por 10 segundos, luego encender el Modem confirmar sin funciona: Si o No")

@bot.message_handler(commands=['2'])
def send_welcome(message):
	bot.reply_to(message, "Para brindarle un mejor servicio debe comunicarse con nuestro departamento de servicio al cliente telefonico al numero 8091005000")

@bot.message_handler(commands=['Si'])
def send_welcome(message):
  bot.reply_to(message, "Gracias por comunicarse, disculpar los inconvenientes y estamos a la orden")


@bot.message_handler(commands=['No'])
def send_welcome(message):
	bot.reply_to(message, "Compruebe que este bien conectada el cable DSL en la parte detras del Modem y que DSL (Internet) u Online esten encendido, de ser asi y no funcionar presionar 3 en caso de funcionar luego de esto presionar 4")


@bot.message_handler(commands=['3'])
def send_welcome(message):
	bot.reply_to(message, "Se ha creado un reporte por su servicio el cual sera atendido en menos de 48 horas")

@bot.message_handler(commands=['4'])
def send_welcome(message):
  bot.reply_to(message, "Gracias por comunicarse, disculpar los inconvenientes y estamos a la orden")

bot = commands.Bot(command_prefix='>')
@bot.command()
async def ping(ctx):
  await ctx.send('pong')

@bot.command()
async def Hola(ctx):
	await ctx.send('Hola, ¿Como estas?')

@bot.command()
async def Buenas(ctx):
	await ctx.send('Buenas, ¿Como estas?')

@bot.command()
async def Bien(ctx):
	await ctx.send('Que bueno, Bot Service le asiste, Escriba Uno-Asistencia Tecnica y Dos-Otros')

@bot.command()
async def Mal(ctx):
	await ctx.send('Que mal, Bot Service le asiste, Escriba Uno-Asistencia Tecnica y Dos-Otros')

@bot.command()
async def  Uno(ctx):
	await ctx.send('Desconecte el modem de la energia electrica por 10 segundos, luego encender el Modem confirmar sin funciona: Si o No')

@bot.command()
async def Dos(ctx):
	await ctx.send('Para brindarle un mejor servicio debe comunicarse con nuestro departamento de servicio al cliente telefonico al numero 8091005000')

@bot.command()
async def Si(ctx):
	await ctx.send('Gracias por comunicarse, disculpar los inconvenientes y estamos a la orden')

@bot.command()
async def No(ctx):
	await ctx.send('Compruebe que este bien conectada el cable DSL en la parte detras del Modem y que DSL (Internet) u Online esten encendido, de ser asi y no funcionar responder con tres en caso de funcionar luego de esto responder con cuatro ')

@bot.command()
async def Tres(ctx):
	await ctx.send('Se ha creado un reporte por su servicio el cual sera atendido en menos de 48 horas')

@bot.command()
async def Cuatro(ctx):
	await ctx.send('Gracias por comunicarse, disculpar los inconvenientes y estamos a la orden')


chat = ChatBot('Redaccion_De_Informe')
talk= ['Hola','Hola, ¿Como estas?','Bien','Que bueno, Bot Service le asiste, Numero = 1-Asistencia Tecnica y 2-Otros', 'Mal', 'Que mal, Bot Service le asiste, Numero = 1-Asistencia Tecnica y 2-Otros' '1','Desconecte el modem de la energia electrica por 10 segundos, luego encender el Modem confirmar sin funciona: Si o No', 'Si', 'Gracias por comunicarse, disculpar los inconvenientes y estamos a la orden', 'No', 'Compruebe que este bien conectada el cable DSL en la parte detras del Modem y que DSL (Internet) u Online esten encendido, de ser asi y no funcionar presionar 3 en caso de funcionar luego de esto presionar 4', '3', 'Se ha creado un reporte por su servicio el cual sera atendido en menos de 48 horas', '4', 'Gracias por comunicarse, disculpar los inconvenientes y estamos a la orden', '2', 'Para brindarle un mejor servicio debe comunicarse con nuestro departamento de servicio al cliente telefonico al numero 8091005000']
trainer = ListTrainer(chat)
trainer.train(talk)
while True:
      solicitud = input('Tu: ')
      respuesta = chat.get_response(solicitud)
      print('Bot: ',respuesta)

bot.run('NzI2NTg5MjM3MjUxODAxMTAw.XvffHQ.JAH_HdlTSBCesFT6py9rUlhmg_I')

bot.polling()
