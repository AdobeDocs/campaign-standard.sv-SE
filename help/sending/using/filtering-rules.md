---
solution: Campaign Standard
product: campaign
title: Filtreringsregler
description: Använd filtreringsregler för att förfina publikationen i dina meddelanden.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typologiregler
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 3%

---


# Filtreringsregler {#filtering-rules}

Med filtreringsregler kan du utesluta en del av meddelandemålet enligt villkor som definierats i en fråga, till exempel profiler i karantän eller profiler som redan har skickats ett visst antal e-postmeddelanden.

## Typologiregler för standardfiltrering {#default-filtering-typology-rules}

Tabellen nedan innehåller information om de färdiga filtreringsreglerna och deras relaterade kanaler.

| Etikett | Kanal | Beskrivning |
---------|----------|---------
| **[!UICONTROL Address not specified]** | Alla | Utesluter målpopulationen utan angiven adress (e-postadress, postadress osv.) enligt den valda kanalen). |
| **[!UICONTROL Address on denylist]** | Alla | Exkluderar adresser som finns på blockeringslista. |
| **[!UICONTROL Duplicate]** | Alla | Exkluderar dubbletter som baseras på målpopulationsfältet **[!UICONTROL Address]**. |
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

Detta för att undvika att läggas till i blockeringslista på grund av skadlig aktivitet, särskilt användning av en svampfälla. Om du till exempel använder en svällning för att prenumerera via ett av dina webbformulär, skickas ett bekräftelsemeddelande via e-post till den svällningen, vilket gör att din adress automatiskt läggs till i blockeringslista.

>[!NOTE]
>
>Adresserna och domännamnen som finns i den globala undertryckningslistan är dolda. Endast antalet uteslutna mottagare anges i leveransanalysloggarna.

## Skapa en filtreringsregel {#creating-a-filtering-rule}

Du kan skapa egna filtreringsregler efter behov. Du kan t.ex. filtrera målpopulationen för nyhetsbrev så att de som är yngre än 18 år aldrig får någon kommunikation.

Följ de här stegen för att skapa en filtreringstypologiregel:

1. Skapa en ny typologiregel. De viktigaste stegen för att skapa typologiregler beskrivs i [det här avsnittet](../../sending/using/managing-typology-rules.md).

1. Välj regeltypen **[!UICONTROL Filtering]** och ange sedan önskad kanal.

1. På fliken **[!UICONTROL Filtering criteria]** väljer du prenumerationerna i kategorin **[!UICONTROL Subscription]**.

   ![](assets/typology_create-rule-subscription.png)

1. På fliken **[!UICONTROL Explorer]** i frågeredigeraren drar och släpper du noden **[!UICONTROL Subscriber]** i skärmens huvuddel.

   ![](assets/typology_create-rule-subscriber.png)

1. Markera fältet **[!UICONTROL Age]** och definiera filtreringsvillkoren så att prenumerantens ålder är 18 år eller äldre.

   ![](assets/typology_create-rule-age.png)

1. Länka den här regeln till en typologi på fliken **[!UICONTROL Typologies]**.

   ![](assets/typology_create-rule-typology.png)

1. Kontrollera att typologin är markerad i den leverans- eller leveransmall som du vill använda. Mer information om detta finns i [det här avsnittet](../../sending/using/managing-typologies.md#applying-typologies-to-messages).

   ![](assets/typology_template.png)

När den här regeln används i ett meddelande, kommer de abonnenter som betraktas som minderåriga automatiskt att uteslutas.

## Konfigurerar filtreringsregelns målkontext {#configuring-filtering-rules-targeting-context}

Med Campaign Standard kan du konfigurera dimensionerna **Mål** och **Filtering** beroende på vilka data du vill använda.

Det gör du genom att öppna typologiregelns egenskaper och sedan gå till avsnittet **[!UICONTROL Advanced information]**.

Som standard utförs filtrering på **[!UICONTROL Profiles]**. Om regeln till exempel är avsedd för ett mobilprogram kan du ändra **[!UICONTROL Filtering dimension]** till **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Begränsa tillämpligheten för en filtreringsregel {#restricting-the-applicability-of-a-filtering-rule}

Du kan begränsa tillämpligheten för en filtreringsregel enligt meddelandet som ska skickas.

1. På typologiregelns **[!UICONTROL Application criteria]**-flik avmarkerar du alternativet **[!UICONTROL Apply the rule on all deliveries]** som är aktiverat som standard.

   ![](assets/typology_limit.png)

1. Använd frågeredigeraren för att definiera ett filter. Du kan till exempel bara tillämpa regeln på meddelanden vars etikett börjar med ett visst ord eller vars ID innehåller vissa bokstäver.

   ![](assets/typology_limit-rule.png)

I det här fallet tillämpas regeln bara på meddelanden som motsvarar de definierade villkoren.
