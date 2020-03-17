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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Filtreringsregler{#filtering-rules}

Med filtreringsregler kan du utesluta en del av meddelandemålet enligt villkor som definierats i en fråga, till exempel profiler i karantän eller profiler som redan har skickats ett visst antal e-postmeddelanden.

Du kan till exempel filtrera nyhetsbrevets prenumeranter så att de som är yngre än 18 år aldrig får meddelanden.

## Skapa en filtreringsregel {#creating-a-filtering-rule}

1. Skapa en typologiregel för **filtrering** , som kan tillämpas på alla kommunikationskanaler.

   ![](assets/typology_create-rule.png)

1. På **[!UICONTROL Filtering criteria]** fliken väljer du prenumerationerna i **[!UICONTROL Subscription]** kategorin.

   ![](assets/typology_create-rule-subscription.png)

1. Dra och släpp noden på fliken **[!UICONTROL Explorer]** i frågeredigeraren **[!UICONTROL Subscriber]** till skärmens huvuddel.

   ![](assets/typology_create-rule-subscriber.png)

1. Markera **[!UICONTROL Age]** fältet och definiera filtreringsvillkoren så att prenumeranternas ålder är 18 eller högre.

   ![](assets/typology_create-rule-age.png)

1. Länka den här regeln till en typologi på fliken **[!UICONTROL Typologies]** .

   ![](assets/typology_create-rule-typology.png)

1. Kontrollera att den aktuella typologin är markerad i leveransmallen som du vill använda.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >Om du vill komma åt leveransmallarna väljer du **[!UICONTROL Resources]** > **[!UICONTROL Templates]** på navigeringsmenyn som du kommer åt via Adobe Campaign-logotypen.

När den här regeln används i ett meddelande, kommer de abonnenter som betraktas som minderåriga automatiskt att uteslutas.

## Begränsa tillämpligheten för en filtreringsregel {#restricting-the-applicability-of-a-filtering-rule}

Du kan begränsa tillämpligheten för en filtreringsregel enligt meddelandet som ska skickas.

1. Avmarkera alternativet som är aktiverat som standard på fliken **[!UICONTROL Application criteria]** för typologiregeln **[!UICONTROL Apply the rule on all deliveries]** .

   ![](assets/typology_limit.png)

1. Använd frågeredigeraren för att definiera ett filter. Du kan till exempel bara tillämpa regeln på meddelanden vars etikett börjar med ett visst ord eller vars ID innehåller vissa bokstäver.

   ![](assets/typology_limit-rule.png)

I det här fallet tillämpas regeln bara på meddelanden som motsvarar de definierade villkoren.

## Undantagsregler för standardleverans {#default-deliverability-exclusion-rules}

Två filtreringsregler är tillgängliga som standard: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) och **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Under e-postanalysen jämför dessa regler mottagarnas e-postadresser med de förbjudna adresserna eller domännamnen i en krypterad global undertryckningslista som hanteras i leveransinstansen. Om det finns en matchning skickas inte meddelandet till den mottagaren.

Detta för att undvika att bli svartlistad på grund av skadlig aktivitet, särskilt användning av en svampfälla. Om en svällning till exempel används för att prenumerera via ett av dina webbformulär, skickas ett bekräftelsemeddelande via e-post till den svällningen, vilket gör att din adress automatiskt blir svartlistad.

>[!NOTE]
>
>Adresserna och domännamnen som finns i den globala undertryckningslistan är dolda. Endast antalet uteslutna mottagare anges i leveransanalysloggarna.

