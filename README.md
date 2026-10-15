# 📱 Oficina: Construindo o Manual do WhatsApp do Zero com Quarto e GitHub Pages

Guia rápido com as **principais informações**, **comandos de terminal** e **símbolos (tags)** utilizados durante a oficina prática de criação do livro digital.

---

## 📌 Informações Gerais da Oficina

* **Duração estimada:** 3 horas e 15 minutos (em 8 blocos práticos).
* **Objetivo:** Cada participante constrói seu próprio manual do WhatsApp, aprende a formatar textos e imagens em Markdown e publica o material em dois formatos:
  1. **Site interativo na internet:** acessível no celular via GitHub Pages (`https://usuario.github.io/manual-pulsar/`);
  2. **Livro digital em PDF:** pronto para impressão (`_book/Manual-do-WhatsApp.pdf`).
* **Metodologia:** Mão na massa — a turma cria as pastas, cria os arquivos `.qmd`, digita as tags e acompanha o resultado ao vivo.
* **Ferramentas utilizadas:**
  * **VS Code:** mesa de trabalho (edição dos textos e arquivos);
  * **Quarto CLI:** máquina de impressão (compila o site e o PDF);
  * **Git e GitHub:** vitrine digital (guarda as versões e coloca o site no ar).

---

## 📥 Material da Aula (Download das Imagens)

Para realizar a oficina, baixe o pacote contendo as capturas de tela do WhatsApp Web:

👉 **[Clique aqui para baixar o pacote de imagens (Google Drive)](https://drive.google.com/file/d/1Fi1HxUDPvNNlldcuLDVbm84iVEPHdyCG/view?usp=drive_link)**

> **Como usar:** Após baixar o arquivo compactado, extraia e copie a pasta `images/` para dentro da pasta do seu projeto `manual-pulsar/`.

---

## ⌨️ Todos os Comandos Utilizados na Oficina (Em Ordem de Uso)

Execute os comandos no terminal do Windows (**PowerShell**) ou no terminal integrado do VS Code (`Ctrl + '` ou menu `Terminal > New Terminal`).

### 1. Preparação e Identificação (Bloco 2)
Diz ao computador quem é o autor das versões salvas:
```powershell
# Identificar o seu nome completo (entre aspas)
git config --global user.name "Seu Nome Completo"

# Identificar o mesmo e-mail cadastrado na sua conta do GitHub
git config --global user.email "seu-email@exemplo.com"

# Conferir se as informações foram salvas corretamente
git config --global --list
```

---

### 2. Criação do Projeto do Livro (Bloco 3)
Executado dentro da pasta `Documentos\manual\`:
```powershell
# Cria a estrutura inicial de um livro em branco
quarto create project book manual-pulsar

# Entra na pasta do projeto recém-criado
cd manual-pulsar

# Abre o projeto diretamente no VS Code
code .
```

---

### 3. Visualização em Tempo Real / Prévia (Blocos 4 e 5)
Executado no terminal do VS Code para acompanhar a construção das páginas:
```powershell
# Inicia o servidor local e abre o navegador
quarto preview
```
> **Dica:** O navegador atualiza sozinho a cada arquivo salvo (`Ctrl + S`).  
> **Para parar a prévia** e liberar o terminal para outros comandos: clique no terminal e pressione `Ctrl + C` (digite `S` e dê `Enter` se solicitado).

---

### 4. Geração do PDF Final (Bloco 6)
Executado com a prévia parada:
```powershell
# Compila todo o livro e cria a pasta _book com o site e o PDF
quarto render
```
> O arquivo gerado fica em: `manual-pulsar\_book\Manual-do-WhatsApp.pdf`.

---

### 5. Publicação no GitHub Pages (Bloco 7)
Coloca o site no ar na internet:
```powershell
# Envia a versão compilada para o branch gh-pages do seu repositório no GitHub
quarto publish gh-pages
```
* Quando perguntar se confirma o endereço de publicação: digite `Y` e pressione `Enter`.
* Autorize o acesso no navegador se solicitado.

---

### 6. Ciclo de Atualização Pós-Aula (Bloco 8)
Para fazer alterações ou adicionar novos capítulos no futuro:
1. Edite o arquivo no VS Code e confira com `quarto preview`;
2. No VS Code, vá em **Source Control** (`Ctrl + Shift + G`), escreva uma mensagem e clique em **Commit** > **Sync Changes**;
3. Publique a nova versão no ar com o comando sem confirmação:
   ```powershell
   quarto publish gh-pages --no-prompt
   ```
4. Atualize a página do site no navegador com `Ctrl + F5`.

---

## 🏗️ A "Fórmula de 5 Passos" para Criar Qualquer Página

Toda página nova no manual segue este ciclo:

```text
1. Criar Pasta (New Folder) ➔ 2. Criar Arquivo .qmd (New File) ➔ 3. Escrever Textos e Tags ➔ 4. Registrar no _quarto.yml ➔ 5. Salvar e Ver no Navegador
```

1. **Criar a pasta no VS Code** (ex.: `basico`, `conversas`, `grupos`);
2. **Criar o arquivo `.qmd`** (ex.: `conhecendo.qmd`, `perfil.qmd`, `mensagens.qmd`);
3. **Escrever o conteúdo com as tags** (títulos, listas, imagens e caixas);
4. **Cadastrar o arquivo no `_quarto.yml`** respeitando o recuo de 2 espaços por nível;
5. **Salvar (`Ctrl + S`)** e conferir o resultado atualizado na prévia (`quarto preview`).

---

## 🏷️ Guia Rápido de Tags e Símbolos (Markdown)

| O que você quer criar | Como você escreve no arquivo `.qmd` | Resultado visual |
|---|---|---|
| **Título do Capítulo** | `# Meu Capítulo {#sec-rotulo}` | **1 Meu Capítulo** |
| **Seção / Subtítulo** | `## Minha Seção` | **1.1 Minha Seção** |
| **Título sem Número** | `## Apresentação {.unnumbered}` | **Apresentação** |
| **Texto em Negrito** | `**clique aqui**` | **clique aqui** |
| **Texto em Itálico** | `*palavra em inglês*` | *palavra em inglês* |
| **Passos Numerados** | `1. Primeiro passo`<br>`2. Segundo passo` | 1. Primeiro passo<br>2. Segundo passo |
| **Subitens (3 espaços)** | `   - Detalhe ou opção A` | &nbsp;&nbsp;&nbsp;◦ Detalhe ou opção A |
| **Lista com Bolinhas** | `- Item da lista` | • Item da lista |
| **Inserir Imagem** | `![Legenda da foto](../images/foto.jpg){#fig-rotulo}` | Imagem com borda e legenda numerada |
| **Tecla do Teclado** | `<kbd>Enter</kbd>` | Botão visual cinza: <kbd>Enter</kbd> |
| **Código ou Símbolo** | `` `@` `` ou `` `web.whatsapp.com` `` | Texto monoespaçado de máquina |
| **Link para Capítulo** | `veja no @sec-rotulo` | Link automático: veja no <u>Capítulo 1</u> |
| **Link para Figura** | `como na @fig-rotulo` | Link automático: como na <u>Figura 1.1</u> |
| **Caixa de Dica** | `::: {.callout-tip}`<br>`## Título`<br>`Texto da dica.`<br>`:::` | Bloco de destaque com ícone de lâmpada |
| **Caixa de Cuidado** | `::: {.callout-warning}`<br>`## Cuidado`<br>`Texto de alerta.`<br>`:::` | Bloco de destaque com aviso |
| **Caixa de Observação** | `::: {.callout-note}`<br>`## Nota`<br>`Texto da nota.`<br>`:::` | Bloco de destaque neutro |
| **Tabela Simples** | `\| Coluna 1 \| Coluna 2 \|`<br>`\|---\|---\|`<br>`\| Dado A \| Dado B \|` | Tabela formatada em linhas e colunas |

---

## ⌨️ Atalhos Úteis do Teclado

* `Ctrl + S`: Salva o arquivo atual (atualiza a prévia do navegador na hora);
* `Ctrl + C` (no terminal): Interrompe o processo ativo (ex.: encerra o `quarto preview`);
* `Ctrl + Shift + G`: Abre o painel do Git / Source Control no VS Code;
* `Ctrl + '` (ou `Ctrl + J`): Mostra/esconde o terminal integrado;
* `Shift + 3`: Insere o símbolo `#` (cerquilha);
* `Shift + 8`: Insere o asterisco `*`;
* `Shift + ;`: Insere os dois-pontos `:` (usado em `:::`);
* `Shift + teclas [ e ]`: Insere as chaves `{ }`.

---

## ⚠️ Regras de Ouro para Evitar Erros

1. **Linha em branco obrigatória:** Sempre pule uma linha vazia entre um parágrafo, um título, uma lista, uma imagem ou uma caixa `:::`. Sem essa linha vazia, o Quarto junta tudo no mesmo parágrafo.
2. **Espaços no `_quarto.yml`, nunca Tab:** O alinhamento das linhas na ficha do livro deve ser feito usando a **barra de espaço** (2 espaços a cada nível de recuo). Usar a tecla Tab gera erro de `YAML`.
3. **Caminho das imagens (`../`):** Como os capítulos ficam dentro de pastas (ex.: `basico/perfil.qmd`), use sempre `../images/nome.jpg` para avisar ao Quarto que ele deve "subir um nível de pasta" para achar a imagem.
4. **Fechamento de caixas:** Toda caixa aberta com `::: {.callout-...}` precisa obrigatoriamente ser fechada com uma linha contendo apenas `:::` no final.
