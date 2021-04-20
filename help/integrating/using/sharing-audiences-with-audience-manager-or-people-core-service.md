---
solution: Campaign Standard
product: campaign
title: Dela målgrupper med Audience Manager eller People Core Service
description: Lär dig hur du importerar eller exporterar målgrupper inom olika Adobe Experience Cloud-lösningar.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 2%

---


# Dela målgrupper med Audience Manager eller People Core Service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importera en målgrupp {#importing-an-audience}

Integrering med Bastjänst för människor gör det möjligt att direkt importera en målgrupp till Adobe Campaign via ett tekniskt arbetsflöde som berikar databasen. Mer information om målgruppsdelning i personbastjänsten finns i denna [dokumentation](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

Import av målgrupper/segment från personbastjänsten i Adobe Campaign kan endast utföras från **[!UICONTROL Audiences]**-menyn av användare som är anslutna via IMS (autentisering via Adobe ID).

1. Gå till menyn **[!UICONTROL Audiences]**.
1. I åtgärdsfältet väljer du **[!UICONTROL Create]** som ska visas på skärmen för att skapa en målgrupp.
1. Ange etiketten för den nya målgruppen.
1. Ställ in målgruppen **[!UICONTROL Type]** till **[!UICONTROL Experience Cloud]** för att ange att målgruppen som skapas är en målgrupp som importerats från personbastjänsten.
1. I fältet **[!UICONTROL Name of the shared audience]** väljer du den målgrupp som ska importeras. Endast segment kan importeras. Detaljerade data som nyckelvärdepar, egenskaper och regler stöds inte.

   ![](assets/aam_import_audience.png)

1. Markera motsvarande **[!UICONTROL Shared Data Source]**.

   Om den valda datakällan är konfigurerad att använda en krypteringsalgoritm, finns det ytterligare ett alternativ som ger dig möjlighet att **[!UICONTROL Force reconciliation with a profile]**. Markera det här alternativet om fältet **[!UICONTROL Channel]** i datakällan är inställt på E-post eller Mobil (SMS) och om du vill utnyttja profildata.

   Om du inte väljer **[!UICONTROL Force reconciliation with a profile]** och om **[!UICONTROL Channel]** är inställt på E-post eller Mobil (SMS) i AMC-datakällan dekrypteras alla krypterade deklarerade ID:n. En målgrupp av typen **Arkiv** med en lista över alla e-postadresser/mobiltelefonnummer skapas/uppdateras. På så sätt förloras ingen e-postadress/inget mobiltelefonnummer när en delad målgrupp importeras via den här integreringen, även om profilen inte finns i Campaign. Observera att den här typen av målgrupper inte kan användas direkt eftersom de måste förenas manuellt med hjälp av arbetsflöden.

1. Bekräfta för att skapa målgruppen.

   Publiken importeras sedan via ett tekniskt arbetsflöde. Den består av poster där ID:t (&quot;besökar-ID&quot; eller&quot;Deklarerat ID&quot;) kunde förenas med profildimensionen. ID:n från People core service segments som inte känns igen av Adobe Campaign importeras inte.

Din målgrupp importeras nu i din Adobe Campaign-databas. Det tar 24-36 timmar att synkronisera importprocessen när segment importeras direkt från personbastjänsten eller Audience Manager. Efter den här perioden kan du hitta och använda din nya målgrupp i Adobe Campaign.

>[!NOTE]
>
>Om du importerar målgrupper från Adobe Analytics till Adobe Campaign måste dessa målgrupper först delas i People Core Service eller Audience Manager. Den här processen tar 12-24 timmar, vilket måste läggas till i synkroniseringen av 24-36 timmar med Campaign. I det specifika fallet kan tidsramen för målgruppsdelning vara upp till 60 timmar. Mer information om Adobe Analytics målgruppsdelning i tjänsten People Core och Audience Manager finns i denna [dokumentation](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

## Exportera en målgrupp {#exporting-an-audience}

En målgrupp kan exporteras från Adobe Campaign till Audience Manager eller People core service med hjälp av ett arbetsflöde och aktiviteten **[!UICONTROL Save audience]**.

Den kan utföras i ett nytt arbetsflöde och endast av användare som är anslutna via IMS (autentisering via Adobe ID).

1. Skapa ett nytt arbetsflöde från ett program, en kampanj eller listan över marknadsföringsaktiviteter.
1. Använd de olika aktiviteterna för att skapa en uppsättning profiler.
1. När du har skapat målet drar och släpper du en **[!UICONTROL Save audience]**-aktivitet i arbetsflödet och öppnar den.
1. Välj **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Ange målgruppen med hjälp av fältet **[!UICONTROL Shared audience]**. I det fönster som öppnas kan du välja om du vill välja en befintlig målgrupp eller skapa en ny:

   * Om du väljer en befintlig målgrupp läggs endast de nya posterna till i målgruppen.
   * Om du vill exportera din profillista till en ny målgrupp fyller du i fältet **[!UICONTROL Segment name]** och klickar sedan på **[!UICONTROL Create]** innan du väljer den nya målgruppen.

   ![](assets/aam_save_audience_segment_picker.png)

   För att posterna ska kunna stämmas av och bytas ut måste de ha ett Adobe Experience Cloud-id (Visitor-ID eller Deklarerat ID). Ej avstämda poster ignoreras vid import och export av målgrupper.

1. Avsluta genom att klicka på bockmarkeringen längst upp till höger på skärmen.
1. Markera motsvarande **[!UICONTROL Shared Data Source]**.
1. Om du vill kan du markera rutan **[!UICONTROL Generate an outbound transition]** och använda de profiler som exporterades. Endast de profiler som kan förenas exporteras.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
1. Starta arbetsflödet för att exportera målgrupper. Synkronisering mellan Adobe Campaign och People Core Service kan ta flera timmar

Synkronisering mellan Adobe Campaign och People Core Service tar 24-36 timmar. Efter den här perioden kan du hitta din nya målgrupp i bastjänsten People och återanvända den i andra Adobe Experience Cloud-lösningar. Mer information om hur du använder en delad målgrupp från Adobe Campaign i Adobe People finns i denna [dokumentation](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html).

**Relaterade ämnen:**

* [Arbetsflöden](../../automating/using/get-started-workflows.md)
* [Publiker](../../audiences/using/about-audiences.md)

