# Passo-a-passo para cofigurar o ambiente

### 1. Instalar VS Code e suas extensões:
    - VSCode Icons;
    - Remote WSL;
    - Python;
    - Live Share;
    - Markdown Preview Enhanced;
    - docs-markdown;
    - Github Authentication;
    - Git;

### 2. Instalar o GIT;

### 3. Se usa Windows, baixe o Ubuntu no aplicativo da loja da Microsoft e execute;

### 4. No terminal ubuntu seguir os passos para instalar o Python (Se ainda não tiver):
    - Criar user
    - Criar senha
    - > sudo apt install python3-pip
    - > sudo apt update

### 5. Criar (e ativar) um ambiente virtual Python no terminal do VS Code, dentro da raiz do projeto:
    - > python3 -m venv .venv (ou virtualenv -p python3 myvenv?)   
    - > path_to_venv/Scripts/Activate.bat (não precisou ativar, pq?)


### 5. No VS Code (Terminal WSL):
    - > export PATH=${HOME}/.local/bin:$PATH pip3 install mkdocs-mermaid2-plugin
    - > mkdocs serve (Foi nesse passo que criou o arquivo "mkdocs.yml"?)

### Em qual passo é criado o arquivo index.md?

### 6. Utlize o Mermaid Live Editor para criar grafos:
    - https://mermaid.live/
    - Tutorial: https://jojozhuang.github.io/tutorial/mermaid-cheat-sheet/

### 7. Instale o plugin do Mermaid
    - > pip install mkdocs-mermaid2-plugin
    - Tutorial: https://github.com/fralau/mkdocs-mermaid2-plugin#installation


