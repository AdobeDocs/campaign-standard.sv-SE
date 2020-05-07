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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---


# Skapa profiler{#creating-profiles}

I Adobe Campaign används profiler som standard för att definiera meddelandets huvudmål.

Om du vill skapa eller uppdatera en profil i Campaign kan du:

* Importera en profillista från en fil via ett [arbetsflöde](../../automating/using/importing-data.md#example--import-workflow-template)
* Samla in data online via [landningssidor](../../channels/using/getting-started-with-landing-pages.md)
* Skapa bulk via [REST API](../../api/using/get-started-apis.md)
* Synkronisera profiler från [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* Ange data med hjälp av de grafiska gränssnittsskärmarna, vilket förklaras nedan

Om du till exempel vill skapa en ny profil direkt i användargränssnittet följer du stegen nedan:

1. På hemsidan för Adobe Campaign klickar du på **kundprofilkortet** eller fliken **Profiler** för att få tillgång till listan med profiler.

   ![](assets/profile_creation_1.png)

1. Klicka sedan på **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Ange profildata.

   ![](assets/profile_creation1.png)

   * Kontaktinformationen, t.ex. förnamn, efternamn, kön, födelsedatum, foto, föredraget språk (för [flerspråkiga e-postmeddelanden](../../channels/using/creating-a-multilingual-email.md)) hjälper till att personalisera leveranser bättre.
   * Profilens **[!UICONTROL Time zone]** används för att skicka leveranser i profilens tidszon. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * I **[!UICONTROL Channels]** kategorin, som innehåller e-postadress, mobiltelefonnummer och avanmälningsinformation, kan du se vilken kanal profilen kan nås från.
   * Kategorin uppdateras så snart **[!UICONTROL No longer contact]** profilen avbeställer en kanal.
   * Kategorin innehåller **[!UICONTROL Address]** den postadress som måste fyllas i tillsammans med **[!UICONTROL Address specified]** alternativet att skicka [direktreklam](../../channels/using/about-direct-mail.md) till den här profilen. Om **[!UICONTROL Address specified]** alternativet inte är markerat utesluts den här profilen från all direktreklam.
   * Kategorin anger **[!UICONTROL Access authorization]** profilens organisationsenheter (för att [hantera behörigheter](../../administration/using/about-access-management.md)). Se även [Partitionsprofiler](../../administration/using/organizational-units.md#partitioning-profiles).
   * Kategorin uppdateras automatiskt **[!UICONTROL Traceability]** med information om den användare som skapade eller ändrade profilen.

1. Klicka **[!UICONTROL Create]** för att spara profilen.

Profilen visas nu i listan.

>[!NOTE]
>
>Det går också att skapa profiler med API:t för Adobe Campaign Standard. Mer information finns i den [dedikerade dokumentationen](../../api/using/creating-profiles.md).

Profiler kan också partitioneras beroende på deras organisationsenheter. Om du vill lägga till organisationsfält i dina profiler, se avsnittet [Partitionsprofiler](../../administration/using/organizational-units.md#partitioning-profiles) .

>[!NOTE]
>
>Det önskade språkfältet används för att välja språk när flerspråkiga meddelanden skickas. Mer information om de flerspråkiga meddelandena [finns på den här sidan](../../channels/using/creating-a-multilingual-email.md).

**Relaterade ämnen:**

* [Om landningssidor](../../channels/using/getting-started-with-landing-pages.md) , steg-för-steg-guide
* [Video om att importera profiler](https://video.tv.adobe.com/v/24993?captions=swe)
