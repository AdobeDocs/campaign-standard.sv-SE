---
title: Om typologiregler
description: Upptäck hur typologiregler fungerar i Adobe Campaign.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Om typologiregler{#about-typology-rules}

En typologi är en uppsättning regler som körs under meddelandeanalysfasen och som gör att målet, innehållet och konfigurationen för följande element kan valideras: ämne, URL, bilder, länk för att avbryta prenumerationen, korrekturstorlek osv.

I Adobe Campaign innehåller varje meddelande en länk till en typologi. Den här länken definieras i de avancerade parametrarna för leveransmallens egenskaper (mer information finns i avsnittet [Förberedelser](../../administration/using/configuring-email-channel.md#preparation) ).

>[!NOTE]
>
>Varje meddelande kan bara tilldelas en enda typologi.

För varje typologi listas reglerna för den här typologin i avsnittet **[!UICONTROL Typology rules]** .

![](assets/typology_typo-rule-list.png)

## Hantera typologier {#managing-typologies}

Flera typologier finns som standard i programmet. Beroende på dina behov kan du skapa egna typologier eller ändra befintliga.

1. Öppna **[!UICONTROL List of typologies]** från **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .
1. Välj en typologi om du vill ändra dess innehåll och egenskaper eller skapa en ny.

   ![](assets/typology_list.png)

1. Definiera typen av typologi. Typologier kan vara antingen standard- eller filtreringstypologier.
1. Lägg till de typologiregler du behöver med hjälp av **[!UICONTROL Add an element]** knappen eller ta bort de du inte vill använda.

   Du kan ändra ordningen som reglerna tillämpas i för en viss typologi. Om du vill göra det flyttar du elementen så att de visas i rätt ordning på skärmen. Numren som motsvarar körningsordningen beräknas sedan om automatiskt. Regelprogramläget visas i avsnittet för körningsordning för [typologiregler](#typology-rules-execution-order) .

   Reglerna som visas på den här skärmen kan öppnas i skrivskyddat läge.

Din typologi är klar att användas. Du kan markera det i meddelandeegenskaperna eller i meddelandemallsegenskaperna.

>[!NOTE]
>
>I **[!UICONTROL IP affinity]** fältet kan du hantera tillhörigheterna enligt din konfiguration. Dessa definieras i instansens konfigurationsfil. Kontakta administratören om du vill använda tillhörigheterna.

## Typologiregler {#typology-rules}

Typologiregler är affärsregler som tillämpas under meddelandeförberedelsen. De används för att kontrollera om ett meddelande är giltigt och uppfyller dina kvalitetskriterier. De kontrollerar också om varje medlem i målgruppen är berättigad att ta emot meddelandet.

Typologiregler finns under **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]** .

Det finns två typer av regler:

* **Filtreringsregler** : kan du utesluta en del av meddelandemålet enligt villkor som definierats i en fråga, till exempel profiler i karantän eller profiler som redan har skickats ett visst antal e-postmeddelanden. Se [Filtreringsregler](../../administration/using/filtering-rules.md).
* **Trötthetsregler** : gör att du kan definiera ett maximalt antal meddelanden per profil för att undvika att de efterfrågas för mycket. Se [Trötthetsregler](../../administration/using/fatigue-rules.md).
* **Kontrollregler** : gör det möjligt för användaren att kontrollera giltigheten och kvaliteten på meddelandena innan de skickas, t.ex. teckenvisning, SMS-meddelandestorlek, adressformat osv. Se [Kontrollregler](../../administration/using/control-rules.md).

En typologiregel kan tillämpas på endast en kanal eller på alla kanaler.

![](assets/typology_channel.png)

I fallet **[!UICONTROL Properties]** med en typologiregel kan du ange dess körningsordning. När flera regler måste tillämpas, avgör körningsordningen för varje regel vilka som ska behandlas först. Mer information finns i avsnittet om [körningsordning](#typology-rules-execution-order) för typologiregler.

![](assets/typology_rule-active.png)

En typologiregel kan inaktiveras genom sin **[!UICONTROL Properties]** om du inte vill att regeln ska tillämpas när de meddelanden som berörs av regeln analyseras.

![](assets/typology_rule-order.png)

I **[!UICONTROL Targeting context]** kategorin kan du välja **Måldimension** och **Filtreringsdimension** beroende på vilka data du vill ha som mål.

Som standard utförs filtrering på **[!UICONTROL Profiles]**. Om regeln till exempel är avsedd för ett mobilprogram kan den **[!UICONTROL Filtering dimension]** ändras till **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Körningsordning för typologiregler {#typology-rules-execution-order}

Typologireglerna körs i en ordning som anges under faserna för målinriktning, analys och meddelandepersonalisering.

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
