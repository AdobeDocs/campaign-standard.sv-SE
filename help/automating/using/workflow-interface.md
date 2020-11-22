---
solution: Campaign Standard
product: campaign
title: Arbetsflödesgränssnitt
description: Lär dig gränssnittet och alternativen för att skapa, redigera och köra ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---


# Arbetsflödesgränssnitt{#workflow-interface}

Ni kan skapa arbetsflöden för att hantera hela processer i era kampanjer och program.

Skärmen för arbetsflödesredigering består av följande element:

* Paletten [som](#palette)refererar till de tillgängliga aktiviteterna.
* Den [arbetsyta](#workspace)där aktiviteterna är konfigurerade och ordnade.
* Åtgärdsfältet [](#action-bar), som består av knappar som gör att du kan interagera med arbetsflödet och/eller dess komponenter.
* Med [snabbåtgärderna](#quick-actions), som visas runt en markerad aktivitet, kan du interagera med den.

![](assets/wkf_overview.png)

## Palett {#palette}

Paletten finns till vänster på skärmen. Alla tillgängliga aktiviteter är sorterade i flera kategorier:

* [Målgruppsanpassning](../../automating/using/about-targeting-activities.md): verksamhet som är specifik för målgruppsanpassning, hantering av populationsdata och filtrering
* [Körning](../../automating/using/about-execution-activities.md): aktiviteter som är specifika för att organisera och köra arbetsflöden
* [Kanaler](../../automating/using/about-channel-activities.md): aktiviteter som representerar olika tillgängliga kommunikationskanaler
* [Datahantering (ETL)](../../automating/using/about-data-management-activities.md): åtgärder som är specifika för att hantera data

Om du vill använda en aktivitet från paletten i arbetsflödet drar och släpper du den på arbetsytan.

Du måste konfigurera varje aktivitet som läggs till från paletten innan du startar arbetsflödet.

![](assets/workflow_palette.png)

## Arbetsyta {#workspace}

Arbetsytan är den centrala zonen i arbetsflödesredigeraren. Det är i den här zonen som du kan släppa dina aktiviteter, länka samman dem med övergångar och konfigurera dem.

Om du vill länka två aktiviteter flyttar du pilslutet från den första aktiviteten till nästa tills de ansluter. Du kan också flytta aktiviteten mot pilen bakom för att länka den till föregående aktivitet. Om du flyttar någon av aktiviteterna kommer de att vara länkade.

Övergångar som följer på aktiviteter som behandlar data innehåller de mellanliggande populationerna. Du kan komma åt dem om du markerar **[!UICONTROL Keep interim results]** alternativet i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna.

>[!CAUTION]
>
>Det här alternativet kräver mycket diskutrymme och är utformat för att hjälpa dig att skapa ett arbetsflöde och säkerställa korrekt konfiguration och beteende. Låt det vara omarkerat vid produktionsinstanser.


När en aktivitet är markerad visas snabbåtgärder runt aktiviteten så att du kan interagera med den. Om du till exempel vill konfigurera en aktivitet markerar du den och öppnar den sedan med knappen ![](assets/edit_darkgrey-24px_table.png) i snabbåtgärderna.

Vissa funktioner är bara aktiverade på arbetsytan:

* Välj flera aktiviteter och övergångar genom att dra en zon runt dem.
* Tryck på **Ctrl** + vänsterklicka för att markera flera aktiviteter och/eller övergångar.
* Tryck på **Retur** för att visa detaljerna för den valda aktiviteten eller övergången.
* Tryck på **Ta bort** för att ta bort den markerade aktiviteten.
* Tryck på **Ctrl + C** för att kopiera de markerade aktiviteterna och **Ctrl + V** för att klistra in dem på arbetsytan.

![](assets/workflow_workspace.png)

## Åtgärdsfält {#action-bar}

Beroende på vilka element som är markerade på arbetsytan eller arbetsflödets körningsstatus kan knapparna som är tillgängliga i åtgärdsfältet variera.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Gör att du kan redigera arbetsflödets egenskaper.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Startar arbetsflödet.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pausar arbetsflödet.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Avbryter arbetsflödeskörning. Det går inte att fortsätta från där den stoppades.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Startar om arbetsflödet.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Öppnar arbetsflödets körningslogg.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Aktiverar flermarkeringsläge. Arbetsflödet måste bestå av minst två aktiviteter.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Inaktiverar flervalsläge.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Öppnar den markerade övergången.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Återaktiverar markeringen om den tidigare har inaktiverats eller markerats som pausad.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausar arbetsflödet vid den valda aktiviteten.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Inaktiverar aktiviteten.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Tar bort de aktiviteter som är markerade.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Kopierar de aktiviteter som är markerade.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Klistrar in de aktiviteter som har kopierats.

## Snabbåtgärder {#quick-actions}

När en aktivitet är markerad visas snabbåtgärdsknappar runt aktiviteten så att du kan interagera med den.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Öppnar den markerade aktiviteten.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Kopierar den valda aktiviteten.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Öppnar de avancerade alternativen för den valda e-post- eller SMS-leveransaktiviteten.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Återaktiverar markeringen om den tidigare har inaktiverats eller markerats som pausad.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausar arbetsflödet vid den valda aktiviteten.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Inaktiverar aktiviteten.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Tvingar fram omedelbar bearbetning av markeringen. Den här knappen är bara tillgänglig för <span class="uicontrol">schemaläggaren</span> och <span class="uicontrol">väntande</span> aktiviteter.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Tar bort de aktiviteter som är markerade.

## Duplicera arbetsflödesaktiviteter {#duplicating-workflow-activities}

Med arbetsytan kan du duplicera arbetsflödesaktiviteter genom att kopiera och klistra in dem i samma arbetsflöde, eller i ett annat arbetsflöde från samma Campaign-instans.

När en aktivitet har duplicerats behålls hela dess konfiguration. För leveransaktiviteter (e-post, SMS, push-meddelanden..) dupliceras leveransobjektet som är kopplat till aktiviteten.

>[!NOTE]
>
>Arbetsflödesaktiviteter kan inte dupliceras från en instans till en annan. Aktiviteter från tekniska arbetsflöden kan inte dupliceras.

Så här duplicerar du en aktivitet:

1. Markera aktiviteten och klicka sedan på **[!UICONTROL Copy selection]** knappen bland snabbåtgärderna.

   Du kan också använda kortkommandot **Ctrl + C** .

   ![](assets/wkf_copypaste1.png)

1. Högerklicka på arbetsflödets målarbetsyta och klicka sedan på **[!UICONTROL Paste]** knappen.

   Du kan också använda kortkommandot **CTRL + V** .

   ![](assets/wkf_copypaste2.png)

1. Aktiviteten dupliceras med alla inställningar som har konfigurerats från början.

Det går också att kopiera och klistra in flera aktiviteter, så att du kan duplicera ett helt arbetsflöde.

Välj aktiviteter genom att rita en zon runt dem. och sedan klicka på **[!UICONTROL Copy selection]** knappen i åtgärdsfältet (eller tryck på **Ctrl + C**). Du kan sedan klistra in dem på önskad plats.

![](assets/wkf_copypaste3.png)

