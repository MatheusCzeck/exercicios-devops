# Exercício de Fixação: O "Patch" de Sexta-Feira e o Fantasma do Drift

## 1. O Motivo da Queda (Configuration Drift)
* O Terraform comparou o código do Git com a nuvem. Como o código do Git não tinha as alterações manuais do Líder de Segurança, o Terraform entendeu que aquelas regras eram "lixo" e apagou tudo, desfazendo o bloqueio da falha e cortando os acessos do sistema.
Mariana não errou. O sistema caiu porque a intervenção manual de sexta criou um descompasso (*drift*) entre a realidade da nuvem e o que estava escrito no código. *

## 2. A Correção Correta (DevSecOps Real)
* Mesmo na emergência, a equipe de Segurança deveria ter alterado o código do Terraform no Git e rodado a pipeline. 
Como a infraestrutura é automatizada, atualizar o código e aplicar via esteira levaria poucos minutos, mantendo o sistema seguro, documentado e sem quebrar o trabalho de segunda-feira.*

## 3. Solução Arquitetural (Prevenção)
* Implementar ferramentas de monitoramento contínuo de IaC (como Terraform Cloud, Driftctl ou AWS Config). Se alguém mudar algo manualmente na nuvem, o sistema avisa na hora ou desfaz a mudança sozinho.
Retirar definitivamente o acesso manual da nuvem (mesmo o *break-glass* deve disparar alertas automáticos agressivos) e educar o time de que a única verdade do ambiente é o código no Git (*GitOps*).*