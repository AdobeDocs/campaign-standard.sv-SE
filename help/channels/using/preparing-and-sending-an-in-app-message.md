---
solution: Campaign Standard
product: campaign
title: Förbereda och skicka ett meddelande i appen
description: Skapa meddelande i appen för att rikta in dig på era programprenumeranter med specifikt innehåll.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back;deliveryCreation,wizard
feature: I appen
role: Business Practitioner
exl-id: ef83d991-302b-491e-9cdb-07f5da7a5971
source-git-commit: 7272d2ca2b499069e00a3ded1cb6693147c64dfc
workflow-type: tm+mt
source-wordcount: '1272'
ht-degree: 98%

---

# Förbereda och skicka ett meddelande i appen{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>Anpassning i appen förlitar sig på ett länkningsfält som vanligtvis är ett CRM-ID och/eller inloggnings-ID för mobilapp. Du ansvarar själv för att säkra det här länkningsfältet när det används i samband med Adobe Campaign. Om du inte skyddar länkningsfälten kan ditt personliga meddelande bli sårbart. Adobe ansvarar inte för skador som uppstår på grund av obehörig åtkomst eller användning av profildata om du inte följer säkra metoder för att länkningsfältets disposition, hantering och skydd.

Det finns tre typer av meddelanden i appen i Adobe Campaign:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Den här meddelandetypen gör att du kan ange Adobe Campaign-profiler (CRM-profiler) som prenumererar på ditt mobilprogram som mål. Den här meddelandetypen kan anpassas med alla tillgängliga profilattribut i Adobe Campaign, men kräver en säker handskakning mellan Mobile SDK och Campaigns meddelandetjänst i appen för att säkerställa att meddelanden med personlig och känslig information endast används av behöriga användare.

   Om du vill hämta den här meddelandetypen på användarnas enheter måste Mobile SDK skicka länkningsfält som används för att ansluta en mobilprofil till en CRM-profil i Adobe Campaign. Mer information om SDK-API:er som krävs för att stödja appar finns på den här [sidan](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Med den här meddelandetypen kan du skicka meddelanden till alla användare (nuvarande eller framtida) av ditt mobilprogram, även om de inte har en befintlig profil i Adobe Campaign. Anpassnign är därför inte möjligt när du anpassar meddelandena eftersom användarprofilen kanske inte ens finns i Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Den här meddelandetypen gör att du kan rikta indig på alla kända eller anonyma användare av en mobilapp som har en mobilprofil i Adobe Campaign. Den här meddelandetypen kan endast anpassas med icke-personliga och icke-känsliga attribut och kräver ingen säker handskakning mellan Mobile SDK och Adobe Campaigns meddelandetjänst i appen.

   Mer information om hur du hanterar personliga och känsliga data finns i [Hantera mobilprofilsfält med personliga och känsliga data](#handling-mobile-profile-fields-with-personal-and-sensitive-data).

![](assets/diagram_inapp.png)

## Hantera mobilprofilfält med personliga och känsliga data {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

I Adobe Campaign lagras data för mobilprofilattribut som skickas från mobila enheter i resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, vilket gör att du kan definiera de data som du vill samla in från programprenumeranterna.

Resursen måste utökas för att samla in data som du tänker skicka från den mobila enheten till Adobe Campaign.  Om du vill göra det går du till den här [sidan](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) för detaljerade steg.

Om du vill personalisera meddelanden i appen på ett säkrare sätt måste du konfigurera fält för mobilprofiler från den här resursen på rätt sätt. När du skapar nya fält för mobilprofiler i **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** bör du markera **[!UICONTROL Personal and Sensitive]** så att de inte är tillgängliga vid personalisering av meddelanden i appar.

>[!NOTE]
>
>Om du har en befintlig implementering med ett anpassat resurstillägg i den här tabellen rekommenderar vi att du etiketterar fälten korrekt innan du använder dem för anpassning av meddelanden i appen.

![](assets/in_app_personal_data_2.png)

När den anpassade resursen **[!UICONTROL Subscriptions to an application]** har konfigurerats och publicerats kan du börja förbereda leverans i appen med hjälp av mallen **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Endast icke-personliga och icke-känsliga fält är tillgängliga från resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** för personalisering.

Om du behöver personalisera med fält som är **personliga och känsliga** bör du använda mallen **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**, som har extra säkerhetsfunktioner för att skydda användarnas personuppgifter.

## Förbereder ditt meddelande i appen {#preparing-your-in-app-message}

Stegen för att skapa ett fristående meddelande i appen med Adobe Campaign är följande:

1. Klicka på kortet **[!UICONTROL In-App messaging]** på startsidan för Adobe Campaign.

   Du kan också skapa en app från fliken **Marknadsföringsaktiviteter** genom att klicka på knappen **[!UICONTROL Create]**.

   Observera att ett meddelande i appen också kan skapas från en kampanj, från hemsidan för Adobe Campaign eller i ett arbetsflöde.

1. Välj **Meddelande i appen**.

   ![](assets/inapp_creating.png)

1. Välj en lämplig mall enligt målgruppens behov.

   ![](assets/inapp_creating_2.png)

   Som standard kan du välja någon av följande tre färdiga mallar:

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Ange egenskaperna för Meddelande i appen och välj din mobilapp i fältet **[!UICONTROL Associate a Mobile App to a delivery]**. Observera att om du inte konfigurerade din mobilapp med Adobe Campaign Standard visas den inte i listan. Mer information om konfiguration av mobilprogram finns på den här [sidan](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/inapp_creating_3.png)

1. Välj den målgrupp som du vill rikta in dig på i appen. Din målgrupp är förfiltrerad beroende på vilket mobilprogram som är associerat med leveransen.

   Observera att det här steget inte behövs med **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** eftersom det riktar sig till alla användare i ett mobilprogram.

   ![](assets/inapp_creating_8.png)

1. Dra och släpp den händelse som ska utlösa meddelandet på fliken **[!UICONTROL Triggers]**. När du väljer en utlösare väljer du en åtgärd som användarna utför och som gör att meddelandet i appen visas.

   Det finns fyra typer av händelser:

   * **[!UICONTROL Mobile Application events]**: Anpassade händelser som implementeras i ditt mobilprogram.

      Mer information om skapande av händelser finns på den här [sidan](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html).

   * **[!UICONTROL Life Cycle events]**: Körklara livscykelhändelser som stöds av Adobe Mobile SDK.

      Mer information om livscykelhändelser finns på den här [sidan](https://experienceleague.adobe.com/docs/mobile-services/android/metrics.html).

   * **[!UICONTROL Analytics Events]**: Följande tre kategorier stöds beroende på vad som finns i din mobilapp: Adobe Analytics, Kontextdata eller Vytillstånd.

      Observera att dessa händelser endast är tillgängliga om du har en Adobe Analytics-licens.

   * **[!UICONTROL Places]**: Följande tre kategorier utnyttjar platsdata i realtid för att leverera innehållsmässigt relevanta mobilupplevelser: Placerar kontextdata, Placerar anpassade metadata eller Placerar händelsetyp.

      Mer information om Adobe Platser finns i [Platsdokumentationen](https://placesdocs.com/).
   ![](assets/inapp_creating_4.png)

1. Om du använder ett **[!UICONTROL Analytics Events]** fylls händelserna Adobe Analytics och Vytillstånd i automatiskt baserat på de rapportsviter som konfigurerats i Analytics-tillägget i Adobe Experience Platform Launch, medan kontextdatahändelser måste läggas till manuellt.

   Observera att dessa händelser endast är tillgängliga om du har en Adobe Analytics-licens.

   ![](assets/inapp_creating_7.png)

1. Om du använder en **[!UICONTROL Places]**-utlösare fylls Placerar kontextdata, Placerar anpassade metadata eller Placerar händelsetyp automatiskt i baserat på alla bibliotek och deras intressepunkter som skapats i Adobe Places.

   Observera att den här utlösaren endast används på enheten för de intressepunkter från biblioteken som valts i Places-tillägget i Experience Platform Launch. Mer information om tillägget-tillägget och hur du installerar det finns i den här [dokumentationen](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. På fliken **[!UICONTROL Frequency & duration]** väljer du frekvens för utlösaren, start- och slutdatum, veckodag och tidpunkt på dagen då ditt Meddelande i appen ska vara aktivt.

   ![](assets/inapp_creating_5.png)

1. Redigera innehållet i meddelandet och definiera de avancerade alternativen. Se [Anpassa ett meddelande i appen](https://helpx.adobe.com/campaign/standard/channels/using/customizing-an-in-app-message.html).

   ![](assets/inapp_creating_6.png)

1. Klicka på **[!UICONTROL Create]**.

Ditt Meddelande i appen kan nu skickas till din målgrupp.

**Relaterade ämnen:**

* [Anpassa ett meddelande i appen](../../channels/using/customizing-an-in-app-message.md)
* [Rapport i appen](../../reporting/using/in-app-report.md)
* [Skicka ett meddelande i appen i ett arbetsflöde](../../automating/using/in-app-delivery.md)

## Skicka ditt meddelande i appen {#sending-your-in-app-message}

När du är klar med leveransen och godkännandestegen har utförts kan du skicka meddelandet.

1. Klicka på **[!UICONTROL Prepare]** för att beräkna målet och generera meddelandena.

   ![](assets/inapp_sending_4.png)

1. När förberedelsen är klar visar fönstret **Distribution** följande nyckeltal: **Mål** och **Ska levereras**.

   Du kan kontrollera fönstret Distribution genom att klicka på knappen ![](assets/lp_link_properties.png) för att se om det finns potentiella undantag eller fel i leveransen.

   ![](assets/inapp_sending_5.png)

1. Klicka på **[!UICONTROL Confirm]** för att börja skicka ditt meddelande i appen.

   ![](assets/inapp_sending_6.png)

1. Kontrollera leveransstatus via meddelandepanelen och loggarna. Mer information om detta hittar du i det här [avsnittet](../../sending/using/monitoring-a-delivery.md).

   Antalen för nyckeltalen **[!UICONTROL Delivered]** och **[!UICONTROL Sent]** baseras på vad som har skickats från Campaign till tjänsten för meddelandeleverans. Observera att dessa nyckeltal inte är en indikation på antalet mobila enheter som tagit emot eller laddat ned meddelandet från meddelandetjänsten.

   ![](assets/inapp_sending_7.png)

1. Mät effekten av dina Meddelanden i appen med leveransrapporter. Mer information om rapportering finns i [det här avsnittet](../../reporting/using/in-app-report.md).

**Relaterade ämnen:**

* [Rapport i appen](../../reporting/using/in-app-report.md)
* [Skicka ett meddelande i appen i ett arbetsflöde](../../automating/using/in-app-delivery.md)
