# Enviar email Gmail usando python

![image](https://github.com/SelmaCantelli/Enviar-email-usando-python/assets/77678430/64a0f073-07af-45ec-933b-9b5aea857d8b)


# Enviar email Hotmart usando python

import smtplib
import ssl
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText

# Configurações do remetente
remetente_email = "seu_email@hotmail.com"
remetente_senha = "sua_senha"

# Configurações do destinatário
destinatario_email = "destinatario_email@hotmail.com"

# Configurações do servidor SMTP do Outlook.com
smtp_server = "smtp-mail.outlook.com"
porta = 587  # A porta TLS padrão é 587

# Criação da mensagem
mensagem = MIMEMultipart()
mensagem['From'] = remetente_email
mensagem['To'] = destinatario_email
mensagem['Subject'] = 'Assunto do Email'

corpo_email = 'Corpo do email vai aqui.'
mensagem.attach(MIMEText(corpo_email, 'plain'))

# Conexão segura com o servidor SMTP
contexto = ssl.create_default_context()
server = smtplib.SMTP(smtp_server, porta)
server.starttls(context=contexto)

# Login no servidor
server.login(remetente_email, remetente_senha)

# Envio do email
server.sendmail(remetente_email, destinatario_email, mensagem.as_string())

# Fechar a conexão com o servidor
server.quit()
