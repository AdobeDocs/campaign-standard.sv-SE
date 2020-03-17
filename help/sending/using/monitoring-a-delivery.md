---
title: Övervaka en leverans i Adobe Campaign Standard
description: Upptäck hur ni övervakar en leverans i Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Övervaka leverans{#monitoring-a-delivery}

Det finns flera sätt att övervaka en leverans och mäta dess effekt:

* **Meddelandeloggar**: Loggarna kan nås direkt från meddelandekontrollpanelen. De visar detaljerna för utskicket, vilket mål som har uteslutits och varför samt spårningsinformation som öppningar och klick.

   Om du vill visa meddelandeloggarna klickar du på ikonen längst ned till höger i **[!UICONTROL Deployment]** blocket.

   Flera flikar innehåller information (om den finns) om **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]** och **[!UICONTROL Tracking logs]** **[!UICONTROL Tracked URLs]**. Se [Leveransloggar](#delivery-logs).

   ![](assets/sending_delivery1.png)

   Loggen innehåller alla meddelanden som rör leveransen och korrekturet. Med specifika ikoner kan du identifiera fel eller varningar. Mer information finns i [Godkänna meddelanden](../../sending/using/previewing-messages.md).

   Du kan exportera loggen genom att klicka på **[!UICONTROL Export list]** knappen.

   ![](assets/sending_delivery2.png)

* **Leveransmeddelanden**: För att hålla reda på leveransframgångar eller leveransfel tillhandahåller Adobe Campaign ett e-postvarningssystem som skickar meddelanden till användarna om viktiga systemaktiviteter.
* **Rapporter**: Från meddelandekontrollpanelen kan du få åtkomst till flera rapporter för det här specifika meddelandet. Du har också en **[!UICONTROL Reports]** meny där du kan få tillgång till en komplett lista med inbyggda eller anpassade rapporter som du kan använda för att skapa konturer för specifika mätvärden som är relaterade till ditt meddelande eller din kampanj.
* En administratör kan också exportera loggar i en separat fil som kan bearbetas i dina egna rapporterings- eller BI-verktyg. Mer information finns i [Exportera loggar](../../automating/using/exporting-logs.md).

**Relaterade ämnen:**

* [Få aviseringar när fel uppstår](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporter](../../reporting/using/about-dynamic-reports.md)

## Leveransloggar {#delivery-logs}

### Skicka loggar {#sending-logs}

På fliken **[!UICONTROL Sending logs]** visas en historik över alla förekomster av leveransen. Listan över skickade meddelanden och deras status lagras här. Du kan visa leveransstatus för varje mottagare.

För varje profil med **[!UICONTROL Sent]** status visas **[!UICONTROL Date]** kolumnen när meddelandet skickades.

![](assets/sending_delivery3.png)

Klicka på pennikonen till höger om motsvarande rad om du vill visa information om en viss sändningslogg.

![](assets/sending_access-sending-log.png)

Alla avsändande loggdetaljer är skrivskyddade. Du kan också se en förhandsvisning av spegelsidan.

![](assets/sending_sending-log.png)

>[!NOTE]
>
>Om du vill visa återgivning av spegelsidan i användargränssnittet för Campaign måste URL:en för spegelsidservern vara säker. I så fall använder du https:// i stället för http:// för att konfigurera den här URL:en när du [konfigurerar varumärket](../../administration/using/branding.md#configuring-and-using-brands).

### Uteslutningsloggar {#exclusion-logs}

På **[!UICONTROL Exclusion logs]** fliken visas alla meddelanden som har uteslutits från det skickade målet och orsaken till sändningsfelet anges.

![](assets/sending_delivery4.png)

### Uteslutningsorsaker {#exclusion-causes}

På fliken **[!UICONTROL Exclusion causes]** visas volymen (i antal meddelanden) för meddelanden som har uteslutits från målsändningen.

![](assets/sending_delivery5.png)
