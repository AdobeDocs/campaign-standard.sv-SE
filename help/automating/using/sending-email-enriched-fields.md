---
title: Skicka ett e-postmeddelande med berikade fält
description: 'I exemplet nedan visas hur du skickar ett e-postmeddelande med ytterligare data som hämtats från en extern fil via aktiviteten för inläsningsfilen.  '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 75%

---


# Skicka ett e-postmeddelande med berikade fält {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

Aktiviteten för att läsa in filer gör det även möjligt att skicka ett e-postmeddelande som har berikats med ytterligare data från en extern fil i samma arbetsflöde.

I exemplet nedan visas hur du skickar ett e-postmeddelande med ytterligare data som hämtats från en extern fil via aktiviteten för inläsningsfilen.  I det här exemplet innehåller den externa filen en lista med profiler med tillhörande kontonummer.  Du vill importera denna data för att skicka ett e-postmeddelande till varje profil med deras kontonummer.

![](assets/load_file_workflow_ex2.png)

Så här skapar du arbetsflödet:

1. Drag and drop a [Query](../../automating/using/query.md) activity into your workflow and open it to define the main target.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Drag and drop a [Load file](../../automating/using/load-file.md) activity to assign some data to a profile. I det här exemplet läser du in en fil som innehåller kontonummer som motsvarar vissa profiler i databasen.

   ![](assets/load_file_activity.png)

1. Drag and drop an [Enrichment](../../automating/using/enrichment.md) activity into your workflow and link the load file and query activities to it.

1. På fliken **[!UICONTROL Advanced relations]** för berikningsaktiviteter markerar du **[!UICONTROL 0 or 1 cardinality simple link]** och definierar fälten som ska användas för avstämning.  Här använder vi efternamnet för att stämma av data med databasprofilerna.

   ![](assets/load_file_enrichment_relation.png)

1. Markera de element som du vill använda i e-postmeddelandet på fliken **[!UICONTROL Additional data]**.  Här väljer du Kontonummer (kolumn från filen som du hämtade genom aktiviteten av inläsningsfilen).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Mer information finns i [beriknings](../../automating/using/enrichment.md)-avsnittet.

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity into your workflow and open it to refine the main target.

   ![](assets/load_file_segmentation.png)

   Mer information finns i avsnittet [Segmentering](../../automating/using/segmentation.md) .

1. Drag and drop an [Email delivery](../../automating/using/email-delivery.md) activity into your workflow and open it.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Lägg till ett personaliserat fält och välj den ytterligare data som definieras i berikningsaktiviteten (kontonummer) från noden **[!UICONTROL Additional data (targetData)]**.    Detta gör att kontonumret för varje profil i e-postinnehållet dynamiskt kan hämtas.

   ![](assets/load_file_perso_field.png)

1. Spara e-postmeddelandet och starta arbetsflödet.

E-postmeddelandet skickas till målet.  Varje profil får e-postmeddelandet med motsvarande kontonummer.

![](assets/load_file_email.png)
