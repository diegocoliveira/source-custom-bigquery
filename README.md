Aqui está o `README.md` com os passos detalhados para duplicar, renomear e publicar sua imagem Docker personalizada no Docker Hub:

```markdown
# Conector Customizado do BigQuery

Este guia fornece instruções para duplicar o conector BigQuery da Airbyte, personalizar e publicar sua própria imagem Docker.

## Passo a Passo

### 1. Duplicar e Renomear a Pasta do Conector

Primeiro, faça uma cópia da pasta do conector `source-bigquery` para `source-custom-bigquery`:

```bash
cp -r /airbyte/airbyte-integrations/connectors/source-bigquery /airbyte/airbyte-integrations/connectors/source-custom-bigquery
```

### 2. Gerar a Imagem Docker do Conector Customizado

Após duplicar a pasta, gere a imagem Docker para o novo conector com o comando:

```bash
airbyte-ci connectors --name source-custom-bigquery build
```

### 3. Renomear a Imagem Docker para seu Docker Hub

Renomeie a imagem criada para o repositório do Docker Hub, substituindo `<seu_dockerhub_usuario>` pelo seu nome de usuário no Docker Hub (neste caso, `diegocoliveira07`):

```bash
docker tag airbyte/source-custom-bigquery:dev diegocoliveira07/source-custom-bigquery:0.1.4
```

### 4. Login no Docker Hub

Faça login no Docker Hub para autenticar sua conta:

```bash
docker login
```

### 5. Publicar a Imagem Docker no Docker Hub

Após o login, publique a imagem no Docker Hub:

```bash
docker push diegocoliveira07/source-custom-bigquery:0.1.4
```

---

Agora, a imagem `diegocoliveira07/source-custom-bigquery:0.1.4` estará disponível no Docker Hub e pronta para ser usada ou compartilhada!
```

