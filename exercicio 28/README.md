# Exercício de Fixação: Troubleshooting na Pipeline de CI

## 1. O Erro do Carlos
* Ele testou só os testes de unidade na máquina dele. Deveria ter rodado a suíte completa (incluindo o Selenium) antes de enviar o código.
## 2. O que o Time Faz Agora
* Para tudo. O foco total é consertar o build. O Carlos corrige ou desfaz o que fez, e a Ana não envia nada até o painel ficar verde de novo.

## 3. Maven vs. Selenium
* O Maven garantiu que o código compilava e as peças se encaixavam; o Selenium fingiu ser o usuário e avisou que o botão sumiu da tela antes de dar ruim na produção.