# 📊 ANS Data Extractor & Analyzer

Este projeto tem como objetivo **automatizar o download, extração e análise dos dados públicos da ANS** (Agência Nacional de Saúde Suplementar), especificamente:

- Demonstrações contábeis trimestrais das operadoras.
- Cadastro das operadoras de planos de saúde ativas.

Além disso, o projeto prepara scripts SQL para importar os dados em banco de dados e realizar análises.

---

## 📁 Estrutura do Projeto

```
pdf2csv/
│
├── dados_ans/
│   ├── demonstracoes_contabeis/    # Arquivos ZIP das demonstrações contábeis
│   └── operadoras/                 # Relatório CSV de operadoras ativas
│
├── ExtrairTabela.py               # Script de extração de tabelas de PDF para CSV e ZIP
├── baixar_arquivos_ans.py         # Script para baixar os dados da ANS
├── importar_dados.sql             # Script SQL para criação de tabelas e importação dos CSVs
├── analises.sql                   # Script SQL com consultas analíticas
└── README.md                      # Este arquivo
```

---

## ⚙️ Requisitos

- Python 3.10+
- Bibliotecas Python:
  - `pandas`
  - `requests`
  - `pdfplumber`
  - `zipfile` (embutido)

Para instalar as dependências:
```bash
pip install pandas requests pdfplumber
```

---

## 🚀 Como Usar

### 1. Baixar os Arquivos da ANS
Execute o script para baixar os arquivos necessários:
```bash
python baixar_arquivos_ans.py
```

### 2. Extrair e Converter Tabelas PDF (Opcional)
Se necessário, use `ExtrairTabela.py` para extrair tabelas específicas de PDFs:
```bash
python ExtrairTabela.py
```

### 3. Importar os dados no banco de dados
Use os scripts `.sql` fornecidos para:

- Criar as tabelas
- Importar os dados dos CSVs
- Executar análises

> Suporte para **MySQL 8+** ou **PostgreSQL 10+**.

---

## 📈 Consultas Analíticas Incluídas

- Top 10 operadoras com maiores despesas em “EVENTOS/SINISTROS CONHECIDOS” no último trimestre.
- Top 10 operadoras com maiores despesas nessa categoria no último ano.

---

## 📌 Fontes Oficiais

- [Demonstrações Contábeis ANS](https://dadosabertos.ans.gov.br/FTP/PDA/demonstracoes_contabeis/)
- [Cadastro de Operadoras Ativas](https://dadosabertos.ans.gov.br/FTP/PDA/operadoras_de_plano_de_saude_ativas/)

---

## 👨‍💻 Autor

Desenvolvido por Nicole Maximiano — Desafio técnico.
