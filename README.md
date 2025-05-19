# mcp-whatsapp-waha
Este projeto implementa um servidor usando o protocolo MCP com integração ao WAHA para envio de mensagens no WhatsApp.


## Pre-requisitos

Python 3.10 ou uma versão mais atualizada.
Você deve utilizar Python MCP SDK 1.2.0 ou mais atualizado.

Foi utilizado Windows 10 para fazer esse projeto.

## Ferramentas

- `send_message`: Envia uma mensagem para um número internacional.
- `send_message_by_name`: Envia mensagem para um nome cadastrado.

## Como usar

1. Suba o servidor WAHA com Docker.

1.1 Para fazer isso, basta realizar o comando:

   ```bash docker pull devlikeapro/waha```
   
1.2 Em seguida você deve:

   ```bash docker run -it --rm -p 3000:3000/tcp --name waha devlikeapro/waha```
   
1.3 No seu local host você será capaz de autenticar sua conta do WhatsApp
http://localhost:3000/dashboard


2. Para configurar seu WhatsApp, basta conectar na parte de sessões
  ![image](https://github.com/user-attachments/assets/d4515000-f20f-48ad-a634-5ab3ccfe980f)
2.1 Depois você deve abrir seu WhatsApp conectado no seu celular e escanear o QRCode
  ![image](https://github.com/user-attachments/assets/7b15677a-9f50-4ebf-a57b-b50fae5bb09e)
2.2 Tudo deve estar funcionando agora.
   ![image](https://github.com/user-attachments/assets/ef55aaa4-cdac-4e7b-9db7-13b57d784843)


3. Agora você vai precisar configurar o servidor MCP, para isso é muito simples:
   
3.1 Instale o "uv" e prepare um projeto Python e ambiente:

   ```powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"```
   
3.2 Depois disso os seguintes comandos:

```# Create a new directory for our project
uv init weather
cd weather

# Create virtual environment and activate it
uv venv
.venv\Scripts\activate

# Install dependencies
uv add mcp[cli] httpx

# Create our server file
new-item weather.py
```

3.3 No seu arquivo `weather.py` basta substituir pelo o desse repositório, com ele teremos todas as funcionalidades e os contatos pré-definidos.

4. Rode o servidor MCP:
   ```bash python weather.py```

5. Para esse exemplo, foi instalado a Claudia Desktop `https://claude.ai/download`, basta instalar-la e criar um `claude_desktop_config.json` na pasta de instalação.
Normalmente `C:\Users\SeuUsuário\AppData\Roaming\Claude`.


## Contatos pré-carregados
- João: +5511999999999
- Maria: +5511988888888
- Ana: +5511977777777

## Exemplos de uso
Utilizando o recurso send_message
![image](https://github.com/user-attachments/assets/8739b219-ee2d-484d-9f7a-e5cd3523def0)
![image](https://github.com/user-attachments/assets/e585b283-1ad1-475e-a0c2-27dfe2770803)

Utilizando o recurso por nome

![image](https://github.com/user-attachments/assets/d5e50689-c8e7-4ecd-91d2-3ae85c26506c)
![image](https://github.com/user-attachments/assets/a2b4a3d3-80f2-4b41-bea8-d1b9c12151fe)
