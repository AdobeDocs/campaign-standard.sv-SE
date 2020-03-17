---
title: Om Adobe Experience Cloud-utlösare
description: Genom att spåra specifika beteenden från kunder med Adobe Analytics kan ni nu skicka personaliserade e-postmeddelanden till era kunder i Adobe Campaign.
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Om Adobe Experience Cloud-utlösare{#about-adobe-experience-cloud-triggers}

Integrationen mellan huvudtjänsten Experience Cloud Activation **[!UICONTROL Triggers]** och Adobe Campaign gör att ni kan skicka personaliserade e-postmeddelanden till era kunder som en reaktion på specifika beteenden som Adobe Analytics spårar på er webbplats (inom 15 minuter).

I Adobe Experience Cloud definierar ni olika triggers, det vill säga de kundbeteenden som ni vill övervaka, till exempel alla kunder som avbrutit sitt besök på er webbplats, gjort en sökning på er webbplats men inte gjort något köp, eller till och med de kunder vars session har gått ut. När du skapar en utlösare definierar du utlösarens villkor och de data som ska skickas i händelsen (överföringen) till Adobe Campaign.

I Adobe Campaign väljer du den utlösare som skapades tidigare, berikar händelsedata med datamarappdata och du definierar en mall för transaktionsmeddelanden som är länkad till den utlösaren. När en kund till exempel avbryter sitt besök på din webbplats skickas ett event till Adobe Campaign som sedan kan återanvända evenemanget via ett e-postmeddelande som skickas till kunden inom 15 minuter.

**Relaterade ämnen:**

* Lär dig mer om de olika typerna av utlösare: Dokumentation [för](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)Adobe Experience Cloud.
* Titta på videon [Trigger Remarketing Messages som bygger på Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) (Webbplatsaktivitet).
* Upptäck våra två [övergivningsutlösare](../../integrating/using/abandonment-triggers-use-cases.md).

## Utlöser användarprocess {#triggers-user-process}

>[!CAUTION]
>
>Innan huvudanvändarstegen körs måste funktionerna konfigureras. Mer information finns i [Aktivera funktionen](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Konfigurera lösningar och tjänster](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) och [Skapa en mappad utlösare i Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

De viktigaste stegen i användarprocessen, i Adobe Campaign, är:

1. Skapa en utlösarhändelse länkad till en befintlig Adobe Experience Cloud-utlösare.
1. Publicera utlösarhändelsen.
1. Definiera innehållet i transaktionsmeddelandemallen.
1. Testa mallen (skapa en testprofil och skicka ett korrektur).
1. Publicera transaktionsmeddelandemallen.

Fullständiga användningsexempel beskrivs i [det här avsnittet](../../integrating/using/abandonment-triggers-use-cases.md).

## Viktiga anteckningar {#important-notes}

Här är några viktiga saker att tänka på innan du använder utlösarna - Campaign-integrering:

* Push-meddelanden stöds inte för utlösare. Endast e-post och SMS stöds.
* Du kan berika utlösaren med metadata som har hämtats in via analyser som e-post-ID, sidnamn osv.
* Du kan koppla utlösaren till en profil som lagras i Campaign Standard och använda profilens fält för att anpassa meddelandet.
* Så snart en utlösare tas emot behandlas den och stäms av och skickas ut. Det tar ca 5 till 15 minuter beroende på hur många utlösare som har tagits emot, antalet anpassningsfält som används i mallen.

>[!NOTE]
>
>Mer information om bästa praxis och tekniska begränsningar finns i [Utlösare - bästa praxis och begränsningar](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

