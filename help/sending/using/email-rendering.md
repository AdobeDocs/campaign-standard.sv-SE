---
title: E-poståtergivning
description: Upptäck e-poståtergivningsfunktionen.
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b43e6be265ff2d8ce357ef44672a755028e2e5af
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 0%

---


# E-poståtergivning{#email-rendering}

Innan du klickar på **[!UICONTROL Send]** knappen måste du se till att meddelandet visas på ett optimalt sätt på en mängd olika webbklienter, webbmejl och enheter.

Adobe Campaign hämtar återgivningen och gör den tillgänglig i en dedikerad rapport. På så sätt kan du förhandsgranska det skickade meddelandet i olika sammanhang där det kan tas emot.

De mobil-, meddelande- och webbpostklienter som är tillgängliga för **e-poståtergivning** i Adobe Campaign finns listade på Litmus- [webbplatsen](https://litmus.com/email-testing) (klicka på **Visa alla e-postklienter**).

## Kontrollera rapporten för e-poståtergivning {#checking-the-email-rendering-report}

När du har skapat e-postleveransen och definierat innehållet samt målpopulationen följer du stegen nedan.

1. Klicka på **Målgrupp** för att öppna **[!UICONTROL Test profiles]** fliken.

   ![](assets/email_rendering_05.png)

1. Använd frågeredigeraren för att definiera de testprofiler som du vill använda, inklusive testprofilerna som ska användas för **e-poståtergivning** . Se [Testprofiler](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Kontrollera och bekräfta frågan och spara sedan ändringarna.
1. Klicka på **[!UICONTROL Test]** knappen i åtgärdsfältet.

   ![](assets/email_rendering_07.png)

1. Markera **[!UICONTROL Email rendering]** alternativet och klicka sedan på **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >Med det här **[!UICONTROL Proof + Email rendering]** alternativet kan du skicka ett korrektur och använda e-poståtergivningsfunktionen samtidigt. Du kan få ditt meddelande godkänt av korrekturmottagarna och samtidigt testa hur meddelandet kommer att tas emot beroende på vilka inkorgar som används. I det här fallet måste du även välja Korrekturtestprofiler. Se [Testprofiler](../../audiences/using/managing-test-profiles.md).

   Testleveransen skickas.

1. Miniatyrbilderna för återgivning är tillgängliga några minuter efter att du har skickat meddelandena. Du öppnar dem genom att välja **[!UICONTROL Proofs]** i **[!UICONTROL Summary]** listrutan.

   ![](assets/email_rendering_03.png)

1. Klicka på **[!UICONTROL Proofs]** ikonen i **[!UICONTROL Access email rendering]** listan.

   ![](assets/email_rendering_04.png)

Den dedikerade återgivningsrapporten för e-post visas. Se [Rapportbeskrivning](#email-rendering-report-description)för återgivning via e-post.

**Relaterade ämnen**:

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Skicka korrektur](../../sending/using/sending-proofs.md)
* [Frågeredigerare](../../automating/using/editing-queries.md#about-query-editor)

## Beskrivning av rapport för e-poståtergivning {#email-rendering-report-description}

I den här rapporten visas e-poståtergivningarna så som de visas för mottagaren. E-poståtergivningen kan variera beroende på hur mottagaren öppnar e-postleveransen: i en webbläsare, på en mobil enhet eller via ett e-postprogram.

>[!NOTE]
>
>Antalet tillgängliga återgivningar visas i licensavtalet. Varje leverans med **e-poståtergivning** aktiverat minskar antalet tillgängliga återgivningar (så kallade tokens) med ett.

Rapportsammanfattningen visar antalet mottagna, oönskade (skräppost), ej mottagna eller väntande mottagningar.

![](assets/inbox_rendering_report.png)

Rapporten är uppdelad i tre delar: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]** och **[!UICONTROL Webmails]**. Bläddra nedåt i rapporten för att visa alla återgivningar grupperade i dessa tre kategorier.

![](assets/inbox_rendering_report_3.png)

Klicka på motsvarande kort om du vill ha information om respektive rapport. Återgivningen visas för den valda mottagningsmetoden.

![](assets/inbox_rendering_report_2.png)

På fliken **[!UICONTROL Technical data]** kan du få mer information, t.ex. datum för när du tar emot och hämtar meddelanden samt fullständiga rubriker för e-postmeddelanden.
