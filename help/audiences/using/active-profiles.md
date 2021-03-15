---
solution: Campaign Standard
product: campaign
title: Aktiva profiler
description: Ni kan få tillgång till en dedikerad rapport om kundstatistik och visualisera aktiva profiler i er Campaign-databas.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiler
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Aktiva profiler{#active-profiles}

Adobe Campaign tillhandahåller en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen. Endast administratörer har åtkomst till den här rapporten, under **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Om du är värd för AWS och använder Campaign Standard från build 10368 kan du även övervaka antalet aktiva profiler som används på dina instanser direkt från Kontrollpanelen. Mer information finns i [dokumentationen till kontrollpanelen](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Observera att mätvärden för aktiva profiler endast är tillgängliga och relevanta för **marknadsinstanser**. Det är varken tillämpligt eller tillgängligt för körningsinstanser, vilket innebär MID-instanser (mellankällning) och RT-instanser (Message Center/Real-time Messaging).


De profiler som uteslöts under färdigställande av leveransen (typologiregler, karantän, kontrollgrupper) beaktas inte. En profil som har valts av flera leveranser räknas bara en gång. Längst ned i rapporten finns en lista med aktiva profiler för varje måldimension.

Den här rapporten genereras varje månad av det tekniska arbetsflödet **[!UICONTROL Billing]**. Den innehåller antalet aktiva profiler som var målinriktade under den senaste 12-månaders rullande perioden.

Observera att de profiler som uteslöts under leveransförberedelsen (typologiregler, karantän) inte beaktas. Dessutom kommer en profil som är inriktad på flera leveranser endast att räknas en gång.

![](assets/audience_active_profiles2.png)

Längst ned i rapporten finns en lista över aktiva profiler som bearbetats av faktureringsarbetsflödet:

* Källan **[!UICONTROL NmsRecipient]** innehåller alla kunder som kontaktats med hjälp av information från deras Campaign Standard-profil.

* Å andra sidan kommer kunder som var inriktade på att använda en viss informationsdel (e-postadress, telefonnummer), utan någon relation till sin Campaign-profil, att hamna under källan **[!UICONTROL anonymous]**.
