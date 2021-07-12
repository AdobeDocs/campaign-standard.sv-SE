---
solution: Campaign Standard
product: campaign
title: Tekniska arbetsflöden
description: Tekniska arbetsflöden är färdiga arbetsflöden som är utformade för att hantera tekniska bakgrundsprocesser i Adobe Campaign och säkerställa att plattformen fungerar korrekt.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Instansinställningar
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 95%

---

# Tekniska arbetsflöden{#technical-workflows}

Tekniska arbetsflöden levereras med Adobe Campaign.  Tekniska arbetsflöden är operationer eller jobb som schemalagts för att utföras regelbundet på servern.

De gör att du kan utföra underhållsåtgärder på databasen, dra nytta av spårningsinformationen för leveranserna och uppdatera de preliminära jobben för leveranserna.

Funktionella administratörer har tillgång till tekniska arbetsflöden under menyn **[!UICONTROL Administration > Application settings > Workflows]**.

>[!NOTE]
>
>Som funktionell administratör kan du starta om eller pausa tekniska arbetsflöden och ändra deras egenskaper och struktur.

![](assets/technical_workflows.png)

## Förteckning över tekniska arbetsflöden {#list-of-technical-workflows}

Tekniska arbetsflöden används för att hantera självutlösande bakgrundsprocesser och tekniska processer i Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etikett</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B-tester</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> I det här arbetsflödet analyseras spårningsloggarna för varje variant.        I slutet av A/B-testet beräknas varianten som vunnit per automatik.        Som standard startas det varje dag.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Fakturering</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Det här arbetsflödet skickar systemaktivitetsrapporten till användaren för fakturering via e-post.        Som standard startas det automatiskt varje dag kl. 01:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Databasrensning</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Det här arbetsflödet är arbetsflödet för databasunderhåll. Det kör olika statistik och processer och tar bort föråldrade data från databasen enligt den konfiguration som har definierats. Som standard startas det automatiskt varje dag klockan 04:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prognos</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span><br /> </td> 
   <td> Detta arbetsflöde utför analysen av leveranser som lagras i den preliminära prognosen (skapandet av de preliminära loggarna).        Som standard startas det varje dag kl. 01:00. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importera en delad målgrupp</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Det här arbetsflödet synkroniserar målgruppsdata i Adobe Experience Cloud som importeras i Adobe Campaign.        Som standard startas det varje timme.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Dela rapporter direkt</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> Det här arbetsflödet startas direkt när en rapport är schemalagd att skickas.        Rapporten konverteras till en pdf-fil och skickas sedan i ett e-postmeddelande till målmottagarna.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Avstämning av KPI:er med Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> Det här arbetsflödet hämtar KPIer från rapporteringstjänsten en gång om dagen och sammanställer dem tillsammans med data från Adobe Analytics.        Sedan avrundas skillnaden vid behov.        Som standard startas det varje dag kl. 04.20.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Lokal arkivering i meddelandecentret</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> Det här arbetsflödet arkiverar realtidshändelser i en historisk tabell.        Som standard startas det varje timme.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Rapporteringsaggregat</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Det här arbetsflödet uppdaterar aggregaten som används i rapporterna.        Som standard startas det automatiskt kl. 02:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Dela KPI:er med Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> Det här arbetsflödet överför KPI-data var 15:e minut från Adobe Campaign Standard till Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Synkronisera med Launch</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Det här arbetsflödet synkroniserar de mobila egenskaperna i Adobe Launch som importerats i Adobe Campaign Standard.  Det startar var 15:e minut.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Återställning av spårningsloggar</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Det här arbetsflödet synkroniserar de mobila egenskaperna i Adobe Launch som importerats i Adobe Campaign Standard.  Det startar var 15:e minut.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Återställningsspårningsloggar</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> Det här arbetsflödet återställer förlorade spårningsloggar. Observera att det här tekniska arbetsflödet används i särskilda sammanhang och begränsas till enbart intern användning i Adobe. <br> Som standard startas det var 10:e minut.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatera leveransindikatorer</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Det här arbetsflödet uppdaterar leveransens KPI:er (Key Performance Indicator).  Som standard startas det varje timme.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatera händelsestatus</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Med det här arbetsflödet kan du tilldela en status till en händelse.  Följande händelsestatusar är tillgängliga:<br /> <strong>Väntande</strong>: Händelsen är köad.  Ingen meddelandemall har ännu tilldelats den.<br /> <span class="uicontrol">Väntande leverans</span> : Händelsen är köad. En meddelandemall har tilldelats den och bearbetas av leveransen.<br /> <strong>Skickat</strong>: Den här statusen kopieras från leveransloggarna.  Det betyder att leveransen skickats.<br /> <strong>Ignoreras av leveransen</strong>: Den här statusen kopieras från leveransloggarna.  Det betyder att leveransen ignorerats.<br /> <strong>Leveransen misslyckades</strong>: Den här statusen kopieras från leveransloggarna.  Det betyder att leveransen misslyckats.<br /> <span class="uicontrol">Händelsen beaktas</span> inte: Händelsen kunde inte länkas till en meddelandemall.  Händelsen kommer inte att bearbetas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uppdatering för leverans</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Med det här arbetsflödet kan du skapa en lista över regler för kvalifikation vid studsning samt en lista över domäner och MX på plattformen.  Det här arbetsflödet fungerar endast om HTTPS är öppet.  Som standard startas det automatiskt kl. 02:00.<br /> </td> 
  </tr> 
 </tbody> 
</table>
