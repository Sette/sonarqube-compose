# Sonarqube compose file

# Nome do Projeto

Uma breve descrição do que seu projeto faz.

## 📦 Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/sette/sonarqube-compose.git
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

## ✅ Análise de Qualidade com SonarQube

Este projeto utiliza o **SonarQube** para garantir padrões elevados de qualidade, segurança e manutenibilidade do código.

### Benefícios do SonarQube

- **Redução de Bugs & Vulnerabilidades**: Detecta erros e riscos de segurança antes de ir para produção.
- **Código Limpo e Manutenível**: Identifica más práticas, duplicações e oportunidades de refatoração.
- **Relatórios Visuais**: Gera dashboards gráficos detalhados sobre cobertura de testes, code smells, complexidade, entre outros.
- **Aumento da Confiança**: Proporciona maior segurança ao evoluir e manter o sistema.

### Como rodar a análise local

1. Garanta que o [SonarQube](https://www.sonarqube.org/downloads/) esteja rodando localmente ou use sua instância cloud.

   # Opção 1: Criar arquivo .env na raiz do projeto
   echo "SONAR_TOKEN=seu_token_aqui" > .env

   # Opção 2: Export direto no terminal
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
