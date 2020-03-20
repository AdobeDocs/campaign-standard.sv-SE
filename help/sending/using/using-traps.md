---
title: Använda svällningar
description: Lär dig hur du använder svällning i meddelanden.
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
source-git-commit: a7c2d444b7d971124b676fa2392b51aab40e5629

---


# Använda svällningar {#using-traps}

När du använder svällningar skickas meddelandet till [testprofilen](../../audiences/using/managing-test-profiles.md) på samma sätt som det skickas till huvudmålet för att identifiera om klientfilen används bedrägligt.

Svällningar är ursprungligen avsedda för direktreklam. De gör att du kan:

* Kontrollera att din direktmeddelandeleverantör verkligen skickar kommunikationen.
* Ta emot e-postmeddelandet samtidigt och på samma villkor som dina kunder.
* Behåll en exakt kopia av det skickade meddelandet.
* Kontrollera att din klientlista inte används felaktigt av din direktmeddelandeleverantör. Om någon annan kommunikation skickas till testprofilens adress kan din klientfil ha använts utan att du visste om det. Därför bör testprofilens adress endast användas i detta syfte.

Mer information om hur du lägger till svällningar till en målgrupp för ett direktutskick finns i [Lägga till test- och svällningsprofiler](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

För de andra kommunikationskanalerna kan du lägga till svällningstestprofiler i huvudmålet för att:

* Kontrollera att meddelandet har skickats.
* Hämta och spara en exakt kopia av meddelandet.
* Spåra när det skickades och togs emot.

Om du vill använda en testprofil som en svällning måste den ingå i meddelandets målgrupp.

>[!NOTE]
>
>Till skillnad från testprofiler som används för [korrektur](../../sending/using/sending-proofs.md) eller [e-poståtergivning](../../sending/using/email-rendering.md)skickas meddelandet samtidigt till huvudmålet och till testprofilerna som används som svällning.

När du definierar målgruppen för ett meddelande:

1. Välj en testprofil på **[!UICONTROL Test profiles]** fliken. Se till att den har **[!UICONTROL Trap]** avsedd användning.

   ![](assets/trap_select.png)

1. Klicka på **[!UICONTROL Prepare]** knappen när meddelandeinnehållet är klart. Se [Förbereda sändningen](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Se till att du har valt ett huvudmål. Annars går det inte att skicka meddelandet.

1. Klicka på **[!UICONTROL Confirm]** knappen. Se [Bekräfta sändningen](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Meddelandet skickas till huvudmålet och till testprofilen.

Du kan använda svällning när du skickar transaktionsmeddelanden. I det här fallet får testprofilen ett meddelande per händelsekonfiguration. Mer information om transaktionsmeddelanden finns i det här [avsnittet](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>När du använder en testprofil som en svällning väljs motsvarande ytterligare data slumpmässigt ut från en verklig målprofil och tilldelas till svällningstestprofilen för alla inkapslade fält i ett meddelande. Mer information om berikning finns i [det här exemplet](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
