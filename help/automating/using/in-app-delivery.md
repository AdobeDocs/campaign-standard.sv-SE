---
title: Leverans i appen
description: Med leveransaktiviteten i appen kan du konfigurera sändning av meddelanden i appen i ett arbetsflöde.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Leverans i appen{#in-app-delivery}

## Beskrivning {#description}

![](assets/wkf_in_app_1.png)

Med leveransaktiviteten **i appen** kan du konfigurera sändning av meddelanden i appen i ett arbetsflöde. Med meddelanden i appen kan du visa ett meddelande när användaren är aktiv i programmet. Mer information om leverans i appen finns i det här [avsnittet](../../channels/using/about-in-app-messaging.md).

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis för att automatisera sändning av ett meddelande i appen till en målgrupp som beräknas i samma arbetsflöde. **[!UICONTROL In-App delivery]**

Mottagarna definieras uppströms aktiviteten i samma arbetsflöde, via målinriktade aktiviteter som frågor, skärningar osv.

Meddelandeförberedelsen utlöses enligt arbetsflödets körningsparametrar. På meddelandekontrollpanelen kan du välja om du vill begära eller inte få en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Query]** aktivitet i arbetsflödet. Observera att **[!UICONTROL Query]** aktivitetens målinriktningsdimension på **[!UICONTROL Properties]** fliken måste uppdateras enligt mallen som valts i steg 4:

   * Måldimensionen ska ställas in på **[!UICONTROL mobileApp (mobileAppV5)]** för mallen **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * Måldimensionen ska ställas in på **[!UICONTROL profile (profile)]** för mallen **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * Måldimensionen ska ställas in på **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** för mallen **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Dra och släpp en **[!UICONTROL In-App delivery]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png) knappen från aktivitetens snabbåtgärder.

   ![](assets/wkf_in_app_3.png)

1. Välj meddelandetypen i appen. Detta beror på vilka data som används i din **[!UICONTROL Query]** aktivitet.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Med den här meddelandetypen kan ni inrikta er på Adobe Campaign-profiler som har prenumererat på ert mobilprogram och anpassa meddelanden i appen med profilattribut som är tillgängliga i Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Med den här meddelandetypen kan du skicka ett meddelande till alla användare av ditt mobilprogram, även om de inte har en befintlig profil i Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Den här meddelandetypen gör att du kan rikta dig till alla användare av en mobilapp som har en mobilprofil i Campaign, oavsett om den är känd eller okänd, och anpassa meddelanden i appen med alla profilattribut som har hämtats från den mobila enheten.
   ![](assets/wkf_in_app_4.png)

1. Ange meddelandeegenskaperna i appen och välj din mobilapp i **[!UICONTROL Associate a Mobile App to a delivery]** fältet.
1. Dra och släpp den händelse som ska utlösa meddelandet på **[!UICONTROL Triggers]** fliken. Tre kategorier av händelser är tillgängliga:
1. Definiera innehåll i appen. Se avsnittet om anpassning [](../../channels/using/customizing-an-in-app-message.md)i appen.
1. Som standard innehåller aktiviteten **[!UICONTROL In-App delivery]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL In-App delivery]** aktivitet går du till **[!UICONTROL General]** fliken med de avancerade aktivitetsalternativen ( ![](assets/dlv_activity_params-24px.png) knappen i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som meddelandet skickades till. De målmedlemmar som utesluts under färdigställandet av leveransen undantas från denna övergång.
   ![](assets/wkf_in_app_5.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till kontrollpanelen i appen. Det är bara innehållet som kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via meddelandekontrollpanelen, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]** alternativet. Genom att avmarkera det här alternativet skickas meddelanden utan föregående meddelande när beredningen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Med hjälp av länkarna i rutan push-meddelandesammanfattning får du direktåtkomst till länkade element (arbetsflöde, kampanj, osv.).

I de överordnade leveranserna, som du kommer åt från listan över marknadsföringsaktiviteter, kan du visa det totala antalet försändelser som har bearbetats (enligt den aggregeringsperiod som angavs när **[!UICONTROL In-App delivery]** aktiviteten konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]** block ![](assets/wkf_dlv_detail_button.png).
