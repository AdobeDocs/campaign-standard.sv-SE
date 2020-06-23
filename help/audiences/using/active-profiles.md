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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Aktiva profiler{#active-profiles}

Adobe Campaign tillhandahåller en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen. Endast administratörer har åtkomst till den här rapporten, under **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

Det **[!UICONTROL Billing]** tekniska arbetsflödet genererar varje månad en rapport som innehåller antalet aktiva profiler som var målinriktade under den senaste 12-månaders rullande perioden.

De profiler som uteslöts under färdigställandet (typologiregler, karantänregler) beaktas inte. En profil som har valts av flera leveranser räknas bara en gång. Längst ned i rapporten finns en lista med aktiva profiler för varje måldimension.

![](assets/audience_active_profiles2.png)

Om du är värd för AWS och använder Campaign Standard från build 10368 kan du även övervaka antalet aktiva profiler som används på dina instanser direkt från Kontrollpanelen. Mer information finns i dokumentationen [för](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)Kontrollpanelen.
