---
title: Hantera typologiregler
description: Lär dig hur du använder typologiregler.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: 5ef66b1b-1c81-42fb-a18c-fcf7f21e1ff7
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 96%

---

# Hantera typologiregler {#managing-typology-rules}

## Om typologiregler {#about-typology-rules}

Typologiregler är affärsregler som gör att du kan kontrollera och filtrera meddelandet innan du skickar det. Följande är tillgängliga typer av typologiregler:

* **Filtreringsregler** : Med den här typen av regel kan du utesluta en del av meddelandemålet enligt villkor som definierats i en fråga, till exempel profiler i karantän eller profiler som redan har skickats ett visst antal e-postmeddelanden. Mer information om detta finns i [det här avsnittet](../../sending/using/filtering-rules.md).

* **Utmattningsregler**: Med den här typen av regler kan du definiera ett maximalt antal meddelanden per profil för att undvika att skicka för många begäranden till dem. Mer information om detta finns i [det här avsnittet](../../sending/using/fatigue-rules.md).

* **Kontrollregler**: Med den här typen av regler kan användaren kontrollera giltigheten och kvaliteten på meddelanden innan de skickas, t.ex. teckenvisning, SMS-meddelandestorlek, adressformat, o.s.v. Mer information om detta finns i [det här avsnittet](../../sending/using/control-rules.md).

Typologiregler finns under **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]**.

Som standard finns flera färdiga **filtrerings**- och **kontrolltypologiregler** tillgängliga. De beskrivs i avsnitten [Filtreringsregler](../../sending/using/filtering-rules.md) och [Kontrollregler](../../sending/using/control-rules.md).

Beroende på dina behov kan du ändra befintliga typologiregler eller skapa nya, med undantag för **[!UICONTROL Control]**-regler som är skrivskyddade och inte kan ändras.

## Skapa en typologiregel {#creating-a-typology-rule}

Följande är de viktigaste stegen för att skapa en typologiregel:

1. Gå till **[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Typologies]**/**[!UICONTROL Typology rules]** och klicka sedan på **[!UICONTROL Create]**.

   ![](assets/typology_create-rule.png)

1. Ange typologin **[!UICONTROL Label]** och ange **[!UICONTROL Channel]** för vilka regeln ska gälla.

   ![](assets/typology-rule-label.png)

1. Ange typologiregeln **[!UICONTROL Type]** och konfigurera den efter dina behov. Observera att typologiregelkonfigurationen varierar beroende på vilken typ de har. Mer information finns i avsnitten **[Filtreringsregler](../../sending/using/filtering-rules.md)** och **[Utmattningsregler](../../sending/using/fatigue-rules.md)**.

1. Markera de typologier som du vill inkludera den nya regeln i. Det gör du genom att markera fliken **[!UICONTROL Typologies]** och sedan klicka på knappen **[!UICONTROL Create element]**.

   ![](assets/typology-typologies-tab.png)

1. Välj önskad typologi och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/typology-link.png)

1. När du har valt alla typologier klickar du på **[!UICONTROL Create]** för att bekräfta att du har skapat typologiregeln.

## Körningsordning för typologiregler {#typology-rules-execution-order}

Typologiregler körs i en ordning som anges under faserna för målinriktning, analys och meddelandeanpassning.

I standarddriftsläget används reglerna i följande sekvens:

1. Kontrollregler, om de tillämpas i början av målinriktningen.
1. Filtreringsregler:

   * Interna ansökningsregler för adresskvalifikation: definierad adress/ej verifierad adress/adress på blockeringslista/adress i karantän/adresskvalitet.
   * Filtreringsregler som definieras av användaren.

1. Kontrollregler, om de tillämpas när målinriktningen är slut.
1. Kontrollregler, om de tillämpas i början av anpassningen.
1. Kontrollregler, om de tillämpas när anpassningen är klar.

Du kan däremot anpassa körningsordningen för samma typ av regler i varje typologi. Om flera regler körs under samma fas för meddelandebearbetning kan du välja i vilken ordning de ska tillämpas.

En filtreringsregel vars körningsordning finns på nummer 20 körs t.ex. före en filtreringsregel vars körningsordning finns på nummer 30.

Du kan ange körningsordningen i **[!UICONTROL Properties]** för en typologiregel. När flera regler måste tillämpas, bestämmer körningsordningen för varje regel vilka som ska bearbetas först. Mer information finns i avsnittet om [Körningsordning för typologiregler](#typology-rules-execution-order).

![](assets/typology_rule-active.png)

En typologiregel kan inaktiveras genom sin **[!UICONTROL Properties]** om du inte vill att regeln ska tillämpas när de meddelanden som berörs av regeln analyseras.

![](assets/typology_rule-order.png)
