# Sonarqube compose file

Um projeto Docker Compose para facilitar a configuração e execução local do SonarQube, proporcionando aos desenvolvedores uma solução simples e rápida para análise de qualidade de código durante o desenvolvimento de pacotes e APIs.

## 🎯 Objetivo

Este projeto fornece uma configuração Docker Compose completa para executar o SonarQube localmente, permitindo que desenvolvedores realizem análises de qualidade de código de forma integrada ao seu fluxo de desenvolvimento, sem a necessidade de configurações complexas de infraestrutura e antecipando etapas de CI/CD.

## ⚡ Funcionalidades

- **Setup Rápido**: Configure o SonarQube em segundos com um único comando
- **Ambiente Isolado**: Execução em containers Docker, mantendo o ambiente de desenvolvimento limpo
- **Persistência de Dados**: Configuração de volumes para manter histórico de análises
- **Pronto para Produção**: Configurações otimizadas para diferentes cenários de uso
- **Multi-linguagem**: Suporte nativo para análise de projetos em diversas tecnologias


## ✅ Análise de Qualidade com SonarQube

Este projeto utiliza o **SonarQube** para garantir padrões elevados de qualidade, segurança e manutenibilidade do código.

### Benefícios do SonarQube

- **Redução de Bugs & Vulnerabilidades**: Detecta erros e riscos de segurança antes de ir para produção.
- **Código Limpo e Manutenível**: Identifica más práticas, duplicações e oportunidades de refatoração.
- **Relatórios Visuais**: Gera dashboards gráficos detalhados sobre cobertura de testes, code smells, complexidade, entre outros.
- **Aumento da Confiança**: Proporciona maior segurança ao evoluir e manter o sistema.


## 📦 Instalação

1. Clone o repositório:
```bash
git clone https://github.com/sette/sonarqube-compose.git
```

1.1 Entre no projeto:
```bash
cd sonarqube-compose
```

## 🚀 Uso

Para rodar e acompanhar no terminal:

```bash
   docker compose up 
```

Para rodar em segundo plano:

```bash
   docker compose up -d
```

## 🔧 Configuração Inicial

### 1. Acesse o SonarQube Localmente
Certifique-se que o SonarQube está rodando em sua máquina (por padrão na porta 9000).
Abra seu navegador e acesse:

http://localhost:9000

### 2. Faça login
O usuário e senha padrão são:
- **Username**: `admin`
- **Password**: `admin`

Após o primeiro login, será solicitado mudar a senha.

### 3. Crie um novo projeto
No menu lateral, clique em "Create new project" ou no botão "+" > "Create Project".
Informe um **Project Key** (identificador único para o projeto) e um **Project Display Name** (nome mostrado na UI).
Clique em "Set Up".

### 4. Escolha o método de análise
Selecione se deseja analisar manualmente ou usar um CI.
Para início rápido, selecione "Locally".

### 5. Gere um token
Será solicitado criar um token de autenticação:
- Dê um nome ao token (exemplo: `my-project-token`).
- Clique em **Generate** e copie o token.
- ⚠️ **Importante**: guarde esse token, pois ele não será mostrado novamente.

### 6. Siga as instruções para rodar o scanner
O assistente irá mostrar o comando para rodar o SonarScanner, incluindo:
- O Project Key que você acabou de criar.
- O token que você gerou.

### Como rodar a análise local

1. Garanta que o [SonarQube](https://www.sonarqube.org/downloads/) esteja rodando localmente ou use sua instância cloud.

   #### Opção 1: Criar arquivo .env na raiz do projeto
   echo "SONAR_TOKEN=seu_token_aqui" > .env

   #### Opção 2: Export direto no terminal
   export SONAR_TOKEN=seu_token_aqui

2. Execute o scanner, por exemplo:
   ```bash
   # Exemplo para projetos Node.js
   sonar-scanner \
    -Dsonar.projectKey=nome-do-projeto \
    -Dsonar.sources=. \
    -Dsonar.host.url=http://localhost:9000 \
    -Dsonar.login=${SONAR_TOKEN} \
    -Dsonar.python.version=3.11
   ```
3. Veja os resultados no painel do SonarQube.

## 📚 Referências

- [Documentação Oficial SonarQube](https://docs.sonarqube.org/)
