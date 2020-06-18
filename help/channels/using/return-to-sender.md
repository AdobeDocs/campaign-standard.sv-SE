---
title: Återgå till avsändaren
description: Lär dig hur du får ett meddelande om en felaktig adress och utelämnar den från framtida kommunikation.
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Återgå till avsändaren{#return-to-sender}

Platta filutbyten med Direct Mail-leverantörer med information om att skicka tillbaka till avsändaren stöds. På så sätt kan motsvarande postadresser uteslutas från framtida kommunikation. På så sätt kan ni också få meddelande om en felaktig adress och kontakta kunden via andra kanaler eller uppmuntra honom att uppdatera sin postadress.

En kontakt har till exempel flyttats till en ny plats och har inte försett dig med sin nya postadress. Providern hämtar listan över felaktiga adresser och skickar den här informationen till Adobe Campaign som automatiskt lägger till felaktiga adresser i blockeringslistan.

För att den här funktionen ska fungera innehåller standardmallen för leverans av direktreklam i innehållet leveranslogg-ID:t. Adobe Campaign kan alltså synkronisera profil- och leveransdata med den information som returneras av leverantören.

![](assets/direct_mail_return_sender_1.png)

En importmall finns under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplicera den här mallen för att skapa en egen mall. Mer information om hur du använder importmallar finns i [Använda importmallar](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

När importen är klar utför Adobe Campaign automatiskt följande åtgärder:

* Felaktiga adresser läggs till i blocklistan på profilnivå
* Huvudindikatorerna för leverans uppdateras
* Leveransloggarna uppdateras

