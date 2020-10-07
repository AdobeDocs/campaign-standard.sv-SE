---
title: Förfrågningsexempel
description: I det här avsnittet visas hur du använder en Query-aktivitet.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 90%

---


# Förfrågningsexempel {#query-samples}

I det här avsnittet visas ett användbart exempel för en **[!UICONTROL Query]** aktivitet. For more on how to use a **[!UICONTROL Query]** activity, refer to [this section](../../automating/using/query.md).

## Målriktat mot enkla profilattribut {#targeting-on-simple-profile-attributes}

I följande exempel så visas en frågeaktivitet som är konfigurerad för att rikta sig till män mellan 18 och 30 år och som bor i London.

![](assets/query_sample_1.png)

## Inriktat på e-postattribut {#targeting-on-email-attributes}

I följande exempel så visas en frågeaktivitet som har konfigurerats för målprofiler med e-postadressdomänen orange.co.uk.

![](assets/query_sample_emaildomain.png)

I följande exempel så visas en frågeaktivitet som konfigurerats för målprofiler vars e-postadress har angetts.

![](assets/query_sample_emailnotempty.png)

## Målprofiler vars födelsedag är idag {#targeting-profiles-whose-birthday-is-today}

I följande exempel visas en frågeaktivitet som konfigurerats för målprofiler vars födelsedag är idag.

1. Dra **[!UICONTROL Birthday]**-filtret i förfrågan.

   ![](assets/query_sample_birthday.png)

1. Ange **[!UICONTROL Filter type]** som **[!UICONTROL Relative]** och markera **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Målprofiler som öppnade en viss leverans {#targeting-profiles-who-opened-a-specific-delivery}

I följande exempel visas en förfrågan som konfigurerats för att filtrera profiler som öppnade leveransen med etiketten &quot;Sommartid&quot;.

1. Dra **[!UICONTROL Opened]**-filtret i förfrågan.

   ![](assets/query_sample_opened.png)

1. Välj leverans och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Målprofiler för vilka leveranser som misslyckades av en viss anledning {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

I följande exempel visas en förfrågan som konfigurerats för att filtrera profiler för vilka leveranser som misslyckades på grund av att deras brevlåda var full.  Förfrågan är bara tillgänglig för användare med administrationsrättigheter och som tillhör **[!UICONTROL All (all)]** organisationsenheterna (se [det här avsnittet](../../administration/using/organizational-units.md)).

1. Markera **[!UICONTROL Delivery logs]**-resursen för att filtrera direkt i leveransloggs-tabellen (se [Använda andra resurser än måldimensioner](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Dra **[!UICONTROL Nature of failure]**-filtret i förfrågan.

   ![](assets/query_sample_failure2.png)

1. Välj typ av fel som du vill rikta dig mot.  I vårt fall **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Målprofiler som inte har kontaktats under de 7 senaste dagarna {#targeting-profiles-not-contacted-during-the-last-7-days}

I följande exempel så visas en förfrågan som konfigurerats för att filtrera profiler som inte kontaktats under de 7 senaste dagarna.

1. Dra **[!UICONTROL Delivery logs (logs)]**-filtret i förfrågan.

   ![](assets/query_sample_7days.png)

   Välj **[!UICONTROL Does not exist]** i listrutan och dra sedan **[!UICONTROL Delivery]**-filtret.

   ![](assets/query_sample_7days1.png)

1. Konfigurera filtret enligt nedan.

   ![](assets/query_sample_7days2.png)

## Målprofiler som klickade på en specifik länk {#targeting-profiles-who-clicked-a-specific-link-}

1. Dra **[!UICONTROL Tracking logs (tracking)]**-filtret i förfrågan.

   ![](assets/query_sample_trackinglogs.png)

1. Dra **[!UICONTROL Label (urlLabel)]**-filtret.

   ![](assets/query_sample_trackinglogs2.png)

1. I **[!UICONTROL Value]**-fältet skriver du den etikett som definierades när länken infogades i leveransen och bekräftar sedan.

   ![](assets/query_sample_trackinglogs3.png)
