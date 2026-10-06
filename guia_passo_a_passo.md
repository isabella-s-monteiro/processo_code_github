# Guia Passo a Passo — Python, VS Code, Git e GitHub

Este guia mostra, do zero, como preparar um ambiente para trabalhar com projetos em Python e armazená-los no GitHub.

> **Importante:** você não precisa conhecer Python, Git ou GitHub para começar. O guia explica os termos e mostra o que deve acontecer em cada etapa.

## Antes de começar: segurança

Nunca coloque no código ou no GitHub:

* senhas;
* tokens;
* chaves de API;
* credenciais;
* dados pessoais ou confidenciais.

Se um arquivo contém informações sensíveis, ele não deve ser enviado ao repositório.

---

# 1. O que vamos fazer

Ao final, o fluxo será:

```text
Criar conta no GitHub
        ↓
Criar pasta do projeto
        ↓
Instalar/verificar Python
        ↓
Instalar VS Code
        ↓
Conhecer o terminal
        ↓
Criar ambiente virtual (venv)
        ↓
Instalar bibliotecas
        ↓
Instalar/verificar Git
        ↓
Criar repositório no GitHub
        ↓
Conectar o projeto ao GitHub
        ↓
Fazer o primeiro commit
        ↓
Enviar o projeto (push)
        ↓
Testar se tudo está funcionando
```

---

# 2. Glossário rápido

Antes de começar, conheça os principais termos usados neste guia.

### Python

Linguagem de programação utilizada para desenvolver os códigos do projeto.

### VS Code

Programa usado para escrever, editar e organizar códigos.

### Terminal

Janela em que você executa comandos de texto para dar instruções ao computador.

Neste guia, usaremos principalmente o terminal integrado do VS Code.

### Git

Ferramenta de controle de versão. Ele registra alterações feitas no projeto e permite acompanhar seu histórico.

### GitHub

Plataforma online onde repositórios Git podem ser armazenados, compartilhados e colaborados.

### Repositório

Espaço que reúne os arquivos de um projeto e o histórico das alterações feitas nele.

### Biblioteca

Conjunto de códigos já desenvolvidos por outras pessoas que pode ser instalado para adicionar funcionalidades ao Python.

### Ambiente virtual (`venv`)

Ambiente isolado para instalar as bibliotecas utilizadas por um determinado projeto.

### Commit

Registro de um conjunto de alterações no histórico do Git.

### Push

Envia os commits do computador para o repositório remoto, como o GitHub.

### Pull

Busca alterações existentes no repositório remoto e traz essas alterações para o computador.

### `.gitignore`

Arquivo que informa ao Git quais arquivos e pastas devem ser ignorados e não enviados ao repositório.

### `main`

Nome normalmente utilizado para a principal branch do projeto.

### `origin`

Nome padrão usado pelo Git para identificar o repositório remoto conectado ao projeto local.

---

# 3. Criar uma conta no GitHub

Se você ainda não possui uma conta:

1. Acesse o GitHub.
2. Clique em **Sign up**.
3. Informe seu endereço de e-mail.
4. Crie sua senha.
5. Escolha seu nome de usuário.
6. Confirme seu endereço de e-mail.
7. Faça login.

Pronto. Sua conta está criada.

> **Atenção:** Git e GitHub não são a mesma coisa. O Git é uma ferramenta instalada no computador. O GitHub é um serviço online.

---

# 4. Criar a pasta do projeto

Crie uma pasta para o projeto.

Por exemplo:

```text
C:\projetos\meu-projeto
```

Use um nome claro e simples.

Evite nomes genéricos como:

```text
trabalho-aula-1
atividade-python
teste
novo projeto final definitivo
```

Prefira um nome que descreva o conteúdo do projeto.

Se possível, utilize uma pasta local, como `C:\projetos`. Pastas sincronizadas por serviços como OneDrive podem, em alguns casos, causar conflitos ou problemas com ambientes virtuais.

### Resultado esperado

Você terá uma pasta vazia destinada ao projeto.

---

# 5. Instalar ou verificar o Python

Instale o Python caso ainda não esteja instalado.

Depois, abra o terminal e execute:

```bash
python --version
```

Em alguns computadores, pode ser necessário utilizar:

```bash
py --version
```

### Resultado esperado

O terminal deve mostrar uma versão do Python, por exemplo:

```text
Python 3.x.x
```

Não é necessário utilizar exatamente a mesma versão mostrada neste guia.

### Se não funcionar

Se aparecer uma mensagem informando que Python não foi encontrado:

1. verifique se o Python está instalado;
2. tente `py --version`;
3. se necessário, instale o Python;
4. feche e abra novamente o VS Code depois da instalação.

---

# 6. Instalar o VS Code

O VS Code será o ambiente utilizado para organizar e editar o projeto.

Depois da instalação:

1. Abra o VS Code.
2. Selecione **File > Open Folder**.
3. Abra a pasta criada para o projeto.

### Resultado esperado

A pasta do projeto aparecerá no painel lateral do VS Code.

---

# 7. Conhecer o terminal do VS Code

O terminal é uma interface de texto usada para executar comandos no computador.

No VS Code, abra:

**Terminal → New Terminal**

O terminal aparecerá na parte inferior da janela.

Neste guia, ele será usado para executar comandos do Python e do Git.

---

# 8. Criar o ambiente virtual

O ambiente virtual (`venv`) mantém as bibliotecas deste projeto separadas das bibliotecas de outros projetos.

No terminal, dentro da pasta do projeto:

```bash
python -m venv .venv
```

Isso criará uma pasta chamada:

```text
.venv
```

> O ambiente virtual fica dentro da pasta do projeto, mas **não será enviado para o GitHub**.

## Ativar o ambiente virtual

No Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Quando estiver ativo, normalmente aparecerá algo como:

```text
(.venv)
```

no início da linha do terminal.

### Se o PowerShell bloquear a ativação

Se aparecer um erro relacionado à execução de scripts, utilize:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

Essa alteração vale somente para a sessão atual do PowerShell.

Depois tente novamente:

```powershell
.\.venv\Scripts\Activate.ps1
```

### Resultado esperado

O terminal deverá indicar que o ambiente `.venv` está ativo.

---

# 9. Instalar as bibliotecas

Com o ambiente virtual ativado, instale as bibliotecas necessárias.

Exemplo:

```bash
pip install pandas matplotlib openpyxl
```

### O que são essas bibliotecas?

* **pandas:** análise e manipulação de dados;
* **matplotlib:** criação de gráficos;
* **openpyxl:** leitura e escrita de arquivos Excel.

### Resultado esperado

O terminal deverá indicar que as bibliotecas foram instaladas.

Você pode testar:

```bash
python -c "import pandas, matplotlib, openpyxl; print('OK')"
```

Resultado esperado:

```text
OK
```

---

# 10. Sair do ambiente virtual

Quando terminar de trabalhar no ambiente virtual, você pode sair dele com:

```bash
deactivate
```

O indicador:

```text
(.venv)
```

deixará de aparecer no terminal.

---

# 11. O que fazer no dia seguinte?

Você **não precisa criar o ambiente virtual novamente**.

Também não precisa instalar novamente as bibliotecas.

O fluxo será:

```text
Abrir o VS Code
        ↓
Abrir a pasta do projeto
        ↓
Abrir o terminal
        ↓
Ativar o .venv
        ↓
Trabalhar no projeto
        ↓
git status
        ↓
git add .
        ↓
git commit
        ↓
git push
```

Para ativar novamente:

```powershell
.\.venv\Scripts\Activate.ps1
```

---

# 12. Instalar ou verificar o Git

O Git é responsável pelo controle de versões do projeto.

Verifique se está instalado:

```bash
git --version
```

### Resultado esperado

Algo semelhante a:

```text
git version 2.x.x
```

Se o comando não for reconhecido, instale o Git e abra novamente o VS Code.

---

# 13. Criar o repositório no GitHub

Entre na sua conta do GitHub.

Crie um novo repositório.

Informe um nome para o repositório.

Para este primeiro projeto, é recomendável criar o repositório remoto **sem adicionar automaticamente**:

* README;
* `.gitignore`;
* licença.

Isso permite que o primeiro envio seja feito a partir do projeto que já está no computador.

Depois, clique para criar o repositório.

### Resultado esperado

Você terá um repositório vazio no GitHub.

---

# 14. Iniciar o Git no projeto

Volte ao terminal do VS Code.

Certifique-se de estar dentro da pasta do projeto.

Execute:

```bash
git init
```

O Git passará a controlar o projeto.

### Resultado esperado

O terminal informará que um repositório Git foi inicializado.

---

# 15. Criar o `.gitignore`

Crie um arquivo chamado:

```text
.gitignore
```

Para um projeto Python, ele deve incluir pelo menos:

```gitignore
.venv/
__pycache__/
*.pyc
```

O objetivo é impedir que arquivos desnecessários ou específicos do ambiente local sejam enviados ao GitHub.

> Arquivos de dados, como CSV e XLSX, não devem ser ignorados automaticamente. Antes de enviá-los, verifique se não contêm informações confidenciais ou restritas.

---

# 16. Verificar o projeto

Execute:

```bash
git status
```

O Git mostrará quais arquivos ainda não estão sendo acompanhados.

### Resultado esperado

Você deverá ver os arquivos do projeto listados como novos ou não rastreados.

---

# 17. Adicionar os arquivos

Para preparar os arquivos para o próximo commit:

```bash
git add .
```

Depois confira:

```bash
git status
```

Os arquivos deverão aparecer como preparados para commit.

---

# 18. Criar o primeiro commit

Execute:

```bash
git commit -m "Configura projeto inicial"
```

Um commit é um registro das alterações no histórico do projeto.

### Resultado esperado

O Git informará que os arquivos foram registrados no commit.

---

# 19. Conectar o projeto ao GitHub

No GitHub, copie o endereço do repositório criado.

Depois, no terminal:

```bash
git remote add origin URL_DO_REPOSITORIO
```

Substitua `URL_DO_REPOSITORIO` pelo endereço do seu repositório.

Depois verifique:

```bash
git remote -v
```

### Resultado esperado

O Git deverá mostrar o endereço do repositório remoto associado ao nome:

```text
origin
```

---

# 20. Definir a branch principal

Utilize:

```bash
git branch -M main
```

Isso define `main` como o nome da branch principal local.

---

# 21. Fazer o primeiro push

Agora envie o projeto para o GitHub:

```bash
git push -u origin main
```

O Git enviará os commits locais para o repositório remoto.

### Resultado esperado

Ao atualizar a página do GitHub, os arquivos do projeto deverão aparecer.

---

# 22. Se o `git push` for recusado

**Não execute comandos aleatoriamente para tentar resolver o problema.**

Primeiro leia a mensagem exibida pelo Git.

Se o repositório remoto já tiver alterações que não existem no computador, o Git pode impedir o `push`.

Isso pode acontecer, por exemplo, quando o repositório do GitHub já foi criado com um README ou outro arquivo.

Nesse caso, não utilize automaticamente:

```bash
git push --force
```

O `--force` pode substituir o histórico remoto e causar perda de alterações.

Também não utilize automaticamente:

```bash
git pull --allow-unrelated-histories
```

Esse comando pode ser necessário em determinados cenários, mas não deve ser apresentado como uma solução universal para iniciantes.

**Regra:** leia a mensagem de erro e identifique primeiro o cenário.

---

# 23. Conferir o GitHub

Abra o repositório no GitHub.

Confira se:

* os arquivos aparecem;
* o código está disponível;
* o `.venv` não aparece;
* o histórico de commits está disponível;
* o README aparece corretamente, se houver um;
* nenhum arquivo contém senha, token ou chave de API.

---

# 24. Rotina normal de trabalho

Depois que tudo estiver configurado, o processo será muito mais simples.

### Começar a trabalhar

Ative o ambiente virtual:

```powershell
.\.venv\Scripts\Activate.ps1
```

### Verificar alterações

```bash
git status
```

### Adicionar alterações

```bash
git add .
```

### Registrar alterações

```bash
git commit -m "Descrição da alteração"
```

### Enviar para o GitHub

```bash
git push
```

---

# 25. O que NÃO fazer

* Não envie a pasta `.venv/`.
* Não coloque senhas, tokens ou chaves de API no código.
* Não envie dados pessoais ou confidenciais.
* Não execute comandos encontrados aleatoriamente na internet sem entender o que fazem.
* Não use `git push --force` simplesmente porque o `push` apresentou um erro.
* Não apague arquivos do projeto para tentar resolver um problema do Git sem entender a causa.
* Não crie um novo ambiente virtual toda vez que abrir o projeto.
* Não instale bibliotecas fora do ambiente virtual sem saber por que está fazendo isso.

---

# 26. O que é obrigatório e o que é opcional?

## Necessário para este guia

* Python
* VS Code
* extensão Python do VS Code
* Git
* ambiente virtual (`venv`)
* bibliotecas utilizadas pelo projeto
* conta no GitHub

## Opcional

Dependendo do projeto, você poderá utilizar:

* Jupyter Notebook;
* GitLens;
* outras extensões do VS Code;
* outras bibliotecas Python.

Não instale ferramentas apenas porque aparecem em tutoriais. Instale aquilo que o projeto realmente precisa.

---

# 27. Teste final

Ao terminar a configuração, execute os testes abaixo.

### Python

```bash
python --version
```

Deve retornar uma versão do Python.

### Git

```bash
git --version
```

Deve retornar a versão instalada do Git.

### Bibliotecas

Com o `.venv` ativado:

```bash
python -c "import pandas, matplotlib, openpyxl; print('OK')"
```

O resultado esperado é:

```text
OK
```

### Git

```bash
git status
```

O comando deve funcionar sem apresentar erro.

### GitHub

No repositório remoto, confirme:

* os arquivos aparecem;
* `.venv` não aparece;
* o último commit está registrado;
* não existem senhas, tokens ou informações confidenciais.

## Configuração concluída

Se todos os testes acima funcionarem, o ambiente está configurado e o projeto está conectado ao GitHub.

---

# 28. Resumo do processo

Depois de aprender o fluxo, você poderá pensar nele assim:

```text
PYTHON
  ↓
VS CODE
  ↓
TERMINAL
  ↓
.venv
  ↓
BIBLIOTECAS
  ↓
GIT
  ↓
REPOSITÓRIO LOCAL
  ↓
COMMIT
  ↓
GITHUB
  ↓
PUSH
```

O objetivo não é apenas copiar comandos.

É entender **onde você está, o que está fazendo, por que está fazendo e como verificar se funcionou**.
