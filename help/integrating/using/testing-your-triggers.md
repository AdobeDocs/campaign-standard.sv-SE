---
title: Testa utlösarna
description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Testa utlösarna{#testing-your-triggers}

Följande felsökningstips hjälper dig att lösa de vanligaste problemen du kan stöta på när du använder utlösare med Adobe Campaign:

**Är funktionen aktiverad?**

Om du vill kontrollera om utlösare - Campaign-integrering är aktiverad klickar du på Adobe Campaign-logotypen i det övre vänstra hörnet och väljer sedan **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Du borde se **[!UICONTROL Experience Cloud Triggers]** objektet.

Om du ser det går du vidare till nästa steg.

Om inte, kontakta er kontoansvarige på Adobe eller er partner inom sektorn för professionella tjänster. Se [Aktivera funktionen](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Försök skapa en utlösare**

Följ stegen som beskrivs i [Skapa en mappad utlösare i Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) för att skapa en utlösare.

Om utlösaren skapas går du vidare till nästa steg. Annars innebär det att slutpunktsanslutningen för utlösaren misslyckades. Kontrollera om utlösare har etablerats i Experience Cloud (aktiveringstjänster). Om så inte är fallet kontaktar du din Adobe-kontoansvarige eller partner för professionella tjänster. Följande information krävs:

* Företagsnamn för Marketing Cloud
* IMS-ORG-ID
* Analytics-inloggningsföretag (kan vara samma som Marketing Cloud-företagets namn)

**Prova att publicera utlösaren**

Följ stegen som beskrivs i [Skapa en mappad utlösare i Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) för att publicera utlösaren.

Gå vidare till nästa steg om publikationen lyckades. Annars kontaktar du Adobe för att starta om instansen och försöka igen.

**Generera utlösaren från webbplatsen**

Följ stegen som beskrivs i [Redigera transaktionsmeddelandemallen](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) för att redigera och publicera transaktionsmallen. Testa sedan genereringen av utlösaren från webbplatsen.

Om utlösaren tas emot av Analytics går du vidare till nästa steg. Om inte, kontrollera följande:

* Utlösaren är aktiverad för Analytics
* Den webbplats som används för MCID och Analytics är aktiverad i DTM
* Den korrekta rapportsviten för Analytics används när utlösare skapas

**Tar Campaign emot utlösaren?**

Om inte, kontrollerar du om utlösaren tas emot från pipelinen.

Om inte, kontakta Adobe för att kontrollera konfigurationen av pipeline-slutpunkterna.

Om så är fallet följer du de här stödlinjerna:

* Kontrollera avstämnings-ID-typen i Campaign-datakällan.
* CustomerId-datakällan skapas via kundattribut.
* Kontrollera datakällans ID.
* Be Adobe att starta om Campaign-instansen efter datakällkonfigurationen.
* Kontrollera problem med tolkning av utlösare i utlösarrapporten.

**Är utlösaren i väntande status?**

Om inte, gå vidare till nästa steg. Om så är fallet följer du de här stödlinjerna:

* Kontrollera att transaktionsmallen är publicerad.
* Om tröskelvärdet för propensityScore är aktiverat för Campaign kontrollerar du utlösarens benägenhetspoäng från pipeline.
* Kontrollera att profilen inte är svartlistad.
* Kontrollera tillämpningen av typologiregler.
* Kontrollera transaktionsmeddelandets loggar.

**Är meddelandet giltigt?**

Om meddelandet inte är giltigt kontrollerar du följande:

* För utlösarfält för anrikning som markerats som ogiltiga validerar du transaktionsmallen från de associerade EventCusResource-samlingarna.
* Validera meddelandeformatet

