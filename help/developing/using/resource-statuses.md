---
solution: Campaign Standard
product: campaign
title: Resursstatus
description: Identifiera de olika resursstatusarna utifrån deras publiceringstillstånd.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Resursstatus{#resource-statuses}

Beroende på publicerings- eller aktiveringsstatus kan resurserna ha olika status.

Det finns två kolumner som är dedikerade för att visa dessa statusvärden på **[!UICONTROL Custom resources]**-skärmen.

![](assets/schema_colonne_1.png)

**Publiceringsstatus**

* **Utkast**: resursen har precis skapats eller omformulerats. Om du vill skapa databastabellerna och motsvarande API:er måste resursen publiceras på nytt. Om en resurs skrivs om blir den automatiskt inaktiv efter publiceringssteget.
* **Väntande omutkast**: resursen har omarbetats. Utkastet görs om under nästa publicering. Omformulering är oåterkalleligt. Flera varningsmeddelanden visas för att informera användaren, både när de skriver om och förbereder publicering.

   Mer information om omritning finns i [Ta bort en resurs](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >Alternativet **[!UICONTROL Cancel re-draft]** är tillgängligt när resursen som du vill göra om utkast fortfarande innehåller länkar via andra resurser med statusen Publicerad. Med det här alternativet kan du återställa processen för att göra om utkast. De anpassade resurserna återgår sedan till sin ursprungliga status.

* **Publicerat**: resursen har publicerats. Om resursen ändras efter det senaste ändringsdatumet visas ett meddelande som bjuder in dig att publicera resursen igen för att ta hänsyn till de senaste ändringarna.

Fältet **[!UICONTROL Do not publish latest modifications]** förhindrar att ändringar beaktas vid framtida publikationer.

Det här fältet kan konfigureras i den anpassade resursdefinitionen.
