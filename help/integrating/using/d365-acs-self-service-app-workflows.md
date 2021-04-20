---
title: Arbetsflöden för integreringsapplikationer
description: Integreringsarbetsflöden för kampanjer och Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---


# Kampanj - Integreringsarbetsflöden för Microsoft Dynamics 365

På sidan **[!UICONTROL Workflows]** visas de tekniska arbetsflödena och deras status.

Integreringsprogrammet har tre arbetsflöden:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 till Campaign**
* Skicka *kontakter* från Microsoft Dynamics 365 till Adobe Campaign
* *Anpassade entiteter*: Hämta in anpassade tabeller från Microsoft Dynamics 365 till Adobe Campaign. [Läs mer](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Detta kallas även **Ingress** (som hänvisar till inmatning av data från Microsoft Dynamics 365 till Adobe Campaign)

**Kampanj för Microsoft Dynamics 365**
* E-postmarknadsföringsevenemang från Adobe Campaign Standard skickas till Dynamics 365 (skicka via e-post, öppna, klicka, studsa). [Läs mer](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Detta kallas även **Egress** (refererar till utegångsdata från Adobe Campaign till Microsoft Dynamics 365)

**Opt-In/Out**

Opt-out-status (t.ex. blockeringslista) kan synkroniseras från Microsoft Dynamics 365 till Adobe Campaign eller från Adobe Campaign till Microsoft Dynamics 365. Data kan också synkroniseras dubbelriktat (dvs. dataflöden i båda riktningarna). [Läs mer](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Vi rekommenderar att du avbryter arbetsflödet för **Microsoft Dynamics 365 till Campaign** innan du publicerar ändringar i antingen Adobe Campaign Standard eller Microsoft Dynamics 365. Dessa ändringar omfattar uppdateringar av resurser/entiteter (och deras associerade fält), länkar, identifierarkolumner osv. som för närvarande används av integreringen. Om du inte gör det kan det leda till dataförlust och/eller att arbetsflödet oväntat stoppas.

## Arbetsflödets eftersläpning

Integreringsprogrammet läser först in data och skriver sedan data till målet. Kolumnen **[!UICONTROL Backlog]** anger antalet poster som har placerats i kö och väntar på att skrivas. Detta värde förväntas växa när du har en stor mängd data att bearbeta (t.ex. kör integreringen för första gången, du spelar upp data osv.).

>[!NOTE]
>Om dina Microsoft Dynamics 365- och/eller Campaign-poster inte uppdateras bör du först kontrollera om det finns ett stort antal poster som väntar på att skrivas till målet.


## Arbetsflödesstatus {#workflow-status}

Kolumnen **[!UICONTROL Status]** anger statusen för bakgrundsprocesserna som är associerade med arbetsflödet. Möjliga värden är:

* **KÖRS**: Processen körs och dina data bör synkroniseras.
* **STOPPAD**: Processen körs inte just nu, så du bör inte förvänta dig att dina data ska synkroniseras.
* **STARTAR**: Du har begärt att arbetsflödesprocesserna ska startas. Programmet har ännu inte börjat synkronisera data som är associerade med arbetsflödet, men du kan förvänta dig det efter några minuter (när det sedan visar statusen **RUNNING**)
* **MISSLYCKADES**: Arbetsflödesprocesserna kördes men fel uppstod och de kunde inte återskapas från dessa.

## Tillgängliga åtgärder

Möjliga åtgärder listas nedan.

* **Redigera**: Om du klickar på pennikonen skickas du till en annan sida där du kan uppdatera arbetsflödet. Kom ihåg att alla ändringar du gör INTE börjar gälla förrän du avbryter arbetsflödet och sedan startar om det.

* **Start**: En Start-knapp begär att ett stoppat arbetsflöde ska startas. Den här knappen visas endast när processerna som är kopplade till arbetsflödet har stoppats. Processerna ändras först till&quot;STARTING&quot; och sedan till&quot;RUNNING&quot;. De data som är associerade med arbetsflödet kommer inte att börja synkroniseras förrän arbetsflödet är i tillståndet &quot;RUNNING&quot;.

   Startknappen är en växlingsknapp. Om arbetsflödesprocesserna redan har startats ändras knappen till en **Stopp**-knapp.

* **Stopp**: En  **** Stopbutton begär att ett arbetsflöde som körs stoppas. Den här knappen visas endast när processerna som är kopplade till arbetsflödet körs.

När du redigerar ett arbetsflöde inkluderas dina uppdateringar INTE direkt i de processer som körs, förrän du avbryter arbetsflödet och sedan klickar på knappen **Start**. Därefter ingår uppdateringarna i de processer som körs (när processen återgår till tillståndet **RUNNING**).

En varningsindikation har lagts till i knappen **Stoppa** för att du ska få veta när (a) har uppdaterat arbetsflödet, men (b) inte har utfört stopp/start för det här arbetsflödet.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
