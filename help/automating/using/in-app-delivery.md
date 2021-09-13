---
title: Leverans i appen
description: Med leveransaktiviteten i appen kan du konfigurera sändning av meddelanden i appen i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 47%

---

# Leverans i appen{#in-app-delivery}

## Beskrivning {#description}

![](assets/wkf_in_app_1.png)

Med aktiviteten **Leverans i appen** kan du konfigurera sändning av meddelanden i appen i ett arbetsflöde. Med meddelanden i appen kan du visa ett meddelande när användaren är aktiv i programmet. Mer information om leverans i appen finns i det här [avsnittet](../../channels/using/about-in-app-messaging.md).

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL In-App delivery]** används vanligtvis för att automatisera sändning av ett meddelande i appen till en målgrupp som beräknas i samma arbetsflöde.

Mottagarna definieras uppströms aktiviteten i samma arbetsflöde, via målinriktade aktiviteter som frågor, skärningar osv.

Förberedelsen av meddelande utlöses enligt arbetsflödets körningsparametrar. Från kontrollpanelen för meddelanden kan du välja om du vill begära en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Query]**-aktivitet i arbetsflödet. Observera att **[!UICONTROL Query]**-aktivitetens målinriktningsdimension på fliken **[!UICONTROL Properties]** måste uppdateras enligt den mall som valts i steg 4:

   * Måldimensionen ska ställas in på **[!UICONTROL mobileApp (mobileAppV5)]** för mallen **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * Måldimensionen ska ställas in på **[!UICONTROL profile (profile)]** för mallen **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * Måldimensionen ska ställas in på **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** för mallen **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Dra och släpp en **[!UICONTROL In-App delivery]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png)-knappen från aktivitetens snabbåtgärder.

   ![](assets/wkf_in_app_3.png)

1. Välj meddelandetypen i appen. Detta beror på vilka data som används i din **[!UICONTROL Query]**-aktivitet.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Den här meddelandetypen gör att du kan rikta in dig på Adobe Campaign-profiler som har prenumererat på ditt mobilprogram och anpassa meddelanden i appen med profilattribut som är tillgängliga i Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Med den här meddelandetypen kan du skicka ett meddelande till alla användare av ditt mobilprogram, även om de inte har en befintlig profil i Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Den här meddelandetypen gör att du kan rikta dig till alla användare av en mobilapp som har en mobilprofil i Campaign, oavsett om den är känd eller okänd, och anpassa meddelanden i appen med alla profilattribut som har hämtats från den mobila enheten.

   ![](assets/wkf_in_app_4.png)

1. Ange meddelandeegenskaperna i appen och välj din mobilapp i fältet **[!UICONTROL Associate a Mobile App to a delivery]**.
1. Dra och släpp den händelse som ska utlösa meddelandet på fliken **[!UICONTROL Triggers]**. Tre kategorier av händelser är tillgängliga:
1. Definiera innehåll i appen. Se avsnittet [Anpassning i appen](../../channels/using/customizing-an-in-app-message.md).
1. Som standard innehåller aktiviteten **[!UICONTROL In-App delivery]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL In-App delivery]**-aktivitet går du till fliken **[!UICONTROL General]** med de avancerade aktivitetsalternativen (knappen ![](assets/dlv_activity_params-24px.png) i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som meddelandet skickades till. De målmedlemmar som utesluts under färdigställandet av leveransen undantas från denna övergång.

   ![](assets/wkf_in_app_5.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till kontrollpanelen i appen. Endast dess innehåll kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via kontrollpanelen för meddelanden, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]**-alternativet. Om du avmarkerar det här alternativet skickas meddelanden utan föregående meddelande när förberedelsen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Med hjälp av länkarna i rutan push-meddelandesammanfattning får du direktåtkomst till länkade element (arbetsflöde, kampanj, osv.).

I de överordnade leveranserna, som du kommer åt från listan över marknadsföringsaktiviteter, kan du visa det totala antalet skickade som har bearbetats (enligt den aggregeringsperiod som angavs när aktiviteten **[!UICONTROL In-App delivery]** konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]**-block genom att markera ![](assets/wkf_dlv_detail_button.png).
