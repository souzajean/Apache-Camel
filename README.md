# 🚨 How to use Apache Camel Framework in SAP CI

##SAP BTP CPI - How to use Apache Camel in SAP CI


![Capa](imagens/capa-linkedin.png)


Este projeto demonstra como usar o Content Modifier usando o Header - Property e Body

## 📌 Objetivo

Entender os conceitos do Apache Camel no dia a dia
---


# :building_construction: Arquitetura do iFlow

### :one: O fluxo foi desenvolvido no SAP Cloud Integration (CPI) seguindo as etapas abaixo.

### Criando nosso Iflow
![Fluxo](imagens/Screenshot_1.png)
<br><br>

### Criando o Integration Flow
![Fluxo](imagens/Screenshot_2.png)
```
Address: /NotificationEmail
```
<br>

### Adicionando o Artefato do Integration Flow
![Fluxo](imagens/Screenshot_3.png)

<br>

### Criando o Integration Flow
![Fluxo](imagens/Screenshot_4.png)
```
CustomEmailNotification
```

<br>
:gear: Etapas da Integração

<br>

### :two:  Manage Security

Criando nosso usuário para enviar o E-Mail
### Security Material
![Fluxo](imagens/Screenshot_5.png)

<br>

### Criando Credentials
![Fluxo](imagens/Screenshot_6.png)

<br>

### Editando Credentials
![Fluxo](imagens/Screenshot_7.png)
```
GmailUser
```
<br>

### :three:  Configuração Google Gmail
### Acessar ao Site
```
https://myaccount.google.com/apppasswords
```
![Fluxo](imagens/Screenshot_8.png)
```
SAP CPI
```
<br>

### Armazenar a senha
![Fluxo](imagens/Screenshot_9.png)

<br>

### Adicionar a senha nas Credentials
![Fluxo](imagens/Screenshot_10.png)

<br>

### Editando nosso Iflow
![Fluxo](imagens/Screenshot_11.png)

<br>

### :four:  HTTPS Sender

<br>

### Adicionando o HTTPS
![Fluxo](imagens/Screenshot_12.png)

<br>

### Configurando o Endpoint
O fluxo é iniciado através de um endpoint HTTPS, permitindo que aplicações externas consultem o serviço.

![Fluxo](imagens/Screenshot_13.png)

```
/NotificationEmail
```
<br>

### :five: Content Modifier – Definição  Prepare Email Payload

Nesta etapa são definidas as configurações que vamos usar para o Pauload.


### Adicionando o Content Modifier
![Fluxo](imagens/Screenshot_14.png)

<br>

### Renomeando o Content Modifier
Renomeamos o Content Modifier 
![Fluxo](imagens/Screenshot_15.png)
```
Prepare Email Payload
```
<br>

### Configurando o Content Modifier - Header
![Fluxo](imagens/Screenshot_16.png)

Em Header adicionamos
```
Message Header
create   -   CPI_Tenant   -    Expression   -    ${header.CamelHttpUrl}          - java.lang.String
```
<br>

### Configurando o Content Modifier - Property
![Fluxo](imagens/Screenshot_17.png)

Em Property adicionamos
```
Exchange Property
create   -   Iflow_Name   -    Constant     -    NotificationEmail
create   -   Date_Now     -    Expression   -    ${date:now:yyyy-MM-dd HH:mm:ss}    - java.lang.String
```
<br>

### :six: End – Receiver

Nesta etapa, vamos utilizar o adapter de Email para que possamos realizar as conexões e configurações no adapter, para recebermos o e-mail da forma que queremos.

O retorno é recebido no formato HTML.

### Adicionamos o Adapter Mail
![Fluxo](imagens/Screenshot_18.png)

<br>

### Configuração do Mail - Connection
![Fluxo](imagens/Screenshot_19.png)
```
Address: smtp.gmail.com
Protection: SMTPS
Authentication: Plain User/Password
```
<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_20.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_21.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_22.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_23.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_24.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_25.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_26.png)


<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_27.png)


<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_28.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_29.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_30.png)

<br>

### Configuração do Mail - Processing
Vamos marcar Body Mime Type: Text/HTML
![Fluxo](imagens/Screenshot_31.png)




<br><br>

## 📦 Exemplo prático – iFlow para baixar

📦 [Download do iFlow – EmailNotification](https://github.com/souzajean/EmailNotification/raw/main/Package/CustomEmailNotification.zip)




> O arquivo pode ser importado diretamente no SAP Integration Suite (CPI).

