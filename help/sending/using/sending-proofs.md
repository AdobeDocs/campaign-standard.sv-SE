---
solution: Campaign Standard
product: campaign
title: Skicka korrektur
description: Lär dig hur du skickar korrektur.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
translation-type: tm+mt
source-git-commit: e20485978deba54f45010a41921b948f049222f2
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 100%

---


# Skicka korrektur {#sending-proofs}

## Om korrektur {#about-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan det skickas iväg till huvudmålet. Mottagarna av korrekturet ansvarar för att godkänna meddelandet (innehållet och formen).

Det finns två typer av korrekturmottagare:

* **Testprofiler** ger dig möjligheten att rikta in dig på fler mottagare som inte matchar de definierade målkriterierna.

   De kan läggas in i målgruppen för ett meddelande för att upptäcka om mottagardatabasen används på ett bedrägligt sätt eller för att säkerställa att e-postmeddelanden kommer fram till inkorgen. Mer information finns i [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

   >[!NOTE]
   >
   >Om du vill skicka korrektur måste testprofilerna inkluderas i meddelandets målgrupp.

* **Med ersättningsprofiler** kan du placera dig själv som en av målprofilerna och få en exakt representation av meddelandet som profilen får. Mer information finns i [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md).

   >[!NOTE]
   >
   >Den här funktionen är endast tillgänglig för e-postkanalen.

## Utskick av korrektur {#sending-a-proof}

Så här skickar du korrektur:

1. Kontrollera att mottagarna av korrektur har konfigurerats:
   * **Testprofiler** måste finnas med i meddelandets målgrupp.
   * **Ersättningsprofiler** måste läggas till när förberedelsen av meddelandet har slutförts (se [detta avsnitt](../../sending/using/testing-messages-using-target.md)).

1. Klicka på knappen **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Välj den typ av korrektur som du vill använda:

   * **[!UICONTROL Email rendering]**: Välj det här alternativet om du vill testa hur meddelandet tas emot i de inkorgar som det är avsett för. Mer information finns i [E-poståtergivning](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: Välj det här alternativet om du vill testa meddelandet innan det skickas iväg till huvudmålet. Mottagarna av korrekturet ansvarar för att godkänna leveransen genom att kontrollera både innehållet och formatet.
   * **[!UICONTROL Proof + Email rendering]**: det här alternativet kombinerar de två föregående alternativen.

   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >E-poståtergivning är endast tillgängligt för testprofiler. Om inga testprofiler har lagts till i meddelandet kan du bara välja det **[!UICONTROL Proof]** alternativet.

1. Bekräfta ditt val.

   Korrektur skickas till mottagarna som har konfigurerats.

   ![](assets/bat_select2.png)

1. Du kan visa dina korrektur i **[!UICONTROL Proofs]** rullgardinslistan.

   ![](assets/bat_view.png)

1. Välj ett korrektur för att komma åt sammanfattningen. Om du har valt alternativet **E-poståtergivning** som korrekturtyp för ett e-postmeddelande visas ikonen **[!UICONTROL Access email rendering]** till höger om korrekturetiketten. Se [E-poståtergivning](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Beroende på kommentarerna från de personer som tar emot korrekturen kan du bli ombedd att ändra innehållet i leveransen. När ändringarna är klara måste du starta om e-postförberedelserna och sedan skicka ett nytt korrektur. Du hittar alla nya korrektur med hjälp av knappen **[!UICONTROL Show proofs]**.

Du måste skicka så många korrektur som behövs tills du är klar med innehållet. När detta är klart kan du skicka leveransen till huvudmålet och stänga cykeln för godkännande.

## Konfigurera korrekturens ämnesrad {#configuring-proofs-subject-line}

När ett korrektur skickas konfigureras ämnesraden som standard med prefixet **&quot;Korrektur&quot;**, samt en räknare som anger korrekturets nummer.

![](assets/proof-prefix.png)

Följ de här stegen om du vill ändra ämnesraden:

1. Klicka på knappen **[!UICONTROL Open properties]** i kontrollpanelen för meddelandet.
1. I **[!UICONTROL Advanced parameters]**-avsnittet definierar du det prefix som du vill använda som standard på ämnesraden.

Aktivera **[!UICONTROL Hide proof prefix counter]**-alternativet om du vill dölja korrekturets nummer i ämnesraden.

>[!NOTE]
>
>Om du vill dölja hela korrekturprefixet lämnar du fältet **[!UICONTROL Subject line prefix]** tomt.

![](assets/proof-prefix-configuration.png)

1. Klicka på **[!UICONTROL Confirm]**. Inställningarna används som standard för all korrektur som skickas för det markerade meddelandet.

**Relaterat ämne:**

* [Skicka ett test, förbereda och skicka en e-post](../../sending/using/get-started-sending-messages.md#video)-video
* [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md)
* [Hantera testprofiler](../../audiences/using/managing-test-profiles.md)
* [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
* [Konfigurera e-postkanal](../../administration/using/configuring-email-channel.md)
