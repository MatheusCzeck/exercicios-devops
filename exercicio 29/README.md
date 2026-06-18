# Exercício de Fixação: O Falso Positivo na Black Friday

## 1. Cultura DevOps e Silos
*  O erro foi que cada líder defendeu apenas a sua área ("meu código tá verde" / "meu servidor tá com CPU baixa") em vez de trabalharem juntos para achar o problema. 
* **O que significa:** O sistema pode estar tecnicamente perfeito, mas se o cliente não consegue comprar, ele falhou para o negócio.

## 2. Métricas e Observabilidade
* O que faltou foi monitorar métricas de negócio (como quedas nas vendas por minuto) e erros invisíveis (como telas travadas por timeout).
* Se o pipeline monitorasse as vendas na versão de teste (Canary), ele veria a queda e faria o rollback automático sozinho.

## 3. Reunião Sem Culpa (Post-Mortem)
* **Como fazer:** Focar no **motivo** do erro acontecer e não em achar um culpado. O objetivo é melhorar o sistema (criar alertas de banco de dados) para que o problema nunca mais se repita.