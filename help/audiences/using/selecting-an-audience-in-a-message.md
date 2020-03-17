---
title: Välja en målgrupp i ett meddelande
description: '"Stegvisa procedurer för att välja målgrupper i ett e-postmeddelande: huvudmålpopulation och testprofiler."'
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Välja en målgrupp i ett meddelande{#selecting-an-audience-in-a-message}

Med Adobe Campaign kan ni konfigurera flera profiltyper inom ett meddelandes målgrupp.

Målgrupper kan definieras när meddelandet skapas via guiden Skapa eller från meddelandekontrollpanelen om meddelandet redan har skapats.

>[!NOTE]
>
>Om målgruppen har byggts in i ett arbetsflöde och berikats med ytterligare data, kan ni inte använda dessa data för att personalisera en fristående leverans. De kan bara användas från en leverans som körs i ett arbetsflöde.

1. Gå till målgruppsblocket från kontrollpanelen för att börja.

   ![](assets/delivery_audience_definition_1.png)

   Skärmen som definierar målgrupperna öppnas. Det finns två flikar där du kan definiera var och en av de målgrupper som ska få meddelandet separat:

   * Mål
   * Testprofiler
   ![](assets/delivery_audience_definition_2.png)

1. Definiera huvuddelen **[!UICONTROL Target]** av e-postmeddelandet. Det här är den vanliga målgruppen för e-postmeddelandet.

   Målet definieras på fliken **[!UICONTROL Target]** och består av identifierade profiler från databasen.

   Du kan etablera huvudmålet med [frågeredigeringsfunktionerna](../../automating/using/editing-queries.md#creating-queries) .

   På den här fliken innehåller paletten bara fördefinierade filter och de målgrupper som har definierats i de identifierade profilerna **[!UICONTROL Shortcuts]** . På fliken **[!UICONTROL Explorer]** kan du komma åt ytterligare konfigurationer.

   Du kan därför återanvända och kombinera befintliga målgrupper, lägga till fler filter till dem, osv.

1. Definiera det **[!UICONTROL Test profiles]** du vill använda för e-postmeddelandet. Testprofilerna får de korrektur som du kan skicka innan för att testa e-postmeddelandet innan du skickar det till huvudmålet.

   Mer information om hur du konfigurerar testprofiler finns i avsnittet [Testprofiler](../../audiences/using/managing-test-profiles.md) .

Målgruppsblocket uppdateras sedan och visar att ett mål- och testprofiler har valts för e-postmeddelandet i fråga.

![](assets/delivery_audience_definition_3.png)

