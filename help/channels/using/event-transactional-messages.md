---
title: Transaktionsmeddelanden för händelser
description: Lär dig hur du skapar och publicerar ett transaktionsmeddelande för en händelse.
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Transaktionsmeddelanden för händelser{#event-transactional-messages}

Du kan skicka transaktionsmeddelanden för en händelse. Den här typen av transaktionsmeddelanden innehåller inte profilinformation: leveransmålet definieras av data som finns i själva händelsen.

När du har skapat och publicerat en händelse (övergivna varukorgar enligt [detta avsnitt](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)) skapas motsvarande transaktionsmeddelande automatiskt.

Konfigurationsstegen beskrivs i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) .

För att händelsen ska kunna utlösa att ett transaktionsmeddelande skickas måste du anpassa meddelandet, testa det och publicera det.

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]** säkerhetsgruppen.
>
>Händelsetransaktionsmeddelanden innehåller ingen profilinformation och är därför inte kompatibla med trötthetsregler (även om det gäller en anrikning med profiler). Se [Trötthetsregler](../../administration/using/fatigue-rules.md#choosing-the-channel).

## Definiera en testprofil i ett transaktionsmeddelande {#defining-a-test-profile-in-a-transactional-message}

Definiera en anpassad testprofil som gör att du kan förhandsgranska meddelandet och skicka ett bevis för att kontrollera det.

### Skapa en testprofil i transaktionsmeddelandet {#creating-a-test-profile-within-the-transactional-----------message}

1. Klicka på logotypen i det övre vänstra hörnet och välj sedan **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** **[!UICONTROL Transactional messages]** för att komma åt det meddelande du skapade.

   ![](assets/message-center_4.png)

1. Skapa en testprofil som ska länkas till din händelse.

   ![](assets/message-center_test-profile.png)

1. Ange den information som ska skickas i JSON-format i **[!UICONTROL Event data used for personalization]** -avsnittet. Det här är det innehåll som kommer att användas när du förhandsgranskar meddelandet och när testprofilen tar emot korrekturet.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Du kan också ange information som hör till profiltabellen. Se [Förbättra transaktionens meddelandeinnehåll](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. När du har skapat testprofilen föranges den i transaktionsmeddelandet. Klicka på **[!UICONTROL Test profiles]** meddelandeblocket för att kontrollera korrekturens mål.

   ![](assets/message-center_5.png)

### Skapa en testprofil utanför transaktionsmeddelandet {#creating-a-test-profile-outside-the-transactional-----------message}

Du kan också skapa en ny testprofil eller använda en som redan finns på **[!UICONTROL Test profiles]** menyn.

1. Klicka på **[!UICONTROL Adobe Campaign]** logotypen i det övre vänstra hörnet och välj sedan **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Markera händelsen som du just har skapat i avsnittet på sidan med den testprofil som du har valt. **[!UICONTROL Event]** I det här exemplet väljer du&quot;Avsluta kundvagn (EVTcartAbandonment)&quot;.
1. Ange den information som ska skickas i JSON-format i **[!UICONTROL Event data]** textrutan.

   ![](assets/message-center_3.png)

1. Spara ändringarna.

Du kan nu komma åt meddelandet som du skapade och välja den uppdaterade testprofilen.

**Relaterade ämnen:**

* [Hantera testprofiler](../../audiences/using/managing-test-profiles.md)
* [Definiera målgrupper](../../audiences/using/creating-audiences.md)

## Anpassa ett transaktionsmeddelande {#personalizing-a-transactional-message}

Följ stegen nedan för att konfigurera personalisering i ett transaktionsmeddelande:

1. Klicka på **[!UICONTROL Content]** blocket för att ändra meddelandets ämne och innehåll. I det här exemplet väljer du en mall som innehåller bilder och text. Mer information om mallar för e-postinnehåll finns i [Designa med mallar](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Lägg till ett ämne och redigera meddelandeinnehållet efter dina behov.

   >[ANMÄRKNING]
   >
   >Länken till den övergivna vagnen är en länk till en extern URL som dirigerar om personen till kundvagnen. Den här parametern hanteras inte i Adobe Campaign.

1. I det här exemplet vill du lägga till tre fält som du definierade när du [skapade händelsen](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): Förnamn, efternamn, efternamn, totalbelopp. Det gör du genom att [infoga ett anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field) i meddelandeinnehållet.

1. Bläddra till fälten genom **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Om du vill förbättra innehållet i meddelandet lägger du till fält genom att markera dem i den tabell som du länkade händelsen till. I vårt exempel markerar du **[!UICONTROL Title (salutation)]** fältet i **[!UICONTROL Profile]** tabellen genom **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Infoga alla fält som behövs.

   ![](assets/message-center_8.png)

1. Förhandsgranska meddelandet genom att välja den profil som du har definierat för den här händelsen.

   Stegen för att förhandsgranska ett meddelande finns i avsnittet [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md) .

   ![](assets/message-center_9.png)

   Du kan kontrollera att personaliseringsfälten matchar informationen som anges i testprofilen. Mer information finns i [Definiera en testprofil i ett transaktionsmeddelande](#defining-a-test-profile-in-a-transactional-message).

## Använda produktlistor i ett transaktionsmeddelande {#using-product-listings-in-a-transactional-message}

Du kan skapa produktlistor som refererar till en eller flera datainsamlingar i innehållet i ett transaktionsmeddelande. I ett e-postmeddelande om att kunden överger en kundvagn kan du till exempel inkludera en lista över alla produkter som fanns i kundvagnen när de lämnade webbplatsen, med en bild, priset och en länk till varje produkt.

>[!CAUTION]
>
>Produktlistor är bara tillgängliga när du redigerar transaktionsmeddelanden via [e-postdesignerns](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) gränssnitt.

Följ stegen nedan för att lägga till en lista över övergivna produkter i ett transaktionsmeddelande.

Du kan också titta på en uppsättning videor som förklarar de steg som krävs för att konfigurera produktlistor i ett transaktionsmejl. Mer information finns på [den här sidan](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>Adobe Campaign stöder inte kapslade produktlistor, vilket innebär att du inte kan inkludera en produktlista i en annan.

### Definiera en produktlista {#defining-a-product-listing}

Innan du kan använda en produktlista i ett transaktionsmeddelande måste du på händelsenivå definiera listan med produkter och fälten för varje produkt i listan som du vill visa. Mer information finns i [Definiera datainsamlingar](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Klicka på blocket i transaktionsmeddelandet för att ändra e-postinnehållet. **[!UICONTROL Content]**
1. Dra och släpp en strukturkomponent på arbetsytan. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Markera till exempel en strukturkomponent med en kolumn och lägg till en textkomponent, en bildkomponent och en knappkomponent. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Markera den strukturkomponent som du nyss skapade och klicka på **[!UICONTROL Enable product listing]** ikonen i det sammanhangsberoende verktygsfältet.

   ![](assets/message-center_loop_create.png)

   Strukturkomponenten är markerad med en orange ram och inställningarna visas på den vänstra paletten **[!UICONTROL Product listing]** .

   ![](assets/message-center_loop_palette.png)

1. Välj hur elementen i samlingen ska visas:

   * **[!UICONTROL Row]**: vågrätt, vilket innebär varje element på en rad under det andra.
   * **[!UICONTROL Column]**: lodrätt, vilket innebär att varje element ligger intill varandra på samma rad.
   >[!NOTE]
   >
   >Alternativet **[!UICONTROL Column]** är bara tillgängligt när du använder en strukturkomponent med flera kolumner ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** och **[!UICONTROL 4:4 column]** ). När du redigerar produktlistan ska du bara fylla i den första kolumnen: de övriga kolumnerna kommer inte att beaktas. Mer information om hur du väljer strukturkomponenter finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Välj den datainsamling du skapade när du konfigurerade händelsen som är relaterad till transaktionsmeddelandet. Du hittar den under **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** -noden.

   ![](assets/message-center_loop_selection.png)

   Mer information om hur du konfigurerar händelsen finns i [Definiera datainsamlingar](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Använd den **[!UICONTROL First item]** nedrullningsbara listan för att välja vilket element som ska starta listan som visas i e-postmeddelandet.

   Om du till exempel väljer 2 visas inte det första objektet i samlingen i e-postmeddelandet. Produktlistan börjar på den andra artikeln.

1. Välj det maximala antalet objekt som ska visas i listan.

   >[!NOTE]
   >
   >Om du vill att elementen i listan ska visas lodrätt ( **[!UICONTROL Column]** ), begränsas det maximala antalet objekt enligt den valda strukturkomponenten (2, 3 eller 4 kolumner). Mer information om hur du väljer strukturkomponenter finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Fylla i produktlistan {#populating-the-product-listing}

Följ stegen nedan om du vill visa en lista över produkter som kommer från händelsen som är länkad till transaktionsmeddelandet.

Mer information om hur du skapar en samling och relaterade fält när du konfigurerar händelsen finns i [Definiera datainsamlingar](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Markera bildkomponenten som du infogade, markera **[!UICONTROL Enable personalization]** och klicka på pennan i inställningspanelen.

   ![](assets/message-center_loop_image.png)

1. Markera **[!UICONTROL Add personalization field]** i det **[!UICONTROL Image source URL]** fönster som öppnas.

   Öppna noden som motsvarar den samling du skapade (här **[!UICONTROL Context]** ) i noden **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** > **[!UICONTROL Product list]** och markera bildfältet som du definierade (här **[!UICONTROL Product image]** ). Klicka på **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   Det anpassningsfält som du har valt visas nu i inställningspanelen.

1. Välj **[!UICONTROL Insert personalization field]** i det sammanhangsberoende verktygsfältet vid önskad position.

   ![](assets/message-center_loop_product.png)

1. Öppna noden som motsvarar samlingen du skapade (här **[!UICONTROL Context]** ) i noden **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** > **[!UICONTROL Product list]** och markera fältet som du skapade (här **[!UICONTROL Product name]** ). Klicka på **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   Det anpassningsfält som du har valt visas nu på önskad plats i e-postinnehållet.

1. Fortsätt på samma sätt om du vill infoga priset.
1. Markera text och välj **[!UICONTROL Insert link]** i det sammanhangsberoende verktygsfältet.

   ![](assets/message-center_loop_link_insert.png)

1. Markera **[!UICONTROL Add personalization field]** i det **[!UICONTROL Insert link]** fönster som öppnas.

   Öppna noden som motsvarar den samling du skapade (här **[!UICONTROL Context]** ) i noden **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** > **[!UICONTROL Product list]** och markera URL-fältet som du skapade (här **[!UICONTROL Product URL]** ). Klicka på **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >Av säkerhetsskäl måste du infoga anpassningsfältet i en länk som börjar med ett korrekt statiskt domännamn.

   ![](assets/message-center_loop_link_select.png)

   Det anpassningsfält som du har valt visas nu i inställningspanelen.

1. Välj strukturkomponenten som produktlistan ska tillämpas på och välj **[!UICONTROL Show fallback]** för att definiera ett standardinnehåll.

   ![](assets/message-center_loop_fallback_show.png)

1. Dra en eller flera innehållskomponenter och redigera dem efter behov.

   ![](assets/message-center_loop_fallback.png)

   Reservinnehållet visas om samlingen är tom när händelsen utlöses, till exempel om en kund inte har något i kundvagnen.

1. Redigera formaten för produktlistan i inställningspanelen. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).
1. Förhandsgranska e-postmeddelandet med en testprofil som är länkad till den relevanta transaktionshändelsen och för vilken du har definierat samlingsdata. Lägg till exempel till följande information i avsnittet **[!UICONTROL Event data]** för den testprofil som du vill använda:

   ![](assets/message-center_loop_test-profile_payload.png)

   Mer information om hur du definierar en testprofil i ett transaktionsmeddelande finns i [det här avsnittet](#defining-a-test-profile-in-a-transactional-message).

## Testa ett transaktionsmeddelande {#testing-a-transactional-message}

När du har sparat ditt transaktionsmeddelande kan du nu skicka ett bevis för att testa det.

![](assets/message-center_10.png)

Hur du skickar ett korrektur beskrivs i avsnittet [Skicka ett korrektur](../../sending/using/sending-proofs.md) .

## Publicera ett transaktionsmeddelande {#publishing-a-transactional-message}

När du har kontrollerat ditt transaktionsmeddelande kan du publicera det.

![](assets/message-center_12.png)

Så snart händelsen &quot;Avsluta kundvagn&quot; utlöses får mottagaren automatiskt ett meddelande med mottagarens titel och efternamn, kundvagns-URL, senaste produkt som efterfrågats eller en lista över produkter om du har definierat en produktlista samt det totala kundvagnsbelopp som ska skickas.

Använd **[!UICONTROL Reports]** knappen för att få åtkomst till rapporter om ditt transaktionsmeddelande. Se [Rapporter](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Pausa en publikation för transaktionsmeddelanden {#suspending-a-transactional-message-publication}

Du kan göra uppehåll i publiceringen av ditt transaktionsmeddelande genom att använda **[!UICONTROL Pause]** -knappen för att t.ex. ändra data i meddelandet. Händelserna behandlas därför inte längre utan hålls i en kö i Adobe Campaign-databasen.

Händelserna som står i kö behålls under en tidsperiod som definieras i REST API (se [REST API-dokumentationen](../../api/using/about-campaign-standard-apis.md)) eller i utlösarhändelsen om du använder huvudtjänsten Triggers (se [Arbeta med Campaign och Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

När du klickar på **[!UICONTROL Resume]** den här åtgärden bearbetas alla händelser som står i kö (förutsatt att de inte har gått ut). De innehåller nu alla ändringar som utfördes medan mallpubliceringen pausades.

## Avpublicera ett transaktionsmeddelande {#unpublishing-a-transactional-message}

Om du klickar **[!UICONTROL Unpublish]** kan du avbryta publikationen för transaktionsmeddelandet, men även publikationen för motsvarande händelse, som tar bort resursen som motsvarar händelsen som du skapade från REST-API:t. Även om händelsen utlöses via din webbplats skickas inte längre motsvarande meddelanden och de lagras inte i databasen.

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>Om du vill publicera meddelandet igen måste du gå tillbaka till motsvarande händelsekonfiguration, publicera det och sedan publicera meddelandet. Mer information finns i [Publicera ett transaktionsmeddelande](#publishing-a-transactional-message).

Om du avpublicerar ett pausat transaktionsmeddelande kan du behöva vänta upp till 24 timmar innan du kan publicera det igen. Detta gör att alla händelser som skickades till kön kan rensas i arbetsflödet. **[!UICONTROL Database cleanup]** Stegen för att pausa ett meddelande finns i avsnittet [Pausa ett transaktionspublikationsmeddelande](#suspending-a-transactional-message-publication) .

Arbetsflödet, som körs varje dag kl. 4, är tillgängligt via **[!UICONTROL Database cleanup]** > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** **[!UICONTROL Workflows]**.

## Ta bort ett transaktionsmeddelande {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

Genom att markera ett transaktionsmeddelande kan du ta bort det med **[!UICONTROL Delete element]** knappen även om det redan har publicerats. Du kan bara ta bort ett transaktionsmeddelande under vissa förhållanden:

* **Transaktionsmeddelanden**: Om du vill ta bort ett transaktionsmeddelande ska det avpubliceras och inte pausas.

   Om transaktionsmeddelandet är opublicerat måste händelsekonfigurationen också avpubliceras för att ditt transaktionsmeddelande ska kunna tas bort, såvida inte ett annat transaktionsmeddelande är länkat till motsvarande händelse. Mer information om hur du avpublicerar ett transaktionsmeddelande finns i det här [avsnittet](#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >Om du tar bort ett transaktionsmeddelande som redan har skickat meddelanden tas även dess loggar för sändning och spårning bort.

* **Transaktionsmeddelanden från en färdig händelsemall (interna transaktionsmeddelanden)**: Om du vill ta bort ett internt transaktionsmeddelande ska det avpubliceras och inte pausas.

   Det ska inte heller vara det enda transaktionsmeddelandet i händelsen, andra meddelanden måste länkas till motsvarande händelse.

## Återförsöksprocess för transaktionsmeddelande {#transactional-message-retry-process}

Ett temporärt olevererat transaktionsmeddelande kan komma att skickas igen automatiskt tills leveransen går ut. Mer information om leveransens varaktighet finns i Parametrar för [giltighetsperiod](../../administration/using/configuring-email-channel.md#validity-period-parameters).

När ett transaktionsmeddelande inte skickas finns det två system för återförsök:

* På nivån för transaktionsmeddelanden kan ett transaktionsmeddelande misslyckas innan händelsen tilldelas till en körningsleverans, vilket innebär mellan händelsemottagningen och leveransförberedelsen. Se Återförsöksprocess för [händelsebearbetning](#event-processing-retry-process).
* När händelsen har tilldelats en körningsleverans kan transaktionsmeddelandet misslyckas på den sändande processnivån på grund av ett tillfälligt fel. Se [Återförsöksprocess](#message-sending-retry-process)för att skicka meddelanden.

### Återförsöksprocess för händelsebearbetning {#event-processing-retry-process}

Om händelsen inte kan tilldelas en körningsleverans, skjuts händelsebearbetningen upp. Försök utförs sedan igen tills den har tilldelats en ny körningsleverans.

>[!NOTE]
>
>En uppskjuten händelse visas inte i transaktionsmeddelandets sändande loggar eftersom den ännu inte har tilldelats en körningsleverans.

Händelsen kunde till exempel inte tilldelas en körningsleverans eftersom dess innehåll inte var korrekt, det uppstod ett problem med åtkomsträttigheter eller varumärke, ett fel upptäcktes när typologiregler tillämpades osv. I så fall kan du pausa meddelandet, redigera det för att åtgärda problemet och publicera det igen. Systemet för nya försök tilldelar det sedan till en ny körningsleverans.

### Meddelande som skickar återförsöksprocess {#message-sending-retry-process}

När händelsen har tilldelats en körningsleverans kan transaktionsmeddelandet misslyckas på grund av ett tillfälligt fel, om mottagarens postlåda till exempel är full. Mer information finns i [Försök igen efter ett tillfälligt leveransfel](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>När en händelse tilldelas till en körningsleverans visas den i sändningsloggarna för den här körningsleveransen, och endast för tillfället. De misslyckade leveranserna visas på fliken **[!UICONTROL Execution list]** i transaktionsmeddelandet.

### Begränsningar {#limitations}

**Logguppdatering skickas**

Under återförsöksprocessen uppdateras inte de avsändande loggarna för den nya körningsleveransen omedelbart (uppdateringen utförs via ett schemalagt arbetsflöde). Det innebär att meddelandet kan vara i **[!UICONTROL Pending]** status även om transaktionshändelsen har bearbetats av den nya körningsleveransen.

**Körningen misslyckades**

Du kan inte stoppa en körningsleverans. Om den aktuella körningsleveransen misslyckas skapas en ny så snart en ny händelse tas emot och alla nya händelser bearbetas av den nya körningsleveransen. Inga nya händelser bearbetas av den misslyckade körningsleveransen.

Om vissa händelser som redan har tilldelats en körningsleverans har skjutits upp och om körningsleveransen misslyckas, tilldelar inte systemet återförsök de uppskjutna händelserna till den nya körningsleveransen, vilket betyder att dessa händelser går förlorade.
