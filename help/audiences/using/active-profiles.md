---
solution: Campaign Standard
product: campaign
title: Aktiva profiler för kampanj
description: Lär dig hur du får tillgång till kundstatistik och aktiva profiler
feature: Profiler
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: f66a4e35e1f42a3d7630556d020ce76adfea5891
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 1%

---

# Aktiva profiler{#active-profiles}

Kampanjfunktionsadministratörer har åtkomst till **[!UICONTROL Customer metrics]**-rapporten från **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Den här rapporten genereras varje månad av det **[!UICONTROL Billing]** tekniska arbetsflödet och visar antalet **aktiva profiler**.

En &quot;profil&quot; är ett register över information som representerar en slutkund, potentiell kund eller lead. Profiler betraktas som **aktiva** om de har hämtats via en kampanjleverans under de senaste 12 månaderna via någon kanal.

Enligt ert kontrakt har var och en av era Campaign-instanser ett visst antal aktiva profiler. Se licensavtalet för information om antalet köpta aktiva profiler.

![](assets/audience_active_profiles_list.png)



* De profiler som uteslöts under leveransförberedelsen (t.ex. efter typologiregler eller karantänmekanism) beaktas inte.

* Mottagare av transaktionsmeddelanden räknas som aktiva profiler.

* En profil som har valts av flera leveranser räknas bara en gång.

* Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen.

Längst ned på sidan visas måldimensionerna med antalet profiler för varje. Mottagare av transaktionsmeddelanden är kopplade till dimensionen **Anonym**.

>[!NOTE]
>
>Som administratör kan du också övervaka antalet aktiva profiler som används på dina instanser direkt från Kontrollpanelen. Mer information finns i [dokumentationen till kontrollpanelen](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).

