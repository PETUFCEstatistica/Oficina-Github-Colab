<div align="center">

<img src="Logo_PET2.png" alt="Logo do PET Estatística UFC" width="200"/>

# Oficina de GitHub e Colab

*Aprenda a organizar um projeto de análise de dados, versioná-lo no GitHub e executá-lo no Google Colab, usando os anúncios do Airbnb em Nova York (2019) como exemplo.*

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PETUFCEstatistica/Oficina-Github-Colab/blob/main/codigos/01-limpeza_de_dados.ipynb)
[![Baixar Notebook](https://img.shields.io/badge/Baixar-Notebook-blue?logo=jupyter&logoColor=white)](https://github.com/PETUFCEstatistica/Oficina-Github-Colab/raw/main/codigos/01-limpeza_de_dados.ipynb)
[![Usar este template](https://img.shields.io/badge/Usar_este-template-2ea44f?logo=github&logoColor=white)](https://github.com/PETUFCEstatistica/Oficina-Github-Colab/generate)
[![Site](https://img.shields.io/badge/Site-Visitar-orange?logo=googlechrome&logoColor=white)](https://sites.google.com/view/petestatisticaufc/)
[![Licença: GPL-3.0](https://img.shields.io/badge/Licen%C3%A7a-GPL--3.0-yellow)](LICENSE)

</div>

---

## Sumário

- [Oficina de GitHub e Colab](#oficina-de-github-e-colab)
  - [Sumário](#sumário)
  - [Sobre a oficina](#sobre-a-oficina)
  - [Antes de começar](#antes-de-começar)
  - [O que vamos construir](#o-que-vamos-construir)
  - [Parte 1: Criar o repositório no GitHub](#parte-1-criar-o-repositório-no-github)
    - [Passo 1.1: Criar o repositório com os arquivos essenciais](#passo-11-criar-o-repositório-com-os-arquivos-essenciais)
    - [Passo 1.2: Escolher a licença](#passo-12-escolher-a-licença)
    - [Passo 1.3: Criar a estrutura de pastas e o `requirements.txt`](#passo-13-criar-a-estrutura-de-pastas-e-o-requirementstxt)
    - [Passo 1.4: Adicionar os dados brutos](#passo-14-adicionar-os-dados-brutos)
    - [Passo 1.5: Primeira versão do README](#passo-15-primeira-versão-do-readme)
  - [Parte 2: Conectar o Colab ao GitHub e usar o Git](#parte-2-conectar-o-colab-ao-github-e-usar-o-git)
    - [Passo 2.1: Criar o notebook](#passo-21-criar-o-notebook)
    - [Passo 2.2: Criar um token de acesso](#passo-22-criar-um-token-de-acesso)
    - [Passo 2.3: Clonar o repositório no Colab](#passo-23-clonar-o-repositório-no-colab)
    - [Passo 2.4: Comandos básicos do Git](#passo-24-comandos-básicos-do-git)
    - [Passo 2.5: Salvar o notebook no GitHub e sincronizar](#passo-25-salvar-o-notebook-no-github-e-sincronizar)
  - [Parte 3: Limpeza e análise exploratória](#parte-3-limpeza-e-análise-exploratória)
  - [Parte 4: Usando este repositório de Template](#parte-4-usando-este-repositório-de-template)
  - [Boas práticas](#boas-práticas)
  - [Problemas comuns](#problemas-comuns)
  - [Créditos](#créditos)
  - [Licença](#licença)

## Sobre a oficina

Esta oficina foi realizada em **12/11/2026** pelos alunos participantes do **PET Estatística** da Universidade Federal do Ceará (UFC).

Durante a aula, você vai construir o **seu próprio repositório do zero**, seguindo este tutorial. Este repositório é o **resultado final**, um gabarito de referência: se o tempo acabar, você pode abrir, baixar ou clonar os notebooks daqui e continuar depois (veja a [Parte 4](#parte-4-se-o-tempo-acabar)).

Ao longo da oficina, você vai:

1. Criar o repositório e configurar os arquivos essenciais (`.gitignore`, `LICENSE`, `README.md`) e a estrutura de pastas
2. Entender **como estruturar os arquivos** de um projeto de análise de dados.
3. Organizar o projeto no Colab e aprender os comandos básicos do Git.
4. Fazer a **limpeza** e uma **análise exploratória básica** dos anúncios do Airbnb em Nova York em 2019.
5. Salvar o seu trabalho de volta no GitHub.

> [!IMPORTANT]
> **Esta não é uma análise estatística completa.** O foco é o *fluxo de trabalho* (organização, versionamento e execução). A análise exploratória serve de exemplo prático, e o relatório em LaTeX é apenas um esqueleto para você adaptar aos seus próprios projetos.

Este README foi escrito como um **tutorial**: você pode acompanhá-lo durante a oficina ou refazer tudo depois, no seu ritmo.

## Antes de começar

Você vai precisar de:

- Uma conta no [GitHub](https://github.com/signup) (gratuita).
- Uma conta Google, para usar o [Google Colab](https://colab.research.google.com/).
- Um navegador e conexão com a internet. Não é necessário instalar nada no computador.

## O que vamos construir

Organizar bem os arquivos desde o início evita bagunça e facilita a colaboração. Esta é a estrutura final do projeto:

```
Oficina-Github-Colab/
├── codigos/
│   ├── 01-limpeza_de_dados.ipynb
│   └── 02-analise_exploratoria.ipynb
├── dados/
│   ├── brutos/
│   │   └── dados-brutos.csv
│   └── limpos/
│       └── dados-limpos.csv
├── relatorio/
│   └── relatorio-final.tex
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

O que cada pasta guarda:

- `codigos/`: Notebooks da análise. O prefixo numérico (`01-`, `02-`...) indica a **ordem de execução**.
- `dados/brutos/`: Dados originais, **exatamente como foram obtidos**. Nunca edite esses arquivos.
- `dados/limpos/`: Dados já tratados, gerados pelo código. Se algo der errado, basta refazer a partir dos brutos.
- `relatorio/`: Relatório final em LaTeX.

Arquivos importantes para todo repositório:

- `.gitignore`: Lista de arquivos que o Git deve **ignorar** (temporários, checkpoints, senhas etc.).
- `requirements.txt`: Bibliotecas Python necessárias, para que qualquer pessoa reproduza o ambiente.
- `LICENSE`: Define como outras pessoas podem usar o seu código.
- `README.md`: A "porta de entrada" do projeto, que é este arquivo.

> Conforme o projeto cresce, a estrutura pode ganhar novos arquivos, como `03-inferencia.ipynb`, uma pasta `relatorio/sessoes/` (com `introducao.tex`, `metodologia.tex`, `resultados.tex`...) e um `refs.bib` para as referências.

> [!TIP]
> Evite espaços e acentos em nomes de arquivos e pastas. Prefira `dados-limpos.csv` a `Dados Limpos.csv`.

---

## Parte 1: Criar o repositório no GitHub

### Passo 1.1: Criar o repositório com os arquivos essenciais

1. No GitHub, clique no **+** (canto superior direito) e em **New repository**.
2. Preencha os campos:

   | Campo | O que escolher |
   |-------|----------------|
   | **Repository name** | Um nome sem espaços, como `oficina-github-colab` |
   | **Description** | Uma frase sobre o projeto |
   | **Visibility** | **Public** |
   | **Add README file** | Ativado |
   | **Add .gitignore** | Ativado, com o template **Python** |
   | **Add license** | Ativado (veja o Passo 1.2) |

3. Clique em **Create repository**.

> [!IMPORTANT]
> **O `.gitignore` vem primeiro.** Ele precisa existir *antes* dos seus primeiros commits: depois que o Git passa a rastrear um arquivo, ignorá-lo não o remove do histórico. É por isso que configuramos tudo já na criação do repositório.

O template **Python** já ignora arquivos que você não quer versionar, como `.ipynb_checkpoints/`, `__pycache__/` e `.env` (onde costumam ficar senhas). Como este projeto também tem LaTeX, vamos acrescentar algumas linhas:

1. Abra o `.gitignore` no seu repositório e clique no lápis (**Edit**).
2. Adicione ao final do arquivo:

   ```
   # LaTeX
   relatorio/build/
   *.aux
   *.log
   *.bbl
   *.blg
   *.synctex.gz
   ```

3. Clique em **Commit changes**.

### Passo 1.2: Escolher a licença

Sem licença, ninguém pode legalmente usar ou modificar o seu código. Algumas opções comuns:

| Licença | Em resumo |
|---------|-----------|
| **MIT** | Muito permissiva: qualquer pessoa pode usar e modificar o código, mantendo o aviso de copyright. |
| **Apache-2.0** | Permissiva, com concessão explícita de patentes. |
| **GPL-3.0** | *Copyleft*: trabalhos derivados precisam continuar abertos, com a mesma licença. É a usada nesta oficina. |

O site [choosealicense.com](https://choosealicense.com/) ajuda a decidir. Lembre-se de que a licença do **código** não é a mesma dos **dados**: confira sempre as condições de uso da fonte dos dados.

### Passo 1.3: Criar a estrutura de pastas e o `requirements.txt`

O Git **não rastreia pastas vazias**: uma pasta só existe no repositório se tiver pelo menos um arquivo dentro. Por convenção, usamos um arquivo vazio chamado `.gitkeep` para "segurar" a pasta.

1. No seu repositório, clique em **Add file > Create new file**.
2. No campo do nome, digite `codigos/.gitkeep`. A barra (`/`) cria a pasta automaticamente. Deixe o conteúdo em branco.
3. Clique em **Commit changes**.
4. Repita para `dados/brutos/.gitkeep`, `dados/limpos/.gitkeep` e `relatorio/.gitkeep`.

Depois, crie o arquivo `requirements.txt` (também em **Add file > Create new file**) com as bibliotecas que vamos usar:

```
pandas
numpy
matplotlib
seaborn
plotly
```

### Passo 1.4: Adicionar os dados brutos

1. Baixe o arquivo [`dados-brutos.csv`](https://github.com/PETUFCEstatistica/Oficina-Github-Colab/raw/main/dados/brutos/dados-brutos.csv) deste repositório de referência.
2. No seu repositório, entre na pasta `dados/brutos/`.
3. Clique em **Add file > Upload files**, arraste o CSV e clique em **Commit changes**.

### Passo 1.5: Primeira versão do README

Clique no lápis do `README.md` e escreva um título e uma frase de descrição. Vamos voltar a ele no final, quando já tivermos resultados.

> **Checkpoint:** ao final da Parte 1, o seu repositório deve ter `.gitignore`, `LICENSE`, `README.md`, `requirements.txt` e as pastas `codigos/`, `dados/brutos/` (com o CSV), `dados/limpos/` e `relatorio/`.

---

## Parte 2: Conectar o Colab ao GitHub e usar o Git

### Passo 2.1: Criar o notebook

1. Acesse [colab.research.google.com](https://colab.research.google.com/) e clique em **Novo notebook**.
2. Clique no título (`Untitled0.ipynb`) e renomeie para `01-limpeza_de_dados.ipynb`.

### Passo 2.2: Criar um token de acesso

O Colab roda em uma máquina virtual temporária. Para que ela possa **enviar** alterações ao seu repositório, ela precisa provar que é você, e para isso usamos um *token de acesso* (uma espécie de senha com permissões limitadas).

1. No GitHub, clique na sua foto > **Settings** > **Developer settings** > **Personal access tokens** > **Fine-grained tokens** > **Generate new token**.
2. Defina um nome e uma validade curta (por exemplo, 7 dias).
3. Em **Repository access**, escolha **Only select repositories** e selecione o seu repositório.
4. Em **Permissions > Repository permissions**, defina **Contents** como **Read and write**.
5. Clique em **Generate token** e **copie o token** (ele só é mostrado uma vez).
6. No Colab, clique no ícone de chave (**Secrets**) na barra lateral, depois em **Adicionar novo secret**. Use o nome `GITHUB_TOKEN`, cole o token no valor e **ative o acesso ao notebook**.

> [!WARNING]
> O token é como uma senha. Nunca o cole diretamente no código, não o publique e não o mostre na tela (por exemplo, evite rodar `!git remote -v`, que o exibe).

### Passo 2.3: Clonar o repositório no Colab

Na primeira célula do notebook:

```python
from google.colab import userdata
import os

token = userdata.get("GITHUB_TOKEN")
USUARIO = "SEU-USUARIO"
REPO = "SEU-REPOSITORIO"

# Baixa o repositório para a máquina virtual do Colab
if not os.path.exists(REPO):
   !git clone https://{token}@github.com/{USUARIO}/{REPO}.git

%cd {REPO}

# Identifica quem assina os commits
!git config --global user.name "Seu Nome"
!git config --global user.email "seu-email@exemplo.com"
```

- `if not os.path.exists(REPO)` confirma que não foi clonado duas vezes e evita erros.
- `git clone` copia o repositório do GitHub para o Colab.
- `%cd` entra na pasta do projeto, para que os caminhos (como `dados/brutos/dados-brutos.csv`) funcionem a partir da raiz.
- `git config` define o nome e o e-mail que aparecem nos seus commits.

> **Atenção:** cada notebook do Colab tem a sua própria sessão. Quando você abrir outro notebook (por exemplo, o `02`), precisará repetir essa célula.

### Passo 2.4: Comandos básicos do Git

O Git trabalha em etapas. Primeiro você **escolhe** o que entra no próximo "pacote" de alterações, depois **fecha** o pacote com uma mensagem e, por fim, **envia** ao GitHub:

```
 Sua pasta de trabalho
        │  git add
        ▼
 Área de preparação (staging)
        │  git commit
        ▼
 Histórico local
        │  git push                ▲
        ▼                          │  git pull
      GitHub  ─────────────────────┘
```

| Comando | O que faz |
|---------|-----------|
| `git status` | Mostra o que mudou e o que está preparado para o commit |
| `git add arquivo` | Coloca um arquivo na área de preparação (`git add .` coloca tudo) |
| `git commit -m "mensagem"` | Registra uma versão no histórico, com uma mensagem que explica a mudança |
| `git push` | Envia seus commits para o GitHub |
| `git pull` | Traz para o Colab as mudanças que estão no GitHub |
| `git log --oneline` | Lista o histórico de commits |
| `git diff` | Mostra exatamente o que foi alterado nos arquivos |

No Colab, coloque `!` na frente dos comandos. Experimente:

```python
!git status
!git log --oneline
```

### Passo 2.5: Salvar o notebook no GitHub e sincronizar

O notebook em si é salvo pelo menu do Colab, enquanto os arquivos que o código gera (CSVs, por exemplo) são enviados com os comandos do Git.

1. No Colab, vá em **Arquivo > Salvar uma cópia no GitHub** (na primeira vez, autorize o acesso).
2. Escolha o repositório e a branch `main`, informe o caminho `codigos/01-limpeza_de_dados.ipynb` e escreva uma mensagem de commit, como "Adiciona notebook de limpeza".
3. De volta ao notebook, traga essa mudança para o Colab:

   ```python
   !git pull
   !ls codigos
   ```

O notebook agora aparece na pasta do Colab. É por isso que o `git pull` existe: o GitHub recebeu um commit que a sua cópia local ainda não tinha.

---

## Parte 3: Limpeza e análise exploratória

---

## Parte 4: Usando este repositório de Template

Este repositório contém os notebooks finalizados, para você olhar, executar e usar como ponto de partida:

| Notebook | Descrição | Abrir |
|----------|-----------|-------|
| `01-limpeza_de_dados.ipynb` | Leitura, tratamento e salvamento da base limpa | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PETUFCEstatistica/Oficina-Github-Colab/blob/main/codigos/01-limpeza_de_dados.ipynb) |
| `02-analise_exploratoria.ipynb` | Análise exploratória e gráficos | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PETUFCEstatistica/Oficina-Github-Colab/blob/main/codigos/02-analise_exploratoria.ipynb) |

Caso você queira copiar este repositório como um template para sua conta clique em **Use this template** > **Create a new repository** (ou em **Fork**). Um clone sozinho **não** publica nada na sua conta, pois continua apontando para este repositório. Para publicar, é preciso ter o seu próprio repositório no GitHub.

Caso deseje apenas **clonar** copie o repositório para o Colab ou para o seu computador através deste código:

   ```python
   !git clone https://github.com/PETUFCEstatistica/Oficina-Github-Colab.git
   %cd Oficina-Github-Colab
   ```
> [!TIP]
> **Ficou para trás na Parte 1 ou 2?** Crie a sua cópia pelo template e continue direto da [Parte 3](#parte-3-limpeza-e-análise-exploratória). Depois você refaz o passo a passo com calma.

--- 

## Boas práticas

- **Nunca altere os dados brutos.** Toda transformação deve estar escrita em código, para ser reproduzível.
- **Faça commits pequenos e frequentes**, com mensagens que expliquem o que mudou.
- **Rode `git pull` antes de `git push`** para evitar conflitos.
- **Numere os notebooks** na ordem em que devem ser executados.
- **Liste as dependências** em `requirements.txt` para que outras pessoas consigam rodar o seu projeto.
- **Nunca envie senhas, tokens ou dados sensíveis** ao GitHub. Se um segredo for publicado por engano, revogue-o imediatamente.
- **Cuidado com o tamanho dos arquivos:** o GitHub bloqueia arquivos acima de 100 MB.
- **Documente** a origem dos dados, as decisões de limpeza e as limitações da análise.

## Problemas comuns

| Problema | Solução |
|----------|---------|
| `FileNotFoundError` ao ler o CSV | Você esqueceu de rodar a célula de clonagem (`git clone` + `%cd`). Rode `!pwd` para conferir se está na pasta do projeto. |
| `destination path already exists` ao clonar | O repositório já foi clonado nesta sessão. Pule o `git clone` e use apenas `%cd NOME-DO-REPOSITORIO`. |
| Erro ao ler `GITHUB_TOKEN` | Confira o nome do secret e se o **acesso ao notebook** está ativado. |
| `Authentication failed` ou erro `403` | O token está incorreto, expirou, não inclui o seu repositório ou não tem permissão **Contents: Read and write**. |
| `! [rejected] ... fetch first` no `push` | O GitHub tem commits que você ainda não tem. Rode `!git pull` e depois `!git push`. |
| `divergent branches` no `pull` | Rode `!git pull --no-rebase`. |
| `nothing to commit` | Nada mudou desde o último commit. Use `!git status` para conferir. |
| Uma pasta vazia não aparece no GitHub | O Git não rastreia pastas vazias. Adicione um arquivo `.gitkeep` dentro dela. |
| Meu trabalho sumiu | A sessão do Colab expirou antes de você enviar. Envie ao GitHub com frequência. |

## Créditos

Material elaborado por **Gabriel Sena** ([@Gabrielsena-eng](https://github.com/Gabrielsena-eng)) para o **PET Estatística** da Universidade Federal do Ceará.

## Licença

Este projeto está licenciado sob a **GNU General Public License v3.0**. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
