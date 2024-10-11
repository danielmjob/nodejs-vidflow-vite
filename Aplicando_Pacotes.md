# Adicionando pacote externo "ESLint" ao projeto

Crie o package.json com NPM em um NOVO terminal (não feche o anterior) digite:
npm init
npm init @eslint/config@0.4.6
Escolha essas respostas para as perguntas
-> To check syntax and find problems
-> JavaScript modules
-> None of these
-> use TypeScript?No
-> Browser
-> JSON
-> instal them now?Yes
-> npm

Execute o pacote
npx eslint script.js

Apenas em caso de Erro
Devido a versões superiores a 9 pode ser necessária a migração usando o comando:
npx @eslint/migrate-config .eslintrc.json

Procurando erros em todos os arquivos do projeto
npx eslint .

Evitando erros ao enviar para git
crie um arquivo com nome .gitignore
dentro dele digite: node_modules

No VSCode instale a extensão ESLint, assim ele ficará sempre rodando
Aconselhavel instalar Prettier - formatador/padronizador de código (https://prettier.io/docs/en/install)
npm install --save-dev --save-exact prettier@3.0.3
Confirmando se foi instalado:
npx prettier -v

Nas configurações do VSCode
Arquivo settings.json
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true

Instalando o Json server localmente:
npm install json-server@0.16.0 --save-dev
para verificar:
npx json-server -v

Automatizando usando scripts
Dentro do arquivo package.json adicione
"api-local": "json-server --watch backend/videos.json"
"checar-codigo": "eslint ."

Como no exemplo abaixo

"scripts": {
"test": "echo \"Error: no test specified\" && exit 1",
"api-local": "json-server --watch backend/videos.json",
"checar-codigo": "eslint ."
},

Agora no terminal digite:
npm run api-local

Adicionando Axios ao projeto (para requisições)
npm install axios@1.6.0 -E

Lidando com as dependencias de produção
Pacote vite:

No powershell
npm create vite@latest

√ Project name: ... nodejs-vidflow-vite
√ Select a framework: » Vanilla
√ Select a variant: » JavaScript

entre na pasta criada
abra o projeto
digite no terminal do projeto: npm install

no powershell digite: npm run dev
ele irá criar um servidor vite

Com isso foi criado um novo projeto agora iremos migrar o projeto antigo para esse novo

exclua no NOVO
public
counter.js
index.html
javascript.svg
main.js
style.css

copie do antigo e cole no novo
backend
css/img
.eslintrc.json
index.html
script.js
eslint.config.mjs

em Packge.json
cole as essas dependencias (que estão no antigo)
"eslint": "9.12.0",
"json-server": "0.17.4",
"prettier": "3.0.3"

Copie e cole tambem

      "dependencies": {
    "axios": "1.6.0"

}

E os scripts
"test": "echo \"Error: no test specified\" && exit 1",
"api-local": "json-server --watch backend/videos.json",
"checar-codigo": "eslint ."

No script js na primeira linha digite

import axios from "axios";

Use o comando (Json server)
npm run api-local

caso apresente erro verifique se o script no index esta dessa forma

<script src="script.js" type="module"></script>

Preparando para Deploy
em um novo terminal digite:
npm run build
npm run preview

abra o link que ele irá disponibilizar no meu caso gerou (http://localhost:4173/)

dentro do packge.json crie o script
"build-preview": "vite build --watch",
rode o comando: npm run build-preview

agora é so Subir para o Git e fazer o deploy no Vercel
