---
title: Skapa målgrupper
description: Lär dig hur du skapar målgrupper i Adobe Campaign.
page-status-flag: never-activated
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbbe
context-tags: readAudience,main;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Skapa målgrupper{#creating-audiences}

## Skapa frågemålgrupper {#creating-query-audiences}

I det här avsnittet beskrivs hur du skapar en **frågepublik** . Du kan också skapa målgrupper genom att importera en fil eller målinrikta i ett [arbetsflöde](../../automating/using/get-started-workflows.md).

Från målgruppslistan kan ni skapa målgrupper genom att utföra frågor i Adobe Campaign-profiler eller importera en Adobe Experience Cloud-målgrupp.

1. Gå till målgruppslistan via **[!UICONTROL Audiences]** fliken eller kortet.

   ![](assets/audiences_query_1.png)

1. Välj **[!UICONTROL Create]** att få åtkomst till skärmen för att skapa en ny publik.

   ![](assets/audiences_query.png)

1. Ge er målgrupp ett namn. Målgruppsetiketten används i listan över målgrupper och i paletten för frågeverktyget.
1. Välj en **[!UICONTROL Query]** målgruppstyp: de målgrupper som definieras av en fråga beräknas om vid varje ytterligare användning.

   ![](assets/audience_type_selection.png)

1. Välj sedan den **[!UICONTROL Targeting dimension]** som du vill använda för att filtrera kunderna. Varje målgrupp består av en enda målinriktningsdimension. Du kan till exempel inte skapa en målgrupp som består av både profiler, testprofiler och prenumeranter. Mer information om måldimensioner finns på [den här sidan](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Skapa frågan för att definiera målgruppspopulationen. Mer information finns i avsnittet [Redigera frågor](../../automating/using/editing-queries.md).
1. Klicka på **[!UICONTROL Create]** knappen för att spara din publik.

>[!NOTE]
>
>Du kan lägga till en beskrivning till den här målgruppen och definiera åtkomstauktoriseringarna via **[!UICONTROL Edit properties]** -ikonen.

## Skapa listmålgrupper {#creating-list-audiences}

I det här avsnittet beskrivs hur du skapar en **List** -målgrupp efter målgruppsanpassning i ett arbetsflöde. Du kan också skapa målgrupper genom att importera en fil till ett [arbetsflöde](../../automating/using/get-started-workflows.md) eller via en fråga på **[!UICONTROL Audiences]** menyn.

Så här skapar du en **List** -målgrupp:

1. Klicka på **Skapa** på fliken **Marknadsföringsaktiviteter** och välj sedan **Arbetsflöde**.

   ![](assets/audiences_list_1.png)

1. Dra och släpp och konfigurera sedan målinriktningsaktiviteterna så att du kan välja en population som har en **känd** dimension. Listan över tillgängliga aktiviteter och deras konfiguration finns i avsnittet [Målaktiviteter](../../automating/using/about-targeting-activities.md) .

   Du kan använda en **[!UICONTROL Query]** aktivitet eller importera data med en **[!UICONTROL Load file]** aktivitet innan du använder en **[!UICONTROL Reconciliation]** aktivitet för att identifiera dimensionen för de data som importeras. Här vill vi rikta oss till mottagare som prenumererar på sportnyhetsbrevet med en **[!UICONTROL Query]** aktivitet.

   ![](assets/audiences_list_2.png)

1. Dra och släpp en aktivitet i arbetsflödet efter att du har skapat den. **[!UICONTROL Save audience]** Du kan t.ex. välja att **[!UICONTROL Create or update an audience]** skapa och sedan automatiskt uppdatera målgruppen med nya data. I det här fallet lägger du till en **[!UICONTROL Scheduler]** aktivitet i början av arbetsflödet.

   Mer information om hur du konfigurerar den här aktiviteten finns i avsnittet [Spara målgrupp](../../automating/using/save-audience.md) .

   ![](assets/audiences_list_3.png)

1. Spara och starta arbetsflödet.

   Eftersom målgruppen **[!UICONTROL Save audience]** placeras efter en målinriktning med en känd dimension är målgrupperna som skapas via den här aktiviteten **List** -målgrupper.

   Innehållet i den sparade målgruppen är sedan tillgängligt i målgruppens detaljerade vy, som du kommer åt via listan över målgrupper. Kolumnerna som är tillgängliga från den här vyn motsvarar kolumnerna för den inkommande övergången i arbetsflödets sparningsaktivitet. Till exempel: kolumnerna i den importerade filen, de ytterligare data som lagts till från en fråga.

   ![](assets/audiences_list_4.png)

## Skapa filmålgrupper {#creating-file-audiences}

I det här avsnittet beskrivs hur du skapar en **filmålgrupp** genom att importera en fil till ett arbetsflöde. Du kan också skapa målgrupper från en målinriktningsaktivitet i ett [arbetsflöde](../../automating/using/get-started-workflows.md) eller via en fråga på **[!UICONTROL Audiences]** menyn.

Så här skapar du en publik med **filer** :

1. Klicka på **Skapa** på fliken **Marknadsföringsaktiviteter** och välj sedan **Arbetsflöde**.
1. Dra och släpp och konfigurera sedan en **[!UICONTROL Load file]** aktivitet som gör att du kan importera en ifyllning med en **okänd** dimension när arbetsflödet körs. Mer information om hur du konfigurerar den här aktiviteten finns i avsnittet [Läs in fil](../../automating/using/load-file.md) .

   ![](assets/audience_files_1.png)

1. Dra och släpp en **[!UICONTROL Save audience]** aktivitet efter **[!UICONTROL Load file]** aktiviteten. Mer information om hur du konfigurerar den här aktiviteten finns i avsnittet [Spara målgrupp](../../automating/using/save-audience.md) .
1. Spara och starta arbetsflödet.

   ![](assets/audience_files_2.png)

   När filen **[!UICONTROL Save audience]** placeras efter en import är datamätningen okänd och målgrupperna som skapas via den här aktiviteten är **Filmålgrupper** .

   Innehållet i den sparade målgruppen är sedan tillgängligt i målgruppens detaljerade vy, som du kommer åt via listan över målgrupper. Kolumnerna som är tillgängliga från den här vyn motsvarar kolumnerna för den inkommande övergången i arbetsflödets sparningsaktivitet. Till exempel: kolumnerna i den importerade filen, de ytterligare data som lagts till från en fråga.

   ![](assets/audience_files_3.png)

## Skapa Experience Cloud-målgrupper {#creating-experience-cloud-audiences}

Med Adobe Campaign kan ni dela och utbyta målgrupper med Adobe Experience Cloud. En publik av typen **Experience Cloud** importeras direkt från personbastjänsten till Adobe Campaign med det **[!UICONTROL Import shared audience]** tekniska arbetsflödet.

Till skillnad från **frågetypsanvändare** som hämtar profiler från Adobe Campaign består **Experience Cloud** -publiken av en lista med besökar-ID:n.

För att den här integreringen ska fungera måste du först konfigurera den. Mer information om konfiguration och hur du importerar eller exporterar målgrupper med huvudtjänsten Personer finns i följande [avsnitt](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

![](assets/audience_peoplecore.png)

## Redigera målgrupper {#editing-audiences}

Det finns olika sätt att redigera en målgrupp beroende på målgruppstypen:

* Om du vill redigera en **frågepublik** går du till listan över målgrupper via **[!UICONTROL Audiences]** menyn eller **[!UICONTROL Audiences]** kortet från hemsidan för Adobe Campaign.

   Öppna rätt målgrupp. Alla element i en tidigare skapad publik kan redigeras.

   >[!CAUTION]
   >
   >Om du ändrar **[!UICONTROL Filtering dimension]** i frågan kommer de regler som tidigare har definierats att gå förlorade.

* Om du vill redigera en **List** eller **File** -målgrupp redigerar du arbetsflödet som det skapades från och ändrar **[!UICONTROL Save audience]** aktiviteten. Starta arbetsflödet så att målgruppen ändras.
* Om du vill redigera en **Experience Cloud** -målgrupp läser du avsnittet [Importera/exportera målgrupper med](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) personbastjänsten.

## Ta bort målgrupper {#deleting-audiences}

Det finns två sätt att ta bort en eller flera målgrupper. Först kan du lägga till ett förfallodatum till din målgrupp

Så här gör du:

1. Nå en av era målgrupper.
1. Klicka på ![](assets/edit_darkgrey-24px.png) knappen för att komma åt målgruppens konfiguration.

   ![](assets/audience_delete_2.png)

1. I **[!UICONTROL Expires on]** fältet lägger du till ett förfallodatum till målgruppen.

   ![](assets/audience_delete_3.png)

1. Klicka **[!UICONTROL Confirm]** då **[!UICONTROL Save]**.

Ditt förfallodatum är nu konfigurerat. Så snart detta datum har passerats raderas målgruppen automatiskt.

Eller om du vill ta bort en målgrupp kan du markera en eller flera målgrupper och sedan klicka på **[!UICONTROL Delete element]** knappen.

![](assets/audience_delete_1.png)

