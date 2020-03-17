---
title: Skapa direktreklam
description: Följ de här stegen för att skapa direktreklam i Adobe Campaign.
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Skapa direktreklam{#creating-the-direct-mail}

Att skapa direktreklam påminner mycket om att skapa ett vanligt e-postmeddelande. I följande steg beskrivs konfigurationen som är specifik för den här kanalen. Mer information om andra alternativ finns i [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md) .

1. Skapa en ny direktutskick. Du kan skapa en från Adobe Campaigns [hemsida](../../start/using/interface-description.md#home-page), i en [kampanj](../../start/using/marketing-activities.md#creating-a-marketing-activity) eller i en [marknadsföringsaktivitetslista](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >Du kan också lägga till en direktmeddelandeaktivitet i ett arbetsflöde. Mer information finns i handboken [Arbetsflöden](../../automating/using/direct-mail-delivery.md) .

   ![](assets/direct_mail_1.png)

1. Välj en färdig **[!UICONTROL Direct mail]** mall eller någon av dina egna mallar. Mer information om mallar finns i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md) .

   ![](assets/direct_mail_2.png)

1. Ange de allmänna egenskaperna för leveransen.

   ![](assets/direct_mail_3.png)

1. Definiera målgruppen som du vill inkludera i extraheringsfilen samt test- och svällningsprofilerna. Se [Definiera målgrupp](../../channels/using/defining-the-direct-mail-audience.md)för direktreklam.

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >Målgruppsdefinitionen liknar mycket den som används för att definiera en vanlig e-postpublik. Se [Skapa målgrupper](../../audiences/using/creating-audiences.md).

1. Redigera innehållet i filen: kolumner som ska inkluderas för varje profil, filstruktur, sidhuvud och sidfot. Se [Definiera innehåll](../../channels/using/defining-the-direct-mail-content.md)för direktreklam.

   ![](assets/direct_mail_5.png)

1. Klicka på **[!UICONTROL Schedule]** avsnittet på kontrollpanelen för leverans för att definiera kontaktdatumet. För direktreklam är kontaktdatumet obligatoriskt. Mer information finns i [Schemalägga sändning](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Om du har lagt till testprofiler (se [Lägga till test- och svällningsprofiler](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)) kan du testa leveransen innan du förbereder den slutliga filen. Du kan skapa en exempelfil som endast innehåller de valda testprofilerna.

   Klicka på **[!UICONTROL Test]** för att generera exempelfilen. Klicka på **[!UICONTROL Summary]**, i det övre vänstra hörnet och välj sedan **[!UICONTROL Proofs]**. Markera korrekturet till vänster på skärmen och klicka på det **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >Rollen krävs för att Adobe Campaign ska kunna exportera filen och göra den tillgänglig för hämtning. **[!UICONTROL Export]** Kontakta administratören.

   ![](assets/direct_mail_19.png)

1. När du har definierat leveransinnehåll, målgrupp och kontaktdatum klickar du på **[!UICONTROL Prepare]** knappen på kontrollpanelen.

   ![](assets/direct_mail_16.png)

   Typologiregler används. Alla ospecificerade postadresser är till exempel uteslutna från målet. Därför måste du se till att du har markerat **[!UICONTROL Address specified]** rutan i profilinformationen (se [Rekommendationer](../../channels/using/about-direct-mail.md#recommendations)). Om du har definierat en **[!UICONTROL Maximum volume of message]** post i egenskaperna för direktreklam eller på mallnivå, används den också här.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Ni kan ange globala regler för flerkanalströtthet som automatiskt utesluter överdimensionerade profiler från kampanjer. Se [Trötthetsregler](../../administration/using/fatigue-rules.md).

1. Klicka på **[!UICONTROL Explore file]** för att förhandsgranska de första 100 raderna i filen.

   ![](assets/direct_mail_18.png)

   Den fullständiga filen kan hämtas lokalt till vänster på skärmen. När du laddar ned filen skapas en loggpost på **[!UICONTROL Export audits]** menyn. Mer information om exportgranskningar finns i avsnittet [Granska export](../../administration/using/auditing-export-logs.md) .

   >[!NOTE]
   >
   >Rollen krävs för att Adobe Campaign ska kunna exportera filen och göra den tillgänglig för hämtning. **[!UICONTROL Export]** Kontakta administratören.

   Om du behöver ändra leveransinnehållet behöver du bara klicka på **[!UICONTROL Regenerate file]** knappen för att ta hänsyn till ändringen. Du behöver inte gå igenom beredningen igen.

   ![](assets/direct_mail_21.png)

1. Bekräfta att filen är slutgiltig genom att klicka på den **[!UICONTROL Confirm]** på kontrollpanelen.

   ![](assets/direct_mail_20.png)

Du kan nu skicka extraheringsfilen till din direktutskick. Det finns flera alternativ:

* Skicka det via vanlig e-post, med filen bifogad
* Skicka via Campaign: utföra din direktreklam i ett [kampanjarbetsflöde](../../automating/using/direct-mail-delivery.md) och lägga till en **[!UICONTROL Transfer file]** som kan skicka filen via till exempel FTP. Se [Överför fil](../../automating/using/transfer-file.md).

Leverantören hämtar listan över felaktiga adresser och skickar informationen till Adobe Campaign, som automatiskt svartlistar de felaktiga adresserna. Se [Återgå till avsändaren](../../channels/using/return-to-sender.md).
