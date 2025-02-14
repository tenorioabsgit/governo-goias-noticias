# 📰 Web Scraping - Notícias do Governo de Goiás

Este projeto realiza **web scraping** das notícias publicadas no portal oficial do **Governo de Goiás** (`https://goias.gov.br`), extraindo **títulos, links, datas, categorias e conteúdos completos** das notícias.

## 📌 Funcionalidades

✅ Coleta de **títulos**, **links** e **datas** das notícias  
✅ Extração do **conteúdo completo** de cada notícia  
✅ Organização dos dados em um **arquivo CSV**  
✅ Utiliza as bibliotecas **rvest, httr e dplyr** para manipulação dos dados  

---

## 🛠 Tecnologias Utilizadas

- **Linguagem:** R
- **Pacotes:** `rvest`, `httr`, `dplyr`
- **Formato de saída:** `.csv` (valores separados por vírgula)

---

## 📂 Estrutura do Código

```
📁 /  (Diretório Raiz)
├── webscraping_goias_gov.R   # Código principal do Web Scraping
└── noticias_goias_gov.csv    # Arquivo de saída com as notícias extraídas
```

---

## 🚀 Como Executar

### 1️⃣ **Instalar os pacotes necessários**
Antes de rodar o script, certifique-se de que os pacotes **rvest**, **httr** e **dplyr** estão instalados no R. Para instalá-los, execute:

```r
install.packages(c("rvest", "httr", "dplyr"))
```

### 2️⃣ **Executar o Script**
Rode o script `webscraping_goias_gov.R` no RStudio ou diretamente no R:

```r
source("webscraping_goias_gov.R")
```

### 3️⃣ **Aguardar a Coleta dos Dados**
O código irá percorrer todas as páginas de notícias do site (`1226 páginas`), coletando os dados e armazenando no arquivo `noticias_goias_gov.csv`.

---

## 📊 Estrutura do Arquivo de Saída (`noticias_goias_gov.csv`)

O CSV gerado terá a seguinte estrutura:

| Título | Link | Publicação | Última Atualização | Categoria | Conteúdo |
|--------|------|------------|--------------------|-----------|----------|
| Título da Notícia | URL da Notícia | Data de Publicação | Última Atualização | Categoria(s) | Texto Completo |

---

## 🛑 Possíveis Problemas e Soluções

### ⚠️ **Erro de Bloqueio pelo Site**
Se o site bloquear a requisição, tente alterar o **User-Agent** dentro do script:

```r
pagina <- GET(url, add_headers('User-Agent' = 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, como Gecko) Chrome/91.0.4472.124 Safari/537.36'))
```

### ⏳ **O Processo Está Muito Lento?**
- O site pode ter **limites de requisição**, então experimente adicionar **pausas** entre as requisições:

```r
Sys.sleep(3)  # Espera 3 segundos antes de carregar a próxima página
```

---

🚀 **Pronto para coletar dados!** Se tiver dúvidas, me avise! 😊
