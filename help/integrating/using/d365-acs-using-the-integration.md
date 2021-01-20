---
title: Använda Microsoft Dynamics 365­integrationen
description: Lär dig hur du använder Microsoft Dynamics 365 med integrering av Campaign Standarder
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---


# Använda integreringen med Microsoft Dynamics 365

Det finns flera dataflöden som Adobe Campaign Standard-integreringen med Microsoft Dynamics 365 utför. Dessa flöden beskrivs i [den här sidan](../../integrating/using/d365-acs-self-service-app-workflows.md).

Mer information om dataflödena finns längre ned i det här dokumentet i avsnittet [Dataflöden](#data-flows).

## Adobe Campaign Standard användarupplevelse

När en kontakt skapas, ändras eller tas bort (om borttagen är aktiverad) i Microsoft Dynamics 365 skickas den vidare till Campaign Standarden. Dessa kontakter visas på profilskärmen i Campaign och kan användas i marknadsföringskampanjer. Se skärmen Profiler nedan.

![](assets/MSdynamicsACS-usage1.png)

När ett avanmälningsattribut ändras i Campaign återspeglas det i Dynamics 365 om du har valt avanmälningskonfigurationen **Unidirectional (Campaign to Microsoft Dynamics 365)** eller **Dubbelriktad** och om du har det angivna attributet korrekt mappat.

## Microsoft Dynamics 365 - användarupplevelse

För egress skickas följande e-postmarknadsföringshändelser från Campaign till Dynamics 365 och visas i tidslinjevyn i Microsoft Dynamics 365 som anpassade aktiviteter:

* Adobe Campaign Email Send

* Adobe Campaign Email Open

* Adobe Campaign E-postadress Klicka på

* Adobe Campaign Email Bounce

Om du vill visa en kontakts tidslinje går du till din kontaktlista genom att klicka på Försäljningssida i listrutan Dynamics 365. Klicka sedan på Kontakter på den vänstra menyraden och välj en kontakt.

>[!NOTE]
>
>Appen **Adobe Campaign för Microsoft Dynamics 365** i AppSource måste installeras i din Microsoft Dynamics 365-instans för att de här händelserna ska kunna visas. [Läs mer](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Här nedan ser du en ögonblicksbild av kontaktskärmen för&quot;Dynamics-användare&quot;. I tidslinjevyn kommer du att märka att Dynamics-användaren har fått ett e-postmeddelande som är kopplat till kampanjnamnet&quot;2019LoyaltyCamp&quot; och leveransnamnet&quot;DM190&quot;. Dynamics-användaren öppnade e-postmeddelandet och klickade också på en URL i e-postmeddelandet. båda dessa åtgärder skapade händelser som också visas nedan. Om du tittar till höger kommer du att se kortet för Relationship Assistant (RA); för närvarande innehåller det en uppgift att följa upp den klickade URL:en.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Nedan finns en stängning av tidslinjevyn för Dynamics-användare.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Nedan finns en närbild på RA-kortet (Relationship Assistant). AppSource-appen innehåller ett arbetsflöde som söker efter en klickningshändelse för e-postadress i Adobe. När den här händelsen inträffar skapas en uppgift och ett förfallodatum anges. Detta gör att aktiviteten kan visas i RA-kortet, vilket ger den extra synlighet. Det finns ett liknande arbetsflöde för e-poststudshändelser i Adobe, där en uppgift läggs till för att stämma av den ogiltiga e-postadressen. Dessa arbetsflöden kan stängas av i lösningen.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Om du klickar på ämnet för sändningshändelsen visas ett formulär som liknar det nedan. Formulären för öppnings- och studshändelser liknar varandra.

![](assets/do-not-localize/mirror_page_url_send.png)

Formuläret för klickningshändelser för e-post-URL lägger till ett extra attribut för den URL som du klickade på:

![](assets/do-not-localize/mirror_page_url_click.png)

Här följer en lista över attributen och en beskrivning:

* **Ämne**: Föremålet för evenemanget. bestående av kampanj-ID och leverans-ID för e-postleveransen

* **Ägare**: Programanvändaren som skapas i stegen efter etableringen

* **Angående**: Kontaktens namn

* **Kampanjnamn**: Kampanj-ID i Campaign Standard

* **Leveransnamn**: Leverans-ID i Campaign Standard

* **Datum skickat/öppnat/klickat/studsat**: Datum/tid när händelsen skapades

* **Spårnings-URL**: URL som användaren klickade på

* **URL för** speglingssida: URL:en till spegelsidan för e-postmeddelandet som skickades/öppnades/klickades/studsades. Utgångsperioden för e-postspegelsidan kan ändras på konfigurationsskärmen för motsvarande aktivitet i e-postkanalen för Campaign. [Läs mer](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Om du vill avanmäla dig återspeglas det i Campaign när ett avanmälningsattribut ändras i Microsoft Dynamics 365 om du har valt avanmälningskonfigurationen **Unidirectional (Campaign to Microsoft Dynamics 365)** eller **Dubbelriktad** och om du har det angivna attributet korrekt mappat.

## Dataflöden {#data-flows}

### Kontakt och anpassad entitetsinspelning

Nya, uppdaterade och borttagna poster (Obs! borttagen måste vara aktiverad) skickas från kontaktregistret för Microsoft Dynamics 365 till profiltabellen för Campaign.

Tabellmappningar kan konfigureras i integreringsprogrammets användargränssnitt för att mappa Microsoft Dynamics 365-registerattribut till Campaign-registerattribut. Tabellmappningarna kan ändras för att lägga till/ta bort attribut efter behov.

Dataflödets inledande körning är avsedd för överföring av alla mappade poster, inklusive sådana som markerats som &quot;inaktiva&quot;. kommer integreringen endast att bearbeta inkrementella uppdateringar. Undantaget är om data spelas upp eller om ett filter har konfigurerats. grundläggande, attributbaserade filtreringsregler kan konfigureras för att avgöra vilka poster som ska synkroniseras med Campaign.

Grundläggande ersättningsregler kan konfigureras i integreringsprogrammets användargränssnitt för att ersätta ett attributvärde med ett annat värde (t.ex. &quot;green&quot; för &quot;#00FF00&quot;, &quot;F&quot; för 1 osv.).

Beroende på hur många poster du har kan du behöva använda din Campaign SFTP-lagring för den första dataöverföringen. [Läs mer](#initial-data-transfer).

Kampanjprofiltabellattributet externalId måste fyllas i med kontaktattributet contactId i Dynamics 365 för att kontaktingress ska fungera. Anpassade kampanjentiteter måste också fyllas i med ett unikt ID-attribut för Dynamics 365. Det här attributet kan dock lagras i alla anpassade enhetsattribut för Campaign (d.v.s. behöver inte vara externalId).

>[!NOTE]
>
>För inpressning av anpassade entiteter måste ändringsspårning vara aktiverat i Dynamics 365 för synkroniserade anpassade entiteter.

#### Anpassade entiteter

[Integreringen av Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) stöder anpassade entiteter, vilket gör att anpassade entiteter i Dynamics 365 kan synkroniseras med motsvarande anpassade resurser i Campaign.

De nya uppgifterna i de anpassade resurserna kan användas för flera syften, inklusive segmentering och personalisering.

Integreringen stöder både länkade och icke-länkade tabeller. Länkning stöds upp till tre nivåer (d.v.s. level1->level2->level3).

>[!IMPORTANT]
>
>Om någon anpassad kampanjresurspost innehåller personlig information, gäller speciella rekommendationer. Läs mer [i det här avsnittet](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).


När du konfigurerar dataflöden för anpassade entiteter är det viktigt att du är medveten om följande:

* Att skapa och ändra anpassade Campaign-resurser är känsliga åtgärder som bara måste utföras av expertanvändare.
* För anpassade entitetsdataflöden måste ändringsspårning vara aktiverat i Dynamics 365 för synkroniserade anpassade entiteter.
* Om en överordnad och länkad underordnad post skapas nära samma tid i Dynamics 365, på grund av den parallella bearbetningen av integreringen, finns det en liten risk för att en ny underordnad post kan skrivas till Campaign före den överordnade posten.

* Om den överordnade och underordnade posten är länkad på Campaign-sidan med alternativet **1 enkel kardinalitetslänk**, förblir den underordnade posten dold och otillgänglig (via gränssnittet eller API) tills den överordnade posten kommer till Campaign.

* (Om du antar **1 enkel kardinalitetslänk** i Campaign) Om den underordnade posten uppdateras eller tas bort i Dynamics 365, och den ändringen skrivs till Campaign innan den överordnade posten visas i Campaign (inte troligt, men med en fjärrfunktion), kommer uppdateringen eller borttagningen inte att bearbetas i Campaign och ett fel kommer att genereras. Vid uppdatering måste posten i fråga uppdateras i Dynamics 365 igen för att den uppdaterade posten ska kunna synkroniseras. Vid radering måste posten i fråga hanteras separat på Campaign-sidan eftersom det inte längre finns en post i Dynamics 365 att radera eller uppdatera.

* Om du stöter på en situation där du tror att du har dolda underordnade poster och inte kan komma åt dem, kan du tillfälligt ändra kardinalitetslänktypen till **0 eller 1 enkel kardinalitetslänk** för att komma åt dessa poster.

En mer utförlig översikt över anpassade resurser för Campaign finns [i det här avsnittet](../../developing/using/key-steps-to-add-a-resource.md).

### Händelseflöde för e-postmarknadsföring{#email-marketing-event-flow}

E-postmarknadsföringshändelser skickas från Campaign till Microsoft Dynamics 365 för att visas i tidslinjevyn.

Marknadsföringshändelsetyper som stöds:
* Skicka - e-post har skickats till mottagare
* Öppna - e-post öppnad av mottagare
* Klicka - URL i e-post som mottagaren klickat på
* Studsa - e-post till mottagare fick en hård studsning

Följande händelseattribut visas i Dynamics 365:
* Namn på marknadsföringskampanj
* Namn på e-postleverans
* Tidsstämpel
* URL för e-postspegelsida
* URL-klickad (endast klickningshändelser)

E-postmarknadsföringshändelser kan aktiveras/inaktiveras per typ (skicka, öppna, klicka, studsa) så att endast de händelsetyper du väljer skickas till Dynamics 365.

### Avanmälningsflöde {#opt-out-flow}

Värden för avanmälan (t.ex. blockeringslista) synkroniseras mellan systemen. har du följande alternativ att välja mellan när du registrerar dig:

* **Enkelriktad (Microsoft Dynamics 365 till Campaign)**: Dynamics 365 är en källa till sanning för avanmälan. Attributen för avanmälan synkroniseras i en riktning från Dynamics 365 till Campaign Standard&quot;
* **Unidirectional (Campaign to Microsoft Dynamics 365)**: Campaign Standard är källan till sanning för avanmälan. Attribut för avanmälan synkroniseras i en riktning från Campaign Standard till Dynamics 365
* **Dubbelriktad**: Dynamics 365 OCH Campaign Standard är båda sanningskällor. Attributen för avanmälan synkroniseras dubbelriktat mellan Campaign Standard och Dynamics 365

Om du har en separat process för att hantera avanmälningssynkronisering mellan systemen kan även integreringens avanmälningsdataflöde inaktiveras.

>[!NOTE]
>
>I integreringsprogrammets användargränssnitt är **enkelriktade (Microsoft Dynamics 365 till Campaign)** och **dubbelriktade** avanmälningsfall konfigurerade i ett separat avanmälningsarbetsflöde. [Läs mer](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>Användningsexemplet **Unidirectional (Campaign to Microsoft Dynamics 365)** opt-out är ett undantag; den är konfigurerad i ingressen (kontakt till profil).


Flödesmappning för avanmälan ska anges av kunden eftersom affärskraven kan skilja sig mellan olika företag. På Campaign-sidan kan endast OTB-avanmälningsattribut användas för avanmälningsmappning:

* blockeringslista
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

I Dynamics 365 har de flesta avanmälningsfält prefixet &quot;donot&quot;. Du kan dock även använda andra attribut för avanmälan om datatyperna är kompatibla.

### Inledande dataöverföring {#initial-data-transfer}

Den initiala dataöverföringen kan ta en stund beroende på hur många poster du har inhämtat från Microsoft Dynamics 365. Efter den första dataöverföringen hämtar integreringen de stegvisa uppdateringarna.
