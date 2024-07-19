---
title: Använda Segment Builder
description: Lär dig hur du använder Segment Builder för att skapa målgrupper.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 3%

---

# Använda Segment Builder {#using-the-segment-builder}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

Med segmentbyggaren kan du skapa målgrupper genom att definiera regler som baseras på data från [kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

I det här avsnittet beskrivs globala koncept när du skapar ett segment. Mer information om själva segmentbyggaren finns i användarhandboken för [Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

Segment Builder-gränssnittet består av följande:

* Den vänstra rutan innehåller alla attribut, händelser och målgrupper som är tillgängliga för att skapa segmentet genom att dra och släppa önskade fält på arbetsytan för segmentbyggaren.
* I mittområdet finns en arbetsyta som du kan använda för att skapa segmentet genom att definiera och kombinera regler från de tillgängliga fälten.
* I huvudet och den högra rutan visas segmentets egenskaper (d.v.s. namn, beskrivning och beräknade kvalificerade profiler för segmentet).

![](assets/aep_audiences_interface.png)

## Bygga ett segment

Så här skapar du ett segment:

Segmentverktyget bör nu visas på arbetsytan. Det gör att ni kan skapa ett segment med hjälp av data från Adobe Experience Platform som så småningom kommer att användas för att skapa er målgrupp.

1. Namnge segmentet och ange sedan en beskrivning (valfritt).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Se till att den sammanfogningsprincip du vill använda är markerad i inställningspanelen.

   Mer information om sammanfogningsprinciper finns i det dedikerade avsnittet i användarhandboken för [Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Leta efter önskade fält i den vänstra rutan och dra dem till arbetsytan i mitten.

   ![](assets/aep_audiences_dragfield.png)

1. Konfigurera reglerna som motsvarar de fält som dras.

   ![](assets/aep_audiences_configure_rules.png)

1. Klicka på knappen **[!UICONTROL Create segment]**.

## Hitta rätt fält för ett segment

I den vänstra rutan visas alla attribut, händelser och målgrupper som är tillgängliga för att skapa regler.

Fälten i listan är attribut som hämtats av ditt företag och har gjorts tillgängliga via [Experience Data Model (XDM) System](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).

Fälten är ordnade i flikar:

* **[!UICONTROL Attributes]**: Befintliga profilattribut som kan komma från din Adobe Campaign-databas och/eller Adobe Experience Platform. De avser statisk information som bifogas en profil (t.ex. e-postadress, bosättningsland, lojalitetsprogrammets status osv.).

  ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**: Aktiviteter som identifierar konsumenter som har haft någon interaktion med företagets kontaktytor, till exempel&quot;alla som har beställt två gånger på två veckor&quot;. Detta kan strömmas från Adobe Analytics eller kapslas direkt in i Adobe Experience Platform med ETL-verktyg från tredje part.

  ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**Segmentering för flera enheter** gör att du kan utöka profildata med ytterligare data baserat på produkter, butiker eller andra klasser som inte är profiler. När de är anslutna blir data från ytterligare klasser tillgängliga som om de vore inbyggda i profilschemat.
>
>Mer information om detta hittar du i den [dedikerade dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html).

Som standard visar Segment Builder fält där data redan finns. Om du vill visa det fullständiga schemat, inklusive fält för vilka data inte finns, aktiverar du alternativet **[!UICONTROL Show full XDM schema]** från inställningarna.

![](assets/aep_audiences_populatedfields.png)

Symbolen i slutet av varje fält innehåller ytterligare information om attributet och hur det används.

![](assets/aep_audiences_isymbol.png)

## Definiera regler för ett segment

>[!NOTE]
>
>Avsnittet nedan innehåller global information om regeldefinition. Mer information finns i användarhandboken för [Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

Så här skapar du en regel:

1. Hitta fältet i den vänstra rutan som visar de attribut eller händelser som regeln ska baseras på.

1. Dra fältet till arbetsytan i mitten och konfigurera det sedan enligt den önskade segmentdefinitionen. Det finns flera funktioner för sträng och datum/tid.

   I exemplet nedan är regeln inriktad på alla profiler med ett kön som är lika med &quot;Man&quot;.

   ![](assets/aep_audiences_malegender.png)

   Den beräknade populationen som motsvarar segmentet beräknas om automatiskt i avsnittet **[!UICONTROL Segment Properties]**.

1. Knappen **[!UICONTROL View Profiles]** ger dig en förhandsgranskning av de första 20 posterna som motsvarar regeln, så att du snabbt kan validera segmentet.

   ![](assets/aep_audiences_samplepreview.png)

   Du kan lägga till så många ytterligare regler som du vill för att skapa rätt profiler.

   När du lägger till en regel i en behållare läggs den till i befintliga regler med operatorn AND. Klicka vid behov på den logiska operatorn för att ändra den.

   ![](assets/aep_audiences_andoperator.png)

När de två reglerna är sammanlänkade utgör de en behållare.

## Jämföra fält

Med segmentbyggaren kan du jämföra två fält för att definiera en regel. Till exempel kvinnor vars hemadress är i en annan postnummer än deras arbetsadress.

Följ dessa steg för att göra detta:

1. Dra det första fältet som du vill jämföra (t.ex. hemadressens postnummer) till arbetsytan i mitten.

   ![](assets/aep_audiences_comparing_1.png)

1. Välj det andra fältet (t.ex. arbetsadressens postnummer) som ska jämföras med det första fältet.

   Dra den till arbetsytan i mitten, i samma behållare som det första fältet, i rutan **[!UICONTROL Drop here to compare operands]**.

   ![](assets/aep_audiences_comparing_2.png)

1. Konfigurera operatorn mellan de två fälten efter behov. I det här exemplet vill vi att vårt segment ska ha profiler med en annan hemadress än arbetsadressen.

   ![](assets/aep_audiences_comparing_3.png)

Regeln är nu konfigurerad och klar att aktiveras som målgrupp.
