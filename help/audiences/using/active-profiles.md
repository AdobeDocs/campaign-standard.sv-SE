---
title: Aktiva profiler
description: Ni kan få tillgång till en dedikerad rapport om kundstatistik och visualisera aktiva profiler i er Campaign-databas.
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---


# Aktiva profiler{#active-profiles}

Adobe Campaign tillhandahåller en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen. Endast administratörer har åtkomst till den här rapporten, under **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Om du är värd för AWS och använder Campaign Standard från build 10368 kan du även övervaka antalet aktiva profiler som används på dina instanser direkt från Kontrollpanelen. For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Observera att mätvärden för aktiva profiler endast är tillgängliga och relevanta för **marknadsinstanser** . Det är varken tillämpligt eller tillgängligt för körningsinstanser, vilket innebär MID-instanser (mellankällning) och RT-instanser (Message Center/Real-time Messaging).


De profiler som uteslöts under färdigställande av leveransen (typologiregler, karantän, kontrollgrupper) beaktas inte. En profil som har valts av flera leveranser räknas bara en gång. Längst ned i rapporten finns en lista med aktiva profiler för varje måldimension.

Den här rapporten genereras varje månad av det **[!UICONTROL Billing]** tekniska arbetsflödet. Den innehåller antalet aktiva profiler som var målinriktade under den senaste 12-månaders rullande perioden.

Observera att de profiler som uteslöts under leveransförberedelsen (typologiregler, karantän) inte beaktas. Dessutom kommer en profil som är inriktad på flera leveranser endast att räknas en gång.

![](assets/audience_active_profiles2.png)

Längst ned i rapporten finns en lista över aktiva profiler som bearbetats av faktureringsarbetsflödet:

* I **[!UICONTROL NmsRecipient]** källan finns alla kunder som kontaktats med hjälp av information från deras Campaign Standard-profil.

* Å andra sidan kommer kunder som var inriktade på att enbart använda en viss informationsdel (e-postadress, telefonnummer), utan någon relation till sin Campaign-profil, att hamna under **[!UICONTROL anonymous]** källan.
