---
solution: Campaign Standard
product: campaign
title: Skapa en anpassad profildimension
description: Lär dig hur du skapar en anpassad profildimension baserad på anpassade profildata.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---


# Skapa en anpassad profildimension{#creating-a-custom-profile-dimension}

Rapporter kan också skapas och hanteras baserat på anpassade profildata som skapats med det anpassade profilresurstillägget.

I det här exemplet vill vi skapa det anpassade profilfältet **Lojalitetsprogram** som ska delas in i tre nivåer: guld, silver och brons. Den anpassade profilen utökas sedan så att den kan användas som en anpassad profildimension i dynamiska rapporter.

* [Steg 1: Skapa ett nytt profilfält](#step-1--create-a-new-profile-field)
* [Steg 2: Utöka de sändande loggarna med profilfältet](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Steg 3: Skapa en leverans som riktar sig till mottagare som är registrerade i lojalitetsprogrammet](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Steg 4: Skapa en dynamisk rapport för att filtrera mottagare med den anpassade profildimensionen](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Steg 1: Skapa ett nytt profilfält {#step-1--create-a-new-profile-field}

Först måste vi skapa det nya profilfältet **Lojalitetsprogram** som tilldelar lojalitetsnivån till våra mottagare: guld, silver eller brons.

>[!NOTE]
>
>Anpassade resurser kan bara hanteras av en administratör.

För att göra detta:

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** och sedan den anpassade resursen **[!UICONTROL Profile (profile)]** på den avancerade menyn.

   ![](assets/custom_profile_1.png)

1. På fliken **[!UICONTROL Data structure]** i kategorin **[!UICONTROL Fields]** klickar du på knappen **[!UICONTROL Add field]**.

   ![](assets/custom_profile_2.png)

1. Ange **[!UICONTROL Label]**, **[!UICONTROL ID]** och välj den anpassade resursen **[!UICONTROL Type]**. Här har vi valt **[!UICONTROL Text]** eftersom mottagarna kan välja mellan guld, silver och brons.

   ![](assets/custom_profile_3.png)

1. Klicka på ikonen ![](assets/custom_profile_22.png) för att definiera fältet.

   ![](assets/custom_profile_12.png)

1. Här måste vi ange auktoriserade värden genom att markera **[!UICONTROL Specify a list of authorized valued]** och skapa varje värde genom att klicka på **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Ange **[!UICONTROL Label]** och **[!UICONTROL Value]** och klicka sedan på **[!UICONTROL Add]**. I det här exemplet måste vi skapa värdet guld, silver och brons. Klicka på **[!UICONTROL Confirm]** när du är klar.

   ![](assets/custom_profile_14.png)

1. Klicka på fliken **[!UICONTROL Screen definition]**.  I listrutan **[!UICONTROL Detail screen configuration]** markerar du **[!UICONTROL Add personalized fields]** för att skapa ett nytt avsnitt i vår profil.

   ![](assets/custom_profile_4.png)

1. Klicka på knappen **[!UICONTROL Add an element]** för att skapa det nya avsnittet. Välj **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** eller **[!UICONTROL List]**, sedan fältet som ska läggas till i det nya avsnittet.

   ![](assets/custom_profile_5.png)

1. Du kan också lägga till en titel i avsnittet i fältet **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Klicka på **[!UICONTROL Save]** när konfigurationen är klar.

   ![](assets/custom_profile_6.png)

1. På den avancerade menyn väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** för att börja publicera din anpassade resurs.
1. Klicka på **[!UICONTROL Prepare publication]** och klicka sedan på knappen **[!UICONTROL Publish]** när färdigställandet är klart.

   ![](assets/custom_profile_7.png)

Det nya profilfältet är nu klart att användas och markeras av dina mottagare.

![](assets/custom_profile_8.png)

## Steg 2: Utöka de sändande loggarna med profilfältet {#step-2--extend-the-sending-logs-with-the-profile-field}

Nu när ditt profilfält har skapats måste vi utöka de sändande loggarna med vårt profilfält för att skapa den associerade anpassade profildimensionen i dynamiska rapporter.

Innan du utökar loggen med vårt profilfält bör du kontrollera att PII-fönstret har accepterats för åtkomst till fliken **[!UICONTROL Sending logs extension]**. Se denna [sida](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) för mer information om detta.

>[!NOTE]
>
>Loggar kan bara utökas med profilfält av administratören.

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** och sedan den anpassade resursen **[!UICONTROL Profile (profile)]** på den avancerade menyn.
1. Öppna listrutan **[!UICONTROL Sending logs extension]**.
1. Klicka på knappen **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Markera det fält du skapat tidigare och klicka på **[!UICONTROL Confirm]**.
1. Markera **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** om du vill skapa en anpassad profildimension.

   ![](assets/custom_profile_10.png)

   Det här alternativet är bara tillgängligt om PII-fönstret har godkänts. Se denna [sida](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) för mer information om detta.

1. Klicka på **[!UICONTROL Add]** och spara sedan den anpassade resursen.
1. Eftersom den anpassade resursen ändrades måste den publiceras för att implementera de nya ändringarna.

   På den avancerade menyn väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** för att börja publicera din anpassade resurs.

1. Klicka på **[!UICONTROL Prepare publication]** och klicka sedan på knappen **[!UICONTROL Publish]** när färdigställandet är klart.

   ![](assets/custom_profile_7.png)

Din anpassade profil är nu tillgänglig som en anpassad profildimension i dina rapporter.

Nu när fältet har skapats och loggen har utökats med det här profilfältet kan du börja rikta in mottagare i leveranser.

## Steg 3: Skapa en leverans som riktar sig till mottagare som är registrerade i lojalitetsprogrammet {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

När profilfältet har publicerats kan du påbörja leveransen. I det här exemplet vill vi inrikta oss på alla mottagare som är registrerade i lojalitetsprogrammet.

1. På fliken **[!UICONTROL Marketing activities]**, klicka på **[!UICONTROL Create]** och välj sedan **[!UICONTROL Email]**.
1. Välj en **[!UICONTROL Email type]** och ange e-postens egenskaper.
1. Dra och släpp aktiviteten **[!UICONTROL Profiles (attributes)]** om du vill ha en målmottagare registrerad i lojalitetsprogrammet.
1. Markera det fält du skapat tidigare i listrutan **[!UICONTROL Field]**.

   ![](assets/custom_profile_16.png)

1. Välj din **[!UICONTROL Filter conditions]**. Här vill vi rikta in oss på mottagare som ingår i en av de tre lojalitetsprogrammens nivåer.

   ![](assets/custom_profile_17.png)

1. Klicka på **[!UICONTROL Confirm]** och klicka sedan på **[!UICONTROL Next]** när filtreringen är klar.
1. Definiera och anpassa meddelandeinnehåll, avsändarens namn och ämne. Mer information om hur du skapar e-postmeddelanden finns på den här [sidan](../../designing/using/designing-content-in-adobe-campaign.md).

   Klicka sedan på **[!UICONTROL Create]**.

1. När det är klart kan du förhandsgranska och skicka meddelandet. Mer information om hur du förbereder och skickar meddelanden finns på den här [sidan](../../sending/using/preparing-the-send.md).

När e-postmeddelandet har skickats korrekt till de valda mottagarna kan du börja filtrera dina data och spåra hur bra leveransen är med rapporter.

## Steg 4: Skapa en dynamisk rapport för att filtrera mottagare med den anpassade profildimensionen {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

När leveransen är klar kan du dela upp rapporter med hjälp av din anpassade profildimension från tabellen **[!UICONTROL Profile]**.

1. På fliken **[!UICONTROL Reports]** väljer du en färdig rapport eller klickar på knappen **[!UICONTROL Create]** för att starta en från början.

   ![](assets/custom_profile_18.png)

1. I kategorin **[!UICONTROL Dimensions]** klickar du på **[!UICONTROL Profile]** och drar och släpper sedan den anpassade profildimensionen **Lojalitetsprogram** i frihandstabellen.

   ![](assets/custom_profile_19.png)

1. Dra och släpp måtten **[!UICONTROL Processed/Sent]** och **[!UICONTROL Open]** för att börja filtrera data.

   ![](assets/custom_profile_20.png)

1. Dra och släpp en visualisering på arbetsytan om det behövs.

   ![](assets/custom_profile_21.png)

**Relaterat ämne:**

* [Använda anpassade profildata för att skapa insiktsfulla rapporter](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
