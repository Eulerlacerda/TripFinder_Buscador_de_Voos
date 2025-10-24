# TripFinder_Buscador_de_Voos
Busca_de_passagens_areas

TripFinder - Buscador de Voos
<!-- Sugestão: Adicione um screenshot da sua aplicação aqui -->
# ✈️ TripFinder - Buscador de Voos

TripFinder é uma aplicação de desktop desenvolvida em Python que permite aos usuários buscar ofertas de voos em tempo real utilizando a API da Amadeus. Os resultados podem ser visualizados diretamente na interface e enviados por e-mail.

---

## 📑 Índice

- [Visão Geral](#visão-geral)
- [Funcionalidades](#funcionalidades)
- [Como Funciona](#como-funciona)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Configuração do Ambiente](#configuração-do-ambiente)
  - [Pré-requisitos](#pré-requisitos)
  - [Instalação](#instalação)
  - [Obtenção das Chaves de API](#obtenção-das-chaves-de-api)
- [Como Usar](#como-usar)
- [Estrutura do Código](#estrutura-do-código)
  - [Módulos Principais](#módulos-principais)
  - [Funções Chave](#funções-chave)
- [Como Contribuir](#como-contribuir)

---

## 📌 Visão Geral

Este projeto nasceu da necessidade de encontrar as melhores ofertas de voos de forma simples e automatizada. A aplicação se conecta à API Amadeus for Developers para obter dados de voos, processa essas informações e as apresenta em uma interface gráfica amigável construída com Tkinter. Além disso, oferece a funcionalidade de enviar os resultados da busca diretamente para um e-mail.

---

## ⚙️ Funcionalidades

- **Busca de Voos em Tempo Real**: Pesquisa ofertas de voos entre duas localidades (usando códigos IATA).
- **Busca em Múltiplos Períodos**: Realiza buscas automáticas para diferentes datas futuras (1, 7, 15, 30 e 60 dias à frente) para encontrar as melhores oportunidades.
- **Conversão de Moeda**: Converte os preços dos voos (originalmente em USD) para BRL.
- **Interface Gráfica Simples**: Uma janela intuitiva para inserir os dados da busca e visualizar os resultados.
- **Envio de Resultados por E-mail**: Permite que o usuário envie o relatório completo da busca para qualquer endereço de e-mail usando uma conta Gmail.

---

## 🧰 Tecnologias Utilizadas

- **Python 3**: Linguagem de programação principal.
- **Amadeus for Developers API**: Fornecedor dos dados de voos.
- **Tkinter**: Biblioteca padrão do Python para a criação da interface gráfica (GUI).
- **Dotenv**: Para gerenciamento seguro de variáveis de ambiente (chaves de API e credenciais).
- **SMTPLib**: Para o envio de e-mails através de um servidor SMTP (Gmail).

---

## 🛠️ Configuração do Ambiente

### 📋 Pré-requisitos

- Python 3.7+
- Uma conta no Amadeus for Developers para obter as chaves da API.
- Uma conta de e-mail do Gmail para ser usada como remetente.

> Importante: É necessário gerar uma "Senha de App" na sua conta Google, pois a autenticação padrão (usuário/senha) não é mais suportada por segurança. Veja como gerar uma Senha de App aqui.

### 📦 Instalação

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/tripfinder.git
cd tripfinder
Instale as dependências:

bash
pip install amadeus python-dotenv
🔑 Obtenção das Chaves de API
Crie o arquivo de ambiente:

No caminho C:/Users/Euler/Documents/TripFinder/env/ (ou em um local de sua preferência, ajustando o código), crie um arquivo chamado .env.txt.

Adicione suas credenciais ao arquivo .env.txt:

env
AMADEUS_API_KEY="SUA_API_KEY_DA_AMADEUS"
AMADEUS_API_SECRET="SEU_API_SECRET_DA_AMADEUS"
EMAIL_USER="seu_email@gmail.com"
EMAIL_PASSWORD="SUA_SENHA_DE_APP_DO_GMAIL"
Substitua os valores pelas suas credenciais reais. Atenção: A EMAIL_PASSWORD deve ser a "Senha de App" de 16 dígitos gerada pelo Google, e não a sua senha de login comum.

▶️ Como Usar
Execute o script Python:

bash
python seu_script.py
Preencha os campos na interface:

Origem (IATA): Insira o código IATA do aeroporto de partida (ex: GRU para Guarulhos).

Destino (IATA): Insira o código IATA do aeroporto de chegada (ex: JFK para Nova Iorque).

Clique em "Buscar Voos": A aplicação irá consultar a API para diferentes datas e exibir os resultados na área de texto.

Envie por E-mail (Opcional): Clique em "Enviar Resultados por E-mail". Uma caixa de diálogo solicitará o e-mail do destinatário. Após inserir o e-mail e confirmar, os resultados serão enviados.

🧱 Estrutura do Código
O script é organizado em funções modulares para facilitar a manutenção e o entendimento.

📚 Módulos Principais
os, dotenv: Carregam as credenciais de forma segura a partir de um arquivo .env.

amadeus: Cliente da API para realizar as buscas de voos.

datetime: Manipula as datas para as buscas futuras.

smtplib, email.mime.text: Constroem e enviam os e-mails.

tkinter: Constrói todos os elementos da interface gráfica.

🔧 Funções Chave
search_flights(origin, destination, min_days_ahead): Conecta-se à API da Amadeus, busca voos para uma data específica, formata os resultados e os retorna.

perform_searches(origin, destination): Orquestra múltiplas chamadas a search_flights para diferentes períodos de tempo.

send_email(subject, body, to_email): Configura uma conexão com o servidor SMTP do Gmail e envia o e-mail com os resultados.

search_flights_gui(): Função chamada pelo botão "Buscar Voos", que coleta os dados da interface e exibe os resultados.

send_results_email(): Função chamada pelo botão de envio de e-mail, que captura os resultados e solicita o e-mail do destinatário.

🤝 Como Contribuir
Contribuições são sempre bem-vindas! Se você tem uma ideia para melhorar o projeto:

Faça um Fork do projeto.

Crie uma Branch para sua nova funcionalidade:

bash
git checkout -b feature/MinhaFeature
Faça o Commit de suas alterações:

bash
git commit -m 'Adiciona MinhaFeature'
Faça o Push para a Branch:

bash
git push origin feature/MinhaFeature
Abra um Pull Request.
