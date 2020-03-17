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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Resursstatus{#resource-statuses}

Resurserna kan ha olika status beroende på publicerings- eller aktiveringsstatus.

Det finns två kolumner som är dedikerade för att visa dessa statusvärden på **[!UICONTROL Custom resources]** skärmen.

![](assets/schema_colonne_1.png)

**Publiceringsstatus**

* **Utkast**: resursen har precis skapats eller omformulerats. Om du vill skapa databastabellerna och motsvarande API:er måste resursen publiceras på nytt. Om en resurs håller på att skrivas in på nytt kommer den automatiskt att göras inaktiv efter publiceringssteget.
* **Väntande omutkast**: resursen har omarbetats. Utkastet görs om under nästa publicering. Omformulering är oåterkalleligt. Flera varningsmeddelanden varnar användaren om detta både när de skriver om och när de förbereder publicering.

   Mer information om omritning finns i [Ta bort en resurs](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >Alternativet är **[!UICONTROL Cancel re-draft]** tillgängligt när den resurs som du vill göra om utkast fortfarande innehåller länkar via andra resurser med statusen&quot;Publicerad&quot;. Med det här alternativet kan du återställa processen för att göra om utkast. De anpassade resurserna återgår sedan till sin ursprungliga status.

* **Publicerat**: resursen har publicerats. Om resursen ändras efter det senaste ändringsdatumet visas ett meddelande där användaren ombeds publicera för att ta hänsyn till de senaste ändringarna.

Fältet **[!UICONTROL Do not publish latest modifications]** förhindrar att ändringar beaktas vid framtida publikationer.

Det här fältet kan konfigureras i den anpassade resursdefinitionen.
