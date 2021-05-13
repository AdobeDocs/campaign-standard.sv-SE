---
solution: Campaign Standard
product: campaign
title: Aktiva profiler för kampanj
description: Lär dig hur du får tillgång till kundstatistik och aktiva profiler
feature: Profiler
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 1%

---

# Kundstatistik {#customer-metrics}

Kampanjfunktionsadministratörer har åtkomst till **[!UICONTROL Customer metrics]**-rapporten från **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

Den här rapporten innehåller:

* Experience Cloud ID
* IMS-organisations-ID
* antalet **aktiva profiler**
* listan med måldimensioner som är tillgängliga i instansen

Den här rapporten genereras varje månad av det tekniska arbetsflödet **[!UICONTROL Billing]**.

## Aktiva profiler{#active-profiles}

Enligt ert kontrakt har var och en av era Campaign-instanser ett visst antal aktiva profiler. Se licensavtalet för information om antalet köpta aktiva profiler.

>[!NOTE]
>
>Som administratör kan du också övervaka antalet aktiva profiler som används på dina instanser direkt från Kontrollpanelen. Mer information finns i [dokumentationen till kontrollpanelen](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).


En &quot;profil&quot; är ett register över information som representerar en slutkund, potentiell kund eller lead. Profiler betraktas som **aktiva** om de har hämtats via en kampanjleverans under de senaste 12 månaderna via någon kanal. De profiler som uteslöts under leveransförberedelsen (t.ex. efter typologiregler eller karantänmekanism) beaktas inte. En profil som har valts av flera leveranser räknas bara en gång. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen.

![](assets/audience_active_profiles2.png)

Längst ned i rapporten finns en lista med aktiva profiler för varje måldimension. Här visas antalet aktiva profiler som var målinriktade under den senaste 12-månaders rullande perioden.

* Källan **[!UICONTROL NmsRecipient]** innehåller alla profiler som kontaktats med hjälp av information från deras Campaign Standard-profil.

* Kunderna **[!UICONTROL anonymous]**-källan visar antalet profiler som var riktade med enbart en viss informationsdel (e-postadress, telefonnummer), utan relation till deras Campaign-profil.
