# 📧 Gmail Bot Organizer

Um bot inteligente em Python que organiza automaticamente seus e-mails do Gmail, categorizando-os, removendo da caixa de entrada e marcando como lidos.

## 🚀 Funcionalidades

- ✅ **Categorização Inteligente**: Organiza e-mails em 17 categorias predefinidas
- 📤 **Limpeza da Inbox**: Remove todos os e-mails da caixa de entrada após categorizar
- 📖 **Marcação Automática**: Marca e-mails não lidos como lidos automaticamente
- 🏷️ **Labels Automáticas**: Cria e aplica labels no Gmail para cada categoria
- ⚡ **Processamento em Massa**: Processa até 1.000 e-mails por execução
- 🛡️ **Tratamento de Erros**: Continua funcionando mesmo se alguns e-mails falharem
- 📊 **Relatórios Detalhados**: Mostra estatísticas completas de processamento
- 🔧 **Totalmente Personalizável**: Adicione suas próprias regras e categorias

## 📋 Categorias Disponíveis

O bot organiza automaticamente seus e-mails nas seguintes categorias:

| Categoria | Descrição | Exemplos |
|-----------|-----------|----------|
| 📢 **Alertas** | Avisos e alertas de segurança | Alertas do Google, avisos urgentes |
| 🎓 **Educação** | Conteúdo educacional | Cursos online, universidades, certificados |
| 📅 **Eventos** | Convites e eventos | Reuniões, webinars, conferências |
| 💰 **Financeiro** | Assuntos bancários e financeiros | Bancos, faturas, cartões, extratos |
| 📰 **Newsletters** | Boletins informativos | Marketing, informativos, promoções |
| 👤 **Pessoal** | E-mails pessoais | Família, amigos, eventos pessoais |
| ✍️ **Petições** | Abaixo-assinados | Change.org, causas sociais |
| 🚀 **Projetos** | Desenvolvimento e trabalho | GitHub, Trello, projetos profissionais |
| 🎯 **Promoções** | Ofertas e descontos | Black Friday, cupons, liquidações |
| 🧾 **Recibos** | Comprovantes de compra | PayPal, pedidos online, compras |
| 📱 **Redes Sociais** | Notificações de redes sociais | Facebook, Instagram, LinkedIn |
| 🏥 **Saúde** | Assuntos médicos | Consultas, planos de saúde, exames |
| 🆘 **Suporte** | Atendimento ao cliente | Tickets, ajuda técnica, dúvidas |
| 💼 **Vagas de emprego** | Oportunidades de trabalho | LinkedIn Jobs, recrutamento |
| ✈️ **Viagens** | Reservas e viagens | Hotéis, passagens, bookings |
| ⚖️ **Jurídico** | Questões legais | Contratos, processos, advogados |
| 📁 **Outros** | E-mails não categorizados | Categoria padrão |

## 🛠️ Instalação

### Pré-requisitos

- Python 3.7 ou superior
- Conta Gmail ativa
- Acesso ao Google Cloud Console

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/gmail-bot-organizer.git
cd gmail-bot-organizer
```

### 2. Instale as dependências

```bash
pip install google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client
```

### 3. Configure a API do Gmail

Este é o passo mais importante! Siga cuidadosamente:

#### 3.1. Acesse o Google Cloud Console

1. Vá para [Google Cloud Console](https://console.cloud.google.com/)
2. Faça login com sua conta Google
3. Crie um novo projeto ou selecione um existente

#### 3.2. Ative a Gmail API

1. No menu lateral, vá em **"APIs e Serviços"** → **"Biblioteca"**
2. Procure por **"Gmail API"**
3. Clique em **"Gmail API"** e depois em **"ATIVAR"**

#### 3.3. Configure a Tela de Consentimento OAuth

1. Vá em **"APIs e Serviços"** → **"Tela de consentimento OAuth"**
2. Escolha **"Externo"** e clique em **"CRIAR"**
3. Preencha apenas os campos obrigatórios:
   - **Nome do app**: "Gmail Bot Organizer"
   - **E-mail de suporte do usuário**: seu e-mail
   - **E-mail do desenvolvedor**: seu e-mail
4. Clique em **"SALVAR E CONTINUAR"** em todas as etapas
5. Na seção **"Usuários de teste"**, adicione seu próprio e-mail

#### 3.4. Crie as Credenciais OAuth

1. Vá em **"APIs e Serviços"** → **"Credenciais"**
2. Clique em **"+ CRIAR CREDENCIAIS"** → **"ID do cliente OAuth 2.0"**
3. Escolha **"Aplicativo para computador"**
4. Dê um nome (ex: "Gmail Bot")
5. Em **"URIs de redirecionamento autorizados"**, adicione estas URLs (uma por linha):

```
http://localhost:8080
http://localhost:8080/
http://localhost:8081
http://localhost:8081/
http://localhost:9090
http://localhost:9090/
http://127.0.0.1:8080
http://127.0.0.1:8080/
http://127.0.0.1:8081
http://127.0.0.1:8081/
http://127.0.0.1:9090
http://127.0.0.1:9090/
```

6. Clique em **"CRIAR"**
7. **BAIXE o arquivo JSON** e renomeie para `credentials.json`
8. Coloque o arquivo `credentials.json` na pasta do projeto

## 🚀 Como Usar

### Execução Básica

```bash
python gmail_bot.py
```

### Primeira Execução

1. O bot abrirá seu navegador automaticamente
2. Faça login com sua conta Gmail
3. Autorize o acesso às suas mensagens
4. O bot começará a processar seus e-mails automaticamente

### O que o Bot Faz

1. **Conecta** com sua conta Gmail via API
2. **Busca TODOS** os e-mails da sua caixa de entrada (lidos e não lidos)
3. **Analisa** cada e-mail (assunto, remetente, conteúdo)
4. **Categoriza** baseado nas regras inteligentes
5. **Cria labels** no Gmail para cada categoria
6. **Remove** todos os e-mails da caixa de entrada
7. **Marca** e-mails não lidos como lidos
8. **Gera** relatório detalhado do processamento

### Exemplo de Saída

```
🚀 Iniciando processamento de TODOS os e-mails da caixa de entrada...
📧 Encontrados 856 e-mails na caixa de entrada
⚙️ Processando 856 e-mails da caixa de entrada...

📊 Progresso: 10/856 e-mails processados
📊 Progresso: 20/856 e-mails processados
...

======================================================================
📊 RELATÓRIO FINAL DO PROCESSAMENTO DA CAIXA DE ENTRADA
======================================================================
📧 Total de e-mails encontrados na inbox: 856
📩 E-mails que estavam não lidos: 23
📧 E-mails que já estavam lidos: 833
✅ E-mails processados com sucesso: 856
❌ E-mails com erro: 0
📈 Taxa de sucesso: 100.0%

📋 DISTRIBUIÇÃO POR CATEGORIA:
--------------------------------------------------
   📁 Newsletters: 234 e-mails (27.3%)
   📁 Promoções: 156 e-mails (18.2%)
   📁 Financeiro: 142 e-mails (16.6%)
   📁 Vagas de emprego: 98 e-mails (11.4%)
   📁 Educação: 87 e-mails (10.2%)
   ...

🎯 AÇÕES REALIZADAS:
   ✅ Todos os e-mails foram categorizados com labels
   📤 Todos os e-mails foram removidos da caixa de entrada
   📖 E-mails não lidos foram marcados como lidos
   📁 Caixa de entrada agora está vazia!
======================================================================
```

## ⚙️ Personalização

### Adicionar Regras Personalizadas

Você pode adicionar suas próprias regras de categorização:

```python
# Exemplo: adicionar empresa específica à categoria Trabalho
bot.add_custom_rule('Financeiro', 'domains', 'meubancopreferido.com.br')
bot.add_custom_rule('Educação', 'keywords', 'meu curso específico')
bot.add_custom_rule('Pessoal', 'senders', 'amigo@email.com')
```

### Modificar Categorias

Edite o arquivo `gmail_bot.py` na seção `self.categories` para:
- Adicionar novas categorias
- Modificar palavras-chave existentes
- Incluir domínios específicos
- Adicionar remetentes conhecidos

### Salvar e Carregar Regras

```python
# Salvar regras personalizadas
bot.save_rules_to_file('minhas_regras.json')

# Carregar regras salvas
bot.load_rules_from_file('minhas_regras.json')
```

## 🔧 Solução de Problemas

### Erro: "redirect_uri_mismatch"

**Solução**: Verifique se todas as URIs de redirecionamento foram adicionadas corretamente no Google Cloud Console.

### Erro: "Arquivo credentials.json não encontrado"

**Solução**: 
1. Baixe novamente o arquivo do Google Cloud Console
2. Renomeie para `credentials.json`
3. Coloque na pasta do projeto

### Gmail API não ativada

**Solução**:
1. Vá no Google Cloud Console
2. "APIs e Serviços" → "Biblioteca"
3. Procure "Gmail API" e ative

### Bot não encontra e-mails

**Solução**: O bot processa apenas e-mails na caixa de entrada. Se não há e-mails lá, não haverá processamento.

### Permissões negadas

**Solução**:
1. Delete o arquivo `token.json`
2. Execute o bot novamente
3. Refaça a autorização no navegador

## 📝 Arquivos do Projeto

```
gmail-bot-organizer/
├── gmail_bot.py          # Script principal do bot
├── credentials.json      # Credenciais do Google (você deve criar)
├── token.json           # Token de acesso (criado automaticamente)
├── email_rules.json     # Regras personalizadas (opcional)
├── test_auth.py         # Script de teste de autenticação
└── README.md           # Este arquivo
```

## 🔐 Segurança e Privacidade

- ✅ **Seus dados ficam seguros**: O bot roda localmente no seu computador
- ✅ **Sem armazenamento externo**: Nenhum e-mail é enviado para servidores externos
- ✅ **Acesso limitado**: Usa apenas as permissões necessárias do Gmail
- ✅ **Código aberto**: Você pode revisar todo o código
- ✅ **Token local**: Credenciais ficam apenas no seu computador

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor:

1. Faça um Fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona NovaFeature'`)
4. Push para a branch (`git push origin feature/NovaFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 🙋‍♂️ Suporte

Encontrou algum problema? Abra uma [Issue](https://github.com/seu-usuario/gmail-bot-organizer/issues) no GitHub.

## ⭐ Gostou do Projeto?

Se este bot te ajudou a organizar seus e-mails, considere dar uma ⭐ no repositório!

---

**Desenvolvido com ❤️ para pessoas que querem ter um Gmail organizado e uma caixa de entrada sempre limpa!**