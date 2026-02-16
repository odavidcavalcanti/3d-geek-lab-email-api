# 3D Geek Lab – Contact Email API

API responsável por receber mensagens do formulário de contato do site **3D Geek Lab** e enviar:

- um e-mail ao administrador
- um e-mail automático de confirmação ao usuário

---

## 🔗 Base URL

https://cruel-abra-odavidcavalcanti-5cbd7f08.koyeb.app/


---

## 📌 Endpoint

### `POST /api/contact`

Envia uma mensagem de contato.

---

## 📤 Request

### Headers


### Body
```json
{
  "name": "Nome Completo",
  "email": "exemplo@email.com",
  "messageText": "Olá, gostaria de mais informações."
}
```

| Campo         | Regra                                 |
| ------------- | ------------------------------------- |
| `name`        | obrigatório, máximo 80 caracteres     |
| `email`       | obrigatório, formato de e-mail válido |
| `messageText` | obrigatório                           |

## ⚙️ Tecnologias utilizadas

---

- Java 21
- Spring Boot
- Jakarta Mail
- Docker
- Gmail SMTP (App Password)
- Koyeb (deploy backend)
- Vercel ( deploy frontend + reverse proxy)

---

## 🔐 Configuração de ambiente

A aplicação utiliza variáveis de ambiente para dados sensíveis:

```
GMAIL_USER=seuemail@gmail.com
GMAIL_APP_PASSWORD=app_password_do_gmail
MAIL_TO=seuemail@gmail.com
```

---

## 📦 Executar localmente com Docker

```
docker build -t 3d-geeklab-email-api .
```

```
docker run -p 8080:8080 \
  -e GMAIL_USER=seuemail@gmail.com \
  -e GMAIL_APP_PASSWORD=apppassword \
  -e MAIL_TO=seuemail@gmail.com \
  3d-geeklab-email-api
```

---

## 🧠 Observações

- O frontend consome a API via rewrite da Vercel (/api/*)
- A API não exige autenticação (endpoint público de formulário)

---

## 👤 Autor

**David cavalcanti**

Projeto desenvolvido para fins de estudo e portfólio.

---

## 🙏 Agradecimentos

**Obrigado por chegar até aqui!**

Este projeto faz parte do meu processo de aprendizado e evolução como desenvolvedor.
Qualquer feedback, sugestão, ou crítica construtiva é muito bem-vindo.