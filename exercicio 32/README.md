# Planejamento e Execução de Testes em Interface Web

## Parte 1 – Mapeamento dos Elementos da Interface

Após analisar o código HTML, identifiquei os seguintes elementos e suas regras:

* **Nome Completo (id="nome")**

  * Campo obrigatório.
  * Deve ter no mínimo 5 caracteres.
  * Aceita no máximo 100 caracteres.

* **CPF (id="cpf")**

  * Campo obrigatório.
  * Deve conter apenas números.
  * Deve possuir exatamente 11 dígitos.

* **E-mail Profissional (id="email")**

  * Campo obrigatório.
  * Deve estar em um formato válido de e-mail.

* **Selecione a Vaga (id="vaga")**

  * Campo obrigatório.
  * O usuário precisa selecionar uma vaga da lista.

* **Botão Cancelar (id="btn-cancelar")**

  * Utilizado para cancelar a operação.

* **Botão Iniciar Teste Técnico (id="btn-iniciar-teste")**

  * Inicia desabilitado.
  * Existe uma regra de negócio para sua habilitação.

* **Botão Finalizar Cadastro (id="btn-cadastrar")**

  * Responsável por enviar o formulário.

---

## Parte 2 – Casos de Teste

### CT-001 – Cadastro com dados válidos

**ID do Teste:** CT-001

**Nome do Cenário:** Cadastro realizado com sucesso.

**Pré-condições:** Formulário aberto.

**Passo a Passo:**

1. Preencher o nome com "Matheus Czeck".
2. Preencher o CPF com "12345678901".
3. Informar o e-mail "[matheus@email.com](mailto:matheus@email.com)".
4. Selecionar a opção "Analista de QA" no campo #vaga.
5. Clicar no botão #btn-cadastrar.

**Resultado Esperado:**
O cadastro deve ser realizado sem apresentar mensagens de erro.

---

### CT-002 – Nome com menos de 5 caracteres

**ID do Teste:** CT-002

**Nome do Cenário:** Validação do campo nome.

**Pré-condições:** Formulário aberto.

**Passo a Passo:**

1. Digitar "Ana" no campo nome.
2. Preencher os demais campos corretamente.
3. Clicar em "Finalizar Cadastro".

**Resultado Esperado:**
O sistema deve impedir o cadastro e exibir a mensagem de erro referente ao nome inválido.

---

### CT-003 – CPF com letras

**ID do Teste:** CT-003

**Nome do Cenário:** Validação do formato do CPF.

**Pré-condições:** Formulário aberto.

**Passo a Passo:**

1. Preencher o nome corretamente.
2. Informar "ABC12345678" no campo CPF.
3. Preencher os demais campos corretamente.
4. Clicar em "Finalizar Cadastro".

**Resultado Esperado:**
O sistema deve exibir uma mensagem informando que o CPF deve conter apenas números e 11 dígitos.

---

### CT-004 – Verificar botão "Iniciar Teste Técnico"

**ID do Teste:** CT-004

**Nome do Cenário:** Validação do estado inicial do botão.

**Pré-condições:** Página carregada.

**Passo a Passo:**

1. Acessar a tela de cadastro.
2. Localizar o botão "Iniciar Teste Técnico".

**Resultado Esperado:**
O botão deve estar desabilitado e não permitir interação do usuário.

---

## Parte 3 – Planejamento para Automação

Se eu fosse automatizar esses testes utilizando Selenium ou Cypress, utilizaria os atributos **id** dos elementos, pois eles são únicos e facilitam a localização dos componentes na página.

Para localizar o campo CPF:

```css id="z7m3v1"
#cpf
```

Para o campo CPF, eu utilizaria o seletor **#cpf**, pois o atributo **id** é único na página e permite localizar o elemento de forma rápida e segura. Como exemplo, em Cypress:

```javascript
cy.get('#cpf').type('12345678901')
```

```css id="9d4r2a"
#btn-cadastrar
```

O uso do atributo **id** é uma boa prática porque torna os testes mais estáveis e fáceis de manter. Como cada elemento possui um identificador único, o script consegue encontrá-lo rapidamente, mesmo que ocorram alterações no layout da página.
