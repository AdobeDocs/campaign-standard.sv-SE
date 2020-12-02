---
solution: Campaign Standard
product: campaign
title: Konfigurera transaktionsmeddelanden
description: Lär dig hur du konfigurerar transaktionsmeddelanden.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '3169'
ht-degree: 7%

---


# Konfigurera transaktionsmeddelanden{#configuring-transactional-messaging}

Om du vill skicka ett transaktionsmeddelande med Adobe Campaign måste du först beskriva strukturen för händelsedata.

Händelsekonfigurationen måste utföras av en [administratör](../../administration/using/users-management.md#functional-administrators) enligt stegen nedan.

>[!NOTE]
>
>Konfigurationen kan variera beroende på vilken typ av transaktionsmeddelande du vill skicka. Mer information finns i [Transactional event specific configurations](#transactional-event-specific-configurations).

När händelsen har publicerats:

* Det API som kommer att användas av webbplatsutvecklaren distribueras och transaktionshändelserna kan nu skickas. Se [Integrera utlösaren av händelsen på en webbplats](#integrating-the-triggering-of-the-event-in-a-website).

* Motsvarande transaktionsmeddelande skapas automatiskt. Se [Komma igång med transaktionsmeddelanden](../../channels/using/getting-started-with-transactional-msg.md).

## Skapa en händelse {#creating-an-event}

Börja med att skapa den händelse som passar dina behov.

>[!IMPORTANT]
>
>Endast användare som har rollen **[!UICONTROL Administration]** och som är en del av **[!UICONTROL All]** [organisationsenheten](../../administration/using/organizational-units.md) har rätt behörighet att skapa en händelsekonfiguration.

1. Klicka på **[!UICONTROL Adobe Campaign]**-logotypen i det övre vänstra hörnet och välj sedan **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Klicka på knappen **[!UICONTROL Create]**.
1. Ge händelsen ett **[!UICONTROL Label]** och ett **[!UICONTROL ID]**. Fältet **[!UICONTROL ID]** är obligatoriskt och ska börja med prefixet EVT. Om du inte använder det här prefixet läggs det till automatiskt när du klickar på **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID:t får inte vara längre än 64 tecken, inklusive EVT-prefixet.

1. Välj den kanal som ska användas för att skicka dina transaktionsmeddelanden **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** eller **[!UICONTROL Mobile application]** (push-meddelanden).

   >[!NOTE]
   >
   >Endast en kanal kan användas för varje händelsekonfiguration.    När händelsen har skapats kan du inte ändra kanalen.    

1. Välj den måldimension som motsvarar den önskade händelsekonfigurationen och klicka på **[!UICONTROL Create]**.

   Händelsebaserade transaktionsmeddelanden måldata i själva händelsen, medan profilbaserade transaktionsmeddelanden måldata i Adobe Campaign-databasen. Mer information finns i [Transactional event specific configurations](#transactional-event-specific-configurations).

>[!NOTE]
>
>Antalet skapade realtidshändelser kan påverka din plattform. För att få bästa möjliga prestanda bör du ta bort händelser i realtid som du inte längre behöver. Se [Ta bort en händelse](#deleting-an-event).

## Definiera händelseattributen {#defining-the-event-attributes}

I avsnittet **[!UICONTROL Fields]** definierar du de attribut som ska integreras i händelseinnehållet och sedan kan användas för att anpassa transaktionsmeddelandet.

Stegen för att lägga till och ändra fält är desamma som för [anpassade resurser](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Om du vill skapa ett flerspråkigt transaktionsmeddelande definierar du ett ytterligare händelseattribut med ID:t **[!UICONTROL AC_language]**. Detta gäller endast händelsetransaktionsmeddelanden. När händelsen har publicerats är stegen för att redigera innehållet i ett flerspråkigt transaktionsmeddelande samma som för ett flerspråkigt standardmeddelande. Se [Skapa ett flerspråkigt e-postmeddelande](../../channels/using/creating-a-multilingual-email.md).

## Definiera datainsamlingar {#defining-data-collections}

Du kan lägga till en samling element i händelseinnehållet, där varje element innehåller flera attribut.

Den här samlingen kan användas i ett transaktionsmejl för att lägga till [produktlistor](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message) i innehållet i meddelandet, till exempel en produktlista - med pris, referensnummer, kvantitet osv. för varje produkt i listan.

1. Klicka på knappen **[!UICONTROL Create element]** i **[!UICONTROL Collections]**-avsnittet.

   ![](assets/message-center_collection_create.png)

1. Lägg till en etikett och ett ID för din samling.
1. Lägg till alla fält som du vill visa i transaktionsmeddelandet för varje produkt i listan.

   I det här exemplet har följande fält lagts till:

   ![](assets/message-center_collection_fields.png)

1. På fliken **[!UICONTROL Enrichment]** kan du berika varje objekt i samlingen. På så sätt kan du anpassa elementen i motsvarande produktlista med information från Adobe Campaign-databasen eller från andra resurser som du har skapat.

>[!NOTE]
>
>Stegen för att förbättra elementen i en samling är desamma som beskrivs i avsnittet [Förbättra händelsen](#enriching-the-transactional-message-content). Observera att du inte kan utöka en samling genom att berika händelsen: du måste lägga till en berikning i själva samlingen i **[!UICONTROL Collections]**-avsnittet.

När händelsen och meddelandet har publicerats kan du använda den här samlingen i ditt transaktionsmeddelande.

Här är API-förhandsvisningen för det här exemplet:

![](assets/message-center_collection_api-preview.png)

**Relaterade ämnen:**

* [Förhandsgranska och publicera evenemanget](#previewing-and-publishing-the-event)
* [Använda produktlistor i ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Angriper händelsen {#enriching-the-transactional-message-content}

Du kan utöka transaktionsmeddelandets innehåll med information från Adobe Campaign-databasen för att personalisera dina meddelanden. Från efternamnet eller CRM-ID:t för var och en av mottagarna kan du till exempel återställa data som adress eller födelsedatum eller andra anpassade fält som lagts till i profiltabellen, för att anpassa informationen som skickas till dem.

Det går att utöka transaktionens meddelandeinnehåll med information från utökat **[!UICONTROL Profile and services Ext API]**. Mer information finns i [Utöka API: Publicerar tillägget](../../developing/using/step-2--publish-the-extension.md)

Den här informationen kan också lagras i nya resurser. I så fall måste resursen länkas till **[!UICONTROL Profile]**- eller **[!UICONTROL Service]**-resurserna antingen direkt eller via en annan tabell. I konfigurationen nedan går det till exempel att utöka transaktionsmeddelandeinnehållet med information från resursen **[!UICONTROL Product]**, som produktkategorin eller ID, om resursen **[!UICONTROL Product]** är länkad till resursen **[!UICONTROL Profile]**.

![](assets/message-center_usecaseschema.png)

Mer information om att skapa och publicera resurser finns på [den här sidan](../../developing/using/key-steps-to-add-a-resource.md).

1. Klicka på knappen **[!UICONTROL Create element]** i **[!UICONTROL Enrichment]**-avsnittet.

   ![](assets/message-center_addenrichment.png)

1. Välj den resurs som du vill länka meddelandet med. I det här fallet väljer du resursen **[!UICONTROL Profile]**.

   ![](assets/message-center_new-enrichment.png)

1. Använd knappen **[!UICONTROL Create element]** för att länka ett fält från den markerade resursen till ett av fälten som du tidigare lade till i händelsen (se [Definiera händelseattributen](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. I det här exemplet förenar vi fälten **[!UICONTROL Last name]** och **[!UICONTROL First name]** med motsvarande fält i resursen **[!UICONTROL Profile]**.

   ![](assets/message-center_enrichment-join-fields.png)

   Du kan även utöka transaktionsmeddelandets innehåll med resursen **[!UICONTROL Service]**. Mer information om tjänster finns i det här [avsnittet](../../audiences/using/creating-a-service.md).

1. Om du skapar eller redigerar en profilbaserad händelse väljer du den anrikning som ska användas som meddelandemål under leveranskörningen i **[!UICONTROL Targeting enrichment]**-avsnittet.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >Det är obligatoriskt för profilbaserade händelser att välja en målberikning som baseras på resursen **[!UICONTROL Profile]**.

När händelsen och meddelandet har publicerats kan du med den här länken utöka innehållet i transaktionsmeddelandet.

**Relaterade ämnen:**

* [Förhandsgranska och publicera evenemanget](#previewing-and-publishing-the-event).
* [Anpassa ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Förhandsgranska och publicera händelsen {#previewing-and-publishing-the-event}

Innan du kan använda händelsen måste du förhandsgranska och publicera den.

1. Klicka på knappen **[!UICONTROL API preview]** för att se en simulering av REST API som kommer att användas av webbplatsutvecklaren innan den publiceras. När händelsen har publicerats kan du med den här knappen även se en förhandsgranskning av API:t som är i produktion. Se [Integrera utlösaren av händelsen på en webbplats](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API varierar beroende på den valda kanalen och den valda måldimensionen. Mer information om de olika konfigurationerna finns i [Transactional event specific configurations](#transactional-event-specific-configurations).

1. Klicka på **[!UICONTROL Publish]** för att starta publikationen.

   ![](assets/message-center_pub.png)

   Det API som kommer att användas av webbplatsutvecklaren distribueras och transaktionshändelserna kan nu skickas.

1. Du kan visa publikationsloggarna på motsvarande flik.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Varje gång du ändrar händelsen måste du klicka på **[!UICONTROL Publish]** igen för att generera det uppdaterade REST API som kommer att användas av webbplatsutvecklaren.

   När händelsen har publicerats skapas automatiskt ett transaktionsmeddelande som är länkat till den nya händelsen.

1. Du kan komma åt det här transaktionsmeddelandet direkt via länken i det vänstra området.

   ![](assets/message-center_messagegeneration.png)

För att händelsen ska kunna utlösa att ett transaktionsmeddelande skickas måste du ändra och publicera det meddelande som precis skapades. Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

Du måste även integrera den här utlösande händelsen på din webbplats. Se [Integrera utlösaren av händelsen på en webbplats](#integrating-the-triggering-of-the-event-in-a-website).

När Adobe Campaign börjar ta emot händelser som är relaterade till den här händelsekonfigurationen kan du använda länken **[!UICONTROL Latest transactional events]** under **[!UICONTROL History]**-avsnittet för att få tillgång till de senaste händelser som har skickats av din tredjepartstjänst och bearbetats av Adobe Campaign.

![](assets/message-center_latest-events.png)

Händelserna (i JSON-format) listas från den senaste till den äldsta. Med den här listan kan du kontrollera data som innehåll eller status för en händelse för kontroll- och felsökningsändamål.

### Avpublicerar en händelse {#unpublishing-an-event}

Med knappen **[!UICONTROL Unpublish]** kan du avbryta publiceringen av händelsen, vilket innebär att den resurs som motsvarar händelsen som du skapade tas bort från REST-API:t. Även om händelsen utlöses via din webbplats skickas inte längre motsvarande meddelanden och de lagras inte i databasen.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Om du redan har publicerat motsvarande transaktionsmeddelande avbryts även publikationen för transaktionsmeddelandet. Se [Avpublicera ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Klicka på knappen **[!UICONTROL Publish]** för att generera ett nytt REST API.

### Publiceringsprocess för transaktionsmeddelanden {#transactional-messaging-pub-process}

Diagrammet nedan visar processen för publicering av transaktionsmeddelanden.

![](assets/message-center_pub-process.png)

Mer information om att publicera, pausa och avpublicera transaktionsmeddelanden finns i [det här avsnittet](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

### Ta bort en händelse {#deleting-an-event}

När en händelse har avpublicerats, eller om en händelse inte har publicerats ännu, kan du ta bort den från händelsekonfigurationslistan. Så här gör du:

1. Klicka på **[!UICONTROL Adobe Campaign]**-logotypen i det övre vänstra hörnet och välj sedan **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Håll muspekaren över den händelsekonfiguration du vill använda och välj knappen **[!UICONTROL Delete element]**.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Kontrollera att händelsekonfigurationen har statusen **[!UICONTROL Draft]**, annars kan du inte ta bort den. **[!UICONTROL Draft]**-statusen gäller för en händelse som ännu inte har publicerats eller som har [opublicerats](#unpublishing-an-event).

1. Klicka på knappen **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Om du tar bort en händelsekonfiguration som har publicerats och redan använts tas även motsvarande transaktionsmeddelande(n) och dess avsändande och spårningsloggar bort.

## Söka efter transaktionshändelser {#searching-transactional-events}

Följ stegen nedan för att få tillgång till och söka efter transaktionshändelser som redan har skapats.

1. Klicka på **[!UICONTROL Adobe Campaign]**-logotypen i det övre vänstra hörnet och välj sedan **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Klicka på knappen **[!UICONTROL Show search]**.

   ![](assets/message-center_search-events.png)

1. Du kan filtrera på **[!UICONTROL Publication status]**. På så sätt kan du till exempel bara visa publicerade händelser.
1. Du kan också filtrera händelserna med **[!UICONTROL Last event received]**. Om du till exempel anger 10 visas bara de händelsekonfigurationer som innehåller den senaste händelsen som togs emot för 10 dagar sedan eller mer. Detta gör att du kan visa vilka händelser som har varit inaktiva under en viss period.

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >Standardvärdet är 0. Därefter visas alla händelser.

## Integrera händelseutlösaren på en webbplats {#integrating-the-triggering-of-the-event-in-a-website}

När du har skapat en händelse måste du integrera den som utlöser händelsen på webbplatsen.

I det exempel som beskrivs i [Transactional messaging operating policy](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)-avsnittet vill du att en händelse om att kunden överger kundvagnen ska utlösas när någon av dina kunder lämnar webbplatsen innan de köper produkterna i kundvagnen. För att göra detta måste webbutvecklaren använda Adobe Campaign Standard REST API.

Se [REST API-dokumentation](../../api/using/managing-transactional-messages.md).

## Transactional event specific configur{#transactional-event-specific-configurations}

Konfiguration av transaktionshändelser kan variera beroende på vilken typ av transaktionsmeddelande som du vill skicka (händelse eller profil) och vilken kanal som ska användas.

I följande avsnitt beskrivs vilken specifik konfiguration som ska ställas in enligt önskat transaktionsmeddelande. Mer information om de allmänna stegen för att konfigurera en händelse finns i [Skapa en händelse](#creating-an-event).

### Händelsebaserade transaktionsmeddelanden {#event-based-transactional-messages}

Om du vill skicka ett händelsebaserat transaktionsmeddelande måste du först skapa och konfigurera en händelse som riktar sig till data som finns i själva händelsen.
Mer information finns i [Engaging with transactional messaging](https://helpx.adobe.com/se/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. När du skapar händelsekonfigurationen väljer du måldimensionen **[!UICONTROL Real-time event]** (se [Skapa en händelse](#creating-an-event)).
1. Lägg till fält i händelsen för att kunna anpassa transaktionsmeddelandet (se [Definiera händelseattributen](#defining-the-event-attributes)).
1. Fyll i transaktionsmeddelandets innehåll om du vill använda ytterligare information från Adobe Campaign-databasen (se [Förbättra transaktionsmeddelandets innehåll](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Händelsebaserade transaktionsmeddelanden ska bara använda de data som finns i den skickade händelsen för att definiera mottagaren och meddelandets innehållspersonalisering.        Du kan dock utöka innehållet i transaktionsmeddelandet med information från Adobe Campaign-databasen.        

1. Förhandsgranska och publicera händelsen (se [Förhandsgranska och publicera händelsen](#previewing-and-publishing-the-event)).

   När händelsen förhandsgranskas innehåller REST API ett attribut som anger e-postadressen eller mobiltelefonen enligt den valda kanalen.

   När händelsen har publicerats skapas automatiskt ett transaktionsmeddelande som är länkat till den nya händelsen. För att händelsen ska kunna utlösa att ett transaktionsmeddelande skickas måste du ändra och publicera det meddelande som precis skapades, se [Händelsetransaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

1. Integrera händelsen på webbplatsen (se [Integrera händelseutlösaren på en webbplats](#integrating-the-triggering-of-the-event-in-a-website)).

### Profilbaserade transaktionsmeddelanden {#profile-based-transactional-messages}

Om du vill skicka ett profilbaserat transaktionsmeddelande måste du först skapa och konfigurera data för händelsemål i Adobe Campaign-databasen.

1. När du skapar händelsekonfigurationen väljer du måldimensionen **[!UICONTROL Profile event]** (se [Skapa en händelse](#creating-an-event)).
1. Lägg till fält i händelsen för att kunna anpassa transaktionsmeddelandet (se [Definiera händelseattributen](#defining-the-event-attributes)). Du måste lägga till minst ett fält för att skapa en anrikning. Du behöver inte skapa andra fält som **Förnamn** och **Efternamn** eftersom du kan använda anpassningsfält från Adobe Campaign-databasen.
1. Skapa en berikning för att länka händelsen till **[!UICONTROL Profile]**-resursen (se [Förbättra transaktionsmeddelandets innehåll](#enriching-the-transactional-message-content)). Det är obligatoriskt att skapa en anrikning när du använder en **[!UICONTROL Profile]**-måldimension.
1. Förhandsgranska och publicera händelsen (se [Förhandsgranska och publicera händelsen](#previewing-and-publishing-the-event)).

   När händelsen förhandsgranskas innehåller REST API inte något attribut som anger e-postadressen eller mobiltelefonen så som den hämtas från resursen **[!UICONTROL Profile]**.

   När händelsen har publicerats skapas automatiskt ett transaktionsmeddelande som är länkat till den nya händelsen. För att händelsen ska kunna utlösa att ett transaktionsmeddelande skickas måste du ändra och publicera det meddelande som precis skapades, se [Skicka ett profiltransaktionsmeddelande](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrera händelsen på webbplatsen (se [Integrera händelseutlösaren på en webbplats](#integrating-the-triggering-of-the-event-in-a-website)).

### Händelsebaserade push-meddelanden för transaktioner {#event-based-transactional-push-notifications}

Om du vill kunna skicka push-meddelanden via transaktion måste du konfigurera Adobe Campaign i enlighet med detta. Se [Push configuration](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdkv4.html).

Om du vill skicka ett anonymt transaktionspush-meddelande till alla användare som har valt att ta emot meddelanden från ditt mobilprogram, måste du först skapa och konfigurera en händelse som har de data som finns i själva händelsen som mål. Motsvarande steg visas nedan.

Händelsen måste innehålla följande tre element:

* En **registreringstoken**, som är användar-ID för ett mobilprogram och en enhet. Den kanske inte motsvarar någon profil från Adobe Campaign-databasen.
* Ett **mobilprogramnamn** (ett för alla enheter - Android och iOS). Detta är ID:t för det mobilprogram som konfigurerats i Adobe Campaign och som ska användas för att ta emot push-meddelanden på användarnas enheter. Se denna [sida](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) för mer information om detta
* En **push-plattform** (&quot;gcm&quot; för Android eller&quot;apns&quot; för iOS).

1. När du skapar händelsekonfigurationen väljer du kanalen **[!UICONTROL Mobile application]** och måldimensionen **[!UICONTROL Real-time event]** (se [Skapa en händelse](#creating-an-event)).
1. Lägg till fält i händelsen för att kunna anpassa transaktionsmeddelandet (se [Definiera händelseattributen](#defining-the-event-attributes)).
1. Fyll i transaktionsmeddelandets innehåll om du vill använda ytterligare information från Adobe Campaign-databasen (se [Förbättra transaktionsmeddelandets innehåll](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Händelsebaserade transaktionsmeddelanden ska bara använda de data som finns i den skickade händelsen för att definiera mottagaren och meddelandets innehållspersonalisering.        Du kan dock utöka innehållet i transaktionsmeddelandet med information från Adobe Campaign-databasen.        

1. Förhandsgranska och publicera händelsen (se [Förhandsgranska och publicera händelsen](#previewing-and-publishing-the-event)).

   När du förhandsgranskar händelsen innehåller REST API:t attributen registrationToken, application och pushPlatform som ska användas som mål för leveransen.

   ![](assets/message-center_push_api.png)

   När händelsen har publicerats skapas automatiskt ett transaktionspush-meddelande som är länkat till den nya händelsen. Mer information om hur du ändrar och publicerar det meddelande som precis skapades finns i [Skicka ett transaktionspush-meddelande för en händelse](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Integrera händelsen på webbplatsen (se [Integrera händelseutlösaren på en webbplats](#integrating-the-triggering-of-the-event-in-a-website)).

### Profilbaserade push-meddelanden för transaktioner {#profile-based-transactional-push-notifications}

Om du vill skicka ett transaktionspush-meddelande till de Adobe Campaign-profiler som har prenumererat på ditt mobilprogram måste du först skapa och konfigurera en händelse för Adobe Campaign-databasen.

1. När du skapar händelsekonfigurationen väljer du kanalen **[!UICONTROL Mobile application]** och måldimensionen **[!UICONTROL Profile]** (se [Skapa en händelse](#creating-an-event)).

   Som standard skickas transaktionsmeddelandet till alla mobilprogram som mottagarna prenumererar på. Om du vill skicka push-meddelandet till ett visst mobilprogram markerar du det i listan. De andra mobilapparna kommer att adresseras av meddelandet, men kommer inte att kunna skickas.

   ![](assets/message-center_push_appfilter.png)

1. Lägg till fält i händelsen om du vill anpassa transaktionsmeddelandet (se [Definiera händelseattributen](#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Du måste lägga till minst ett fält för att skapa en anrikning. Du behöver inte skapa andra fält som **Förnamn** och **Efternamn** eftersom du kan använda anpassningsfält från Adobe Campaign-databasen.

1. Skapa en berikning för att länka händelsen till **[!UICONTROL Profile]**-resursen (se [Förbättra transaktionsmeddelandets innehåll](#enriching-the-transactional-message-content)). Det är obligatoriskt att skapa en anrikning när du använder en **[!UICONTROL Profile]**-måldimension.
1. Förhandsgranska och publicera händelsen (se [Förhandsgranska och publicera händelsen](#previewing-and-publishing-the-event)).

   När händelsen förhandsgranskas innehåller REST API inte något attribut som anger registreringstoken, programnamn och push-plattform så som de hämtas från resursen **[!UICONTROL Profile]**.

   När händelsen har publicerats skapas automatiskt ett transaktionspush-meddelande som är länkat till den nya händelsen. Mer information om hur du ändrar och publicerar det meddelande som precis skapades finns i [Skicka ett transaktionspush-meddelande med en profil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) som mål.

1. Integrera händelsen på webbplatsen (se [Integrera händelseutlösaren på en webbplats](#integrating-the-triggering-of-the-event-in-a-website)).

### Konfigurera en händelse för att skicka ett uppföljningsmeddelande {#configuring-an-event-to-send-a-follow-up-message}

Ett uppföljningsmeddelande är en fördefinierad leveransmall för marknadsföring som kan användas i ett arbetsflöde för att skicka meddelanden till mottagarna av ett visst transaktionsmeddelande. Mer information finns i [Uppföljningsmeddelanden](../../channels/using/follow-up-messages.md).

1. Använd samma händelsekonfiguration som du skapade för att skicka ett händelsetransaktionsmeddelande. Se [Händelsebaserade transaktionsmeddelanden](#event-based-transactional-messages).
1. När du konfigurerar händelsen markerar du rutan **[!UICONTROL Create follow-up delivery template for this event]** innan du publicerar händelsen.

   ![](assets/message-center_follow-up-checkbox.png)

1. Förhandsgranska och publicera händelsen (se [Förhandsgranska och publicera händelsen](#previewing-and-publishing-the-event)).

   När händelsen har publicerats skapas automatiskt ett transaktionsmeddelande och en uppföljningsleveransmall som är länkad till den nya händelsen. Mer information om hur du använder uppföljningsmeddelanden finns i [Skicka ett uppföljningsmeddelande](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Användningsfall: konfigurera en händelse för att skicka ett transaktionsmeddelande {#use-case--configuring-an-event-to-send-a-transactional-message}

I det här exemplet vill vi konfigurera en händelse för att skicka bekräftelsemeddelanden efter varje köp på vår webbplats med följande villkor:

Eftersom vi vill identifiera kunden via detta CRM-ID måste du först kontrollera att resursen **[!UICONTROL Profile]** har utökats med det nya fältet.

På samma sätt måste en anpassad resurs som motsvarar inköp ha skapats och publicerats, och den måste vara länkad till **[!UICONTROL Profile]**-resursen. På så sätt kan du hämta information från den här resursen för att utöka meddelandeinnehållet.

Mer information om att skapa och publicera resurser finns på [den här sidan](../../developing/using/key-steps-to-add-a-resource.md).

1. Skapa en ny händelse med kanalen **[!UICONTROL Email]** och måldimensionen **[!UICONTROL Profile]** (se [Skapa en händelse](#creating-an-event)).
1. Definiera de attribut som ska vara tillgängliga för att anpassa transaktionsmeddelandet. I det här fallet lägger du till fälten &quot;CRM ID&quot; och &quot;Product identifier&quot; (se [Definiera händelseattributen](#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. Om du vill utöka meddelandeinnehållet med information om klientens tidigare inköp skapar du en anrikning för **[!UICONTROL Purchase]**-resursen (se [Förbättra transaktionens meddelandeinnehåll](#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Skapa ett kopplingsvillkor mellan fältet&quot;Produktidentifierare&quot; som tidigare lades till i meddelandet och motsvarande fält från resursen **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase3.png)

1. Förhandsgranska och publicera händelsen (se [Förhandsgranska och publicera händelsen](#previewing-and-publishing-the-event)).
1. Integrera händelsen på webbplatsen (se [Integrera händelseutlösaren på en webbplats](#integrating-the-triggering-of-the-event-in-a-website)).

