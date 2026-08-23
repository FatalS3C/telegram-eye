# 👁️ TELEGRAM-EYE

> **Archive. Analyze. Observe.**

**telegram-eye** é uma ferramenta de arquivamento e monitoramento de dados do Telegram, desenvolvida para coletar e organizar conteúdos de alvos previamente configurados pelo usuário.

A ferramenta utiliza uma sessão autenticada do Telegram para acompanhar os IDs configurados e armazenar os conteúdos recebidos, incluindo **mensagens, textos, imagens e outros tipos de mídia**, permitindo posteriormente realizar um *dump* dos dados coletados em diferentes formatos.

---

## ⚠️ Aviso importante

O **telegram-eye deve ser utilizado somente em contas, grupos, canais ou outros ambientes nos quais você tenha autorização para realizar a coleta e o arquivamento dos dados**.

O usuário é integralmente responsável pela utilização da ferramenta e pelo cumprimento das leis, termos de serviço e regras de privacidade aplicáveis.

**Não utilize a ferramenta para acessar, monitorar ou coletar dados de terceiros sem autorização.**

---

# ✨ Funcionalidades

* 🔐 Autenticação através de uma sessão do Telegram
* 🎯 Configuração de múltiplos IDs como alvos
* 💬 Arquivamento de mensagens
* 🖼️ Armazenamento de mídias e imagens
* 📁 Organização dos dados coletados
* 🗃️ Geração automática do script de coleta
* ⚙️ Criação de serviço para Linux
* 🚀 Inicialização automática em VPS ou computador
* 📦 Exportação dos dados coletados
* 🌐 Dump em **HTML**
* 📄 Dump em **TXT**
* 🧩 Dump em **JSON**

---

# 🛠️ Requisitos

Antes de começar, certifique-se de possuir:

* Python <a href='https://www.python.org/downloads/' target="_blank"><img alt='python' src='https://img.shields.io/badge/Python_3-100000?style=for-the-badge&logo=python&logoColor=white&labelColor=057FE4&color=FFFFFF'/></a>
* Uma conta do Telegram
* Uma conexão com a internet
* Uma máquina Linux caso queira utilizar o modo `.service`
* Biblioteca Pyrogram instalada <a href='https://pypi.org/project/Pyrogram/' target="_blank"><img alt='pypi' src='https://img.shields.io/badge/Pyrogram-100000?style=for-the-badge&logo=pypi&logoColor=white&labelColor=057FE4&color=FFFFFF'/></a>

Para verificar se o Python está instalado:

```bash
python3 --version
```

Instalar o necesário

```bash
pip3 install pyrogram
```

```bash
pip install pyrogram
```

---

# 🚀 Primeira execução

Execute o programa principal:

```bash
python3 telegram-eye.py
```

Você verá o menu principal da ferramenta.

Na **primeira execução**, será necessário criar uma sessão do Telegram.

---

# 🔐 1. Criando sua sessão do Telegram

No menu principal, selecione:

```text
[2] Ver sessão
```

Essa opção inicia o processo de autenticação da sua conta Telegram.

Como essa é a primeira vez utilizando o **telegram-eye**, você precisará criar uma aplicação no portal oficial do Telegram para obter as credenciais necessárias.

Acesse:

[my.telegram.org](https://my.telegram.org/auth

Faça login com sua conta e procure pela opção de criação de uma nova aplicação.

Após criar a aplicação, você receberá as credenciais necessárias para configurar a sessão | `API_ID`, `API_HASH`.

Depois de concluir a autenticação, o **telegram-eye** criará a sessão que será utilizada nas próximas execuções.

### ✅ Verificando a sessão

Para confirmar que a autenticação funcionou corretamente, o telegram-eye envia uma mensagem para **Mensagens Salvas** contendo:

```text
telegram eye!!!
```

Se essa mensagem aparecer, sua sessão foi criada com sucesso!.

---

# 🎯 2. Configurando os alvos

Depois de criar sua sessão, execute novamente:

```bash
python3 telegram-eye.py
```

No menu principal, escolha:

```text
[3] Configurar alvos
```

A ferramenta permitirá adicionar os **IDs dos alvos** que deverão ser acompanhados.

Adicione os IDs desejados, um por vez.

Quando terminar de adicionar os alvos, pressione:

```text
CTRL + C
```

Isso encerra a configuração e salva os alvos definidos.

# 3. Iniciando o telegram-eye

Depois de configurar sua sessão e seus alvos, volte ao menu principal e escolha:

```text
[1] Iniciar
```

A ferramenta apresentará duas opções:

```text
[1] Criar arquivo
[2] Criar um .service
```

---

## 📄 Opção 1 — Criar arquivo

Essa opção gera automaticamente:

```text
STALINKG.py
```

Esse arquivo será responsável pela execução da coleta configurada.

Depois de gerado, você pode iniciá-lo manualmente com:

```bash
python3 STALINKG.py
```

A partir desse momento, o script começará a processar os alvos configurados na sessão.

---

# ⚙️ Opção 2 — Criar um `.service`

A segunda opção é destinada principalmente a **Linux, servidores e VPS**.

Ela cria:

```text
STALINKG.py
```

e também os arquivos necessários para executar o processo como um serviço do sistema.

Além disso, será criado um arquivo:

```text
ativar.sh
```

Esse script auxilia na ativação do serviço.

### 🖥️ Por que usar um `.service`?

A principal vantagem é permitir que o processo fique rodando como um serviço no computador ou VPS, sem depender de manter o terminal aberto manualmente.

Isso é especialmente útil para servidores que permanecem ligados continuamente.

---

# ⭐ Recomendação

É recomendado utilizar **as duas opções**:

```text
[1] Criar arquivo
[2] Criar um .service
```

Dessa forma você possui:

* `STALINKG.py` → execução direta/manual
* `.service` → execução como serviço
* `start.sh` → auxiliar para ativação

Assim você mantém uma cópia executável do coletor e, ao mesmo tempo, pode utilizar o serviço do sistema para execução contínua.

---

# 📡 4. OSINT

Depois que o `STALINKG.py` estiver ativo, o telegram-eye passa a processar os dados dos **IDs configurados anteriormente**.

Os conteúdos coletados são armazenados para posterior consulta e exportação.

Dependendo do conteúdo disponível, isso pode incluir:

```text
💬 Mensagens
📝 Textos
🖼️ Imagens
📎 Mídias
📁 Outros conteúdos suportados
```

O processo utiliza a sessão Telegram configurada anteriormente.

---

# 📦 5. Dump dos dados

Depois que a ferramenta tiver coletado dados, volte para o programa principal:

```bash
python3 telegram-eye.py
```

No menu principal, selecione e insira o ID alvo que você está observando:

```text
[dump!]
```

Essa opção permite transformar os dados armazenados em formatos mais fáceis de visualizar ou processar.

Os formatos disponíveis são:

```text
HTML
JSON
TXT
```

---

# 👁️ TELEGRAM-EYE

**Archive. Analyze. Observe.**

Uma ferramenta criada para transformar dados do Telegram em um arquivo organizado, pesquisável e exportável.

> **Use responsibly. Respect privacy. Archive only what you are authorized to archive.**


***Obrigado pela atenção!!***
<a href='https://t.me/fatalsec' target="_blank"><img alt='telegram' src='https://img.shields.io/badge/fatalsec-100000?style=plastic&logo=telegram&logoColor=white&labelColor=black&color=black'/></a> <a href='https://x.com/F4t4lsec' target="_blank"><img alt='x' src='https://img.shields.io/badge/fatalsec-100000?style=plastic&logo=x&logoColor=white&labelColor=black&color=black'/></a> <a href='https://www.youtube.com/channel/UCVroJZsK3Qrvtvnk7NCKn-A' target="_blank"><img alt='youtube' src='https://img.shields.io/badge/Canal_no youtube-100000?style=plastic&logo=youtube&logoColor=white&labelColor=black&color=black'/></a> <a href='https://www.instagram.com/fatalsec' target="_blank"><img alt='instagram' src='https://img.shields.io/badge/Instagram-100000?style=plastic&logo=instagram&logoColor=white&labelColor=black&color=black'/></a>

***Me apoie***
<a href='https://github.com/FatalS3C/FatalS3C/blob/main/my_btc.png?raw=true' target="_blank"><img alt='bitcoin' src='https://img.shields.io/badge/Meu_BTC-100000?style=plastic&logo=bitcoin&logoColor=white&labelColor=black&color=black'/></a> <a href='https://livepix.gg/fatallartes' target="_blank"><img alt='pix' src='https://img.shields.io/badge/LivePix-100000?style=plastic&logo=pix&logoColor=white&labelColor=black&color=black'/></a>

---
# *Nossa comunidade*

![alt text](https://brazukaundernet.github.io/blog/imagens/thumbnail.jpeg)

<a href='https://brazuka-undernet.netlify.app/' target="_blank"><img alt='' src='https://img.shields.io/badge/Site_BRAZUKA-100000?style=for-the-badge&logo=&logoColor=white&labelColor=FA0B0B&color=960000'/></a>

<a href='https://t.me/brazuka_undernet' target="_blank"><img alt='' src='https://img.shields.io/badge/Canal_no telegram-100000?style=for-the-badge&logo=&logoColor=white&labelColor=FA0B0B&color=960000'/></a>
