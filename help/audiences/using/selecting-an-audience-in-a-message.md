---
title: Välja en målgrupp i ett meddelande
description: '"Stegvisa procedurer för att välja målgrupper i ett e-postmeddelande. Huvudmålpopulation och testprofiler."'
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 83%

---


# Välja en målgrupp i ett meddelande{#selecting-an-audience-in-a-message}

Med Adobe Campaign kan du konfigurera flera profiltyper i ett meddelandes målgrupp.

Målgrupper kan definieras när meddelandet skapas via meddelandeskaparhjälparen i kontrollpanelen om meddelandet redan har skapats.

>[!NOTE]
>
>Om målgruppen har byggts in i ett arbetsflöde och berikats med ytterligare data kan du inte använda denna data för att personalisera en fristående leverans.  Datan kan endast användas vid en leverans som körs i ett arbetsflöde.

1. Gå till målgruppsblocket i kontrollpanelen för att börja.

   ![](assets/delivery_audience_definition_1.png)

   Skärmen som definierar målgrupperna öppnas.  Det finns två flikar där du kan definiera var och en av de målgrupper som separat ska få meddelandet:

   * Mål
   * Testprofiler

   ![](assets/delivery_audience_definition_2.png)

1. Definiera huvuddelen **[!UICONTROL Target]** av e-postmeddelandet.    Det här är den vanliga målgruppen för e-postmeddelandet.

   Målet definieras i fliken **[!UICONTROL Target]** och består av identifierade profiler från databasen.

   Du kan etablera huvudmålet med funktionerna för [förfrågningsredigering](../../automating/using/editing-queries.md#creating-queries).

   I den här fliken innehåller **[!UICONTROL Shortcuts]** paletten endast fördefinierade filter och de målgrupper som har definierats i de identifierade profilerna.  På fliken **[!UICONTROL Explorer]** kan du komma åt ytterligare konfigurationer.

   Du kan därför återanvända och kombinera befintliga målgrupper, lägga till fler filter till dem etc.

1. Definiera det **[!UICONTROL Test profiles]** du vill använda för e-postmeddelandet.  Testprofilerna får den version som du kan skicka innan för att testa e-postmeddelandet innan du skickar ut det till huvudmålet.

   Mer information om hur du konfigurerar testprofiler finns i avsnittet [Testprofiler](../../audiences/using/managing-test-profiles.md).

1. Om det behövs kan du definiera en kontrollgrupp med hjälp av motsvarande flik. På så sätt kan du dra tillbaka vissa profiler från målet så att de inte får meddelandet. For more on this, see [Adding a control group](../../sending/using/control-group.md).

1. Du kan också använda ersättningsadresser för att få en exakt representation av meddelandet som profilen kommer att ta emot.  Mer information finns i [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md).

Målgruppsblocket uppdateras sedan och visar att ett mål och testprofiler har valts för e-postmeddelandet i fråga.

![](assets/delivery_audience_definition_3.png)

