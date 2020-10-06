---
title: Skapa och uppdatera profilinformation baserat på mobilprogramdata
description: Lär dig hur du skapar och uppdaterar profilinformation baserat på data från mobilappar.
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Skapa och uppdatera profilinformation baserat på mobilprogramdata

## Översikt

På den här sidan beskrivs stegen för att utveckla ett arbetsflöde som skapar/uppdaterar profildata efter att ett mobilprogram har skickat samla in PII-data på schemalagd basis.

* **PII** står för&quot;personligt identifierbar information&quot;. Det kan vara vilken data som helst, inklusive information som inte visas i profiltabellen från er Campaign-databas, till exempel Analytics for Mobile [Points of Interest](../../integrating/using/about-campaign-points-of-interest-data-integration.md). PII definieras av Mobile App Developer, vanligtvis med en marknadsförare.
* **Samla in PII** är en HTTP-POST-åtgärd till ett Rest API i Adobe Campaign Standard från en mobilapp.

Målet med det här användningsexemplet är att skapa eller uppdatera en Campaign Standard-profil om de PII-data som returneras av ett mobilprogram innehåller profilrelaterade data.

## Förhandskrav

Det finns flera konfigurationssteg som ska utföras för att aktivera push-meddelanden i Campaign Standarden, innan profiler kan skapas eller uppdateras baserat på prenumerationsdata för mobilappar:

1. [Skapa ett mobilprogram](../../administration/using/configuring-a-mobile-application.md)
1. [Integrera Adobe Mobile SDK med mobilapplikationen](https://helpx.adobe.com/se/campaign/kb/integrate-mobile-sdk.html).
1. [Konfigurera Adobe Campaign för att skicka push-meddelanden](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdkv4.html).

## Steg 1 - Utöka profilresursen för push-meddelanden/prenumerationer

Om du vill kunna skapa eller uppdatera profilresursen med PII-data måste du först utöka profilresursen med de önskade fälten. Så här gör du:

* Identifiera de PII-fält som skickas av mobilprogrammet.
* Identifiera fältet som ska användas för avstämning för att associera PII-data med profildata.

![](assets/update_profile1.png)

I det här exemplet återspeglar **[!UICONTROL Fields]** avsnittet de PII-data som skickas av mobilprogrammet. Avsnittet **[!UICONTROL Link to profiles]** anger det fält som används för att associera PII med profildata, där **cusEmail** mappas till **@email**.

Mappningen för profildata när du utökar **[!UICONTROL Subscriptions to an Application]** resursen är SKRIVSKYDDAD. Det används för avstämning. Profilen måste registreras i systemet med de data som krävs för att stämma av profilen med PII-data. I det här fallet måste en e-postadress för profilen matcha ett e-postmeddelande från Hämta PII för att avstämningen ska ske:

* Samla in PII tas emot från en mobilapp för en användare där förnamnet är &quot;Jane, efternamnet är &quot;Doe&quot; och e-postadressen är janedoe@doe.com.
* Profildata måste finnas separat (data måste till exempel anges manuellt eller redan komma från en annan resurs) där profilens e-postadress är janedoe@doe.com.

**Relaterade ämnen:**

* [Utöka prenumerationerna till en programresurs](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Skapa eller utöka en befintlig resurs](../../developing/using/key-steps-to-add-a-resource.md).

## Steg 2 - Skapa arbetsflödet

Om du använder ett arbetsflöde i Campaign Standard kan en administratör unikt identifiera och synkronisera data mellan AppSubscription-data (prenumerantdata) och Profil- eller mottagardata. En arbetsflödesbaserad uppdatering synkroniserar inte profildata i realtid, men bör inte orsaka onödiga databaslås eller overhead.

De viktigaste stegen för att skapa arbetsflödet är:

1. Använd en **[!UICONTROL Query]** aktivitet eller **[!UICONTROL Incremental query]** aktivitet för att få en lista över de senaste prenumerationerna.
1. Använd en **[!UICONTROL Reconciliation]** aktivitet för att mappa PII-data till profilen.
1. Lägg till en verifieringsprocess.
1. Använd en **[!UICONTROL Update data]** för att uppdatera eller skapa profilen med PII-data.

Följande krav antas i det här arbetsflödet:

* Alla/alla fält som har utökats bör vara tillgängliga för att skapa/uppdatera profiltabellen.
* Profiltabellen kan utökas till stöd för fält som inte stöds internt (till exempel T-Shirt Size).
* Alla fält från AppSubscription-tabellen som är tomma ska inte uppdateras i profiltabellen.
* Alla poster som har uppdaterats i tabellen AppSubscription ska inkluderas i nästa körning av arbetsflödet.

Om du vill skapa arbetsflödet drar och släpper du följande aktiviteter på arbetsytan och länkar ihop dem: **[!UICONTROL Start]**, **[!UICONTROL Scheduler]**, **[!UICONTROL Incremental query]**, **[!UICONTROL Update data]**.

![](assets/update_profile0.png)

Följ sedan stegen nedan för att konfigurera varje aktivitet.

### Konfigurera **[!UICONTROL Scheduler]** aktiviteten

På **[!UICONTROL General]** fliken ställer du in **[!UICONTROL Execution frequency]** (till exempel &quot;Dagligen&quot;), **[!UICONTROL Time]** (till exempel &quot;1:00:00 AM&quot;) och **[!UICONTROL Start]** (till exempel Dagens datum).

![](assets/update_profile2.png)

### Konfigurera **[!UICONTROL Incremental query]** aktiviteten.

1. Klicka på **[!UICONTROL Properties]** ikonen för **[!UICONTROL Select an element]** fältet på **[!UICONTROL Resource]** fliken och markera sedan **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elementet.

   ![](assets/update_profile3.png)

1. Dra **[!UICONTROL Target]** filtret på **[!UICONTROL Mobile application]** fliken och välj sedan ett mobilprogramsnamn.

   ![](assets/update_profile4.png)

1. Markera på **[!UICONTROL Processed data]** fliken **[!UICONTROL Use a date field]** och lägg sedan till **[!UICONTROL Last modified (lastModified)]** fältet som **[!UICONTROL Path to the date field]**.

   ![](assets/update_profile5.png)

### Konfigurera **[!UICONTROL Update data]** aktiviteten.

1. Kontrollera att **[!UICONTROL Identification]** fältet är inställt på &quot;Profiler (profil)&quot; på fliken **[!UICONTROL Dimension to update]** och klicka sedan på **[!UICONTROL Create element]** knappen för att lägga till ett fält som ett avstämningsvillkor.

   ![](assets/update_profile_createelement.png)

1. I **[!UICONTROL Source]** fältet väljer du ett fält från tabellen appSubscriptionRcp som ett avstämningsfält. Det kan vara profilens e-postadress, crmId, marketingCloudId osv. I det här exemplet använder vi fältet&quot;Email (cusEmail)&quot;.

1. I **[!UICONTROL Destination]** fältet väljer du ett fält i profiltabellen för att stämma av data från tabellen appSubscriptionRcp. Det kan vara profilens e-postadress eller ett utökat fält som crmId, marketingCloudId osv. I det här exemplet måste vi markera fältet&quot;E-post (e-post)&quot; för att mappa det med fältet&quot;E-post (cusEmail)&quot; från tabellen appSubscriptionRcp.

   ![](assets/update_profile7.png)

1. Klicka på **[!UICONTROL Fields to update]** knappen på **[!UICONTROL Create element]** fliken och mappa sedan fälten som kommer från tabellen appSubscriptionRcp (**[!UICONTROL Source]** fält) med fälten som du vill uppdatera i profiltabellen (**[!UICONTROL Destination]** fältet).

1. Lägg till ett uttryck i **[!UICONTROL Enabled if]** fältet för att se till att motsvarande fält i profiltabellen bara uppdateras om källfältet innehåller ett värde. Det gör du genom att markera fältet i listan och sedan lägga till &quot;!=&#39;&#39;&quot; (om källfältet är `[target/@cusEmail]` i uttrycksredigeraren måste du skriva `[target/@cusEmail] != ''"`).

   ![](assets/update_profile8.png)

>[!NOTE]
>
>I det här fallet utför arbetsflödet en UPSERT, men eftersom det är baserat på en **[!UICONTROL Incremental query]** data infogas det bara. Om du ändrar frågan kan det påverka vilka data som infogas eller uppdateras.
>Inställningarna på fliken Fält som ska uppdateras avgör dessutom vilka fält som infogas eller uppdateras under specifika förhållanden. Dessa inställningar kan vara unika för varje program eller kund.
>Var försiktig när du konfigurerar de här inställningarna eftersom det kan få oönskade konsekvenser, eftersom uppdatering av poster i profilen baserat på appSubscriptionRcp-data kan ändra användarnas personliga information utan validering.

När alla fält som ska infogas/uppdateras i profilen har lagts till klickar du på **[!UICONTROL Confirm]**.

![](assets/update_profile9.png)

Spara arbetsflödet och klicka sedan för **[!UICONTROL Start]** att köra arbetsflödet.

![](assets/update_profile10.png)
