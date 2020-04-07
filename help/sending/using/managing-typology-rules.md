---
title: Hantera typologiregler
description: Lär dig hur du använder typologiregler.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c5b1882e143924f94530c166b6af61a1bce30d72

---


# Hantera typologiregler {#managing-typology-rules}

## Om typologiregler {#about-typology-rules}

Typologiregler är affärsregler som gör att du kan kontrollera och filtrera meddelandet innan du skickar det. Tillgängliga typer av typologiregler är:

* **Filtreringsregler** : Med den här typen av regel kan du utesluta en del av meddelandemålet enligt villkor som definierats i en fråga, till exempel profiler i karantän eller profiler som redan har skickats ett visst antal e-postmeddelanden. For more on this, refer to [this section](../../sending/using/filtering-rules.md).

* **Trötthetsregler** : Med den här typen av regler kan du definiera ett maximalt antal meddelanden per profil för att undvika att överdriva dem. For more on this, refer to [this section](../../sending/using/fatigue-rules.md).

* **Kontrollregler** : Den här typen av regler gör att användaren kan kontrollera giltigheten och kvaliteten på meddelanden innan de skickas, t.ex. teckenvisning, SMS-meddelandestorlek, adressformat osv. For more on this, refer to [this section](../../sending/using/control-rules.md).

Typologiregler finns under **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]** .

Som standard finns flera färdiga **filtrerings** - och **kontrolltypologiregler** tillgängliga. De beskrivs i avsnitten [Filtreringsregler](../../sending/using/fatigue-rules.md) och [Kontrollregler](../../sending/using/control-rules.md) .

Beroende på dina behov kan du ändra befintliga typologiregler eller skapa nya, med undantag för **[!UICONTROL Control]** regler som är skrivskyddade och inte kan ändras.

## Skapa en typologiregel {#creating-a-typology-rule}

De viktigaste stegen för att skapa en typologiregel är följande:

1. Gå till **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]** och klicka sedan på **[!UICONTROL Create]**.

![](assets/typology_create-rule.png)

1. Ange typologin **[!UICONTROL Label]** och ange **[!UICONTROL Channel]** till vilken regel ska gälla.

![](assets/typology-rule-label.png)

1. Ange typologiregeln **[!UICONTROL Type]** och konfigurera den efter dina behov. Observera att typologiregelkonfigurationen varierar beroende på vilken typ de har. Mer information finns i avsnitten **[Filtreringsregler](../../sending/using/filtering-rules.md)**och**[ Trötthetsregler](../../sending/using/fatigue-rules.md)** .

1. Markera de typologier som du vill inkludera den nya regeln i. Det gör du genom att markera **[!UICONTROL Typologies]** fliken och sedan klicka på **[!UICONTROL Create element]** knappen.

![](assets/typology-typologies-tab.png)

1. Välj önskad typologi och klicka sedan på **[!UICONTROL Confirm]**.

![](assets/typology-link.png)

1. När du har valt alla typologier klickar du **[!UICONTROL Create]** för att bekräfta att du har skapat typologiregeln.

## Körningsordning för typologiregler {#typology-rules-execution-order}

Typologiregler körs i en ordning som anges under faserna för målinriktning, analys och meddelandeanpassning.

I standarddriftsläget används reglerna i följande sekvens:

1. Kontrollregler, om de tillämpas i början av målinriktningen.
1. Filtreringsregler:

   * Interna ansökningsregler för adresskvalifikation: definierad adress/overifierad adress/svartlistad adress/adresskvalitet i karantän.
   * Filtreringsregler som definieras av användaren.

1. Kontrollregler, om de tillämpas när målinriktningen är slut.
1. Styr regler, om de tillämpas i början av personaliseringen.
1. Styr reglerna, om de tillämpas när personaliseringen är klar.

Du kan dock anpassa körningsordningen för samma typ av regler i varje typologi. Om flera regler körs under samma meddelandebearbetningsfas kan du välja i vilken ordning de ska tillämpas.

En filtreringsregel vars körningsordning är placerad på nummer 20 kommer till exempel att köras före en filtreringsregel vars körningsordning är placerad på nummer 30.

I fallet **[!UICONTROL Properties]** med en typologiregel kan du ange dess körningsordning. När flera regler måste tillämpas, avgör körningsordningen för varje regel vilka som ska behandlas först. Mer information finns i avsnittet om [körningsordning](#typology-rules-execution-order) för typologiregler.

![](assets/typology_rule-active.png)

En typologiregel kan inaktiveras genom sin **[!UICONTROL Properties]** om du inte vill att regeln ska tillämpas när de meddelanden som berörs av regeln analyseras.

![](assets/typology_rule-order.png)