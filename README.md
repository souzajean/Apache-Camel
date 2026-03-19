# 🚨 SAP BTP CPI – Using Apache Camel Framework  
## 📌 How to Use Apache Camel in SAP Cloud Integration (CI)

📖 Sobre o Projeto

Este projeto demonstra, de forma prática, como utilizar conceitos do Apache Camel dentro do SAP BTP Integration Suite (Cloud Integration – CPI).

O foco principal é mostrar como manipular mensagens utilizando o Content Modifier, trabalhando com:

Headers

Properties

Body

Esses conceitos são fundamentais para qualquer cenário de integração no dia a dia.

🎯 Objetivo

Quando iniciamos no SAP CPI, um dos primeiros aprendizados é entender como o Apache Camel funciona por trás dos iFlows.

Este projeto tem como objetivo:

Demonstrar o uso de Headers, Properties e Body

Explicar como o Apache Camel atua dentro do CPI

Facilitar o entendimento de como os dados trafegam em um iFlow

Servir como base para projetos mais avançados

⚙️ Tecnologias Utilizadas

SAP BTP Integration Suite (Cloud Integration - CPI)

Apache Camel

Content Modifier

🔍 Conceitos Abordados

📌 Headers

Usados para transportar informações técnicas entre etapas do iFlow.

📌 Properties

Utilizadas para armazenar dados temporários durante o processamento da integração.

📌 Body

Contém a mensagem a mensagem principal que está sendo processada.

---


# :building_construction: Arquitetura do iFlow

### :one: O fluxo foi desenvolvido no SAP Cloud Integration (CPI) seguindo as etapas abaixo.
<br><br>
### Criando nosso Iflow
![Fluxo](imagens/Screenshot_1.png)
<br><br><br>

### Criando o Integration Flow
![Fluxo](imagens/Screenshot_2.png)
```
CustomContentModifier
```
<br><br>

### Adicionando o Artefato do Integration Flow
![Fluxo](imagens/Screenshot_3.png)

<br><br>

### Criando o Integration Flow
![Fluxo](imagens/Screenshot_4.png)
```
ModifyContentModifier
```

<br><br>
:gear: Etapas da Integração

<br>

### :two:  Editar o Iflow

### Editar o Iflow
![Fluxo](imagens/Screenshot_5.png)

<br>

### Remover o Receiver
![Fluxo](imagens/Screenshot_6.png)

<br>

### :three:  HTTPS Sender
### Adicionando o HTTPS
![Fluxo](imagens/Screenshot_7.png)

<br>


### Configurando o HTTPS
O fluxo é iniciado através de um endpoint HTTPS, permitindo que aplicações externas consultem o serviço.
![Fluxo](imagens/Screenshot_8.png)
```
Address: /modificar
```
<br>

### :four:  Content Modifier
### Adicionando o Content Modifier
Vamos criar 3 Content Modifier na conexão
![Fluxo](imagens/Screenshot_9.png)

<br>

### Ficando dessa forma
![Fluxo](imagens/Screenshot_10.png)

<br>

### Renomear  Content Modifier - Header
![Fluxo](imagens/Screenshot_11.png)
```
setHeader
```

<br>

### Configurando Content Modifier - Header
![Fluxo](imagens/Screenshot_12.png)
```
Create  -  setHeader  - Constant  -  ValorHeader
```
<br>

### Renomear  Content Modifier - Property

![Fluxo](imagens/Screenshot_13.png)

```
setProperty
```
<br>

### Configurando Content Modifier - Property
![Fluxo](imagens/Screenshot_14.png)
```
Create  -  setProperty  - Constant  -  ValorProperty
```
<br>

### Renomear  Content Modifier - Body
![Fluxo](imagens/Screenshot_15.png)
```
Prepare Email Payload
```
<br>

### Configurando o Content Modifier - Body
![Fluxo](imagens/Screenshot_16.png)

Alteramos o Type: 
```
Expression
```
<br>

No Body:
```
Message Header:       ${header.setHeader}
Exchange Property:    ${property.setProperty}
Message Body CPI:     Mensagem do CPI
Message Body Postman: ${body}
```
<br>

### Configurando o Postman
![Fluxo](imagens/Screenshot_17.png)
```
Mensagem do Postman
```

Resultado:
```
Message Header:       ValorHeader
Exchange Property:    ValorProperty
Message Body CPI:     Mensagem do CPI
Message Body Postman: Mensagem do Postman
```

<br><br>

## 📦 Exemplo prático – iFlow para baixar

📦 [Download do iFlow – EmailNotification](https://github.com/souzajean/EmailNotification/raw/main/Package/CustomEmailNotification.zip)




> O arquivo pode ser importado diretamente no SAP Integration Suite (CPI).

