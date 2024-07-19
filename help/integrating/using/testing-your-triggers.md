---
title: Testa utlösarna
description: Lär dig felsökningstips som hjälper dig att lösa de vanligaste problemen du kan stöta på när du använder Utlösare med Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Testa utlösarna{#testing-your-triggers}

Följande felsökningstips hjälper dig att lösa de vanligaste problemen du kan stöta på när du använder Utlösare med Adobe Campaign:

**Är funktionen aktiverad?**

Om du vill kontrollera om integreringen av utlösare - kampanj är aktiverad klickar du på Adobe Campaign-logotypen i det övre vänstra hörnet och väljer sedan **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Du bör se objektet **[!UICONTROL Experience Cloud Triggers]**.

Om du ser det går du vidare till nästa steg.

Om inte, kontakta er kontoansvarige eller er partner inom sektorn för Adobe. Se [Aktivera funktionen](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Försök skapa en utlösare**

Följ stegen som beskrivs i [Skapa en mappad utlösare i Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) för att skapa en utlösare.

Om utlösaren skapas går du vidare till nästa steg. Annars innebär det att slutpunktsanslutningen för utlösaren misslyckades. Kontrollera om utlösare har etablerats i Experience Cloud (aktiveringstjänster). Om så inte är fallet kontaktar du din kontoansvarige eller partner för professionella tjänster på Adobe. Följande information krävs:

* Marketing Cloud företagsnamn
* Organisations-ID
* Analysinloggningsföretag (kan vara samma som Marketing Cloud företagsnamn)

**Försök publicera utlösaren**

Följ stegen som beskrivs i [Skapa en mappad utlösare i Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) för att publicera utlösaren.

Gå vidare till nästa steg om publikationen lyckades. Om inte, kontakta Adobe för att starta om instansen och försök igen.

**Generera utlösaren från webbplatsen**

Följ stegen som beskrivs i [Redigera transaktionsmeddelandemallen](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) för att redigera och publicera transaktionsmallen. Testa sedan genereringen av utlösaren från webbplatsen.

Om utlösaren tas emot av Analytics går du vidare till nästa steg. Om inte, kontrollera följande:

* Utlösaren är aktiverad för Analytics
* Den webbplats som används för MCID och Analytics är aktiverad i DTM
* Den korrekta rapportsviten för Analytics används när utlösare skapas

**Är utlösaren mottagen av Campaign?**

Om inte, kontrollerar du om utlösaren tas emot från pipelinen.

Om inte, kontakta Adobe för att kontrollera konfigurationen av slutpunkterna för pipeline.

Om så är fallet, följ dessa riktlinjer:

* Kontrollera avstämnings-ID-typen i Campaign-datakällan.
* CustomerId-datakällan skapas via kundattribut.
* Kontrollera datakällans ID.
* Be Adobe att starta om Campaign-instansen efter datakällkonfigurationen.
* Kontrollera problem med tolkning av utlösare i utlösarrapporten.

**Är utlösaren i väntande status?**

Om inte, gå vidare till nästa steg. Om så är fallet, följ dessa riktlinjer:

* Kontrollera att transaktionsmallen är publicerad.
* Kontrollera att profilen inte finns på blockeringslista.
* Kontrollera tillämpningen av typologiregler.
* Kontrollera transaktionsmeddelandets loggar.

**Är meddelandet giltigt?**

Om meddelandet inte är giltigt kontrollerar du följande:

* För utlösarfält för anrikning som markerats som ogiltiga validerar du transaktionsmallen från de associerade EventCusResource-samlingarna.
* Validera meddelandeformatet
