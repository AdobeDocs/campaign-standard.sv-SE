---
title: Dela målgrupper med Audience Manager eller People core service
description: Lär dig hur du importerar eller exporterar målgrupper i olika Adobe Experience Cloud-lösningar.
page-status-flag: never-activated
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Dela målgrupper med Audience Manager eller People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importera en målgrupp {#importing-an-audience}

Integreringen av personbastjänsterna gör att du kan importera en målgrupp direkt till Adobe Campaign via ett tekniskt arbetsflöde för att utöka databasen. Mer information om målgruppsdelning i Bastjänsten People finns i den här [dokumentationen](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Import av målgrupper/segment från personbastjänsten i Adobe Campaign kan utföras från **[!UICONTROL Audiences]** menyn endast av användare som är anslutna via IMS (autentisering via Adobe ID).

1. Gå till **[!UICONTROL Audiences]** menyn.
1. I åtgärdsfältet väljer du **[!UICONTROL Create]** att klistras in på skärmen för att skapa en målgrupp.
1. Ange etiketten för den nya målgruppen.
1. Ställ in målgruppen **[!UICONTROL Type]** på **[!UICONTROL Experience Cloud]** att ange att målgruppen som skapas är en målgrupp som importerats från personbastjänsten.
1. I **[!UICONTROL Name of the shared audience]** fältet väljer du den målgrupp som ska importeras. Endast segment kan importeras. Detaljerade data som nyckelvärdepar, egenskaper och regler stöds inte.

   ![](assets/aam_import_audience.png)

1. Markera motsvarande **[!UICONTROL Shared Data Source]**.

   Om den valda datakällan är konfigurerad att använda en krypteringsalgoritm, finns det ytterligare ett alternativ som ger dig möjlighet att **[!UICONTROL Force reconciliation with a profile]**. Markera det här alternativet om **[!UICONTROL Channel]** fältet i datakällan är inställt på E-post eller Mobil (SMS) och om du vill utnyttja profildata.

   Om du inte väljer alternativet **[!UICONTROL Force reconciliation with a profile]** och om **[!UICONTROL Channel]** är inställt på E-post eller Mobil (SMS) i AMC-datakällan dekrypteras alla krypterade deklarerade ID:n. En målgrupp av typen **File** med en lista över alla e-postadresser/mobiltelefonnummer skapas/uppdateras. På så sätt förloras ingen e-postadress/inget mobiltelefonnummer när en delad målgrupp importeras via den här integreringen, även om profilen inte finns i Campaign. Observera att den här typen av målgrupper inte kan användas direkt eftersom de måste förenas manuellt med hjälp av arbetsflöden.

1. Bekräfta för att skapa målgruppen.

   Publiken importeras sedan via ett tekniskt arbetsflöde. Den består av poster där ID:t (&quot;besökar-ID&quot; eller&quot;Deklarerat ID&quot;) kunde förenas med profildimensionen. ID:n från People core service segments som inte känns igen av Adobe Campaign importeras inte.

Din målgrupp importeras nu i din Adobe Campaign-databas. Det tar 24-36 timmar att synkronisera importprocessen när segment importeras direkt från personkärntjänsten eller Audience Manager. Efter den här perioden kan ni hitta och använda er nya målgrupp i Adobe Campaign.

>[!NOTE]
>
>Om du importerar målgrupper från Adobe Analytics till Adobe Campaign måste dessa målgrupper först delas i People Core Service eller Audience Manager. Den här processen tar 12-24 timmar, vilket måste läggas till i synkroniseringen av 24-36 timmar med Campaign. I det specifika fallet kan tidsramen för målgruppsdelning vara upp till 60 timmar. Mer information om Adobe Analytics-målgruppsdelning i tjänsten People Core och Audience Manager finns i den här [dokumentationen](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exportera en målgrupp {#exporting-an-audience}

En målgrupp kan exporteras från Adobe Campaign till Audience Manager eller People core service med hjälp av ett arbetsflöde och en **[!UICONTROL Save audience]** aktivitet.

Den kan utföras i ett nytt arbetsflöde och endast av användare som är anslutna via IMS (autentisering via Adobe-ID).

1. Skapa ett nytt arbetsflöde från ett program, en kampanj eller listan över marknadsföringsaktiviteter.
1. Använd de olika aktiviteterna för att skapa en uppsättning profiler.
1. När du har skapat målet drar och släpper du en **[!UICONTROL Save audience]** aktivitet i arbetsflödet och öppnar den.
1. Välj **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Ange målgruppen med hjälp av **[!UICONTROL Shared audience]** fältet. I det fönster som öppnas kan du välja om du vill välja en befintlig målgrupp eller skapa en ny:

   * Om du väljer en befintlig målgrupp läggs endast de nya posterna till i målgruppen.
   * Om du vill exportera din profillista till en ny målgrupp fyller du i **[!UICONTROL Segment name]** fältet och klickar sedan **[!UICONTROL Create]** innan du väljer den nya målgruppen.
   ![](assets/aam_save_audience_segment_picker.png)

   För att posterna ska kunna stämmas av och bytas ut måste de ha ett Adobe Experience Cloud-ID (Visitor-ID eller Deklarerat ID). Ej avstämda poster ignoreras vid import och export av målgrupper.

1. Avsluta genom att klicka på bockmarkeringen längst upp till höger på skärmen.
1. Markera motsvarande **[!UICONTROL Shared Data Source]**.
1. Om du vill kan du markera kryssrutan för att använda de profiler som exporterades. **[!UICONTROL Generate an outbound transition]** Endast de profiler som kan förenas exporteras.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
1. Starta arbetsflödet för att exportera målgrupper. Synkronisering mellan Adobe Campaign och People Core Service kan ta flera timmar

Synkroniseringen mellan Adobe Campaign och People Core Service tar 24-36 timmar. Efter den här perioden kan du hitta din nya målgrupp i bastjänsten för människor och återanvända den i andra Adobe Experience Cloud-lösningar. Mer information om hur du använder en delad målgrupp i Adobe Campaign i huvudtjänsten Adobe People finns i den här [dokumentationen](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Relaterade ämnen:**

* [Arbetsflöden](../../automating/using/workflow-data-and-processes.md)
* [Målgrupper](../../audiences/using/about-audiences.md)

