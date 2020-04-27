---
title: Resursstatus
description: Identifiera de olika resursstatusarna utifrån deras publiceringstillstånd.
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Resursstatus{#resource-statuses}

Beroende på publicerings- eller aktiveringsstatus kan resurserna ha olika status.

Det finns två kolumner som är dedikerade för att visa dessa statusvärden på **[!UICONTROL Custom resources]** skärmen.

![](assets/schema_colonne_1.png)

**Publiceringsstatus**

* **Utkast**: resursen har precis skapats eller omformulerats. Om du vill skapa databastabellerna och motsvarande API:er måste resursen publiceras på nytt. Om en resurs skrivs om blir den automatiskt inaktiv efter publiceringssteget.
* **Väntande omutkast**: resursen har omarbetats. Utkastet görs om under nästa publicering. Omformulering är oåterkalleligt. Flera varningsmeddelanden visas för att informera användaren, både när de skriver om och förbereder publicering.

   Mer information om omritning finns i [Ta bort en resurs](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >Alternativet är **[!UICONTROL Cancel re-draft]** tillgängligt när den resurs som du vill göra om utkast fortfarande innehåller länkar via andra resurser med statusen&quot;Publicerad&quot;. Med det här alternativet kan du återställa processen för att göra om utkast. De anpassade resurserna återgår sedan till sin ursprungliga status.

* **Publicerat**: resursen har publicerats. Om resursen ändras efter det senaste ändringsdatumet visas ett meddelande som uppmanar dig att publicera om resursen för att ta hänsyn till de senaste ändringarna.

Fältet **[!UICONTROL Do not publish latest modifications]** förhindrar att ändringar beaktas vid framtida publikationer.

Det här fältet kan konfigureras i den anpassade resursdefinitionen.
