---
solution: Campaign Standard
product: campaign
title: Använda spam-samlare
description: Lär dig hur du använder svällning i meddelanden.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Startadress
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# Använda spam-samlare {#using-traps}

När du använder svällningar skickas meddelandet till [testprofilen](../../audiences/using/managing-test-profiles.md) precis som det skickas till huvudmålet, för att identifiera om klientfilen används bedrägligt.

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
>Till skillnad från testprofiler som används för [korrektur](../../sending/using/sending-proofs.md) eller [e-poståtergivning](../../sending/using/email-rendering.md) skickas meddelandet samtidigt till huvudmålet och till testprofilerna som används som svällningar.

När du definierar målgruppen för ett meddelande:

1. Välj en testprofil på fliken **[!UICONTROL Test profiles]**. Kontrollera att den har **[!UICONTROL Trap]** som avsett användningsområde.

   ![](assets/trap_select.png)

1. När meddelandeinnehållet är klart klickar du på **[!UICONTROL Prepare]**-knappen. Se [Förbereda sändningen](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Se till att du har valt ett huvudmål. Annars går det inte att skicka meddelandet.

1. Klicka på knappen **[!UICONTROL Confirm]**. Se [Bekräfta sändningen](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Meddelandet skickas till huvudmålet och till testprofilen.

Du kan använda svällning när du skickar transaktionsmeddelanden. I det här fallet får testprofilen ett meddelande per händelsekonfiguration. Mer information om transaktionsmeddelanden finns i det här [avsnittet](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>När du använder en testprofil som en svällning väljs motsvarande ytterligare data slumpmässigt ut från en verklig målprofil och tilldelas till svällningstestprofilen för alla inkapslade fält i ett meddelande. Mer information om anrikning finns i [det här exemplet](../../automating/using/enriching-profile-data-file.md).
