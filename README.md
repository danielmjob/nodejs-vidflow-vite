# vidflow

Para rodar o projeto

- no terminal para instalar a versão global (caso queira para outros projetos)
  npm install -g json-server@0.17.4

  Instalando o Json server localmente:
  npm install json-server@0.17.4 --save-dev
  para verificar:
  npx json-server -v

Apenas no Windows

- no PowerShell:
  Get-ExecutionPolicy
  Set-ExecutionPolicy RemoteSigned

  \*\*\* Aconselhavel após terminar de rodar o projeto:
  Set-ExecutionPolicy Restricted

- Após isso, no terminal (dependendo do que foi instalado acima)
  json-server --watch backend/videos.json (para versão global)
  npx json-server --watch backend/videos.json (para versão local)
