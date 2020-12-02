---
solution: Campaign Standard
product: campaign
title: Transaktionsmeddelanden för händelser
description: Lär dig hur du skapar och publicerar ett transaktionsmeddelande för en händelse.
page-status-flag: never-activated
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 69%

---


# Redigera ett transaktionsmeddelande {#editing-transactional-message}

När du har skapat och publicerat en händelse<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))--> skapas motsvarande transaktionsmeddelande automatiskt. Stegen för att konfigurera och publicera händelsen beskrivs i avsnittet [Konfigurera en transaktionshändelse](../../channels/using/configuring-transactional-event.md) och [Publicera en transaktionshändelse](../../channels/using/publishing-transactional-event.md).

Stegen för att komma åt, redigera och anpassa det här meddelandet beskrivs nedan.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). See [Fatigue rules](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

När meddelandet är klart kan det testas och publiceras. Se [Livslängd för transaktionsmeddelande](../../channels/using/publishing-transactional-message.md).

## Åtkomst till transaktionsmeddelanden {#accessing-transactional-messages}

Så här kommer du åt transaktionsmeddelandet som du har skapat:

1. Klicka på logotypen **[!UICONTROL Adobe Campaign]** i det övre vänstra hörnet.
1. Välj **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Klicka på det meddelande du vill redigera.

>[!IMPORTANT]
>
>För att få åtkomst till transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]**-säkerhetsgruppen. Mer information finns i [Hantering av användare](../../administration/using/users-management.md#functional-administrators).

## Anpassa ett transaktionsmeddelande {#personalizing-a-transactional-message}

Följ stegen nedan för att konfigurera anpassning i ett transaktionsmeddelande.

>[!NOTE]
>
>I det här avsnittet beskrivs hur du anpassar ett **händelsebaserat** transaktionsmeddelande.  Konfigurationsstegen för att skapa ett händelsebaserat transaktionsmeddelande visas i [det här avsnittet](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
>
>Specifikationerna för **profilbaserade** transaktionsmeddelanden beskrivs [nedan](#profile-transactional-message-specificities).

Du vill till exempel skicka ett meddelande till webbplatsanvändare som har lagt till produkter i kundvagnen och lämnat webbplatsen utan att gå igenom sina inköp. Det här exemplet presenteras i [Transactional messaging operating policy](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)-avsnittet.

1. Klicka på **[!UICONTROL Content]**-blocket för att ändra meddelandets ämne och innehåll. I det här exemplet väljer du en mall som innehåller bilder och text. Mer information om mallar för e-postinnehåll finns i [Designa e-postmeddelanden med mallar](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Lägg till ett ämne och redigera meddelandeinnehållet efter dina behov.

   >[!NOTE]
   >
   >Länken till den övergivna kundvagnen är en länk till en extern URL som dirigerar om personen till kundvagnen. Den här parametern hanteras inte i Adobe Campaign.

1. I det här exemplet lägger du till tre fält som du definierade när du [skapade händelsen](../../channels/using/configuring-transactional-event.md): Förnamn, efternamn, efternamn, kundvagnens totalbelopp. Du gör det genom att [infoga ett anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field) i meddelandeinnehållet.

1. Bläddra till fälten genom **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Om du vill förbättra innehållet i meddelandet lägger du till fält genom att markera dem i tabellen som du kopplade händelsen till. I det här exemplet väljer du fältet **[!UICONTROL Title (salutation)]** i tabellen **[!UICONTROL Profile]** via **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Infoga alla fält som behövs.

   ![](assets/message-center_8.png)

1. Förhandsgranska meddelandet genom att välja den profil som du har definierat för den här händelsen.

   Stegen för att förhandsgranska ett meddelande finns i avsnittet [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Du kan kontrollera att anpassningsfälten matchar informationen som anges i testprofilen. Mer information finns i [Definiera en specifik testprofil](../../channels/using/publishing-transactional-message.md#defining-specific-test-profile).

## Använda produktlistor i ett transaktionsmeddelande {#using-product-listings-in-a-transactional-message}

Du kan skapa produktlistor som hänvisar till en eller flera datainsamlingar i innehållet i ett transaktionsmeddelande. I ett e-postmeddelande om att kunden överger en kundvagn kan du till exempel inkludera en lista över alla produkter som fanns i kundvagnen när de lämnade webbplatsen, med en bild, priset och en länk till varje produkt.

>[!IMPORTANT]
>
>Produktlistor är bara tillgängliga när du redigerar transaktionsmeddelanden via gränssnitt [E-postdesignare](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Följ stegen nedan om du vill lägga till en lista över övergivna produkter i ett transaktionsmeddelande.

Du kan också titta på [den här uppsättningen videor](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails) som förklarar vilka steg som krävs för att konfigurera produktlistor i ett transaktionsmejl.

>[!NOTE]
>
>Adobe Campaign stöder inte kapslade produktlistor, vilket innebär att du inte kan inkludera en produktlista i en annan.

### Definiera en produktlista {#defining-a-product-listing}

Innan du kan använda en produktlista i ett transaktionsmeddelande måste du på händelsenivå definiera listan med produkter och fälten för varje produkt i listan som du vill visa. Mer information finns i [Definiera datasamlingar](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Klicka på **[!UICONTROL Content]**-blocket i transaktionsmeddelandet om du vill ändra e-postinnehållet.
1. Dra och släpp en strukturkomponent på arbetsytan. Mer information finns i [Definiera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Markera till exempel en strukturkomponent med en kolumn och lägg till en textkomponent, en bildkomponent och en knappkomponent. Mer information finns i [Använda innehållskomponenter](../../designing/using/designing-from-scratch.md#about-content-components).

1. Markera den strukturkomponent som du nyss skapade och klicka på ikonen **[!UICONTROL Enable product listing]** i det sammanhangsberoende verktygsfältet.

   ![](assets/message-center_loop_create.png)

   Strukturkomponenten är markerad med en orange ram och inställningarna visas på den vänstra paletten **[!UICONTROL Product listing]**.

   ![](assets/message-center_loop_palette.png)

1. Välj hur elementen i samlingen ska visas:

   * **[!UICONTROL Row]**: vågrätt, vilket innebär varje element på en rad under det andra.
   * **[!UICONTROL Column]**: lodrätt, vilket innebär att varje element ligger intill varandra på samma rad.

   >[!NOTE]
   >
   >Alternativet **[!UICONTROL Column]** är bara tillgängligt när du använder en strukturkomponent med flera kolumner (**[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** och **[!UICONTROL 4:4 column]**). När du redigerar produktlistan ska du bara fylla i den första kolumnen: de övriga kolumnerna kommer inte att beaktas. Mer information om hur du väljer strukturkomponenter finns i [Definiera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Välj den datainsamling du skapade när du konfigurerade händelsen som är relaterad till transaktionsmeddelandet. Du hittar den under noden **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Mer information om hur du konfigurerar händelsen finns i [Definiera datainsamlingar](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Använd **[!UICONTROL First item]**-listrutan för att välja vilket element som ska starta listan som visas i e-postmeddelandet.

   Om du till exempel väljer 2 visas inte det första punkten i samlingen i e-postmeddelandet. Produktlistan börjar på den andra punkten.

1. Välj det maximala antalet punkter som ska visas i listan.

   >[!NOTE]
   >
   >Om du vill att elementen i listan ska visas lodrätt (**[!UICONTROL Column]**), begränsas det maximala antalet punkter enligt den valda strukturkomponenten (2, 3 eller 4 kolumner). Mer information om hur du väljer strukturkomponenter finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Fylla i produktlistan {#populating-the-product-listing}

Följ stegen nedan om du vill visa en lista över produkter som kommer från händelsen som är kopplad till transaktionsmeddelandet.

Mer information om hur du skapar en samling och relaterade fält när du konfigurerar händelsen finns i [Definiera datainsamlingar](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Markera bildkomponenten som du infogade, markera **[!UICONTROL Enable personalization]** och klicka på pennan i panelen Inställningar.

   ![](assets/message-center_loop_image.png)

1. Markera **[!UICONTROL Add personalization field]** i **[!UICONTROL Image source URL]**-fönstret som öppnas.

   Öppna noden som motsvarar den samling du skapade (här **[!UICONTROL Context]**) i noden **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** > **[!UICONTROL Product list]** och markera bildfältet som du definierade (här **[!UICONTROL Product image]**). Klicka på **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   Det anpassningsfält som du har valt visas nu i panelen Inställningar.

1. Välj **[!UICONTROL Insert personalization field]** i det sammanhangsberoende verktygsfältet vid önskad position.

   ![](assets/message-center_loop_product.png)

1. Öppna noden som motsvarar samlingen du skapade (här **[!UICONTROL Context]**) i noden **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** > **[!UICONTROL Product list]** och markera fältet som du skapade (här **[!UICONTROL Product name]**). Klicka på **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   Det anpassningsfält som du har valt visas nu på önskad plats i e-postinnehållet.

1. Fortsätt på samma sätt om du vill infoga priset.
1. Markera text och välj **[!UICONTROL Insert link]** i det sammanhangsberoende verktygsfältet.

   ![](assets/message-center_loop_link_insert.png)

1. Markera **[!UICONTROL Add personalization field]** i **[!UICONTROL Insert link]**-fönstret som öppnas.

   Öppna noden som motsvarar den samling du skapade (här **[!UICONTROL Context]**) i noden **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** > **[!UICONTROL Product list]** och markera URL-fältet som du skapade (här **[!UICONTROL Product URL]**). Klicka på **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >Av säkerhetsskäl måste du infoga anpassningsfältet i en länk som börjar med ett korrekt statiskt domännamn.

   ![](assets/message-center_loop_link_select.png)

   Det anpassningsfält som du har valt visas nu i panelen Inställningar.

1. Välj strukturkomponenten som produktlistan ska tillämpas på och välj **[!UICONTROL Show fallback]** för att definiera ett standardinnehåll.

   ![](assets/message-center_loop_fallback_show.png)

1. Dra en eller flera innehållskomponenter och redigera dem efter behov.

   ![](assets/message-center_loop_fallback.png)

   Reservinnehållet visas om samlingen är tom när händelsen utlöses, till exempel om en kund inte har något i kundvagnen.

1. Redigera formaten för produktlistan i panelen Inställningar. Mer information finns i [Hantera e-postformat](../../designing/using/styles.md).
1. Förhandsgranska e-postmeddelandet med en testprofil som är kopplad till den relevanta transaktionshändelsen och för vilken du har definierat samlingsdata. Lägg till exempel till följande information i avsnittet **[!UICONTROL Event data]** för den testprofil som du vill använda:

   ![](assets/message-center_loop_test-profile_payload.png)

   Mer information om hur du definierar en testprofil i ett transaktionsmeddelande finns i [det här avsnittet](../../channels/using/publishing-transactional-message.md#defining-specific-test-profile).

## Specifikationer för profilbaserade transaktionsmeddelanden {#profile-transactional-message-specificities}

Du kan skicka transaktionsmeddelanden baserat på kundmarknadsföringsprofiler, vilket gör att du kan använda all profilinformation för att anpassa meddelandeinnehållet, använda länken för att ta bort prenumerationen och tillämpa typologiregler för marknadsföring som [trötthetsregler](../../sending/using/fatigue-rules.md).

* Mer information om skillnaderna mellan händelsebaserade och profilbaserade transaktionsmeddelanden finns i [det här avsnittet](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types).

* Konfigurationsstegen för att skapa ett profilbaserat transaktionsmeddelande beskrivs i [det här avsnittet](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

### Redigera ett profiltransaktionsmeddelande {#editing-profile-transactional-message}

Stegen för att skapa, personalisera och publicera ett profiltransaktionsmeddelande är i huvudsak desamma som för ett händelsetransaktionsmeddelande.

Skillnaderna mellan dessa anges nedan.

1. [Gå till transaktionsmeddelandet som skapades för att redigera det.](#accessing-transactional-messages)
1. Klicka på **[!UICONTROL Content]**-avsnittet i transaktionsmeddelandet.  Förutom e-postmallar för transaktioner kan du även välja valfri e-postmall för resursen **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Välj standardmall för e-post. Liknar alla marknadsföringsmejl innehåller den en **länk för att avbryta prenumerationen**.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Mer information om mallar finns i [det här avsnittet](../../designing/using/using-reusable-content.md#content-templates).

1. Till skillnad från konfigurationer som baseras på realtidshändelser har du **direkt åtkomst till all profilinformation** för att anpassa ditt meddelande. Du kan lägga till [anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field) på samma sätt som du gör för andra vanliga marknadsföringsmeddelanden.

1. Spara ändringarna innan du publicerar meddelandet. Mer information finns i [Publicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

### Övervaka leveransen av ett profilbaserat transaktionsmeddelande {#monitoring-a-profile-transactional-message-delivery}

När meddelandet har publicerats och webbplatsintegreringen är klar så kan du övervaka leveransen.

1. Om du vill visa meddelandets leveranslogg klickar du på ikonen längst ned till höger i **[!UICONTROL Deployment]**-blocket.

   Mer information om åtkomst till loggarna finns i [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md).

1. Klicka på fliken **[!UICONTROL Sending logs]**.  I kolumnen **[!UICONTROL Status]** anger **[!UICONTROL Sent]** att en profil har valt att delta.

   ![](assets/message-center_marketing_sending_logs.png)

1. Välj fliken **[!UICONTROL Exclusions logs]** om du vill visa mottagare som har uteslutits från meddelandemålet, till exempel adresser på blockeringslista.

   ![](assets/message-center_marketing_exclusion_logs.png)

För alla profiler som har avanmält sig exkluderas motsvarande mottagare av typologiregeln **[!UICONTROL Address on denylist]**.

Den här regeln ingår i en specifik typologi som gäller för alla transaktionsmeddelanden som baseras på tabellen **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Relaterade ämnen**:

* Integrera händelseutlösare(../../channels/using/getting-started-with-transactional-msg.md#integrated-event-trigger)
* [Om typologier och typologiregler](../../sending/using/about-typology-rules.md)
