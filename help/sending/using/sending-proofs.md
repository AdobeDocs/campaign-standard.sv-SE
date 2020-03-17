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
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# Skicka korrektur {#sending-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan du skickar det till huvudmålet.

Mottagarna av beviset ansvarar för att godkänna meddelandet (dess innehåll och form). De definieras i **Testprofilerna**. Mer information finns i [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

Om du vill skicka ett bevis måste testprofilerna inkluderas i meddelandets målgrupp.

I ett meddelande:

1. Klicka på **[!UICONTROL Send a test]** knappen.

   ![](assets/bat_select.png)

1. Välj den typ av korrektur som du vill använda:

   * **[!UICONTROL Email rendering]**: Välj det här alternativet om du vill testa hur meddelandet tas emot enligt de inkorgar som är avsedda för. Mer information finns i [E-poståtergivning](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: Välj det här alternativet om du vill testa meddelandet innan det skickas till huvudmålet. Korrekturmottagarna ansvarar för att godkänna leveransen genom att kontrollera både innehållet och formatet.
   * **[!UICONTROL Proof + Email rendering]**: det här alternativet kombinerar de två föregående alternativen.
   ![](assets/bat_select1.png)

1. Bekräfta ditt val.

   Korrektur skickas till testprofilerna.

   ![](assets/bat_select2.png)

1. Du kan visa dina korrektur i den **[!UICONTROL Proofs]** nedrullningsbara listan.

   ![](assets/bat_view.png)

1. Välj ett korrektur för att komma åt sammanfattningen. Om du har valt alternativet **E-poståtergivning** som korrekturtyp för ett e-postmeddelande visas **[!UICONTROL Access email rendering]** ikonen till höger om korrekturetiketten. Se [E-poståtergivning](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Beroende på kommentarerna från de personer som tar emot beviset kan du bli ombedd att ändra innehållet i leveransen. När ändringarna är klara måste du starta om e-postförberedelserna och sedan skicka ett nytt korrektur. Du hittar alla nya korrektur med hjälp av **[!UICONTROL Show proofs]** kommandoknappen.

Du måste skicka så många korrektur som behövs tills du är klar med innehållet. När detta är klart kan du skicka leveransen till huvudmålet och stänga godkännandecykeln.

**Relaterat ämne:**

[Skicka ett test, förbereda och skicka en e-postvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
