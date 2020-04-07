---
title: Filtreringsregler
description: Använd filtreringsregler för att förfina publikationen i dina meddelanden.
page-status-flag: never-activated
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# Filtreringsregler {#filtering-rules}

Med filtreringsregler kan du utesluta en del av meddelandemålet enligt villkor som definierats i en fråga, till exempel profiler i karantän eller profiler som redan har skickats ett visst antal e-postmeddelanden.

## Typologiregler för standardfiltrering {#default-filtering-typology-rules}

Tabellen nedan innehåller information om de färdiga filtreringsreglerna och deras relaterade kanaler.

| Etikett | Kanal | Beskrivning |
---------|----------|---------|---------
| **[!UICONTROL Address not specified]** | Alla | Utesluter målpopulationen utan angiven adress (e-postadress, postadress osv.) enligt den valda kanalen). |
| **[!UICONTROL Blacklisted address]** | Alla | Exkluderar svartlistade adresser. |
| **[!UICONTROL Duplicate]** | Alla | Exkluderar dubbletter som baseras på **[!UICONTROL Address]** målpopulationsfältet. |
| **[!UICONTROL Exclude mobile applications]** | Mobilapplikation | Utesluter appprenumerationer som inte matchar mobilappen som definieras i meddelandet. |
| **[!UICONTROL Exclude mobile applications for In-App]** | I appen | Utesluter appprenumerationer som inte matchar det mobilprogram som definieras i meddelandet (mall i appen). |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | I appen | Utesluter appprenumerationer som inte matchar det mobilprogram som definieras i meddelandet (sändningsmall i appen) |
| **[!UICONTROL Exclude mobile applications for Push]** | Mobilapplikation | Utesluter appprenumerationer som inte matchar det mobilprogram som definieras i meddelandet (för push) |
| **[!UICONTROL Quarantined address]** | Alla | Exkluderar adresser i karantän. |
| **[!UICONTROL Target limited in size]** | Alla | Kontrollerar om den maximala leveransstorleken har uppnåtts för målet. Gäller för direktutskick med alternativet &quot;leveransgräns&quot; aktiverat. |

Utöver dessa standardfiltreringsregler finns två undantagsregler:

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

Under e-postanalysen jämför dessa regler mottagarnas e-postadresser med de förbjudna adresserna eller domännamnen i en krypterad global undertryckningslista som hanteras i leveransinstansen. Om det finns en matchning skickas inte meddelandet till den mottagaren.

Detta för att undvika att bli svartlistad på grund av skadlig aktivitet, särskilt användning av en svampfälla. Om en svällning till exempel används för att prenumerera via ett av dina webbformulär, skickas ett bekräftelsemeddelande via e-post till den svällningen, vilket gör att din adress automatiskt blir svartlistad.

>[!NOTE]
>
>Adresserna och domännamnen som finns i den globala undertryckningslistan är dolda. Endast antalet uteslutna mottagare anges i leveransanalysloggarna.

## Skapa en filtreringsregel {#creating-a-filtering-rule}

Du kan skapa egna filtreringsregler efter behov. Du kan t.ex. filtrera målpopulationen för nyhetsbrev så att de som är yngre än 18 år aldrig får någon kommunikation.

Följ de här stegen för att skapa en filtreringstypologiregel:

1. Skapa en ny typologiregel. De viktigaste stegen för att skapa typologiregler beskrivs i [det här avsnittet](../../sending/using/managing-typology-rules.md).

1. Välj **[!UICONTROL Filtering]** regeltyp och ange sedan önskad kanal.

1. Välj prenumerationerna i **[!UICONTROkategorin på fliken]** Filtreringsvillkor **[!UICONTROL Subscription]** .

   ![](assets/typology_create-rule-subscription.png)

1. Dra och släpp noden på fliken **[!UICONTROL Explorer]** i frågeredigeraren **[!UICONTROL Subscriber]** till skärmens huvuddel.

   ![](assets/typology_create-rule-subscriber.png)

1. Markera **[!UICONTROL Age]** fältet och definiera filtreringsvillkoren så att prenumeranternas ålder är 18 eller högre.

   ![](assets/typology_create-rule-age.png)

1. Länka den här regeln till en typologi på fliken **[!UICONTROL Typologies]** .

   ![](assets/typology_create-rule-typology.png)

1. Kontrollera att typologin är markerad i den leverans- eller leveransmall som du vill använda. For more on this, refer to [this section](../../sending/using/managing-typologies.md#applying-typologies-to-messages).

   ![](assets/typology_template.png)

När den här regeln används i ett meddelande, kommer de abonnenter som betraktas som minderåriga automatiskt att uteslutas.

## Konfigurera filterregelns målkontext {#configuring-filtering-rules-targeting-context}

Med Campaign Standard kan ni konfigurera dimensionerna **Målinriktning** och **Filtrering** så att de används beroende på vilka data ni vill ha som mål.

Det gör du genom att öppna typologiregelns egenskaper och sedan gå till **[!UICONTROL Advanced information]** avsnittet.

Som standard utförs filtrering på **[!UICONTROL Profiles]**. Om regeln till exempel är avsedd för ett mobilprogram kan den **[!UICONTROL Filtering dimension]** ändras till **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Begränsa tillämpligheten för en filtreringsregel {#restricting-the-applicability-of-a-filtering-rule}

Du kan begränsa tillämpligheten för en filtreringsregel enligt meddelandet som ska skickas.

1. Avmarkera alternativet som är aktiverat som standard på fliken **[!UICONTROL Application criteria]** för typologiregeln **[!UICONTROL Apply the rule on all deliveries]** .

   ![](assets/typology_limit.png)

1. Använd frågeredigeraren för att definiera ett filter. Du kan till exempel bara tillämpa regeln på meddelanden vars etikett börjar med ett visst ord eller vars ID innehåller vissa bokstäver.

   ![](assets/typology_limit-rule.png)

I det här fallet tillämpas regeln bara på meddelanden som motsvarar de definierade villkoren.
