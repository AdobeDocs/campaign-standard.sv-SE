---
title: Användningsexempel för avbrytningsutlösare
description: Lär dig hur du använder Experience Cloud Triggers-integreringen med dessa olika användningsfall.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 88007e6f-2cdd-4fea-9739-525beaf7c658
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 94%

---

# Användningsfall för avbrytningsutlösare{#abandonment-triggers-use-cases}

I det här avsnittet beskrivs olika användningsexempel som kan implementeras med hjälp av integreringen mellan Adobe Campaign och Experience Cloud Triggers.    Du hittar två exempel för användningsområden:

* [Utlösare för avbruten bläddring](#browse-abandonment-trigger): skicka ett meddelande till kunder som avbrutit sitt besök på din hemsida.
* [Utlösare för avbruten sökning](#search-abandonment-trigger): engagera besökare som gjort en sökning på er webbplats men som inte har gjort något inköp.

>[!NOTE]
>
>De användningsfall som beskrivs i det här avsnittet är beroende av Experience Cloud Visitor ID.    Det går också att implementera dem med Experience Cloud Declared ID.    Hash-kodade och krypterade deklarerade ID:n stöds också.    Du kan skicka e-post/SMS till en profil som inte finns i Campaign genom att direkt dekryptera den krypterade e-postadressen/det krypterade mobilnumret.    Men i det här fallet kan personalisering med hjälp av profildata inte användas.

## Krav {#pre-requisites}

För att dessa användningsområden ska kunna implementeras måste du ha tillgång till följande lösningar/bastjänster:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select eller Standard.
* Bastjänsten Experience Cloud-utlösare
* Bastjänsten Experience Cloud DTM
* Bastjänsterna Experience Cloud Visitor ID och Experience Cloud People

Du måste även ha en fungerande hemsida.

Mer information finns i [Konfigurera lösningar och tjänster](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Utlösare för avbruten bläddring {#browse-abandonment-trigger}

I det här fallet ska vi skapa en enkel utlösare som aktiveras varje gång en kund avbryter ett besök på hemsidan.  I det här exemplet förutsätts det att du redan har DTM som samlar in och överför data till Adobe Analytics och har skapat alla händelser.

### Skapa en Experience Cloud-utlösare {#creating-an-experience-cloud-trigger}

1. Välj **[!UICONTROL Manage Triggers]** i Experience Cloud Activation Core Service-menyn.

   ![](assets/trigger_uc_browse_1.png)

1. Välj en utlösartyp ( **[!UICONTROL Abandonment]** i vårt användningsfall).

   ![](assets/trigger_uc_browse_2.png)

1. I det här fallet behöver vi en enkel avbrytningsutlösare.  Affärssyftet är att identifiera besökare som bläddrar på vår hemsida för resebokning, tittar på sidan &quot;Erbjudanden&quot; men inte bokar någon resa.  När vi har identifierat den här målgruppen vill vi höra av oss till dem inom en kort tidsperiod.  I det här exemplet väljer vi att skicka utlösaren efter en period på 10 minuter.

   ![](assets/trigger_uc_browse_3.png)

### Använda utlösaren i Adobe Campaign {#using-the-trigger-in-adobe-campaign}

Nu när vi har skapat en Experience Cloud-utlösare kan vi använda den i Adobe Campaign.

I Adobe Campaign måste du skapa en utlösare länkad till den du skapade i Experience Cloud.

1. Om du vill skapa utlösaren i Adobe Campaign klickar du på **Adobe** logotyp, i det övre vänstra hörnet och välj **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Klicka på **[!UICONTROL Create]**.
1. Markera utlösaren som du tidigare skapade och klicka på **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Markera **[!UICONTROL Email]**-kanalen och **[!UICONTROL Real-time event]** måldimensionen och klicka sedan **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. Publicera utlösaren i Adobe Campaign.  Den här processen skapar automatiskt en mall för transaktionsmeddelanden.

   ![](assets/trigger_uc_browse_6.png)

1. Klicka på knappen **[!UICONTROL More]** överst till höger klickar du på **[!UICONTROL Trigger Transactional Template]**.

1. Anpassa innehållet och avsändarinformationen.

   ![](assets/trigger_uc_browse_8.png)

1. Publicera meddelandemallen.  Utlösaren är nu aktiv och i funktion.

   ![](assets/trigger_uc_browse_0.png)

### Kör scenariot {#running-the-scenario}

1. Det här användningsexemplet börjar med ett första e-postmeddelande som skickas till er målgrupp med Adobe Campaign.

   ![](assets/trigger_uc_browse_9.png)

1. Mottagaren öppnar e-postmeddelandet.

   ![](assets/trigger_uc_browse_10.png)

1. Mottagaren klickar på en länk som för dem till webbplatsen. I det här exemplet placerar banderollen mottagaren på startsidan för resebokningssidan.

   ![](assets/trigger_uc_browse_11.png)

1. Mottagaren går till sidan&quot;Erbjudanden&quot; men avbryter plötsligt besöket. Efter en 10-minutersperiod så utlöser Adobe Campaign sändningen av transaktionsmeddelandet.

   ![](assets/trigger_uc_browse_12.png)

1. Du kan när som helst kontrollera Experience Cloud-loggarna för att se hur många gånger utlösaren utlöstes.

   ![](assets/trigger_uc_browse_13.png)

1. Du kan också visa utlösarrapporten för Adobe Campaign.

   ![](assets/trigger_uc_browse_14.png)

## Utlösare för avbruten sökning {#search-abandonment-trigger}

I det här fallet kommer vi att skapa en utlösare för att återengagera besökare som var på vår hemsida för bokningar och sökte efter en destination utan att få några framgångsrika resultat och därför avbröt besöket. Den allmänna processen är densamma som i det föregående användningsfallet (se [Utlösare för avbruten bläddring](#browse-abandonment-trigger)).  Här fokuserar vi på hur vi personaliserar e-postmeddelanden om återmarknadsföring.

### Skapa en Experience Cloud-utlösare {#creating-an-experience-cloud-trigger-1}

Följ stegen som beskrivs i det föregående användningsexemplet för att skapa en Experience Cloud-utlösare.  Se [Skapa en Experience Cloud-utlösare](#creating-an-experience-cloud-trigger).  Den största skillnaden är utlösardefinitionen.

![](assets/trigger_uc_search_1.png)

I det här **[!UICONTROL Include Meta Data]** avsnittet kan du skicka all data som samlats in från Analytics till utlösaren.  I det här exemplet skapar vi en anpassad eVar (till exempel eVar 3) för att samla in söktermen som besökaren anger.  Den här termen används sedan i det transaktionsbaserade e-postmeddelandet som skickas till samma besökare.

### Använda utlösaren i Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. Följ stegen som beskrivs i det föregående användningsexemplet för att skapa utlösaren i Adobe Campaign.  Se [Använda utlösaren i Adobe Campaign](#using-the-trigger-in-adobe-campaign).  Den största skillnaden är hur vi i Adobe Campaign får åtkomst till och använder den metadata som lagts in i utlösarens nyttolast.
1. Klicka på ikonen i den utlösare för avbruten sökning som du skapade i Adobe Campaign för att visa den som har skickats till Adobe Campaign. **[!UICONTROL Event content and enrichment]**

   ![](assets/trigger_uc_search_2.png)

1. Som du kan se skickas den anpassade eVar-variabeln i utlösaren och mappas till **händelsekontexttabellen** (ctx).  Vi har nu tillgång till den för att personalisera transaktionsmeddelandet.

   ![](assets/trigger_uc_search_3.png)

1. I det här exemplet väljer vi att inkludera målsöktermen i ämnesraden och i brödtexten i e-postmeddelandet.

   ![](assets/trigger_uc_search_4.png)

1. När du väljer ett anpassat fält ska du leta efter dina metadata i tabellen **Transaktionella event** (rtEvent) och sedan i undertabellen **Kontext för event** (ctx).

   ![](assets/trigger_uc_search_5.png)

### Kör scenariot {#running-the-scenario-1}

1. Besökaren går vidare till resebokningshemsidan och söker efter en destination.  I det här exemplet letar besökaren efter en resa till Japan men hittar inget resultat.  Det här är en möjlighet för oss att nå tillbaka till besökaren och rekommendera en alternativ reseplan.

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >I det här fallet antar vi att besökaren/mottagaren redan har öppnat och klickat på ett e-postmeddelande som kommer från samma hemsida.  Detta gör att vi kan använda oss av och samla in VisitorID och mappa det till mottagaren.  Vi behöver bara göra detta en gång.

1. En stund senare får samma besökare/mottagare ett meddelande om återmarknadsföring.  Meddelandet innehåller den nyligen sökta destinationen.

   ![](assets/trigger_uc_search_7.png)
