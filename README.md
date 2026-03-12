# Teste Técnico – Portfolio

Este é o repositório base para o teste técnico de desenvolvedor WordPress Senior. O projeto já está configurado com as ferramentas base necessárias: **Bedrock, Sage 11, Docker, e um banco de dados pré-configurado com ACF ativado**.

## O que já está pronto
- ✅ Ambiente Local rodando em Docker (PHP 8.3-apache + MariaDB).
- ✅ WordPress rodando como uma aplicação `Bedrock` (`web/app`).
- ✅ Setup limpo de compilação Front-End rodando `Sage 11` (pasta `web/app/themes/portfolio-theme`).
- ✅ Dump de Banco de Dados de Desenvolvimento disponível em `sql/database.sql` (contém uma instalação em branco de WP e plugins ativados).
- ✅ Advanced Custom Fields já instalado e ativo via Composer. 

## Como Iniciar

### 1. Preparando o Ambiente
Primeiro, clone este repositório para o seu ambiente local e configure o `.env`:
```bash
git clone git@github.com-weboption:weboptionwp/senior-developer-test.git
cd senior-developer-test
cp .env.example .env
```
O arquivo `.env` já vem com as variáveis corretas para rodar pelo Docker, sendo a principal alteração a porta em localhost, `http://localhost:8080`.

### 2. Subindo o Docker
Inicie os containers usando o docker-compose:
```bash
docker compose up -d
```
> O Docker irá utilizar o dump de banco de dados localizado em `sql/database.sql` na primeira vez que for iniciado para criar o seu banco de ambiente. 

O site estará acessível em: `http://localhost:8080/`
O painel admin em: `http://localhost:8080/wp/wp-admin/` (User: `admin`, Senha: `admin`)

### 3. Instalação Front-End (Theme)
Para o Sage funcionar e os assets serem compilados, você precisa rodar o script no seu tema:
```bash
cd web/app/themes/portfolio-theme
composer install
npm install
npm run dev
```

## O Seu Desafio (Requisitos Técnicos)

**O objetivo principal deste teste é testar as suas habilidades técnicas criando a lógica do Custom Post Type, Campos do ACF e montando a tela.**  

1. **Custom Post Type:** Deve criar um CPT de nome `Portfolio`.
2. **ACF Fields:** Deve abrigar os campos do Portfolio via ACF (`Cliente`, `Descrição do projeto`, `Imagem principal`, `URL do projeto`).
3. **Options Page:** Deve criar uma "Portfolio Settings" via ACF com campos para um Botão (`Texto` e `URL`) que irá na home.
4. **Bloco ACF - Portfolio Carousel:** Crie um Bloco (Gutenberg via ACF) chamado `Portfolio Carousel` com os últimos 5 projetos registrados. Cada um deve mostrar imagem, título e link para single.
5. **Template Single Pages:** Crie o `single-portfolio.blade.php` com o detalhe do portfolio.
6. **Layout e Responsividade:** Reproduzirá as Views com fidelidade Pixel-Perfect ao layout enviado pela empresa, com comportamento responsivo. 
7. Crie postagens "dummy" de teste, utilize as imagens do design para povoar o DB, e por favor recrie o arquivo `sql/database.sql` final contendo a "semente" final antes de submeter no seu repositório.

Você será avaliado pela pureza do código (10%), pela qualidade da estruturação no Sage/Bedrock (10%), domínio do ACF e Block API (20%), responsividade (25%) e fidelidade Pixel Perfect ao Layout (35%).

> Dica: Faça a configuração do CPT e Blocks usando código limpo nos arquivos do tema (ou plugin de dependência). 

### Dúvidas ou Problemas?
Entre em contato com o Recrutador(a) ou com a pessoa desenvolvedora te aplicando este teste. Boa Sorte!

### Tempo Gasto
*Preencha aqui o tempo total consumido para a realização do teste:* 
