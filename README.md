<div align="center">

<img src="Logo_PET2.png" alt="drawing" width="200"/>

# Oficina de GitHub e Colab

*Análise estatística dos anúncios do Airbnb em Nova York (2019), desenvolvida na oficina do PET.*

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Gabrielsena-eng/Oficina-PET/blob/main/codigo/01-limpeza-de-dados.ipynb)
[![Baixar Notebook](https://img.shields.io/badge/Baixar-Notebook-blue?logo=jupyter&logoColor=white)](https://github.com/Gabrielsena-eng/Oficina-PET/raw/main/codigo/01-limpeza-de-dados.ipynb)
[![Site](https://img.shields.io/badge/Site-Visitar-green?logo=googlechrome&logoColor=white)](https://seu-site.com)
[![Licença: MIT](https://img.shields.io/badge/Licen%C3%A7a-MIT-yellow)](LICENSE)

</div>

---

## Sobre o projeto

Este repositório reúne a análise de dados feita durante a oficina do **PET**. O objetivo é praticar o fluxo de uma análise estatística através da plataforma Colab, e publicar seu projeto em GitHub.: limpeza dos dados, análise exploratória, aplicação de métodos estatísticos e redação de um relatório final em LaTeX.


## Estrutura padrão para Análise de Dados:

```
├── codigo/
│   ├── 01-limpeza-de-dados.ipynb
│   ├── 02-analise-exploratoria.ipynb
│   └── 03-<outras-analises>.ipynb
├── dados/
│   ├── brutos/
│   │   └── AB_NYC_2019.csv        # dados originais (não editar)
│   └── limpos/
│       └── AB_NYC_limpo.csv       # base tratada
├── relatorio/
│   ├── build/                     # arquivos gerados na compilação
│   ├── relatorio-final.tex
│   ├── refs.bib
│   └── sessoes/
│       ├── preambulo.tex
│       ├── introducao.tex
│       ├── metodologia.tex
│       ├── aplicacoes.tex
│       └── resultados.tex
├── .gitignore
├── requirements.txt
├── LICENSE
└── README.md
```

## Dados

- **Fonte:** *AB_NYC_2019*, dados abertos de anúncios do Airbnb na cidade de Nova York em 2019. [LINK DO KAGGLE AQUI]
- **Descrição:** cada linha representa um anúncio de hospedagem. [Informar número de linhas e colunas.]
- **Principais variáveis:** [Nomes das variáveis.]
- **Dados brutos:** `dados/brutos/AB_NYC_2019.csv`
- **Dados limpos:** `dados/limpos/AB_NYC_limpo.csv`, gerado pelo notebook `01-limpeza-de-dados.ipynb`.

### Tratamentos aplicados

[Liste aqui o que foi feito na limpeza. Exemplos:]

- Remoção de registros duplicados
- Tratamento de valores ausentes em `reviews_per_month` e `last_review`
- Remoção de preços iguais a zero ou valores atípicos
- Conversão de tipos de variáveis

## Como executar

### No Google Colab

1. Clique no botão **Abrir no Colab** no topo desta página, ou use *Arquivo > Abrir notebook > GitHub*.
2. Na primeira célula, clone o repositório e instale as dependências:

   ```python
   !git clone https://github.com/Gabrielsena-eng/Oficina-PET.git
   %cd Oficina-PET
   !pip install -r requirements.txt
   ```

3. Execute os notebooks da pasta `codigo/` em ordem numérica.

### Localmente

```bash
git clone https://github.com/Gabrielsena-eng/Oficina-PET.git
cd Oficina-PET
pip install -r requirements.txt
jupyter notebook
```

## Notebooks

| Notebook | Descrição |
|----------|-----------|
| `01-limpeza-de-dados.ipynb` | Lê os dados brutos, trata valores ausentes e inconsistências e salva a base em `dados/limpos/` |
| `02-analise-exploratoria.ipynb` | Estatísticas descritivas e visualizações |
| `03-<outras-analises>.ipynb` | [Modelos, testes e demais análises] |

## Relatório

O relatório final é escrito em LaTeX e fica na pasta `relatorio/`. O arquivo principal é `relatorio-final.tex`, e cada seção está separada em `relatorio/sessoes/` (introdução, metodologia, aplicações e resultados). As referências ficam em `refs.bib`.

Para compilar:

```bash
cd relatorio
pdflatex -output-directory=build relatorio-final.tex
bibtex build/relatorio-final
pdflatex -output-directory=build relatorio-final.tex
pdflatex -output-directory=build relatorio-final.tex
```

> Se preferir, o relatório também pode ser compilado no Overleaf, enviando a pasta `relatorio/`.

## Autor

**Gabriel Sena** · [GitHub](https://github.com/Gabrielsena-eng)

## Licença

Este projeto está licenciado sob a Licença GNU General Public License v3.0. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
