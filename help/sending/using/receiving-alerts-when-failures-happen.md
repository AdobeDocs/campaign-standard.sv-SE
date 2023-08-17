---
title: Få aviseringar när fel uppstår
description: Lär dig hur du använder varningshanteringssystemet.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2031'
ht-degree: 2%

---

# Få aviseringar när fel uppstår{#receiving-alerts-when-failures-happen}

## Om leveransvarningar {#about-delivery-alerting}

The **Leveransvarningar** är ett varningshanteringssystem som gör det möjligt för en grupp användare att automatiskt få meddelanden som innehåller information om hur deras leveranser utförs.

De skickade meddelandena innehåller en rapport som är baserad på följande kriterier:

* Misslyckade leveranser
* Leveranser med misslyckade förberedelser
* Leveranser med en felaktig felkvot för mjuk studs
* Leveranser med ett dåligt felförhållande för hårda studs
* Leveranser med en väntande status som är längre än vanligt
* Leveranser med låg genomströmning
* Pågående leveranser

Mottagarna av varningarna kan övervaka leveranser som bearbetas av Adobe Campaign och vidta lämpliga åtgärder när det uppstår problem i samband med att de utförs.

Dessa varningsmeddelanden kan anpassas beroende på särskilda varningsvillkor som definieras via en kontrollpanel i Adobe Campaign-gränssnittet.

>[!NOTE]
>
>Varningsmeddelandena levereras endast via e-post.

De skickade meddelandena innehåller:

* A **[!UICONTROL Summary]** visa antalet leveranser som uppfyller de kriterier som du har definierat och etiketten/färgen som du valde för varje kriterium.
* A **[!UICONTROL Details]** ett avsnitt där alla leveranskriterier som definierats för den motsvarande kontrollpanelen och alla leveranser för varje kriterium anges.

![](assets/delivery-alerting_notification.png)

## Kontrollpaneler för leveransvarningar {#delivery-alerting-dashboards}

### Om kontrollpaneler för leveransvarningar {#about-delivery-alerting-dashboards}

Om du vill hantera meddelandenas mottagare, ange aviseringskriterier och komma åt varningshistoriken måste du använda kontrollpaneler.

>[!NOTE]
>
>Om du vill få åtkomst till och konfigurera kontrollpanelerna och aviseringskriterierna måste du ha administratörsbehörighet eller visas i dialogrutan **Leveransansvariga** säkerhetsgrupp. Standardanvändare har inte åtkomst till kontrollpanelerna i Adobe Campaign-gränssnittet. De kan bara ta emot varningsmeddelanden. Mer information om användare och säkerhet i Adobe Campaign finns på [Typer av användare](../../administration/using/users-management.md) och [Om säkerhetsgrupper](../../administration/using/managing-groups-and-users.md#about-security-groups).

I Adobe Campaign gränssnitt kan du

* Skapa och hantera kontrollpaneler för leveransvarningar. Se [Skapa en kontrollpanel för leveransvarningar](#creating-a-delivery-alerting-dashboard).
* Definiera och hantera leveransaviseringskriterier för varje kontrollpanel. Du kan t.ex. skapa varningar baserade på leveranser med misslyckade förberedelser eller leveranser med ett lågt dataflöde. Se [Om varningsvillkor](#about-alerting-criteria).
* Ändra villkorsparametrarna för varje kontrollpanel. Se [Kriterieparametrar](#criteria-parameters).
* Definiera en grupp mottagare för varje kontrollpanel.

  Du vill till exempel bara informera användare med administrationsbehörighet om misslyckade leveranser. Ni vill dock att marknadsföringsanvändarna ska få information om leveranser med ett felförhållande som inte är tillräckligt bra för att studsa. Därför måste du skapa två olika kontrollpaneler och definiera villkoren som du vill använda för varje grupp av mottagare.

* Få åtkomst till historiken för alla skickade aviseringar för varje instrumentpanel.

  När du väljer en kontrollpanel visas den senaste skickade varningen för den här instrumentpanelen som standard. Alla skickade aviseringar visas till vänster på skärmen. Klicka på ett objekt i **[!UICONTROL History]** -lista för att komma åt motsvarande aviseringar.

![](assets/delivery-alerting_dashboard.png)

### Skapa en kontrollpanel för leveransvarningar {#creating-a-delivery-alerting-dashboard}

Om du vill skicka meddelanden baserat på specifika villkor till olika användargrupper måste du använda flera kontrollpaneler. Så här skapar du en ny kontrollpanel:

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Markera **[!UICONTROL Delivery alerting dashboards]** och klicka på **[!UICONTROL Create]**.
1. Kontrollera **[!UICONTROL Enabled]** för att aktivera den aktuella instrumentpanelen.

   Om det här alternativet är inaktiverat skickas inte längre meddelanden som är länkade till den här instrumentpanelen. Det här alternativet är inaktiverat som standard.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Välj den grupp av mottagare som du vill meddela i dialogrutan **[!UICONTROL Alert group]** listruta. Information om hur du ändrar eller skapar en grupp finns i [Skapa en säkerhetsgrupp och tilldela användare](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Från **[!UICONTROL Delivery alerting criteria]** avsnitt, klicka **[!UICONTROL Create element]** för att lägga till villkor. Se [Om varningsvillkor](#about-alerting-criteria).
1. Markera knappen **[!UICONTROL Edit properties]**. I **[!UICONTROL Criteria parameters]** definierar du hur villkoren ska tillämpas. Se [Kriterieparametrar](#criteria-parameters).
1. Klicka **[!UICONTROL Create]** för att spara instrumentpanelen.

Varje gång en leverans uppfyller de villkor som du har definierat i den här kontrollpanelen skickas ett varningsmeddelande till den angivna användargruppen.

## Villkor för leveransvarning {#delivery-alerting-criteria}

### Om varningsvillkor {#about-alerting-criteria}

Om du vill få åtkomst till leveransaviseringskriterierna går du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** och markera **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Följande kriterier kan användas i kontrollpanelerna för leveransvarningar:

* **[!UICONTROL Deliveries failed]**: Alla leveranser som schemalagts inom ett definierat intervall, med en felaktig status.
* **[!UICONTROL Deliveries with preparation failed]**: Alla leveranser som har ändrats inom ett definierat intervall och för vilka förberedelsesteget (målberäkning och innehållsgenerering) har misslyckats. Mer information finns i [Förbereder sändningen](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Alla schemalagda leveranser inom ett definierat intervall med en status på minst **[!UICONTROL In progress]**, med ett felförhållande för mjukt studs som är större än ett definierat procenttal.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Alla schemalagda leveranser inom ett definierat intervall med en status på minst **[!UICONTROL In progress]**, med ett felförhållande för skarpt studs som är större än ett definierat procenttal.
* **[!UICONTROL Deliveries with long start pending]**: Alla schemalagda leveranser inom ett definierat intervall, med en **[!UICONTROL Start pending]** status för längre tid än en definierad varaktighet, **[!UICONTROL Start pending]** status, vilket innebär att meddelanden ännu inte har beaktats av systemet.
* **[!UICONTROL Deliveries with low throughput]**: Alla leveranser påbörjades under längre tid än en definierad varaktighet, med mindre än en definierad procentandel av bearbetade meddelanden, med ett dataflöde som är lägre än ett definierat värde.
* **[!UICONTROL Deliveries in progress]**: Alla schemalagda leveranser inom ett definierat intervall, med **[!UICONTROL In progress]** status.

>[!NOTE]
>
>Alla parametrar som gäller ovanstående villkor har standardvärden. Dessa värden kan ändras i **[!UICONTROL Criteria parameters]** -fliken på kontrollpanelerna för leveransvarningar. Se [Kriterieparametrar](#criteria-parameters).

Du kan välja valfritt objekt i **[!UICONTROL Delivery alerting criteria]** -lista för att komma åt informationen.

![](assets/delivery-alerting_criteria_definition.png)

För varje kriterium kan du definiera följande inställningar:

* **[!UICONTROL Indicators to add in alerts]**, vilket innebär de kolumner som ska visas i meddelandenas **[!UICONTROL Details]** för de leveranser som motsvarar det valda kriteriet.

  ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, vilket innebär etiketten och färgen som visas bredvid leveransvillkoret i sammanfattningen av meddelandet.

  ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Om ett kriterium är uppfyllt för en leverans upprepas detta i varje anmälan som skickas inom övervakningsperioden. I annat fall skickas endast en avisering om dagen (vid den första förekomsten) enligt ett aviseringskriterium för en leverans.

  Som standard är det här alternativet inställt på en gång om dagen för alla villkor.

**Relaterade ämnen:**

* [Skicka loggar](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Varningsfrekvens](#alerting-frequency)
* [Ikoner för marknadsföringsaktiviteter och statusar](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Skapa ett leveransvarningsvillkor {#creating-a-delivery-alerting-criterion}

Du kan skapa nya leveransvarningsvillkor som passar dina behov bättre.

Du kan till exempel skapa ett nytt villkor som gör att du kan skicka ett meddelande med en lista över alla leveranser med en **[!UICONTROL Finished]** status.

För att göra detta måste du först utöka **Leverans** resurs och lägg till ett nytt filter som gör att du bara kan välja leveranser med en **[!UICONTROL Finished]** status.

1. Gå till **Adobe Campaign** > **Administration** > **Utveckling** > **Anpassade resurser** och klicka **[!UICONTROL Create]**.
1. Välj **[!UICONTROL Extend an existing resource]** väljer du **[!UICONTROL Delivery]** från listrutan och klicka på **[!UICONTROL Create]** för att redigera den.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Mer information om hur du utökar en befintlig resurs finns i [Definiera resursen](../../developing/using/creating-or-extending-the-resource.md).

1. I **[!UICONTROL Delivery]** resurs, gå till **[!UICONTROL Filter definition]** och klicka **[!UICONTROL Add an element]** för att skapa ett filter.

   ![](assets/delivery-alerting_new-filter.png)

1. Redigera den nya filterdefinitionen: i **[!UICONTROL Filter definition]** fönster, dra och släppa **[!UICONTROL Status]** objekt på arbetsytan och markera **[!UICONTROL Finished]** som filtervillkor.

   ![](assets/delivery-alerting_filter-status.png)

   Mer information om hur du skapar och redigerar anpassade filter finns i [Definiera filter](../../developing/using/configuring-filter-definition.md).

1. Spara ändringarna och publicera resurserna. Mer information finns i [Publicera en anpassad resurs](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Filtret skapas och kan nu väljas med ett nytt leveransvarningsvillkor.

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, markera **[!UICONTROL Delivery alerting criteria]** och klicka **[!UICONTROL Create]**.
1. I **[!UICONTROL Delivery filter applied by this criterion]** väljer du filtret som du just skapade.

   ![](assets/delivery-alerting_cus-filter.png)

   Du kan definiera villkorsinställningarna på samma sätt som för standardvillkoren. Se [Om varningsvillkor](#about-alerting-criteria).

När du har skapat dessa villkor kan du lägga till dem i en kontrollpanel för leveransvarningar samt andra villkor. Se [Om kontrollpaneler för leveransvarningar](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Relaterat ämne:**

[Lägga till eller utöka en resurs](../../developing/using/key-steps-to-add-a-resource.md)

## Parametrar för leveransavisering {#delivery-alerting-parameters}

### Kriterieparametrar {#criteria-parameters}

I **[!UICONTROL Criteria parameters]** -flik i en [kontrollpanel för leveransvarningar](#creating-a-delivery-alerting-dashboard)kan du definiera inställningarna som gäller för de villkor som valts på den här instrumentpanelen.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Om du till exempel anger 100 i det här fältet skickas ett meddelande endast för leveranser med ett mål som är lika med eller större än 100 mottagare. Den här parametern gäller för alla villkor.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Antal timmar före och efter den aktuella tiden. Endast leveranser som har ett kontaktdatum i det här tidsintervallet beaktas. Den här parametern gäller för alla villkor. Som standard är värdet för det här fältet inställt på 24 timmar.

  Mer information om kontaktdatum finns i [Om schemaläggning](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Ett meddelande skickas för alla leveranser med ett felförhållande för mjukt studs som är större än det angivna värdet. Som standard är fältets värde inställt på 0,05 (5 %).

  Mer information om mjuka studsfel finns i [E-poststudsar](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) och [Lista över leveransfeltyper](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Ett meddelande skickas för alla leveranser med ett felförhållande för hårda studs som är större än det angivna värdet. Som standard är fältets värde inställt på 0,05 (5 %).

  Mer information om hårda studsfel finns i [E-poststudsar](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) och [Lista över leveransfeltyper](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Ett meddelande skickas för alla leveranser med en **[!UICONTROL Start pending]** status för längre tid än vad som anges i detta fält, **[!UICONTROL Start pending]** status, vilket innebär att meddelanden ännu inte har beaktats av systemet.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Endast leveranser startade (med **[!UICONTROL In progress]** status) för mer än den angivna varaktigheten beaktas för **[!UICONTROL Deliveries with low throughput]** kriterium.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Endast leveranser med en procentandel av bearbetade meddelanden som är lägre än den angivna procentandelen beaktas för **[!UICONTROL Deliveries with low throughput]** kriterium.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Endast leveranser med en dataström som är lägre än det angivna värdet beaktas för **[!UICONTROL Deliveries with low throughput]** kriterium.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Endast leveranser med en procentandel av bearbetade meddelanden som är högre än den angivna procentandelen tas med i beräkningen.

### Varningsfrekvens {#alerting-frequency}

The **[!UICONTROL Frequency of delivery alerting]** kan du definiera fördröjningen mellan två varningsmeddelanden. Som standard är den inställd på 10 minuter.

Du kan ändra den här inställningen via **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** -menyn.

>[!NOTE]
>
>Det här alternativet gäller för alla instrumentpaneler som definieras i Adobe Campaign. Du kan inte ange en specifik frekvens för varje instrumentpanel.

## Orsaker till leveransvarningar {#delivery-alerting-reasons}

The **Leveransvarningar** Med den här funktionen får alla berörda Adobe Campaign-användare automatiskt information om leveransstatus via e-post och kontrollpanel.

När du får ett leveransvarningsmeddelande får du några tips om vad du kan göra.

Först och främst, kontrollera leveransens **Logg** för att visa all information om leverans och korrektur. Med de röda och gula ikonerna kan du identifiera fel och varningar. Den röda ikonen anger ett kritiskt fel som förhindrar att leveransen startas.

Om du vill visa historiken för varje förekomst av en leverans väljer du **[!UICONTROL Sending logs]** -fliken. Den innehåller en lista över skickade meddelanden och deras status. Där kan du kontrollera leveransstatus för varje mottagare ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, osv.). Mer information finns i [Skicka loggar](../../sending/using/monitoring-a-delivery.md#sending-logs).

Här är några möjliga orsaker till att du får varningsmeddelanden enligt de kriterier som uppfylls för en leverans.

* **[!UICONTROL Deliveries failed]**: Detta kriterium informerar dig om alla leveranser med felaktig status. Det kan bero på:

   * Ett problem med leveransservern (MTA, Message Transfer Agent)
   * En timeout för anslutningen mellan Adobe Campaign-leveransservern och den mottagande servern
   * Ett leveransproblem
   * Felaktigt arbetsflöde

  Om leveransen har utlösts med ett arbetsflöde kontrollerar du om arbetsflödet har startats korrekt. Mer information finns i [Köra ett arbetsflöde](../../automating/using/about-workflow-execution.md). Annars kontaktar du Adobe Campaign-administratören för att lösa problemet.

* **[!UICONTROL Deliveries with preparation failed]**: Ett fel kan uppstå under färdigställande av leverans i följande fall:

   * Leveransen saknar ämne.
   * Det finns en felaktig syntax i personaliseringsfälten.
   * Målet saknas.
   * Leveransen överskrider storleksgränsen.

  Mer information finns i [Förbereder sändningen](../../sending/using/preparing-the-send.md). Dessa fel upptäcks dock vanligtvis under meddelandeanalysen. Se [Kontrollregler](../../sending/using/control-rules.md).

* Möjliga orsaker till **[!UICONTROL Delivery with bad error ratio for soft bounces]** varning kan vara:

   * Mottagarens server är inte tillgänglig.
   * Mottagarens postlåda är full.

  Mer information finns i **[!UICONTROL Exclusion logs]** och **[!UICONTROL Exclusion causes]** -flikar i leveransloggarna. Se [Uteslutningsloggar](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

  Möjliga orsaker till **[!UICONTROL Delivery with bad error ratio for hard bounces]** varning kan vara:

   * Mottagaren läggs till i blockeringslista, vilket innebär att han/hon inte längre vill bli kontaktad.
   * Mottagarens e-postadress finns inte.
   * Mottagarens domän finns inte.
   * Mottagarens server blockerar leveransen.

  Följ de bästa metoderna nedan för att undvika mjuka och hårda studsfel:

   * Bygg filtreringstypologiregler som utesluter en del av meddelandemålet under leveransanalysen, till exempel mottagare i karantän. Se [Skapa en filtreringsregel](../../sending/using/filtering-rules.md).
   * Uppdatera regelbundet kunddatabasen för att upprätthålla goda karantänhanteringsprocesser. Se [Om karantäner](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * Generellt sett kan du förbättra slutresultatet så bra som möjligt. Se Adobe Campaign [Leverans](../../sending/using/about-deliverability.md) utförlig dokumentation och kontakta Adobe Campaign-administratören för att få hjälp.

* **[!UICONTROL Deliveries with long start pending]**: Vanligtvis innebär detta att det finns ett problem på MTA-nivå (Message Transfer Agent). Körningsprocessen väntar på att vissa resurser ska vara tillgängliga. MTA har kanske inte startats.

  **[!UICONTROL Deliveries with low throughput]**: Återigen är detta ett leveransproblem, vilket innebär att MTA är för långsamt.

  Kontakta Adobe Campaign-administratören om du vill ha mer information om dessa problem.

**Relaterade ämnen:**

* [Förstå leveransfel](../../sending/using/understanding-delivery-failures.md)
* [Förstå karantänshantering](../../sending/using/understanding-quarantine-management.md)
* [Om anmälan och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
