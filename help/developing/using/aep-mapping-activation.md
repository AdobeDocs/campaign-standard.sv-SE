---
title: Aktivera mappning
description: Lär dig hur du aktiverar din datamappning
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c2ed4b3c85ceef3b604a8f68d924c7e5d9fad900

---


# Aktivera mappning {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector är för närvarande en betaversion som kan komma att uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobes kundtjänst om du vill ha tillgång till tjänsten.

När mappningsdefinitionen är klar kan du publicera mappningen. Efter distributionssteget startas datareplikeringen mellan Campaign Standard och Adobe Experience Platform automatiskt. Du kan när som helst stoppa replikeringen genom att klicka på **[!UICONTROL Stop]** knappen.

Beroende på dina mappningsändringar kan du välja att skicka om alla dina poster till Adobe Experience Platform.

![](assets/aep_publishmapping.png)

På distributionspanelen kommer du åt publiceringsloggen och exportloggarna.

![](assets/aep_publog.png)

På fliken **[!UICONTROL Export jobs]** kan du övervaka exportjobbet för den publicerade mappningen.

![](assets/aep_jobstatus.png)

Om du vill övervaka alla dataexportjobb går du till **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

![](assets/aep_statusmapping.png)

Status för dataöverföringsjobb:

* **[!UICONTROL Created]**: Ett datainmatningsjobb skapas och datainmatning pågår.
* **[!UICONTROL Failed]**: Ett datainmatningsjobb misslyckades. I fältet reason beskrivs orsaken till felet. Misslyckandet kan vara övergående eller permanent. Om det uppstår tillfälliga fel skapas ett nytt intag efter ett konfigurerat intervall. Som ett första steg i felsökningen kan användaren kontrollera felets orsaksfält. Om anledningen omdirigerar en användare till Adobe Experience Platform-gränssnittet kan användaren logga in på Adobe Experience Platform och kontrollera batchstatusen i datauppsättningen för att fastställa den exakta felorsaken.
* **[!UICONTROL Uploaded]**: En batch skapas först i Adobe Experience Platform och data importeras sedan till gruppen. I fältet för batch-ID visas batch-ID för batchen i Adobe Experience Platform. Adobe Experience Platform utför också en eftervalidering av gruppen. Batchen markeras först som överförd tills Adobe Experience Platform slutför steget efter valideringen. Ett jobb fortsätter att avfråga Adobe Experience Platform om batchens status efter överföring. En batch kan antingen köras i läget Misslyckades eller i läget Slutfört efter validering i Adobe Experience Platform.
* **[!UICONTROL Success]**: När en batch har överförts till Adobe Experience Platform kontrolleras jobbets status (efter validering på plattform) efter ett konfigurerat intervall. Statusen&quot;Success&quot; har identifierat att data har importerats i Adobe Experience Platform.
