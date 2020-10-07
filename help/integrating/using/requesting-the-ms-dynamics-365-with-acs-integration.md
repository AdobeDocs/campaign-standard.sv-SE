---
title: Begär och konfigurera Microsoft Dynamics 365-integrationen
description: Lär dig hur du begär och konfigurerar Microsoft Dynamics 365 med integrering av Campaign Standarder
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# Begär och konfigurera Microsoft Dynamics 365-integrationen

För att kunna genomföra integreringen måste du följa stegen nedan.

Följ informationen i flödesschemat och flödesschemat nedan för att begära och konfigurera integreringen.

![](assets/provisioning-wf.png)

Information om flödesschema (mappas till steg ovan):

* **Steg 1** - Du förutsätts redan ha, eller håller på att köpa, en licens för Microsoft Dynamics 365 för Försäljning och för Adobe Campaign Standard.

* **Steg 2** - Standardintegrationserbjudandet är kostnadsfritt för alla kunder. Ytterligare kostnader kan dock tillkomma beroende på dina behov (se [Integrationsgarantier och gränser](../../integrating/using/ms-dynamics-365-integration-guardrails.md). En ny försäljningsorder måste signeras för att integreringen ska kunna utnyttjas.

* **Steg 3** - Slutför förintegreringsstegen för Dynamics 365 och Campaign. Se [Konfigurera den här integreringen](#configure-this-integration).

* **Steg 4-7** - Adobe kommer att samarbeta med dig under introduktionsprocessen.

## Konfigurera den här integreringen {#configure-this-integration}

Tre system måste etableras och konfigureras för den här integreringen: Adobe Campaign Standard, Microsoft Dynamics 365 for Sales och integreringsverktyget. Konfigurationsartiklar är länkade nedan.

>[!CAUTION]
>
>För varje system måste dessa steg utföras av en administratör.
>
>Stegen i artiklarna nedan vägleder dig genom att skapa integreringar/registreringar som inbegriper tilldelning av behörigheter och/eller administratörsåtkomst.  Det är ditt ansvar att se till att dessa steg följer företagets regler innan de utförs och att de utförs med omsorg.

I ADOBE CAMPAIGN måste du konfigurera API-åtkomst och konfigurera en ny integrering för integrationsverktyget. Läs [den här artikeln](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)för att uppnå detta.

I MICROSOFT DYNAMICS 365 måste du skapa en ny programregistrering och göra det möjligt för en programanvändare att använda integreringen.  Information om hur du konfigurerar Microsoft Dynamics 365 för den här integreringen finns i [den här artikeln](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Du måste arbeta med Adobe introduktionsteam för att konfigurera dataflödena för ingress, utgång och avanmälan.


## Begär support

Supportbiljetterna kan som vanligt loggas med Adobe Custom Care. Kundtjänst kommer att ta in supportpersonal efter behov.

Om du har problem med integreringsdataflöden måste du ta med rapportsviten som en del av problembeskrivningen samt följande information:

* **Processägare**: Ingenjörsarkitekter

* **ES Process-ID**: Tillhandahålls under introduktionsprocessen

* **Processtitel**: Dynamics 365/Adobe Campaign Standard-integrering

* **Ärendebeskrivning**: Beskrivning av problemet

Stödet för integrering är för närvarande 24x5 (tillgängligt måndag till fredag, exklusive semester och pauser i Adobe).