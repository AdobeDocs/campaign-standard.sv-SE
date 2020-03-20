---
title: Skicka korrektur
description: Lär dig hur du skickar korrektur.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# Skicka korrektur {#sending-proofs}

## Om korrektur {#about-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan du skickar det till huvudmålet. Mottagarna av beviset ansvarar för att godkänna meddelandet (dess innehåll och form).

Det finns två typer av korrekturmottagare:

* **Med testprofiler** kan du rikta in dig på fler mottagare som inte matchar de definierade målinriktningsvillkoren.

   De kan läggas in i målgruppen för ett meddelande för att upptäcka om mottagardatabasen används på ett bedrägligt sätt eller för att säkerställa att e-postmeddelandena kommer fram i inkorgen. Mer information finns i [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

   >[!NOTE]
   >
   >Om du vill skicka ett bevis måste testprofilerna inkluderas i meddelandets målgrupp.

* **Med ersättningsprofiler** kan du placera dig själv i positionen för en av målprofilerna och få en exakt representation av meddelandet som profilen får. Mer information finns i [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md).

   >[!NOTE]
   >
   >Den här funktionen är endast tillgänglig för e-postkanalen.

## Skicka ett bevis {#sending-a-proof}

Så här skickar du korrektur:

1. Kontrollera att korrekturmottagarna har konfigurerats:
   * **Testprofiler** måste finnas med i meddelandets målgrupp.
   * **Ersättningsprofiler** måste läggas till när meddelandets förberedelse har slutförts (se [detta avsnitt](../../sending/using/testing-messages-using-target.md)).

1. Klicka på **[!UICONTROL Send a test]** knappen.

   ![](assets/bat_select.png)

1. Välj den typ av korrektur som du vill använda:

   * **[!UICONTROL Email rendering]**: Välj det här alternativet om du vill testa hur meddelandet tas emot enligt de inkorgar som är avsedda för. Mer information finns i [E-poståtergivning](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: Välj det här alternativet om du vill testa meddelandet innan det skickas till huvudmålet. Korrekturmottagarna ansvarar för att godkänna leveransen genom att kontrollera både innehållet och formatet.
   * **[!UICONTROL Proof + Email rendering]**: det här alternativet kombinerar de två föregående alternativen.
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >E-poståtergivning är endast tillgängligt med testprofiler. Om inga testprofiler har lagts till i meddelandet kan du bara välja det **[!UICONTROL Proof]** alternativet.

1. Bekräfta ditt val.

   Korrektur skickas till mottagarna som har konfigurerats.

   ![](assets/bat_select2.png)

1. Du kan visa dina korrektur i den **[!UICONTROL Proofs]** nedrullningsbara listan.

   ![](assets/bat_view.png)

1. Välj ett korrektur för att komma åt sammanfattningen. Om du har valt alternativet **E-poståtergivning** som korrekturtyp för ett e-postmeddelande visas **[!UICONTROL Access email rendering]** ikonen till höger om korrekturetiketten. Se [E-poståtergivning](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Beroende på kommentarerna från de personer som tar emot beviset kan du bli ombedd att ändra innehållet i leveransen. När ändringarna är klara måste du starta om e-postförberedelserna och sedan skicka ett nytt korrektur. Du hittar alla nya korrektur med hjälp av **[!UICONTROL Show proofs]** kommandoknappen.

Du måste skicka så många korrektur som behövs tills du är klar med innehållet. När detta är klart kan du skicka leveransen till huvudmålet och stänga godkännandecykeln.

## Konfigurera korrekturens ämnesrad {#configuring-proofs-subject-line}

När ett korrektur skickas konfigureras ämnesraden som standard med prefixet **&quot;Korrektur&quot;** samt en räknare som anger korrekturens nummer.

![](assets/proof-prefix.png)

Följ de här stegen om du vill ändra ämnesraden:

1. Klicka på **[!UICONTROL Open properties]** knappen på meddelandekontrollpanelen.
1. I **[!UICONTROL Advanced parameters]** avsnittet definierar du det prefix som du vill använda som standard på ämnesraden.

Aktivera **[!UICONTROL Hide proof prefix counter]** alternativet om du vill dölja korrekturets nummer i ämnesraden.

>[!NOTE]
>
>Om du vill dölja hela korrekturprefixet lämnar du **[!UICONTROL Subject line prefix]** fältet tomt.

![](assets/proof-prefix-configuration.png)

1. Klicka på **[!UICONTROL Confirm]**. Inställningarna används som standard för alla korrektur som skickas för det markerade meddelandet.

**Relaterat ämne:**

* [Skicka ett test, förbereda och skicka en e-postvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
* [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md).
* [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).
* [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
* [Konfigurera e-postkanal](../../administration/using/configuring-email-channel.md)
