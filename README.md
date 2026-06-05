# 📘 Guia Completo de Git, GitHub e Fluxo Profissional

## Índice

- [Visão geral](#visão-geral)
- [1. Fundamentos do fluxo de trabalho](#1-fundamentos-do-fluxo-de-trabalho)
  - [Áreas do Git](#áreas-do-git)
  - [Comandos essenciais para se orientar](#comandos-essenciais-para-se-orientar)
- [2. Configuração inicial](#2-configuração-inicial)
  - [Configurações úteis](#configurações-úteis)
- [3. Criando ou clonando um repositório](#3-criando-ou-clonando-um-repositório)
  - [Criando localmente](#criando-localmente)
  - [Clonando do GitHub](#clonando-do-github)
  - [Conectando um remoto manualmente](#conectando-um-remoto-manualmente)
- [4. `.gitignore` e proteção de arquivos sensíveis](#4-gitignore-e-proteção-de-arquivos-sensíveis)
  - [Regras práticas](#regras-práticas)
  - [Se um segredo já foi commitado](#se-um-segredo-já-foi-commitado)
- [5. Primeiro commit e boas mensagens](#5-primeiro-commit-e-boas-mensagens)
  - [Commit inicial](#commit-inicial)
  - [Conventional Commits](#conventional-commits)
  - [Exemplos](#exemplos)
- [6. Autenticação no GitHub](#6-autenticação-no-github)
  - [SSH](#ssh)
  - [PAT](#pat)
- [7. Branches e estratégia de trabalho](#7-branches-e-estratégia-de-trabalho)
  - [GitHub Flow](#github-flow)
  - [Git Flow](#git-flow)
  - [Quando recomendar cada um](#quando-recomendar-cada-um)
- [8. Git Flow na prática](#8-git-flow-na-prática)
  - [Inicialização](#inicialização)
  - [Criando uma feature](#criando-uma-feature)
  - [Criando release](#criando-release)
  - [Criando hotfix](#criando-hotfix)
- [9. Comandos essenciais do dia a dia](#9-comandos-essenciais-do-dia-a-dia)
  - [Status, histórico e diferenças](#status-histórico-e-diferenças)
  - [Branches](#branches)
  - [Sincronização](#sincronização)
  - [Tags](#tags)
- [10. Desfazendo alterações com segurança](#10-desfazendo-alterações-com-segurança)
  - [Antes do commit](#antes-do-commit)
  - [Depois do commit](#depois-do-commit)
  - [Comando perigoso](#comando-perigoso)
- [11. Stash para mudanças temporárias](#11-stash-para-mudanças-temporárias)
- [12. Pull Requests profissionais](#12-pull-requests-profissionais)
  - [Fluxo básico](#fluxo-básico)
  - [Estrutura recomendada de PR](#estrutura-recomendada-de-pr)
  - [Boas práticas de PR](#boas-práticas-de-pr)
  - [Estratégias de merge](#estratégias-de-merge)
- [13. Como analisar Pull Requests](#13-como-analisar-pull-requests)
  - [Exemplos de comentários úteis](#exemplos-de-comentários-úteis)
  - [Quando aprovar ou pedir mudanças](#quando-aprovar-ou-pedir-mudanças)
- [14. Issues bem escritas](#14-issues-bem-escritas)
  - [Tipos comuns](#tipos-comuns)
  - [Estrutura recomendada para bug](#estrutura-recomendada-para-bug)
  - [Estrutura recomendada para feature](#estrutura-recomendada-para-feature)
  - [Labels úteis](#labels-úteis)
- [15. GitHub Projects](#15-github-projects)
  - [Estrutura simples que funciona bem](#estrutura-simples-que-funciona-bem)
  - [Boas práticas](#boas-práticas-1)
  - [Automação útil](#automação-útil)
- [16. GitHub Actions](#16-github-actions)
  - [Onde fica](#onde-fica)
  - [Exemplo de workflow de CI para Node.js](#exemplo-de-workflow-de-ci-para-nodejs)
  - [Gatilhos mais comuns](#gatilhos-mais-comuns)
  - [Conceitos principais](#conceitos-principais)
- [17. CI/CD na prática](#17-cicd-na-prática)
  - [CI — Integração Contínua](#ci--integração-contínua)
  - [CD — Entrega ou deploy contínuo](#cd--entrega-ou-deploy-contínuo)
  - [Boas práticas de CI/CD](#boas-práticas-de-cicd)
- [18. Segurança no GitHub e nas Actions](#18-segurança-no-github-e-nas-actions)
  - [Regras essenciais](#regras-essenciais)
  - [Permissões mínimas em workflow](#permissões-mínimas-em-workflow)
  - [Riscos comuns](#riscos-comuns)
  - [Branch protection recomendada](#branch-protection-recomendada)
  - [Dependabot e varredura](#dependabot-e-varredura)
- [19. Forks e contribuições externas](#19-forks-e-contribuições-externas)
- [20. GitHub Agents e automação assistida por IA](#20-github-agents-e-automação-assistida-por-ia)
  - [Usos úteis](#usos-úteis)
  - [Limites importantes](#limites-importantes)
  - [Regra prática](#regra-prática)
- [21. Organização de um repositório profissional](#21-organização-de-um-repositório-profissional)
  - [Arquivos importantes](#arquivos-importantes)
- [22. Checklist antes de push, PR e merge](#22-checklist-antes-de-push-pr-e-merge)
  - [Antes do push](#antes-do-push)
  - [Antes de abrir PR](#antes-de-abrir-pr)
  - [Antes do merge](#antes-do-merge)
- [23. Comandos que valem decorar](#23-comandos-que-valem-decorar)
- [24. Glossário rápido](#24-glossário-rápido)
- [25. Recomendação prática final](#25-recomendação-prática-final)

## Visão geral

Este guia foi reorganizado para servir como referência prática de trabalho profissional com **Git e GitHub**, cobrindo desde a configuração inicial até colaboração, segurança, CI/CD, GitHub Projects, Issues, Pull Requests, GitHub Actions e GitHub Agents. O foco é o caminho mais seguro, limpo e comum no mercado.

## 1. Fundamentos do fluxo de trabalho

Fluxo mais comum no dia a dia:

```text
clone -> branch -> commit -> push -> pull request -> review -> merge
```

O Git controla o histórico localmente. O GitHub entra como plataforma de colaboração, revisão, automação e governança do repositório.

### Áreas do Git

```text
Arquivos modificados -> Staging Area -> Repositório local -> Repositório remoto
   working tree           git add           git commit           git push
```

### Comandos essenciais para se orientar

```bash
git status
git log --oneline --graph --all
git diff
git diff --staged
```

## 2. Configuração inicial

Configure sua identidade uma vez por máquina:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
git config --list
```

### Configurações úteis

```bash
# Pull com rebase
git config --global pull.rebase true

# Remove branches remotas apagadas
git config --global fetch.prune true

# Reaproveita resolução de conflitos
git config --global rerere.enabled true
```

Essas opções ajudam a manter o histórico mais limpo e reduzem trabalho repetido ao sincronizar branches.

## 3. Criando ou clonando um repositório

### Criando localmente

```bash
cd api-rest-didatica
git init
git status
```

### Clonando do GitHub

```bash
git clone https://github.com/SEU_USUARIO/api-rest-didatica.git
cd api-rest-didatica
```

### Conectando um remoto manualmente

```bash
git remote add origin https://github.com/SEU_USUARIO/api-rest-didatica.git
git remote -v
git push -u origin main
```

## 4. `.gitignore` e proteção de arquivos sensíveis

O `.gitignore` evita versionar arquivos que não devem ir para o repositório.

Exemplo comum:

```gitignore
node_modules/
.env
.env.*
dist/
build/
coverage/
*.log
prisma/dev.db
.vscode/
.DS_Store
```

### Regras práticas

- Nunca suba `.env`, chaves privadas, tokens, certificados ou dumps de banco.
- Dependências instaladas localmente não devem ser commitadas.
- Arquivos gerados por build, cache e cobertura de testes geralmente não devem entrar no Git.

### Se um segredo já foi commitado

⚠️ **Risco real:** apagar o arquivo e fazer novo commit não remove o segredo do histórico.

Ação recomendada:
1. Revogue imediatamente o token, senha ou chave.
2. Remova o arquivo do repositório atual.
3. Reescreva o histórico só se necessário e com alinhamento da equipe.
4. Force rotação das credenciais expostas.

## 5. Primeiro commit e boas mensagens

### Commit inicial

```bash
git add .
git diff --staged
git commit -m "feat: estrutura inicial da API REST"
```

### Conventional Commits

Padrão recomendado:

```text
<tipo>: <descrição curta>
```

Tipos mais usados:

- `feat`: nova funcionalidade
- `fix`: correção de bug
- `docs`: documentação
- `refactor`: refatoração sem alterar regra de negócio
- `test`: testes
- `chore`: manutenção técnica
- `ci`: pipeline e automação
- `build`: empacotamento e dependências de build

### Exemplos

```bash
git commit -m "feat: adiciona autenticação JWT"
git commit -m "fix: corrige validação de email"
git commit -m "docs: atualiza guia de instalação"
git commit -m "ci: adiciona workflow de testes"
```

## 6. Autenticação no GitHub

O uso de senha no terminal não é o fluxo recomendado. Prefira **SSH** para uso recorrente ou **Personal Access Token (PAT)** quando necessário.

### SSH

```bash
ssh-keygen -t ed25519 -C "seu@email.com"
cat ~/.ssh/id_ed25519.pub
ssh -T git@github.com
```

Depois de cadastrar a chave pública no GitHub:

```bash
git remote set-url origin git@github.com:SEU_USUARIO/api-rest-didatica.git
```

### PAT

Use token com o menor escopo possível. Evite criar token com permissões amplas sem necessidade.

## 7. Branches e estratégia de trabalho

Existem dois modelos muito comuns:

| Modelo | Quando usar | Vantagem principal | Cuidado |
|---|---|---|---|
| GitHub Flow | Apps e times com deploy frequente | Simples e rápido | Requer `main` sempre saudável |
| Git Flow | Projetos com releases planejadas | Organização forte por tipo de branch | Pode ficar mais pesado no dia a dia |

### GitHub Flow

Estrutura simples:

- `main`: branch principal
- `feature/nome-da-tarefa`: branch de trabalho
- PR para revisar e integrar

Exemplo:

```bash
git switch main
git pull origin main
git switch -c feature/autenticacao-jwt
```

### Git Flow

Branches clássicas:

- `main`: produção
- `develop`: integração
- `feature/*`: novas funcionalidades
- `release/*`: preparação de versão
- `hotfix/*`: correções urgentes em produção

### Quando recomendar cada um

- Para projetos pessoais, times pequenos e CI/CD contínuo, prefira **GitHub Flow**.
- Para produtos com ciclos formais de release, homologação e versões controladas, **Git Flow** pode fazer sentido.

## 8. Git Flow na prática

### Inicialização

```bash
git flow init
```

### Criando uma feature

```bash
git flow feature start autenticacao-jwt
# ... commits ...
git flow feature finish autenticacao-jwt
git push origin develop
```

### Criando release

```bash
git flow release start v1.0.0
# ajustes finais
git add .
git commit -m "chore: prepara release v1.0.0"
git flow release finish v1.0.0
git push origin main
git push origin develop
git push origin --tags
```

### Criando hotfix

```bash
git flow hotfix start corrige-validacao-email
# correção
git add .
git commit -m "fix: corrige validação de email"
git flow hotfix finish corrige-validacao-email
git push origin main
git push origin develop
git push origin --tags
```

## 9. Comandos essenciais do dia a dia

### Status, histórico e diferenças

```bash
git status
git log --oneline --graph --decorate --all
git diff
git diff --staged
```

### Branches

```bash
git branch -a
git switch -c nome-da-branch
git switch main
git branch -d nome-da-branch
git push origin --delete nome-da-branch
```

### Sincronização

```bash
git fetch origin
git pull origin main
git push origin main
git push -u origin feature/minha-feature
```

### Tags

```bash
git tag v1.0.0
git tag
git push origin --tags
```

## 10. Desfazendo alterações com segurança

⚠️ Esta é a parte com maior risco de perda de trabalho.

### Antes do commit

```bash
# Descarta alteração local de um arquivo
git restore src/server.js

# Remove do staging, mas mantém a alteração no arquivo
git restore --staged src/server.js
```

### Depois do commit

```bash
# Desfaz o último commit, mas mantém as mudanças
git reset --soft HEAD~1

# Cria um novo commit revertendo outro commit
git revert abc1234
```

### Comando perigoso

```bash
git reset --hard HEAD~1
```

Use `reset --hard` só quando tiver certeza absoluta de que pode perder as alterações locais. Em branch compartilhada, prefira `git revert`.

## 11. Stash para mudanças temporárias

```bash
git stash
git stash list
git stash pop
git stash apply stash@{0}
```

Exemplo de uso: surgiu uma correção urgente e o trabalho atual ainda não está pronto para commit.

## 12. Pull Requests profissionais

Pull Request é a forma padrão de revisar, discutir e aprovar mudanças antes do merge.

### Fluxo básico

```bash
git switch main
git pull origin main
git switch -c feature/minha-feature
# ... commits ...
git push -u origin feature/minha-feature
```

No GitHub:
1. Abra o PR.
2. Defina a base correta (`main` ou `develop`).
3. Preencha título, contexto, motivação e checklist.
4. Peça review.
5. Faça ajustes, se necessário.
6. Faça merge após aprovação e checks verdes.

### Estrutura recomendada de PR

```md
## O que foi feito
- Adiciona autenticação JWT
- Protege rotas privadas

## Por que foi feito
- Necessário para controlar acesso de usuários

## Como testar
- Rodar `npm test`
- Fazer login e acessar rota protegida

## Checklist
- [x] Testes passando
- [x] Sem segredos no código
- [x] Documentação atualizada
```

### Boas práticas de PR

- PR pequeno é mais fácil de revisar.
- Um PR deve resolver um problema claro.
- Não misture refatoração grande com correção pequena sem necessidade.
- Sempre explique impacto técnico e funcional.

### Estratégias de merge

| Tipo | Quando usar | Vantagem | Cuidado |
|---|---|---|---|
| Create a merge commit | Preservar contexto do PR | Histórico explícito | Pode gerar mais nós no grafo |
| Squash and merge | PR com muitos commits intermediários | Histórico mais limpo | Apaga granularidade dos commits |
| Rebase and merge | Histórico linear | Leitura limpa | Exige disciplina com ordem dos commits |

Na maioria dos times, `Squash and merge` é excelente para PRs pequenos e médios.

## 13. Como analisar Pull Requests

Ao revisar um PR, avalie em ordem:

1. **Objetivo:** o PR resolve o problema proposto?
2. **Segurança:** há segredos, permissões excessivas ou risco de injeção?
3. **Legibilidade:** nomes, organização, duplicação e clareza.
4. **Impacto:** o que pode quebrar?
5. **Testes:** existem testes cobrindo o cenário?
6. **CI:** a automação passou sem falhas?

### Exemplos de comentários úteis

- `Sugestão: extrair essa validação para uma função separada para facilitar teste.`
- `Risco: esta action está usando permissões amplas demais. Dá para reduzir para read?`
- `Faltou cobrir o caso de erro quando o token expira.`
- `Esse nome de variável não deixa claro se o valor está em segundos ou milissegundos.`

### Quando aprovar ou pedir mudanças

- **Approve:** quando o código atende objetivo, qualidade e segurança.
- **Request changes:** quando há risco real, bug, falha de segurança, quebra de fluxo ou ausência crítica de testes.
- **Comment:** quando é melhoria opcional ou dúvida de entendimento.

## 14. Issues bem escritas

Issues organizam trabalho, bugs, melhorias e tarefas técnicas.

### Tipos comuns

- Bug
- Feature
- Refactor
- Documentation
- Technical debt
- Security

### Estrutura recomendada para bug

```md
## Descrição
Ao tentar fazer login, a API retorna 500.

## Passos para reproduzir
1. Enviar POST para /login
2. Informar email e senha válidos
3. Observar erro

## Resultado esperado
Retornar 200 com token JWT.

## Resultado atual
Retorna 500.

## Ambiente
Node 20, Windows 11
```

### Estrutura recomendada para feature

```md
## Objetivo
Permitir autenticação com JWT.

## Valor
Restringe acesso a rotas privadas.

## Critérios de aceitação
- Login retorna token
- Rotas privadas exigem bearer token
- Testes cobrindo sucesso e falha
```

### Labels úteis

- `bug`
- `enhancement`
- `documentation`
- `good first issue`
- `help wanted`
- `security`
- `priority:high`

## 15. GitHub Projects

GitHub Projects ajuda a transformar Issues e PRs em fluxo visual de trabalho.

### Estrutura simples que funciona bem

| Coluna | Uso |
|---|---|
| To Do | Ainda não iniciado |
| In Progress | Em desenvolvimento |
| In Review | Em PR ou revisão |
| Done | Finalizado |

### Boas práticas

- Cada card deve apontar para uma Issue ou PR.
- Use campos como prioridade, responsável e sprint quando fizer sentido.
- Evite quadro cheio de tarefas vagas; quebre trabalho grande em partes menores.

### Automação útil

- Issue criada -> entra em `To Do`
- PR aberto -> vai para `In Review`
- PR merged -> vai para `Done`

## 16. GitHub Actions

GitHub Actions é o sistema de automação do GitHub. Ele executa workflows para teste, lint, build, deploy e tarefas operacionais.

### Onde fica

```text
.github/workflows/
```

### Exemplo de workflow de CI para Node.js

```yaml
name: CI

on:
  pull_request:
  push:
    branches: [main, develop]

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: npm

      - name: Install
        run: npm ci

      - name: Lint
        run: npm run lint --if-present

      - name: Test
        run: npm test

      - name: Build
        run: npm run build --if-present
```

### Gatilhos mais comuns

- `push`: executa quando há push.
- `pull_request`: executa em PRs.
- `workflow_dispatch`: execução manual.
- `schedule`: execução agendada.

### Conceitos principais

- **workflow**: arquivo YAML completo
- **job**: conjunto de etapas
- **step**: ação ou comando individual
- **runner**: máquina que executa o job
- **action**: componente reutilizável

## 17. CI/CD na prática

### CI — Integração Contínua

Objetivo: validar automaticamente cada mudança.

Checklist mínimo de CI:

- Instalar dependências
- Rodar lint
- Rodar testes
- Gerar build
- Bloquear merge se algo falhar

### CD — Entrega ou deploy contínuo

Depois que a CI estiver confiável, o deploy pode ser automatizado com segurança.

Exemplo simples de deploy manual:

```yaml
name: Deploy

on:
  workflow_dispatch:

permissions:
  contents: read

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Deploy
        run: echo "Executar script de deploy aqui"
```

### Boas práticas de CI/CD

- Separe CI de deploy quando o projeto crescer.
- Exija aprovação para ambiente de produção.
- Nunca grave segredos no YAML.
- Use ambientes (`environments`) para controlar produção e homologação.

## 18. Segurança no GitHub e nas Actions

Segurança não é detalhe; é parte do fluxo profissional.

### Regras essenciais

- Use `Secrets` e `Variables` do GitHub para credenciais.
- Aplique **menor privilégio** em tokens e permissões das Actions.
- Prefira Actions oficiais ou bem auditadas.
- Fixe versões estáveis das Actions, evitando referências soltas quando possível.
- Proteja branches principais com regras de revisão.

### Permissões mínimas em workflow

```yaml
permissions:
  contents: read
```

Só aumente permissões quando houver necessidade clara, por exemplo publicar pacote, comentar em PR ou gerar release.

### Riscos comuns

- `pull_request_target` mal usado com código de fork.
- Exposição de segredos em logs.
- Uso de `GITHUB_TOKEN` com permissões além do necessário.
- Execução de scripts não confiáveis baixados em tempo de execução.

### Branch protection recomendada

- Exigir PR antes de merge
- Exigir status checks aprovados
- Exigir branch atualizada antes do merge
- Bloquear force push em `main`
- Exigir ao menos 1 review

### Dependabot e varredura

Ative recursos como:

- Dependabot alerts
- Dependabot security updates
- Secret scanning
- Code scanning

## 19. Forks e contribuições externas

Quando o projeto recebe PRs de forks, a atenção com segurança precisa aumentar.

### Cuidados importantes

- Não exponha segredos para workflows disparados por código não confiável.
- Revise com atenção alterações em `.github/workflows/`.
- Evite executar deploy automaticamente a partir de PR externo.

Fluxo comum de contribuição:

```text
fork -> clone -> branch -> commit -> push -> pull request para o repositório original
```

## 20. GitHub Agents e automação assistida por IA

Agents no ecossistema GitHub podem ajudar em revisão, geração de testes, resumo de mudanças e apoio operacional. Eles aceleram trabalho, mas não substituem revisão humana.

### Usos úteis

- Resumir PRs grandes
- Sugerir testes ausentes
- Detectar padrões repetitivos
- Apoiar triagem de Issues
- Explicar falhas de CI

### Limites importantes

- Não confiar cegamente em código gerado.
- Revisar impacto em segurança e arquitetura.
- Nunca conceder permissões excessivas a bots sem necessidade.
- Toda automação com escrita em repositório deve ter trilha clara de auditoria.

### Regra prática

Use agent para ganhar velocidade, mas mantenha aprovação humana para merge, segurança, deploy e mudanças estruturais.

## 21. Organização de um repositório profissional

Estrutura comum:

```text
.github/
  workflows/
src/
tests/
docs/
.env.example
.gitignore
README.md
LICENSE
```

### Arquivos importantes

- `README.md`: visão geral, instalação, uso e comandos
- `.env.example`: modelo de variáveis sem segredos
- `CONTRIBUTING.md`: como contribuir
- `CODEOWNERS`: responsáveis por revisão por área
- `SECURITY.md`: como reportar vulnerabilidades

## 22. Checklist antes de push, PR e merge

### Antes do push

- [ ] Estou na branch correta
- [ ] Rodei testes locais
- [ ] Não há `.env`, token ou segredo no commit
- [ ] A mensagem de commit está clara
- [ ] Não subi arquivos desnecessários

### Antes de abrir PR

- [ ] A branch está atualizada
- [ ] O PR tem objetivo claro
- [ ] Descrevi como testar
- [ ] Relacionei Issue quando existir
- [ ] CI passando

### Antes do merge

- [ ] Reviews concluídos
- [ ] Checks obrigatórios verdes
- [ ] Sem conflitos pendentes
- [ ] Estratégia de merge escolhida conscientemente

## 23. Comandos que valem decorar

```bash
git status
git add .
git commit -m "feat: minha alteração"
git switch -c feature/minha-feature
git fetch origin
git pull origin main
git push -u origin feature/minha-feature
git restore arquivo.txt
git restore --staged arquivo.txt
git revert <hash>
git stash
```

## 24. Glossário rápido

| Termo | Significado |
|---|---|
| Repositório | Projeto com histórico versionado |
| Commit | Registro de uma mudança |
| Branch | Linha paralela de desenvolvimento |
| Merge | União de histórico entre branches |
| Rebase | Reaplicação de commits sobre outra base |
| Tag | Marca imutável de versão |
| PR | Pull Request para revisão e merge |
| Issue | Registro de tarefa, bug ou melhoria |
| Workflow | Automação do GitHub Actions |
| Runner | Máquina que executa jobs |
| Secret | Credencial protegida no GitHub |
| Fork | Cópia do repositório para outra conta |

## 25. Recomendação prática final

Se a meta for adotar um fluxo moderno, simples e seguro, a combinação mais equilibrada para a maioria dos projetos é:

1. `main` protegida
2. Branch por tarefa
3. Commits padronizados
4. PR obrigatório
5. CI rodando lint, testes e build
6. GitHub Projects para organização
7. Secrets, branch protection e permissões mínimas nas Actions

Esse conjunto já coloca o repositório em um padrão profissional muito bom.

Dica Pro: trate `.github/workflows/` e permissões de token com o mesmo cuidado que trata código de produção.

