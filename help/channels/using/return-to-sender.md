---
solution: Campaign Standard
product: campaign
title: Skicka tillbaka till avsändaren
description: Lär dig hur du får ett meddelande om en felaktig adress och utelämnar den från framtida kommunikation.
audience: channels
content-type: reference
topic-tags: direct-mail
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Skicka tillbaka till avsändaren{#return-to-sender}

Platta filutbyten med Direct Mail-leverantörer med information om att skicka tillbaka till avsändaren stöds. På så sätt kan motsvarande postadresser uteslutas från framtida kommunikation. På så sätt kan ni också få meddelande om en felaktig adress och kontakta kunden via andra kanaler eller uppmuntra honom att uppdatera sin postadress.

En kontakt har till exempel flyttats till en ny plats och har inte försett dig med sin nya postadress. Leverantören hämtar listan över felaktiga adresser och skickar den här informationen till Adobe Campaign som automatiskt blocklist de felaktiga adresserna.

För att den här funktionen ska fungera innehåller standardmallen för leverans av direktreklam i innehållet leveranslogg-ID:t. På så sätt kan Adobe Campaign synkronisera profil- och leveransdata med den information som returneras av leverantören.

![](assets/direct_mail_return_sender_1.png)

En importmall är tillgänglig under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplicera den här mallen för att skapa en egen mall. Mer information om hur du använder importmallar finns i [Använda importmallar](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

När importen är klar utför Adobe Campaign automatiskt följande åtgärder:

* Felaktiga adresser läggs till i blockeringslista på profilnivå
* Huvudindikatorerna för leverans uppdateras
* Leveransloggarna uppdateras
