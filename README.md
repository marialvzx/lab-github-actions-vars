# Desafio GitHub Actions - Variáveis e Escopos

## Objetivo
Esse projeto foi feito para praticar o uso de variáveis no GitHub Actions, como:
- env (variáveis de ambiente)
- vars (variáveis do repositório)
- secrets (informações sensíveis)
- GITHUB_ENV (variáveis criadas durante a execução)
- variáveis padrão do GitHub

---

## Resultados Observados

### Escopos de Variáveis
- A variável global (APP_NAME) funciona em todo o workflow
- A variável de job (BUILD_VERSION) funciona apenas dentro do job
- A variável de step (STEP_TEMP) funciona apenas no step onde foi criada

---

### Variáveis Dinâmicas
Foi gerado um número aleatório usando `$RANDOM` e ele foi salvo com `GITHUB_ENV`, podendo ser usado nos próximos passos do mesmo job.

---

### Variáveis Padrão
Foram utilizadas variáveis que o próprio GitHub fornece automaticamente, como:
- GITHUB_ACTOR
- GITHUB_REPOSITORY
- RUNNER_OS

---

## Perguntas de Reflexão

### Por que a secret aparece como ***?
Porque o GitHub protege dados sensíveis. As secrets são ocultadas automaticamente nos logs e aparecem como "***" para evitar vazamento de informações.

---

### O job deploy_app consegue acessar BUILD_VERSION?
Não. Cada job roda em um ambiente separado, então as variáveis criadas em um job não são compartilhadas com outro.

---

## Conclusão
Com esse exercício foi possível entender melhor como usar variáveis no GitHub Actions, evitar repetição de código e proteger informações importantes utilizando secrets.
