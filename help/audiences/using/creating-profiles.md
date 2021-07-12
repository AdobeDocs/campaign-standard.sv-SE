---
solution: Campaign Standard
product: campaign
title: Skapa profiler
description: Lär dig hur du skapar profiler och samlar in data om dina kontakter med hjälp av API:er, importfunktioner, onlineförvärv, automatiska eller manuella uppdateringar.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiler
role: User
level: Beginner
exl-id: 827df9f6-070c-466a-890c-e363de6b129b
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 89%

---

# Skapa profiler{#creating-profiles}

I Adobe Campaign används profiler som standard för att definiera meddelandets huvudmål.

>[!NOTE]
>
>Det går även att skapa profiler med API:n för Adobe Campaign Standard.  Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/creating-profiles.md).

![](assets/do-not-localize/how-to-video.png) [Se hur du importerar profiler med hjälp av ett arbetsflöde i en video](#video)

Om du vill skapa eller uppdatera en profil i Campaign kan du:

* Importera en profillista från en fil via ett [arbetsflöde](../../automating/using/creating-import-workflow-templates.md)
* Samla in data online via [landningssidor](../../channels/using/getting-started-with-landing-pages.md)
* Skapa bulk via [REST API](../../api/using/get-started-apis.md)
* Synkronisera profiler från [Microsoft Dynamics](../../integrating/using/d365-acs-get-started.md)
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
   * Kategorin **[!UICONTROL Access authorization]** anger profilens organisationsenheter som [hanterar behörigheter](../../administration/using/about-access-management.md). Om du vill lägga till fält för organisation i dina profiler, se avsnittet [Partitionsprofiler](../../administration/using/organizational-units.md#partitioning-profiles) .
   * **[!UICONTROL Traceability]**-kategorin uppdateras automatiskt med information om den användare som skapade eller ändrade profilen.

1. Klicka **[!UICONTROL Create]** för att spara profilen.

Profilen visas nu i listan.

>[!NOTE]
>Det önskade språkfältet används för att välja språk när flerspråkiga meddelanden skickas.  Mer information om de flerspråkiga meddelandena [finns på den här sidan](../../channels/using/creating-a-multilingual-email.md).

## Videokurs {#video}

I den här videon visas hur du importerar profiler med ett arbetsflöde.

>[!VIDEO](https://video.tv.adobe.com/v/24993?quality=12)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
