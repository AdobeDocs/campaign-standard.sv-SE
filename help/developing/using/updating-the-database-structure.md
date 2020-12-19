---
solution: Campaign Standard
product: campaign
title: Uppdatera databasstrukturen
description: Läs om hur du uppdaterar Adobe Campaign-databasen.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: deploy,main;eventCusResource,overview
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Uppdatera databasstrukturen{#updating-the-database-structure}

Databasstrukturen måste uppdateras för att dina ändringar av datamodellen ska bli effektiva och kunna användas.

>[!NOTE]
>
>Anpassade resurser uppdateras automatiskt när Adobe uppdaterar automatiskt.

## Publicera en anpassad resurs {#publishing-a-custom-resource}

Om du vill använda ändringarna som gjorts på resurserna måste du utföra en databasuppdatering.

>[!NOTE]
>
>Om ett fält för en anpassad resurs som används för en händelse ändras eller tas bort, kommer motsvarande händelse automatiskt att avpubliceras. Se [Avpublicera en transaktionshändelse](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).

1. I den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** och sedan **[!UICONTROL Publishing]**.
1. Som standard är alternativet **[!UICONTROL Determine modifications since the last publication]** markerat, vilket innebär att endast de ändringar som utförts sedan den senaste uppdateringen kommer att tillämpas.

   >[!NOTE]
   >
   >**[!UICONTROL Repair database structure]** återskapar en korrekt konfiguration om publiceringen misslyckades innan den slutfördes. Alla ändringar som utfördes direkt i databasen och inte med anpassade resurser tas bort.

   ![](assets/schema_extension_12.png)

1. Klicka på **[!UICONTROL Prepare publication]**-knappen för att starta analysen. Observera att stora tabelluppdateringar ska göras när instansen inte är intensivt upptagen av arbetsflöden.

   Mer information om hur du utför åtgärder på API:t för profiler och tjänster finns i [Publicera en resurs med API-tillägg](#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. När publikationen är klar klickar du på **[!UICONTROL Publish]**-knappen för att tillämpa de nya konfigurationerna.
1. När den publicerats anger rutan **[!UICONTROL Summary]** för varje resurs att statusen nu är **[!UICONTROL Published]** och att datumet för den senaste publikationen anges.

   >[!NOTE]
   >
   >Om du gör nya ändringar i en resurs måste du upprepa den här åtgärden för att ändringarna ska tillämpas.

   Om resurserna har statusen **[!UICONTROL Pending re-draft]** innan de publiceras visas ett ytterligare meddelande som uppmanar dig att kontrollera dina åtgärder, eftersom publiceringen resulterar i slutgiltiga ändringar (kolumner, tabeller ...). Det finns en **[!UICONTROL SQL Script]**-flik som du kan använda för att utföra den senaste ändringen. Det innehåller det SQL-kommando som kommer att köras under publikationen.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >Du kan avbryta processen för att göra om utkast genom att klicka på **[!UICONTROL Cancel re-draft]**-knappen. Den här åtgärden återställer resursens status till den ursprungliga statusen.

1. Om det inte gick att publicera kan du alltid gå tillbaka till föregående publikation genom att klicka på **[!UICONTROL Back to latest successful publication]**.

   Observera att om du lämnar publikationen i ett feltillstånd öppnas ett popup-fönster så fort du loggar in på instansen för att påminna dig om att åtgärda publikationen. Din instans kommer inte att uppgraderas med nya produktversioner förrän publikationen är åtgärdad.

   ![](assets/schema_extension_31.png)

## Publicera en resurs med API-tillägg {#publishing-a-resource-with-api-extension}

Du kan skapa profil- och tjänste-API i följande fall:

* När du utökar de anpassade resurserna **[!UICONTROL Profiles]** eller **[!UICONTROL Services]** kan du uppdatera API:t för profiler och tjänster för att integrera de fält som deklarerats i det anpassade resurstillägget.
* När du definierar en anpassad resurs och skapar en länk mellan resurserna **[!UICONTROL Profiles]** eller **[!UICONTROL Services]** och den anpassade resursen kan du utföra en uppdatering som inkluderar den nya resursen i API:t.

Du kan välja det här alternativet på publikationsskärmen.

* Om API:t inte har publicerats än (d.v.s. om du aldrig har utökat resursen eller om du aldrig har markerat det här alternativet för den här resursen eller en annan resurs) kan du välja att skapa det eller inte.

   ![](assets/create-profile-and-services-api.png)

* Om API:t redan har publicerats (d.v.s. om du redan har utökat resursen och markerat det här alternativet en gång) tvingas API-uppdateringen att uppdateras.

   När API:t har skapats uppdateras det automatiskt varje gång du publicerar det igen. Detta ser till profilen eller tjänstresursen för detta API inte förstörs och skadar din instans.

Observera att den anpassade resursen är integrerad som standard, men om du inte vill publicera den här resursen kan du välja det alternativet **[!UICONTROL Hide this resource from APIs]** som är tillgängligt i **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

Efter **[!UICONTROL Prepare Publication]**-steget visar Adobe Campaign skillnaden mellan den aktuella versionen av API:t och den framtida versionen efter publikationen på fliken **[!UICONTROL Profiles & Services API Preview]**. Om du utökar API:t för första gången jämför deltavärdet den färdiganpassade resursdefinitionen med tillägget.

Informationen som visas på fliken är uppdelad i tre avsnitt: tillagda, borttagna och ändrade element.

![](assets/extendpandsapi_diff.png)

Analysen av delta är ett obligatoriskt steg eftersom publiceringssteget ändrar API-beteendet och troligen kommer att påverka den omgivande utvecklingen i en dominoeffekt.

>[!NOTE]
>
>Denna publikation uppdaterar **[!UICONTROL profilesAndServicesExt]**-API:t. **[!UICONTROL profilesAndServices]**-API:t har inte uppdaterats.

Mer information om Adobe Campaign API finns i den dedikerade Adobe Campaign-dokumentationen på [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
