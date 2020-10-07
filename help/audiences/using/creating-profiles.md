---
title: Skapa profiler
description: Lär dig hur du skapar profiler och samlar in data om dina kontakter med hjälp av API:er, importfunktioner, onlineförvärv, automatiska eller manuella uppdateringar.
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 97%

---


# Skapa profiler{#creating-profiles}

I Adobe Campaign används profiler som standard för att definiera meddelandets huvudmål.

>[!NOTE]
>
>Det går även att skapa profiler med API:n för Adobe Campaign Standard.  Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/creating-profiles.md).

Om du vill skapa eller uppdatera en profil i Campaign kan du:

* Importera en profillista från en fil via ett [arbetsflöde](../../automating/using/creating-import-workflow-templates.md)
* Samla in data online via [landningssidor](../../channels/using/getting-started-with-landing-pages.md)
* Skapa bulk via [REST API](../../api/using/get-started-apis.md)
* Synkronisera profiler från [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* Ange data med hjälp av de grafiska gränssnittsskärmarna som förklaras nedan

Om du exempelvis vill skapa en ny profil direkt i användargränssnittet följer du stegen nedan:

1. På Adobe Campaign hemsida klickar du på **kortet för kundprofilen** eller fliken **Profiler** för att få tillgång till listan med profiler.

   ![](assets/profile_creation_1.png)

1. Klicka på **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Ange profildata.

   ![](assets/profile_creation1.png)

   * Kontaktinformationen som exempelvis förnamn, efternamn, kön, födelsedatum, foto, föredraget språk (för [flerspråkiga e-postmeddelanden](../../channels/using/creating-a-multilingual-email.md)) hjälper till att bättre personalisera leveranser.
   * Profilens **[!UICONTROL Time zone]** används för att skicka leveranser i profilens tidszon.  Mer information om detta hittar du i det här [avsnittet](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * I kategorin **[!UICONTROL Channels]** som innehåller e-postadress, mobiltelefonnummer och avanmälningsinformation kan du se via vilken kanal profilen kan nås.
   * Kategorin uppdateras så snart som **[!UICONTROL No longer contact]** profilen avprenumererar från en kanal.
   * Kategorin innehåller **[!UICONTROL Address]** den postadress som måste fyllas i tillsammans med **[!UICONTROL Address specified]** alternativet att skicka [direktmeddelanden](../../channels/using/about-direct-mail.md) till den här profilen.  Om alternativ **[!UICONTROL Address specified]** inte är markerat utesluts den här profilen från alla direktmeddelanden.
   * The **[!UICONTROL Access authorization]** category indicates the profile&#39;s organizational units to [manage permissions](../../administration/using/about-access-management.md). Om du vill lägga till fält för organisation i dina profiler, se avsnittet [Partitionsprofiler](../../administration/using/organizational-units.md#partitioning-profiles) .
   * **[!UICONTROL Traceability]**-kategorin uppdateras automatiskt med information om den användare som skapade eller ändrade profilen.

1. Klicka **[!UICONTROL Create]** för att spara profilen.

Profilen visas nu i listan.

>[!NOTE]
>Det önskade språkfältet används för att välja språk när flerspråkiga meddelanden skickas.  Mer information om de flerspråkiga meddelandena [finns på den här sidan](../../channels/using/creating-a-multilingual-email.md).

**Relaterade ämnen:**

* [Om landningssidor](../../channels/using/getting-started-with-landing-pages.md) , steg-för-steg-guide
* [Video om att importera profiler](https://video.tv.adobe.com/v/24993?captions=swe)
