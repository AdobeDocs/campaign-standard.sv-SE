---
title: Utlösa datainmatning via API:er
description: Lär dig hur du utlöser datainhämtning via API:er.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 5%

---


# Utlösa datainmatning via API:er {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector är för närvarande en betaversion som kan komma att uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

Med Adobe Campaign Standard kan du utlösa direkt inmatning av datamappningar via API:er och hämta status för dina önskemål om inmatning.

Den här sidan beskriver hur du aktiverar och hämtar inmatningsstatus för dina datamappningar. Global information om Campaign Standard-API:er finns i [det här avsnittet](../../api/using/get-started-apis.md).

## Förutsättningar {#prerequisites}

Innan du använder API:erna måste datamappningen först ha konfigurerats och publicerats i Campaign Standardens gränssnitt. Mer information finns i följande avsnitt:

* [Mappningsdefinition](../../developing/using/aep-mapping-definition.md)
* [Aktivera mappning](../../developing/using/aep-mapping-activation.md)

När datamappningen har skapats måste du stoppa den från att köras så att du kan utlösa den från API:erna när du vill. Följ dessa steg för att göra detta:

1. Gå till Campaign Standarden **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

1. Dubbelklicka på datamappningen för att öppna den och klicka sedan på **[!UICONTROL Stop]** knappen.

   ![](assets/aep_datamapping_stop.png)

1. Spara ändringarna

Körningen av datamappningen har stoppats. Du kan använda Campaign Standard-API:er för att utlösa den manuellt.

## Börja omedelbart inmatning av datamappning {#starting-immediate-ingestion}

Omedelbart intag av en XDM-mappning i Adobe Experience Platform utlöses av en POST-åtgärd:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>För att kunna köra anropet till API:t för inklistring av POSTER måste användaren ha en **SQL-funktionskörningsroll** , som en Campaign Standard-administratör kan ge genom att köra nedan JS-skript:
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

POSTEN returnerar information om status för skapad begäran:

* Begäran har skickats för XDM-mappningen:

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Begäran pågår redan för XDM-mappningen:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Begäran misslyckades eftersom XDM-mappningen inte har publicerats eller har stoppats:

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## Hämtar status för en begäran om hämtning {#retrieving-status}

Status för en begäran om att få tillgång kan hämtas med en GET-åtgärd och önskat ID för begäran i parametrarna:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
Detaljerad information om status för XDM-mappningsbegäran och relaterade jobb finns i Campaign Standardens gränssnitt på **[!UICONTROL Status of data export to platform]** menyn (se [Mappningsaktivering](../../developing/using/aep-mapping-activation.md)).

GETEN returnerar informationen nedan:

* **batchId**: detta fält fylls i endast om fel uppstår efter gruppbearbetning och överföring,
* **info**: XDM-mappnings-ID,
* **numRecords**: antalet poster som har importerats (endast framgångsstatus),
* **status**: status för importbegäran (lyckad/misslyckades/pågår)

Möjliga svar på GET-åtgärden är:

* Ingest-begäran lyckades:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* Ingest-begäran misslyckades med 0 inkapslade poster:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* Ingest request failed, with some record uploaded under a batch:

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* Ingest-begäran avbröts efter att vissa poster har importerats (detta kan inträffa i kraschscenarier):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* Pågående inmatningsbegäran (när begäran överförde data i en batch eller när batchen förbereds för begäran):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
