---
title: Konfigurera e-postkanal i Adobe Campaign Standard
description: Lär dig hur du konfigurerar e-postkanalen i Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7af424d2b2ce29811dc0deb015113de2de0124c0

---


# Konfigurera e-postkanal{#configuring-email-channel}

Som [kampanjadministratör](../../administration/using/users-management.md#functional-administrators)kan du konfigurera inställningar för e-postkanaler. Dessa avancerade inställningar omfattar allmänna parametrar för e-postkanal, e-postroutningskonton, regler för e-postbearbetning och e-postegenskaper. På den här sidan får du lära dig hur du redigerar standardvärdena för den allmänna e-postadressen och skickar parametrar.

Observera att vissa e-postinställningar nu hanteras av Adobe Campaign Enhanced MTA. Därför:
* Vissa konfigurationer i gränssnittet för Campaign används inte längre:
   * Inställningarna **[!UICONTROL Retries]** på [Konfigurationsmenyn](#email-channel-parameters) och i [Skicka-parametrarna](#retries-parameters) för e-postegenskaperna.
   * Regler **[!UICONTROL MX management]** och **[!UICONTROL Domain management]** regler på menyn [för](#email-processing-rules)e-postbearbetningsregler.

* Andra parametrar hanteras nu delvis av Förbättrad MTA, medan viss konfiguration fortfarande kan göras i Campaign. De inställningar som påverkas är följande:
   * Parametern **[!UICONTROL Message delivery duration]** i **[!UICONTROL Configuration]** menyn. Mer information finns i [det här avsnittet](#email-channel-parameters).
   * Parametern **[!UICONTROL Delivery duration]** eller **[!UICONTROL Validity limit for sending messages]** i **[!UICONTROL Validity period]** avsnittet. Mer information finns i [det här avsnittet](#validity-period-parameters).
   * Reglerna **[!UICONTROL Bounce mails]** i **[!UICONTROL Email processing rules]**. Mer information finns i [det här avsnittet](#email-processing-rules).

## E-postkanalsparametrar {#email-channel-parameters}

På skärmen för e-postkonfiguration kan du definiera parametrar för e-postkanalen. Administratörer har tillgång till dessa konfigurationer på menyn **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Auktoriserade maskfält**

   I listan **[!UICONTROL Header parameters of sent emails]** visas de auktoriserade e-postadresser som du kan använda för att skicka e-postmeddelanden till dina mottagare (avsändaradress) och för att meddela dem om det finns fel (feladress).  Adobe Campaign kontrollerar att de angivna adresserna är giltiga under meddelandeförberedelsefasen. Det här operativläget ser till att inga adresser används som kan utlösa leveransproblem.
   * Både avsändar- och feladresser konfigureras av Adobe. Dessa fält får inte vara tomma.
   * Du kan inte redigera dessa fält. Om du vill uppdatera en adress kontaktar du Adobes kundtjänstteam.
   * Om du vill lägga till ytterligare en adress kan du använda [Kontrollpanelen](https://docs.adobe.com/content/help/en/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html) för att konfigurera en ny underdomän eller kontakta Adobes kundtjänstteam. Observera att om flera masker används, kommer de att avgränsas med kommatecken.
   * Det är en god vana att ange adresser med en stjärna som **@dindomain.com*: gör att du kan använda alla adresser som slutar med ditt underdomännamn.

* **Leverans**

   Dokumentet **[!UICONTROL Delivery reports ID]** tillhandahålls av Adobes kundtjänstteam. Den identifierar varje instans med ett leverans-ID som används i de tekniska leveransrapporterna.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Leveransparametrar**

   Adobe Campaign skickar meddelanden som börjar på startdatumet. I **[!UICONTROL Message delivery duration]** fältet kan du ange hur länge meddelanden kan skickas.

   >[!IMPORTANT]
   >
   >**Den här parametern i Campaign används nu bara om den är inställd på 3,5 dagar eller mindre.** Om du definierar ett värde som är högre än 3,5 dagar beaktas det inte eftersom det nu hanteras av Adobe Campaign Enhanced MTA.

   Fältet **[!UICONTROL Online resources validity duration]** används för överförda resurser, huvudsakligen för spegelsidan och bilder. Resurserna på den här sidan är giltiga under en begränsad tid (för att spara diskutrymme).

* **Försök igen**

   Tillfälligt olevererade meddelanden kan återförsökas automatiskt. Mer information finns i [Försök igen efter ett tillfälligt leveransfel](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

   >[!NOTE]
   >
   >Det maximala antalet återförsök och den minsta fördröjningen mellan återförsök hanteras nu av Adobe Campaign Enhanced MTA, baserat på hur bra en IP fungerar både historiskt och för närvarande på en viss domän. Inställningarna för **återförsök** i Campaign ignoreras.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **E-postkarantänsparametrar**

   I **[!UICONTROL Time between two significant errors]** fältet anger du ett värde som anger när programmet väntar innan räknaren ökas om fel uppstår. Standardvärdet är **&quot;1d&quot;**, för 1 dag.

   När **[!UICONTROL Maximum number of errors before quarantine]** värdet nås sätts e-postadressen i karantän. Standardvärdet är **&quot;5&quot;**: adressen sätts i karantän på det femte felet. Detta innebär att kontakten automatiskt utesluts från efterföljande leveranser.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   Mer information om karantäner finns i [Mer om karantänhantering](../../sending/using/understanding-quarantine-management.md).

## E-postroutningskonton {#email-routing-accounts}

Det **[!UICONTROL Integrated email routing]** externa kontot anges som standard. Den innehåller de tekniska parametrar som gör att programmet kan skicka e-post.

![](assets/channels_2.png)

Kontotypen måste alltid anges till **[!UICONTROL Routing]**, kanalen till **[!UICONTROL Email]** och leveransläget till **[!UICONTROL Bulk delivery]**.

**Relaterat ämne**:

[Externa konton](../../administration/using/external-accounts.md)

## Regler för e-postbearbetning {#email-processing-rules}

Administratörer **[!UICONTROL Email processing rules]** kan komma åt informationen via **[!UICONTROL Administration > Channels > Email]** menyn.

Observera att e-postdomänerna och MX-reglerna nu hanteras av Adobe Campaign Enhanced MTA:
* **DKIM-signering (DomainKeys Identified Mail)** för e-postautentisering görs av den utökade MTA:n för alla meddelanden med alla domäner. Det signerar inte med **avsändar-ID**, **DomainKeys** eller **S/MIME** om inte annat anges på den förbättrade MTA-nivån.
* Den utökade MTA-servern använder sina egna MX-regler som gör att den kan anpassa din genomströmning efter domän baserat på ditt eget historiska e-postrykte och på realtidsfeedback som kommer från de domäner där du skickar e-post.

### Studsa meddelanden {#bounce-mails}

Asynkrona studsar är fortfarande kvalificerade av Campaign-processen i Mail via **[!UICONTROL Bounce mails]** regeln.

Den här regeln innehåller en lista med teckensträngar som kan returneras av fjärrservrar och som gör att du kan kvalificera felet (**Hård**, **Mjuk** eller **Ignorerad**).

>[!NOTE]
>
>För synkrona felmeddelanden vid leveransfel fastställer Adobe Campaign Enhanced MTA studstyp och -kvalificering och skickar tillbaka informationen till Campaign.

Mer information om studentkvalifikationer finns i det här [avsnittet](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Lista över e-postegenskaper {#list-of-email-properties}

I det här avsnittet beskrivs listan med parametrar som är tillgängliga på egenskapsskärmen i en e-postmall eller e-postmall.

>[!NOTE]
>
>Vissa parametrar är bara tillgängliga i mallar. Vilka parametrar du kan komma åt [beror på dina behörigheter](../../administration/using/users-management.md).

Om du vill redigera egenskaperna för ett e-postmeddelande eller en e-postmall använder du **[!UICONTROL Edit properties]** knappen .

![](assets/delivery_options_1.png)

### Allmänna parametrar {#general-parameters}

Identifiera e-postmeddelandet med hjälp av fälten **[!UICONTROL Label]** och **[!UICONTROL ID]** överst i e-postparameterskärmen. Den här informationen visas i gränssnittet men inte för meddelandemottagarna.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>ID:t måste vara unikt.

I **[!UICONTROL Brand]** fältet kan du välja det varumärke som är kopplat till leveransen. Mer information om hur du använder och konfigurerar varumärken finns i avsnittet [Varumärke](../../administration/using/branding.md) .

I **[!UICONTROL Campaign]** fältet kan du ange kampanjen som är länkad till e-postmeddelandet.

Du kan också lägga till en bild **[!UICONTROL Description]** i motsvarande fält och redigera bilden som visas på e-postminiatyrbilden i listorna.

### Skickar parametrar {#sending-parameters}

Avsnittet **[!UICONTROL Send]** är bara tillgängligt för e-postmallar. Den innehåller följande parametrar:

#### Återställer parametrar {#retries-parameters}

Tillfälligt olevererade meddelanden kan återförsökas automatiskt. Mer information finns i [Försök igen efter ett tillfälligt leveransfel](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Den minsta fördröjningen mellan återförsök och det maximala antalet återförsök hanteras nu av Adobe Campaign Enhanced MTA, baserat på hur bra en IP fungerar både historiskt och för närvarande på en viss domän. Inställningarna **för kampanjåterförsök** ignoreras.

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

Inställningen för **leveranstid** (som definieras i avsnittet Parametrar [för](#validity-period-parameters) giltighetsperiod) som **har konfigurerats i Campaign gäller fortfarande, men bara upp till 3,5 dagar**. Då tas alla meddelanden i kön för nya försök bort från kön och skickas tillbaka som ett avhopp. Mer information om leveransfel finns i det här [avsnittet](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### E-postformatparametrar {#email-format-parameters}

Du kan konfigurera formatet för e-postmeddelanden som ska skickas. Det finns tre alternativ:

* **Använd mottagarinställningar** (standardläge): meddelandeformatet definieras enligt data som lagras i mottagarprofilen och lagras som standard i fältet **E-postformat** (@emailFormat). Om en mottagare vill ta emot meddelanden i ett visst format är detta det format som skickas. Om fältet inte är ifyllt skickas ett multipart-alternativt meddelande (se nedan).
* **Låt mottagaren av e-postklienten välja det lämpligaste formatet (multipart-alternativ)**: meddelandet innehåller båda formaten: text och HTML. Formatet som visas vid mottagning beror på konfigurationen av mottagarens e-postprogramvara (multipart-option).

   >[!IMPORTANT]
   >
   >Det här alternativet inkluderar båda versionerna av meddelandet. Det påverkar därför leveransflödet eftersom meddelandestorleken är större.

* **Skicka alla meddelanden i textformat**: meddelandet skickas i textformat. HTML-formatet skickas inte, utan används bara för spegelsidan när mottagaren klickar på länken i meddelandet.

#### SMTP-testläge {#smtp-test-mode}

Med det här **[!UICONTROL Enable SMTP test mode]** alternativet kan du testa att skicka e-postmeddelanden via en SMTP-anslutning utan att skicka meddelanden.
Meddelandena behandlas tills anslutningen till SMTP-servern har upprättats, men de skickas inte.

![](assets/smtp-test-mode.png)

Det här alternativet är tillgängligt för e-postmeddelanden och e-postmallar.

Om du aktiverar alternativet SMTP-testläge för en e-postmall aktiveras det här alternativet för alla e-postmeddelanden som skapas från den här mallen.

>[!IMPORTANT]
>
>När det här alternativet är aktiverat för ett e-postmeddelande skickas inga meddelanden förrän det är avmarkerat.
>En varning visas i e-postmallens eller e-postmallens kontrollpanel.

Mer information om hur du konfigurerar SMTP finns i avsnittet [Lista över SMTP-parametrar](#list-of-email-smtp-parameters) för e-post.

### Giltighetsperiodens parametrar {#validity-period-parameters}

Avsnittet **[!UICONTROL Validity period]** innehåller följande parametrar:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: När den här rutan är avmarkerad måste du ange en varaktighet i **[!UICONTROL Delivery duration]** - och **[!UICONTROL Resource validity limit]** fälten.

   Markera den här rutan om du vill definiera datum och klockslag.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign skickar meddelanden som börjar på startdatumet. I det här fältet kan du ange hur länge meddelanden kan skickas.

   >[!IMPORTANT]
   >
   >Parametern hanteras nu av Adobe Campaign Enhanced MTA. **Du måste definiera ett värde på upp till 3,5 dagar.** Om du anger ett värde som är högre än 3,5 dagar kommer det inte att tas med i beräkningen.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: Det här fältet används för överförda resurser, huvudsakligen för spegelsidan och bilder. Resurserna på den här sidan är giltiga under en begränsad tid (för att spara diskutrymme).
* **[!UICONTROL Mirror page management]**: spegelsidan är en HTML-sida som är tillgänglig online via en webbläsare. Innehållet är identiskt med e-postinnehållet. Spegelsidan genereras som standard om länken infogas i postinnehållet. I det här fältet kan du ändra hur sidan genereras:

   >[!IMPORTANT]
   >
   >HTML-innehåll måste ha definierats för e-postmeddelandet för den spegelsida som ska skapas.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (standardläge): spegelsidan genereras om länken infogas i postinnehållet.
   * **Framtvinga generering av spegelsidan**: även om ingen länk till spegelsidan infogas i meddelandena, skapas spegelsidan.
   * **Generera inte spegelsidan**: ingen spegelsida genereras, även om länken finns i meddelandena.
   * **Generera en spegelsida som bara är tillgänglig med meddelande-ID**: Med det här alternativet kan du komma åt spegelsidans innehåll, med anpassningsinformation, i leveransloggfönstret.

>[!NOTE]
>
>Parametern **[!UICONTROL Delivery duration]** gäller inte för transaktionsmeddelanden. Mer information om transaktionsmeddelanden finns i [det här avsnittet](../../channels/using/about-transactional-messaging.md).

### Spårningsparametrar {#tracking-parameters}

Avsnittet **[!UICONTROL Tracking]** innehåller följande parametrar:

* **[!UICONTROL Activate tracking]**: I kan du aktivera/inaktivera spårning av meddelande-URL. Om du vill hantera spårning för varje meddelande-URL använder du **[!UICONTROL Links]** -ikonen i åtgärdsfältet för e-postdesignern. Se [Om spårade URL:er](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: I kan du definiera hur länge spårningen ska aktiveras på URL-adresserna.
* **[!UICONTROL Substitution URL for expired URLs]**: Du kan ange en URL till en webbsida som visas när spårningen har upphört att gälla.

### Avancerade parametrar {#advanced-parameters}

Avsnittet **[!UICONTROL Advanced parameters]** innehåller flera parametrar.

I de första fälten kan du ange den information som behövs för att utveckla e-postmeddelanderubriker. Här kan du hantera svarsadressen och texten samt avsändaradressen (som fyller i fältet &quot;Från:&quot;). Den här informationen kan personaliseras.

Klicka på knappen till höger om fältet som ska ändras och lägg sedan till anpassningsfältet, innehållsblocket eller den dynamiska texten.

![](assets/advancedparameters.png)

Infogning och användning av personaliseringsinnehåll finns i dokumentationen om [personalisering av e-postinnehåll](../../designing/using/personalization.md) .

#### Målkontext {#target-context}

Med målgruppskontexten kan du definiera en uppsättning tabeller som ska användas för e-postmarknadsföring (i målgruppsdefinitionsskärmen) och personalisering (definiera personaliseringsfält i HTML-innehållsredigeraren).

#### Routning {#routing}

I det här fältet visas det routningsläge som används. Det refererar till ett externt konto. Detta kan till exempel användas om du vill använda ett externt konto som innehåller specifika varumärkningskonfigurationer.

>[!NOTE]
>
>Externa konton är tillgängliga via menyn **Administration** > **Programinställningar** > **Externa konton** .

#### Förberedelse {#preparation}

Förberedelser av meddelanden beskrivs i avsnittet [Godkännandemeddelanden](../../sending/using/preparing-the-send.md) .

* **[!UICONTROL Typology]**: Före varje sändning måste meddelanden förberedas för att innehållet och konfigurationen ska kunna valideras. De kontrollregler som tillämpas under beredningsfasen definieras i en **typologi**. För e-postmeddelanden omfattar förberedelsen till exempel kontroll av motivet, URL:er och bilder. Välj den typologi som ska användas i det här fältet.

   >[!NOTE]
   >
   >Typologier, som du kommer åt via **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** -menyn, presenteras i [det här avsnittet](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: gör att du kan beräkna etikettvärdet för e-postmeddelandet under meddelandets förberedelsefas med hjälp av anpassningsfält, innehållsblock och dynamisk text.

   Det går också att anpassa leveransetiketten med händelsevariabler som har deklarerats i arbetsflödets externa signalaktivitet. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: Med det här alternativet kan du lägga till SQL-frågeloggar i journalen under förberedelsefasen.

#### Korrekturinställningar {#proof-settings}

I det här avsnittet kan du konfigurera standardprefixet som ska användas i korrekturets ämnesrad. For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### Lista över SMTP-parametrar för e-post {#list-of-email-smtp-parameters}

Avsnittet **[!UICONTROL SMTP]** innehåller följande parametrar:

* **[!UICONTROL Character encoding]**: Markera **[!UICONTROL Force encoding]** rutan om du vill framtvinga meddelandekodning och markera sedan den kodning som du vill använda.
* **[!UICONTROL Bounce mails]**: Som standard tas studsmeddelanden emot i plattformens felinkorg (definieras i **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). Om du vill definiera en specifik feladress för ett e-postmeddelande anger du adressen i **[!UICONTROL Error address]** fältet.
* **[!UICONTROL Additional SMTP headers]**: Med det här alternativet kan ytterligare SMTP-huvuden läggas till i dina meddelanden. Skriptet som anges i **[!UICONTROL Headers]** fältet måste referera till en rubrik per rad i formatet **name:value**. Värden kodas automatiskt om det behövs.

   >[!IMPORTANT]
   >
   >Att lägga till ett skript för att infoga ytterligare SMTP-rubriker är reserverat för avancerade användare. Syntaxen för det här skriptet måste uppfylla kraven för den här innehållstypen: inget oanvänt utrymme, ingen tom rad o.s.v.

### Lista över åtkomstauktoriseringsparametrar {#list-of-access-authorization-parameters}

Avsnittet **[!UICONTROL Access authorization]** innehåller följande parametrar:

* I **[!UICONTROL Organizational unit]** fältet kan du begränsa åtkomsten till det här e-postmeddelandet till vissa användare. De användare som är associerade med den angivna enheten eller överordnade enheter har läs- och skrivåtkomst till det här e-postmeddelandet. Användare som är associerade med underordnade enheter har endast läsåtkomst till det här e-postmeddelandet.

   >[!NOTE]
   >
   >Du kan konfigurera organisationsenheter via menyn **Administration** > **Användare och säkerhet** .

* Fälten **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** och **[!UICONTROL Last modified]** fylls i automatiskt.
