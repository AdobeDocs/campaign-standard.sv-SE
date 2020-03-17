---
title: Tekniska arbetsflöden
description: Tekniska arbetsflöden är färdiga arbetsflöden som är utformade för att hantera tekniska bakgrundsprocesser i Adobe Campaign och säkerställa att plattformen fungerar korrekt.
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Tekniska arbetsflöden{#technical-workflows}

Tekniska arbetsflöden levereras direkt med Adobe Campaign. Tekniska arbetsflöden är operationer eller jobb som schemalagts att utföras regelbundet på servern.

De gör att du kan utföra underhållsåtgärder på databasen, dra nytta av spårningsinformationen i leveranserna och uppdatera de preliminära jobben för leveranserna.

Funktionella administratörer har tillgång till tekniska arbetsflöden på **[!UICONTROL Administration > Application settings > Workflows]** menyn.

>[!NOTE]
>
>Som funktionell administratör kan du starta om eller pausa tekniska arbetsflöden och ändra deras egenskaper och struktur.

![](assets/technical_workflows.png)

## Förteckning över tekniska arbetsflöden {#list-of-technical-workflows}

Tekniska arbetsflöden används för att hantera självutlösande bakgrunds- och tekniska processer i Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etikett</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B-testning</span><br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> I det här arbetsflödet analyseras spårningsloggarna för varje variant. I slutet av A/B-testperioden beräknas den vinnande varianten automatiskt. Som standard startas det varje dag.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Fakturering</span><br /> </td> 
   <td> <span class="uicontrol">fakturering</span><br /> </td> 
   <td> Det här arbetsflödet skickar systemaktivitetsrapporten till användaren för fakturering via e-post. Som standard startas den automatiskt varje dag kl. 1:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Databasrensning</span><br /> </td> 
   <td> <span class="uicontrol">rensa</span><br /> </td> 
   <td> Det här arbetsflödet är arbetsflödet för databasunderhåll: den kör olika statistik och processer och tar bort föråldrade data från databasen enligt den konfiguration som har definierats. Som standard startas den automatiskt varje dag klockan 4.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prognos</span><br /> </td> 
   <td> <span class="uicontrol">prognos</span><br /> </td> 
   <td> Detta arbetsflöde utför analysen av leveranser som lagras i den preliminära prognosen (skapandet av de preliminära loggarna). Som standard startas den varje dag kl. 1:00. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importera en delad målgrupp</span><br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> Det här arbetsflödet synkroniserar Adobe Experience Cloud-målgruppsdata som importeras i Adobe Campaign. Som standard startas den varje timme.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Dela</span> rapporter direkt <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> Det här arbetsflödet startas så snart en rapport är schemalagd att skickas. Rapporten konverteras till en pdf-fil och skickas sedan i ett e-postmeddelande till målmottagarna.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Avstämning av nyckeltal med Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiAvstämning</span><br /> </td> 
   <td> Det här arbetsflödet hämtar nyckeltal från rapporteringstjänsten en gång om dagen och förenar dem med data från Adobe Analytics. Sedan pushas skillnaden vid behov. Som standard startas den varje dag kl. 4.20.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Hantera NMAC-avanmälan</span><br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span><br /> </td> 
   <td> Det här arbetsflödet uppdaterar avbeställningar av meddelanden på mobila enheter. Som standard startas det var sjätte timme mellan 1:00 och 24:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Lokal arkivering</span> i meddelandecentret <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> Det här arbetsflödet arkiverar realtidshändelser i en historisk tabell. Som standard startas den varje timme.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Rapportera aggregat</span><br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span><br /> </td> 
   <td> Det här arbetsflödet uppdaterar aggregaten som används i rapporterna. Som standard startas den automatiskt vid 2:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Dela nyckeltal med Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> Det här arbetsflödet överför KPI-data var 15:e minut från Adobe Campaign Standard till Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatera leveranskörning</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> Det här arbetsflödet uppdaterar leveransspårningen. Som standard startas den var 10:e minut.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatera leveransindikatorer</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> Det här arbetsflödet uppdaterar leveransens KPI:er (Key Performance Indicator). Som standard startas den varje timme.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatera händelsestatus</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> Med det här arbetsflödet kan du tilldela en status till en händelse. Följande händelselägen är tillgängliga:<br /> <strong>Väntande</strong>: Händelsen finns i en kö. Ingen meddelandemall har tilldelats den ännu.<br /> <span class="uicontrol">Väntande leverans</span> : Händelsen finns i kön, en meddelandemall har tilldelats den och bearbetas av leveransen.<br /> <strong>Skickat</strong>: Den här statusen kopieras från leveransloggarna. Det betyder att leveransen skickades.<br /> <strong>Ignoreras av leveransen</strong>: Den här statusen kopieras från leveransloggarna. Det betyder att leveransen ignorerades.<br /> <strong>Leveransen misslyckades</strong>: Den här statusen kopieras från leveransloggarna. Det betyder att leveransen misslyckades.<br /> Händelsen <span class="uicontrol">beaktas</span> inte: Händelsen kunde inte länkas till en meddelandemall. Händelsen kommer inte att bearbetas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatering för leveransbarhet</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span><br /> </td> 
   <td> Med det här arbetsflödet kan du skapa en lista över regler för studsregelkvalificering samt en lista över domäner och MX på plattformen. Det här arbetsflödet fungerar bara om HTTPS är öppet. Som standard startas den automatiskt vid 2:00.<br /> </td> 
  </tr> 
 </tbody> 
</table>

