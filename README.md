# Enviar-email-usando-python

import smtplib
servidor_email = smtplib.SMTP('smtp.gmail.com', 587)
servidor_email.starttls()

servidor_email.login('seu_email@gmail.com', 'sua_senha')
remetente = 'seu_email@gmail.com'
destinatarios = ['destinatario1@gmail.com', 'destinatario2@gmail.com']
conteudo = 'Olá, este é um email de teste.'

servidor_email.sendmail(remetente, destinatarios, conteudo)
