---
title: Skapa en anpassad profildimension
description: Lär dig hur du skapar en anpassad profildimension baserad på anpassade profildata.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---

# Skapa en anpassad profildimension{#creating-a-custom-profile-dimension}

Rapporter kan också skapas och hanteras baserat på anpassade profildata som skapats med det anpassade profilresurstillägget.

I det här exemplet vill vi skapa det anpassade profilfältet **Lojalitetsprogram** som kommer att delas in i tre nivåer: guld, silver och brons. Den anpassade profilen utökas sedan så att den kan användas som en anpassad profildimension i dynamiska rapporter.

* [Steg 1: Skapa ett nytt profilfält](#step-1--create-a-new-profile-field)
* [Steg 2: Utöka de sändande loggarna med profilfältet](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Steg 3: Skapa en leverans riktad till mottagare som är registrerade i lojalitetsprogrammet](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Steg 4: Skapa en dynamisk rapport för att filtrera mottagare med den anpassade profildimensionen](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Steg 1: Skapa ett nytt profilfält {#step-1--create-a-new-profile-field}

Vi måste först skapa det nya profilfältet **Förmånsprogram** som tilldelar våra mottagare lojalitetsnivå: guld, silver eller brons.

>[!NOTE]
>
>Anpassade resurser kan bara hanteras av en administratör.

För att göra detta:

1. Välj på den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** sedan **[!UICONTROL Profile (profile)]** anpassad resurs.

   ![](assets/custom_profile_1.png)

1. Från **[!UICONTROL Data structure]** -fliken, i **[!UICONTROL Fields]** klickar du på **[!UICONTROL Add field]** -knappen.

   ![](assets/custom_profile_2.png)

1. Ange **[!UICONTROL Label]**, **[!UICONTROL ID]** och välja en anpassad resurs **[!UICONTROL Type]**. Här har vi valt **[!UICONTROL Text]** eftersom mottagarna kan välja mellan guld, silver och brons.

   ![](assets/custom_profile_3.png)

1. Klicka på ![](assets/custom_profile_22.png) -ikonen för att definiera fältet.

   ![](assets/custom_profile_12.png)

1. Här måste vi ange auktoriserade värden genom att kontrollera **[!UICONTROL Specify a list of authorized valued]** och skapa varje värde genom att klicka **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Ange **[!UICONTROL Label]** och **[!UICONTROL Value]** klicka sedan på **[!UICONTROL Add]**. I det här exemplet måste vi skapa värdet guld, silver och brons. Klicka på **[!UICONTROL Confirm]** när du är klar.

   ![](assets/custom_profile_14.png)

1. Klicka på fliken **[!UICONTROL Screen definition]**.  I **[!UICONTROL Detail screen configuration]** nedrullningsbar meny, kontrollera **[!UICONTROL Add personalized fields]** för att skapa ett nytt avsnitt i vår profil.

   ![](assets/custom_profile_4.png)

1. Klicka på **[!UICONTROL Add an element]** för att skapa det nya avsnittet. Välj **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** eller **[!UICONTROL List]** och sedan fältet som ska läggas till i det nya avsnittet.

   ![](assets/custom_profile_5.png)

1. Du kan också lägga till en titel i avsnittet i fältet **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Klicka **[!UICONTROL Save]** när konfigurationen är klar.

   ![](assets/custom_profile_6.png)

1. Välj på den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** för att börja publicera din anpassade resurs.
1. Klicka **[!UICONTROL Prepare publication]** när färdigställandet är klart klickar du på **[!UICONTROL Publish]** -knappen.

   ![](assets/custom_profile_7.png)

Det nya profilfältet är nu klart att användas och markeras av dina mottagare.

![](assets/custom_profile_8.png)

## Steg 2: Utöka de sändande loggarna med profilfältet {#step-2--extend-the-sending-logs-with-the-profile-field}

Nu när ditt profilfält har skapats måste vi utöka de sändande loggarna med vårt profilfält för att skapa den associerade anpassade profildimensionen i dynamiska rapporter.

Innan du utökar loggen med vårt profilfält bör du kontrollera att PII-fönstret har accepterats för åtkomst till **[!UICONTROL Sending logs extension]** -fliken. Se denna [sida](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) för mer information om detta.

>[!NOTE]
>
>Loggar kan bara utökas med profilfält av administratören.

1. Välj på den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** sedan **[!UICONTROL Profile (profile)]** anpassad resurs.
1. Öppna **[!UICONTROL Sending logs extension]** nedrullningsbar meny.
1. Klicka på knappen **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Markera det fält du skapat tidigare och klicka på **[!UICONTROL Confirm]**.
1. Kontrollera **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** för att skapa en anpassad profildimension.

   ![](assets/custom_profile_10.png)

   Det här alternativet är bara tillgängligt om PII-fönstret har godkänts. Se denna [sida](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) för mer information om detta.

1. Klicka **[!UICONTROL Add]** spara sedan din anpassade resurs.
1. Eftersom den anpassade resursen ändrades måste den publiceras för att implementera de nya ändringarna.

   Välj på den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** för att börja publicera din anpassade resurs.

1. Klicka **[!UICONTROL Prepare publication]** när färdigställandet är klart klickar du på **[!UICONTROL Publish]** -knappen.

   ![](assets/custom_profile_7.png)

Din anpassade profil är nu tillgänglig som en anpassad profildimension i dina rapporter.

Nu när fältet har skapats och loggen har utökats med det här profilfältet kan du börja rikta in mottagare i leveranser.

## Steg 3: Skapa en leverans riktad till mottagare som är registrerade i lojalitetsprogrammet {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

När profilfältet har publicerats kan du påbörja leveransen. I det här exemplet vill vi inrikta oss på alla mottagare som är registrerade i lojalitetsprogrammet.

1. På fliken **[!UICONTROL Marketing activities]**, klicka på **[!UICONTROL Create]** och välj sedan **[!UICONTROL Email]**.
1. Välj en **[!UICONTROL Email type]** Ange sedan egenskaperna för e-postmeddelandet.
1. Dra och släpp **[!UICONTROL Profiles (attributes)]** aktivitet.
1. Välj det fält du skapat tidigare från **[!UICONTROL Field]** nedrullningsbar meny.

   ![](assets/custom_profile_16.png)

1. Välj **[!UICONTROL Filter conditions]**. Här vill vi rikta in oss på mottagare som ingår i en av de tre lojalitetsprogrammens nivåer.

   ![](assets/custom_profile_17.png)

1. Klicka **[!UICONTROL Confirm]** när du är klar med filtreringen klickar du **[!UICONTROL Next]**.
1. Definiera och anpassa meddelandeinnehåll, avsändarens namn och ämne. Mer information om att skapa e-post finns i [page](../../designing/using/designing-content-in-adobe-campaign.md).

   Klicka sedan på **[!UICONTROL Create]**.

1. När det är klart kan du förhandsgranska och skicka meddelandet. Mer information om hur du förbereder och skickar meddelanden finns i [page](../../sending/using/preparing-the-send.md).

När e-postmeddelandet har skickats korrekt till de valda mottagarna kan du börja filtrera dina data och spåra hur framgångsrik leveransen är med hjälp av rapporter.

## Steg 4: Skapa en dynamisk rapport för att filtrera mottagare med den anpassade profildimensionen {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

När leveransen är klar kan du dela upp rapporter med hjälp av din anpassade profildimension från **[!UICONTROL Profile]** tabell.

1. Från **[!UICONTROL Reports]** väljer du en färdig rapport eller klickar på **[!UICONTROL Create]** för att starta en från början.

   ![](assets/custom_profile_18.png)

1. I **[!UICONTROL Dimensions]** kategori, klicka på **[!UICONTROL Profile]** dra och släpp dina egna **Förmånsprogram** profildimension till frihandstabellen.

   ![](assets/custom_profile_19.png)

1. Dra och släpp **[!UICONTROL Processed/Sent]** och **[!UICONTROL Open]** mätvärden för att börja filtrera data.

   ![](assets/custom_profile_20.png)

1. Dra och släpp en visualisering på arbetsytan om det behövs.

   ![](assets/custom_profile_21.png)

**Relaterat ämne:**

* [Använda anpassade profildata för att skapa insikter om rapporter](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
