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
source-git-commit: 130eaa44dc89a3b013038660d8e3790f05299136

---


# Konfigurera e-postkanal{#configuring-email-channel}

## E-postkanalsparametrar {#email-channel-parameters}

På skärmen för e-postkonfiguration kan du definiera parametrar för e-postkanalen.

![](assets/channels_1.png)

* **Huvudparametrar för skickade e-postmeddelanden**

   I det här avsnittet kan du ange **[!UICONTROL masks]** behörighet för avsändaradressen och feladressen. Om det behövs kan dessa masker separeras med kommatecken. Den här konfigurationen är valfri. När de här fälten anges kontrollerar Adobe Campaign att adresserna som anges är giltiga under meddelandeförberedelsetaget. Det här operativläget ser till att inga adresser används som kan utlösa leveransproblem. Leveransadresserna måste konfigureras på leveransservern.

* **Leverans**

   Detta ID tillhandahålls av supporten. Leveransrapporter måste fungera korrekt.

* **Leveransparametrar**

   Adobe Campaign skickar meddelanden som börjar på startdatumet. I **[!UICONTROL Message delivery duration]** fältet kan du ange hur länge meddelanden kan skickas.

   Fältet **[!UICONTROL Online resources validity duration]** används för överförda resurser, huvudsakligen för spegelsidan och bilder. Resurserna på den här sidan är giltiga under en begränsad tid (för att spara diskutrymme).

* **Försök igen**

   Tillfälligt olevererade meddelanden kan återförsökas automatiskt. I det här avsnittet anges hur många återförsök som ska utföras dagen efter att sändningen har startats (**antal återförsök**) och den minsta fördröjningen mellan återförsök (**återförsöksperiod**).

   Som standard schemaläggs fem återförsök till den första dagen med ett minsta intervall på en timme, som sprids ut över dygnets 24 timmar. Ett nytt försök per dag planeras efter det och fram till leveransdatumet, som definieras i **[!UICONTROL Delivery parameters]** avsnittet.

* **E-postkarantänsparametrar**

   I **[!UICONTROL Time between two significant errors]** fältet anger du ett värde som anger när programmet väntar innan räknaren ökas om fel uppstår. Standardvärde: **&quot;1d&quot;**, i en dag.

   När **[!UICONTROL Maximum number of errors before quarantine]** värdet nås sätts e-postadressen i karantän. Standardvärde: **&quot;5&quot;**: adressen sätts i karantän på det sjätte felet. Detta innebär att kontakten automatiskt utesluts från efterföljande leveranser.

**Relaterat ämne**:

[Om karantänhantering](../../sending/using/understanding-quarantine-management.md)

## E-postroutningskonton {#email-routing-accounts}

Det **[!UICONTROL Integrated email routing]** externa kontot anges som standard. Den innehåller de tekniska parametrar som gör att programmet kan skicka e-post.

![](assets/channels_2.png)

Kontotypen måste alltid anges till **[!UICONTROL Routing]**, kanalen till **[!UICONTROL Email]** och leveransläget till **[!UICONTROL Bulk delivery]**.

**Relaterat ämne**:

[Externa konton](../../administration/using/external-accounts.md)

## Regler för e-postbearbetning {#email-processing-rules}

Administratörer **[!UICONTROL Email processing rules]** kan komma åt informationen via **[!UICONTROL Administration > Channels > Email]** menyn.

Dessa regler innehåller en lista med teckensträngar som kan returneras av fjärrservrar och som gör att du kan kvalificera felet (**Hård**, **Mjuk** eller **Ignorerad**).

Standardreglerna är följande:

### Studsa meddelanden {#bounce-mails}

För synkrona felmeddelanden vid leveransfel fastställer Förbättrat MTA avhoppstypen och kvalificeringen och skickar tillbaka informationen till Campaign. Mer information om Adobe Campaign Enhanced MTA finns i det här [dokumentet](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Asynkrona studsar är fortfarande kvalificerade av Campaign-processen i Mail via **[!UICONTROL Bounce mails]** regeln.

>[!IMPORTANT]
>
>När du har uppgraderat till Förbättrat MTA används inte längre studskvalifikationerna i Campaign- **[!UICONTROL Message qualification]** tabellen. Mer information om studentkvalifikationer finns i det här [avsnittet](../../sending/using/understanding-delivery-failures.md).

<!--The user can create his own rules.

>[!IMPORTANT]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.-->

### Hantering av e-postdomäner {#managing-email-domains}

<!--The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTP relay**: lets you configure the IP address and the port of a relay server for a particular domain.-->

>[!IMPORTANT]
>
>När Adobe Campaign- **[!UICONTROL Domain management]** reglerna uppgraderats till det förbättrade MTA-avtalet används de inte längre.

**DKIM-signering (DomainKeys Identified Mail)** för e-postautentisering görs av den utökade MTA:n för alla meddelanden med alla domäner. Det signerar inte med **avsändar-ID**, **DomainKeys**, **DKIM** eller **S/MIME** om inte annat anges på den utökade MTA-nivån.

Mer information om Adobe Campaign Enhanced MTA finns i det här [dokumentet](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

### MX-hantering {#mx-management}

<!--The MX management rules are used to regulate the flow of outgoing emails for a specific domain. They sample the bounce messages and block sending where appropriate.

The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

To configure MX management rules, simply set a threshold and select certain SMTP parameters. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.-->

>[!IMPORTANT]
>
>När ni har uppgraderat till den förbättrade MTA-versionen används inte längre reglerna för **[!UICONTROL MX management]** leveransflöde i Adobe Campaign.

Den utökade MTA-servern använder sina egna MX-regler som gör att den kan anpassa din genomströmning efter domän baserat på ditt eget historiska e-postrykte och på realtidsfeedback som kommer från de domäner där du skickar e-post.

Mer information om Adobe Campaign Enhanced MTA finns i det här [dokumentet](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

<!--Each rule defines an address mask for the MX. Any MX whose name matches this mask is therefore eligible. The mask can contain "&#42;" and "?" generic characters.

For example, the following addresses:

* a.mx.yahoo.com 
* b.mx.yahoo.com 
* c.mx.yahoo.com

are compatible with the following masks:

* &#42;.yahoo.com
* ?.mx.yahoo.com

These rules are applied in sequence: the first rule whose MX mask is compatible with the targeted MX is applied.

The following parameters are available for each rule:

* **[!UICONTROL Range of IDs]**: this option lets you indicate the ranges of identifiers (publicId) for which the rule applies. You can specify:

    * A number: the rule will only apply to this publicId.
    * A range of numbers (number1-number2): the rule will apply to all publicIds between these two numbers.

  If the field is empty, the rule applies to all IDs.

* **[!UICONTROL Shared]**: this option indicates that the highest number of messages per hour and of connections applies to all MXs linked to this rule. 
* **[!UICONTROL Maximum number of connections]**: maximum number of simultaneous connections to an MX from a given address. 
* **Maximum number of messages**: maximum number of messages that can be sent by one connection. After this amount, the connection is closed and a new one is reopened. 
* **[!UICONTROL Messages per hour]**: maximum number of messages that can be sent in one hour for an MX via a given address.

>[!IMPORTANT]
>
>* The delivery server (MTA) must be restarted if the parameters have been changed. 
>* The modification or creation of management rules is for expert users only. -->

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

Tillfälligt olevererade meddelanden kan återförsökas automatiskt. I det här avsnittet anges hur många försök som ska utföras dagen efter att sändningen har startats ( **[!UICONTROL Max. number of retries]** ) och den minsta fördröjningen mellan återförsök ( **[!UICONTROL Retry period]** ).

Som standard schemaläggs fem återförsök till den första dagen med ett minsta intervall på en timme, som sprids ut över dygnets 24 timmar. Ett nytt försök per dag programmeras efter detta och fram till leveransdatumet, som definieras i avsnittet [Giltighetsperiodens parametrar](#validity-period-parameters) .

Antalet försök kan ändras globalt (kontakta Adobes tekniska administratör) eller för varje leverans- eller leveransmall

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

* **[!UICONTROL Explicitly set validity dates]**: När den här rutan är avmarkerad måste du ange en varaktighet i **[!UICONTROL Delivery duration]** - och **[!UICONTROL Resource validity limit]** fälten. Markera den här rutan om du vill definiera datum och klockslag.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**: Adobe Campaign skickar meddelanden som börjar på startdatumet. I det här fältet kan du ange hur länge meddelanden kan skickas.

   >[!IMPORTANT]
   >
   >När du har uppgraderat till det förbättrade MTA-värdet används parametern i dina Campaign-leveranser endast om den är inställd på 3,5 dagar eller mindre. **[!UICONTROL Delivery duration]** Om du anger ett värde som är högre än 3,5 dagar kommer det inte att tas med i beräkningen. Alla konsekvenser beskrivs i [Adobe Campaign Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html) -dokumentet.

* **[!UICONTROL Resource validity duration]**: Det här fältet används för överförda resurser, huvudsakligen för spegelsidan och bilder. Resurserna på den här sidan är giltiga under en begränsad tid (för att spara diskutrymme).
* **[!UICONTROL Mirror page management]**: spegelsidan är en HTML-sida som är tillgänglig online via en webbläsare. Innehållet är identiskt med e-postinnehållet. Spegelsidan genereras som standard om länken infogas i postinnehållet. I det här fältet kan du ändra hur sidan genereras:

   >[!IMPORTANT]
   >
   >Ett HTML-innehåll måste ha definierats för e-postmeddelandet för den spegelsida som ska skapas.

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
   >Typologier, som du kommer åt via **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** -menyn, presenteras i avsnittet [Typologier](../../administration/using/about-typology-rules.md) .

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
