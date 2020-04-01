---
title: Använda Microsoft Dynamics 365 med Campaign Standard-integrering
description: Lär dig hur du använder Microsoft Dynamics 365 med Campaign Standard-integrering
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bff3b8f8f58c491e4010d24132b0fa3e93c3a7ab

---


# Använda Microsoft Dynamics 365 med Campaign Standard-integrering

Det finns flera jobb som den här integreringen utför:

* **Kontaktsynkronisering**: Kontakter skickas från Dynamics 365 till Campaign (Obs! envägssynkronisering).
* **Synkronisering** av anpassad entitet: Anpassade entitetsposter skickas från Dynamics 365 till Campaign (envägssynkronisering).  Mer information finns på sidan om anpassade entiteter.
* **Händelsevisning**: Vissa e-postmarknadsföringshändelser skickas från Campaign till Dynamics 365. Se anmärkningen nedan.
* **Borttagning** av kontakt: Kampanjprofil läggs till i den sekretessrelaterade borttagningskön när motsvarande kontakt tas bort i Dynamics 365.
* **Synkronisering** av avanmälan: Avanmälningarna synkroniseras mellan Dynamics 365 och Campaign beroende på den konfiguration som kunden väljer under introduktionen (dvs. synkronisering mellan Dynamics 365 och Campaign, synkronisering mellan Campaign och Dynamics 365 eller dubbelriktad synkronisering).
* **enkel inloggning (SSO)**: Din integreringsinformation i Unifi kan nås direkt från Campaign med hjälp av din Adobe IMS-autentisering.

>[!NOTE]
>
>För **händelsevisning** hämtas maximalt 10 000 händelser varje gång utpressningsjobbet körs i Unifi.

## Adobe Campaign Standard - användarupplevelse

När en kontakt skapas ny eller ändras i Dynamics 365 synkroniseras den till Campaign när kontaktsynkroniseringen har körts.  Dessa kontakter visas på profilskärmen i Campaign och kan användas i marknadsföringskampanjer.  Se skärmen Profiler nedan.

![](assets/MSdynamicsACS-usage1.png)

När en kontakt tas bort i Dynamics 365 läggs motsvarande profil i Campaign till i kön för borttagning av sekretesstjänst på skärmen Sekretessbegäran i Campaign.  Mer information om hur du kör förfrågningar om borttagning av registrerade som krävs för att uppfylla gällande datasekretesslagstiftning i Campaign finns i Hur du verkställer juridiskt föreskrivna borttagningsförfrågningar i Adobe Campaign Standard.

![](assets/MSdynamicsACS-usage2.png)

Observera att om du har tvåstegsprocessen aktiverad på egenskapsskärmen måste du manuellt bekräfta borttagningen av varje post på sekretesskärmen innan de tas bort.  Se processskärmen i två steg nedan:

![](assets/MSdynamicsACS-usage3.png)

När ett attribut för avanmälan/svartlista ändras i Campaign återspeglas det i Dynamics 365 om du har valt konfigurationen Campaign-to-Dynamics 365 eller dubbelriktad avanmälan och om du har det attributet korrekt mappat.

Om du vill få tillgång till din integreringsinformation via enkel inloggning går du till menyn Campaign Navigation (Kampanjnavigering) och klickar på Administration > Microsoft Dynamics 365 Integration.

![](assets/sso_d365_admin_panel.png)

Den här sidan innehåller länkar till dokumentation om integreringen och riktlinjer för hur du använder funktionerna i enlighet med dina potentiella juridiska skyldigheter. Klicka på ikonen som automatiskt dirigerar och loggar in dig på din Unifi-instans där du kan hantera integreringsinformationen.

En video med den här funktionen visas i videon nedan.

>[!VIDEO](https://video.tv.adobe.com/v/29254)

>[!NOTE]
>
>Du måste skicka in en anmälan till Adobes kundtjänst (antingen direkt eller via din Adobe-kontakt) för att aktivera signeringsfunktionen i Campaign-instansen.

![](assets/sso_screen.png)

>[!NOTE]
>
>Ikonen för Microsoft Dynamics 365-integrering visas inte på adminpanelen.  Du (eller din Adobe-kontakt) måste skicka in en biljett för att den här funktionsflaggan ska vara aktiverad för Campaign-instansen.
>
>Unifi måste även aktivera användare för enkel inloggning innan de kan logga in via enkel inloggning från Campaign.

## Microsoft Dynamics 365 - användarupplevelse

För visning av händelser skickas följande e-postmarknadsföringshändelser från Campaign till Dynamics 365 och visas i tidslinjevyn i Dynamics 365 som anpassade aktiviteter:

* Skicka e-post för Adobe Campaign

* Adobe Campaign Email Open

* Adobe Campaign Email URL Click

* Adobe Campaign Email Bounce

Om du vill visa en kontakts tidslinje går du till din kontaktlista genom att klicka på Försäljningssida i listrutan Dynamics 365.  Klicka sedan på Kontakter på den vänstra menyraden och välj en kontakt.

>[!NOTE]
>
>Appen Adobe Campaign för Dynamics 365 i AppSource måste installeras i din Dynamics 365-instans för att du ska kunna visa dessa händelser.

Här nedan ser du en ögonblicksbild av kontaktskärmen för&quot;Dynamics-användare&quot;.  I tidslinjevyn kommer du att märka att Dynamics-användaren har fått ett e-postmeddelande som är kopplat till kampanjnamnet&quot;2019LoyaltyCamp&quot; och leveransnamnet&quot;DM190&quot;.  Dynamics-användaren öppnade e-postmeddelandet och klickade också på en URL i e-postmeddelandet. båda dessa åtgärder skapade händelser som också visas nedan.  Om du tittar till höger kommer du att se kortet för Relationship Assistant (RA); för närvarande innehåller det en uppgift att följa upp den klickade URL:en.

![](assets/MSdynamicsACS-usage4.png)

Nedan finns en stängning av tidslinjevyn för Dynamics-användare.

![](assets/MSdynamicsACS-usage5.png)

Nedan finns en närbild på RA-kortet (Relationship Assistant).  AppSource-appen innehåller ett arbetsflöde som söker efter en klickningshändelse för Adobe-e-post.  När den här händelsen inträffar skapas en uppgift och ett förfallodatum anges.  Detta gör att aktiviteten kan visas i RA-kortet, vilket ger den extra synlighet.  Det finns ett liknande arbetsflöde för Adobe Email Bounce-händelser, som lägger till en uppgift för att stämma av den ogiltiga e-postadressen.  Dessa arbetsflöden kan stängas av i lösningen.

![](assets/MSdynamicsACS-usage6.png)

Om du klickar på ämnet för sändningshändelsen visas ett formulär som liknar det nedan.  Formulären för öppnings- och studshändelser liknar varandra.

![](assets/mirror_page_url_send.png)

Formuläret för klickningshändelser för e-post-URL lägger till ett extra attribut för den URL som du klickade på:

![](assets/mirror_page_url_click.png)

Här följer en lista över attributen och en beskrivning:

* Ämne: Föremålet för evenemanget. bestående av kampanj-ID och leverans-ID för e-postleveransen

* Ägare: Programanvändaren som skapas i stegen efter etableringen

* Angående: Kontaktens namn

* Kampanjnamn: Kampanj-ID i Campaign Standard

* Leveransnamn: Leverans-ID i Campaign Standard

* Datum skickat/öppnat/klickat/studsat: Datum/tid när händelsen skapades

* Spårnings-URL: URL som användaren klickade på

* URL för speglingssida: URL:en till spegelsidan för e-postmeddelandet som skickades/öppnades/klickades/studsades

Du kan se en video med spegelsidans URL som används i videon nedan.

>[!VIDEO](https://video.tv.adobe.com/v/29253)

>[!NOTE]
>
>Om du vill avanmäla dig återspeglas det i Campaign när ett avanmälningsattribut ändras i Dynamics 365, om du har valt konfigurationen Dynamics 365-till-Campaign eller dubbelriktad avanmälan och om du har det attributet korrekt mappat.

**Relaterade ämnen**

* Konfigurera Campaign för Campaign/Dynamics 365-integrering
* Konfigurera Dynamics för Campaign/Dynamics 365-integrering
* Konfigurera Unifi för Campaign/Dynamics 365-integrering
* Lär dig mappa anpassade resurser och anpassade entiteter