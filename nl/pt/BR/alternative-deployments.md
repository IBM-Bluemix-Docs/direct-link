---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-01"

keywords: use case, alternatives, deployments, diverse, redundant, default, multi-cloud, other clouds, schematic

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Alternativas para a implementação do IBM Cloud Direct Link
{: #alternatives-for-your-ibm-cloud-direct-link-deployment}

Este documento ilustra algumas alternativas que às vezes nossos clientes escolhem como casos de uso para as suas
implementações do {{site.data.keyword.cloud}} Direct Link.

## Implementações diferentes para o Exchange e o Connect
{: #diverse-deployments-for-exchange-and-connect}

As implementações padrão do Direct Link Connect e do Direct Link Exchange não incluem configuração redundante, embora possam
ser implementados diferentemente em roteadores discretos.

Muitos dos nossos clientes escolhem criar implementações redundantes, configurando uma conexão adicional do Direct Link. Esse
documento apresenta algumas representações esquemáticas de implementações alternativas do IBM Cloud Direct Link.

![Exchange diferente](/images/Direct-Link-Exchange-Diverse.png)

**Figura 1 (acima): uma implementação diferente do IBM Cloud Direct Link Exchange**

O IBM Cloud Direct Link também facilita o estabelecimento de diversas implementações do Connect, conforme mostrado na figura a
seguir.

![Connect diferente](/images/Direct-Link-Connect-Diverse.png)


**Figura 2 (acima): uma implementação redundante e diferente do IBM Cloud Direct Link Connect**

## Usando Exchange e Connect em conjunto com outras nuvens
{: #using-exchange-and-connect-in-conjunction-with-other-clouds}

Alguns dos nossos clientes desejam usar o Direct Link Exchange em conjunto com outros provedores em nuvem, como o AWS, o Azure ou
o Google Cloud. O diagrama a seguir mostra uma visão geral de como estabelecer esse tipo de conexão com um provedor Cloud Exchange.

![Outras nuvens](/images/Direct-Link-Exchange-Other-Clouds.png)

**Figura 3 (acima): usando o IBM Cloud Direct Link Exchange em conjunto com outras nuvens**

Alguns dos nossos clientes desejam usar o Direct Link Connect em conjunto com outros provedores em nuvem, como o AWS, o Azure
ou o Google Cloud. O diagrama esquemático a seguir mostra uma visão geral de como estabelecer esse tipo de conexão com um Telco/NSP.

![Outras nuvens](/images/Direct-Link-Connect-other-clouds.png)

**Figura 4 (acima): usando o IBM Cloud Direct Link Connect em conjunto com outras nuvens**

