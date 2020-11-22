---
solution: Campaign Standard
product: campaign
title: Använda Microsoft Dynamics 365­integrationen
description: Lär dig hur du använder Microsoft Dynamics 365 med integrering av Campaign Standarder
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 0%

---


# Använda Microsoft Dynamics 365­integrationen

Det finns flera jobb som den här integreringen utför:

* **Ingång**:

   * Ta in **kontakter** från Dynamics 365 i Campaign

   * **Anpassade entiteter**: Hämta in anpassade tabeller från Dynamics 365 till Campaign. Läs mer [i det här avsnittet](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Utress**: Ta in e-postmarknadsföringshändelser från ACS till D365 (skicka via e-post, öppna, klicka, studsa)

* **Avanmäl dig**: Avanmälningsstatus för dubbelriktad synkronisering (t.ex. blockeringslista)

Mer information om dataflödena finns [i det här avsnittet](#data-flows).

## Adobe Campaign Standard användarupplevelse

När en kontakt skapas eller ändras (eller tas bort om det är aktiverat) i Dynamics 365 skickas den vidare till Campaign.  Dessa kontakter visas på profilskärmen i Campaign och kan användas i marknadsföringskampanjer.  Se skärmen Profiler nedan.

![](assets/MSdynamicsACS-usage1.png)

När ett avanmälningsattribut ändras i Campaign återspeglas det i Dynamics 365 om du har valt konfigurationen Campaign-to-Dynamics 365 eller dubbelriktad avanmälan och om du har det attributet korrekt mappat.

## Microsoft Dynamics 365 - användarupplevelse

För egress skickas följande e-postmarknadsföringshändelser från Campaign till Dynamics 365 och visas i tidslinjevyn i Dynamics 365 som anpassade aktiviteter:

* Adobe Campaign Email Send

* Adobe Campaign Email Open

* Adobe Campaign E-postadress Klicka på

* Adobe Campaign Email Bounce

Om du vill visa en kontakts tidslinje går du till din kontaktlista genom att klicka på Försäljningssida i listrutan Dynamics 365.  Klicka sedan på Kontakter på den vänstra menyraden och välj en kontakt.

>[!NOTE]
>
>Appen Adobe Campaign för Dynamics 365 i AppSource måste installeras i din Dynamics 365-instans för att du ska kunna visa dessa händelser.

Här nedan ser du en ögonblicksbild av kontaktskärmen för&quot;Dynamics-användare&quot;.  I tidslinjevyn kommer du att märka att Dynamics-användaren har fått ett e-postmeddelande som är kopplat till kampanjnamnet&quot;2019LoyaltyCamp&quot; och leveransnamnet&quot;DM190&quot;.  Dynamics-användaren öppnade e-postmeddelandet och klickade också på en URL i e-postmeddelandet. båda dessa åtgärder skapade händelser som också visas nedan.  Om du tittar till höger kommer du att se kortet för Relationship Assistant (RA); för närvarande innehåller det en uppgift att följa upp den klickade URL:en.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Nedan finns en stängning av tidslinjevyn för Dynamics-användare.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Nedan finns en närbild på RA-kortet (Relationship Assistant).  AppSource-appen innehåller ett arbetsflöde som söker efter en klickningshändelse för e-postadress i Adobe.  När den här händelsen inträffar skapas en uppgift och ett förfallodatum anges.  Detta gör att aktiviteten kan visas i RA-kortet, vilket ger den extra synlighet.  Det finns ett liknande arbetsflöde för e-poststudshändelser i Adobe, där en uppgift läggs till för att stämma av den ogiltiga e-postadressen.  Dessa arbetsflöden kan stängas av i lösningen.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Om du klickar på ämnet för sändningshändelsen visas ett formulär som liknar det nedan.  Formulären för öppnings- och studshändelser liknar varandra.

![](assets/do-not-localize/mirror_page_url_send.png)

Formuläret för klickningshändelser för e-post-URL lägger till ett extra attribut för den URL som du klickade på:

![](assets/do-not-localize/mirror_page_url_click.png)

Här följer en lista över attributen och en beskrivning:

* Ämne: Föremålet för evenemanget. bestående av kampanj-ID och leverans-ID för e-postleveransen

* Ägare: Programanvändaren som skapas i stegen efter etableringen

* Angående: Kontaktens namn

* Kampanjnamn: Kampanj-ID i Campaign Standard

* Leveransnamn: Leverans-ID i Campaign Standard

* Datum skickat/öppnat/klickat/studsat: Datum/tid när händelsen skapades

* Spårnings-URL: URL som användaren klickade på

* URL för speglingssida: URL:en till spegelsidan för e-postmeddelandet som skickades/öppnades/klickades/studsades

>[!NOTE]
>
>Utgångsperioden för e-postspegelsidan kan ändras på konfigurationsskärmen för motsvarande e-postkanalaktivitet för Campaign (se [Giltighetsperiodens parametrar](../../administration/using/configuring-email-channel.md#validity-period-parameters)).

>[!NOTE]
>
>Om du vill avanmäla dig återspeglas det i Campaign när ett avanmälningsattribut ändras i Dynamics 365, om du har valt konfigurationen Dynamics 365-till-Campaign eller dubbelriktad avanmälan och om du har det attributet korrekt mappat.

## Dataflöden {#data-flows}

### Ingång för kontakt och anpassad entitet

Nya och uppdaterade (och borttagna, om aktiverade) poster skickas från kontaktregistret i Dynamics 365 till profilregistret för Campaign.

Tabellmappningar kan konfigureras för att mappa Dynamics 365-registerattribut till Campaign-registerattribut. Tabellmappningarna kan ändras för att lägga till/ta bort attribut efter behov.

Dataflödets inledande körning är avsedd för överföring av alla mappade poster, inklusive sådana som markerats som &quot;inaktiva&quot;. kommer integreringen endast att bearbeta inkrementella uppdateringar. Undantaget till detta är om ett filter har konfigurerats; grundläggande, attributbaserade filtreringsregler kan konfigureras för att avgöra vilka poster som ska synkroniseras med Campaign.

Grundläggande ersättningsregler kan konfigureras för att ersätta ett attributvärde med ett annat värde (t.ex. &quot;green&quot; för &quot;#00FF00&quot;, &quot;F&quot; för 1 osv.).

Beroende på hur många poster du har kan du behöva använda din Campaign SFTP-lagring för den första dataöverföringen.  Se avsnittet&quot;Inledande dataöverföring&quot;.

Kampanjprofiltabellattributet externalId måste fyllas i med kontaktattributet contactId i Dynamics 365 för att kontaktingress ska fungera. Anpassade kampanjentiteter måste också fyllas i med ett unikt ID-attribut för Dynamics 365. Det här attributet kan dock lagras i alla anpassade enhetsattribut för Campaign (d.v.s. behöver inte vara externalId).

>[!NOTE]
>
>För inpressning av anpassade entiteter måste ändringsspårning vara aktiverat i Dynamics 365 för synkroniserade anpassade entiteter.

### Händelseflöde för e-postmarknadsföring

E-postmarknadsföringshändelser skickas från Campaign till Dynamics 365 för att visas i tidslinjevyn.

Marknadsföringshändelsetyper som stöds:
* Skicka - e-post har skickats till mottagare
* Öppna - e-post öppnad av mottagare
* Klicka - URL i e-post som mottagaren klickat på
* Studsa - e-post till mottagare fick en hård studsning

Följande händelseattribut visas i D365:
* Namn på marknadsföringskampanj
* Namn på e-postleverans
* Tidsstämpel
* URL för e-postspegelsida
* URL-klickad (endast klickningshändelser)

E-postmarknadsföringshändelser kan aktiveras/inaktiveras per typ (skicka, öppna, klicka, studsa) så att endast de händelsetyper du väljer skickas till Dynamics 365.

### Avanmäl utflöde

Värden för avanmälan (t.ex. blockeringslista) synkroniseras mellan systemen. har du följande alternativ att välja mellan när du registrerar dig:
* Dynamics 365 är en källa till sanning för avanmälan: Avanmälningsattribut synkroniseras i en riktning från Dynamics 365 till Campaign Standard
* Campaign Standard är källan till sanning för avanmälan: attribut för avanmälan synkroniseras i en riktning från Campaign Standard till Dynamics 365
* Dynamics 365 OCH Campaign Standard är båda sanningskällor: Avanmälningsattribut synkroniseras dubbelriktat mellan Campaign Standard och Dynamics 365

Om du har en separat process för att hantera avanmälningssynkronisering mellan systemen kan även integreringens avanmälningsdataflöde inaktiveras.

Flödesmappning för avanmälan ska anges av kunden eftersom affärskraven kan skilja sig mellan olika företag.  På Campaign-sidan kan endast OTB-avanmälningsattribut användas för avanmälningsmappning:
* blockeringslista
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

I Dynamics 365 har de flesta avanmälningsfält prefixet &quot;donot&quot;. Du kan dock även använda andra attribut för avanmälan om datatyperna är kompatibla.

### Inledande dataöverföring

Dynamics 365-register över 500 kB-poster måste exporteras till din Campaign SFTP-lagring för att kunna importeras via Campaign-arbetsflödet.

Den initiala dataöverföringen är en filbaserad dataöverföring som görs en gång. Efter dataöverföringen använder integreringen API:er för de inkrementella uppdateringarna.
