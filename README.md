# 🚀 Como Instalar o Tailwind CSS no ASP.NET Core MVC e Substituir o Bootstrap

Este guia ensina como instalar o **Tailwind CSS** em aplicações **ASP.NET Core MVC**, substituindo completamente o **Bootstrap** para um design moderno e responsivo.

## 📌 Pré-requisitos
✔️ **Node.js** instalado ([Baixar Node.js](https://nodejs.org/))  
✔️ **Projeto ASP.NET Core MVC** criado  

---

## 📂 Passo a Passo para Instalação

### 🛠️ 1. Remover Bootstrap do Projeto

🔹 **Excluir a pasta Bootstrap**  
```shell
./wwwroot/lib/
```  
🔹 **Remover a referência ao Bootstrap**  
Abra o arquivo `_Layout.cshtml` e remova qualquer `<link>` que importe o Bootstrap.  

---

### 🏗️ 2. Instalar o Tailwind CSS

Abra o **PowerShell** no diretório do seu projeto e execute:  
```shell
npm install tailwindcss @tailwindcss/cli
```  

---

### 📄 3. Configurar o Tailwind CSS

1️⃣ **Limpar o conteúdo de `site.css` e adicionar o import do Tailwind**  
📝 Arquivo: `./wwwroot/css/site.css`  
```css
@import "tailwindcss";
```  

2️⃣ **Criar um arquivo CSS de saída vazio**  
📝 Arquivo: `./wwwroot/css/output.css`  

3️⃣ **Referenciar `output.css` no `_Layout.cshtml`**  
📝 Arquivo: `./Views/Shared/_Layout.cshtml`  
```html
<link rel="stylesheet" href="~/css/output.css" asp-append-version="true" />
```  

---

### ⚡ 4. Criar um Script para Compilação Automática

Adicione o seguinte script ao seu `package.json`:  
📝 Arquivo: `package.json`  
```json
"scripts": {
  "build:css": "npx tailwindcss -i ./wwwroot/css/site.css -o ./wwwroot/css/output.css --watch"
}
```  

---

### 🚀 5. Instalar as Dependências e Rodar o Tailwind

🔹 **Instalar dependências do projeto:**  
```shell
npm install
```  

🔹 **Iniciar o Tailwind CSS:**  
```shell
npm run build:css
```  

📌 **Observação:** Sempre que reiniciar sua IDE, será necessário rodar o comando novamente:  
```shell
npm run build:css
```  

---

## 🎨 Resultado Final
Agora seu **ASP.NET Core MVC** estará utilizando **Tailwind CSS** no lugar do Bootstrap! 🚀  

🔔 **Se gostou, deixe uma ⭐ no repositório!** 😃  

