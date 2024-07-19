---
title: Exempel på frågor
description: I det här avsnittet visas hur du använder en Query-aktivitet.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 0a71e3a7-60e6-49ec-af2e-099ad0d69a15
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 76%

---

# Exempel på frågor {#query-samples}

I det här avsnittet visas användningsexempel för en **[!UICONTROL Query]**-aktivitet. Mer information om hur du använder en **[!UICONTROL Query]**-aktivitet finns i [det här avsnittet](../../automating/using/query.md).

## Målinriktning mot enkla profilattribut {#targeting-on-simple-profile-attributes}

I följande exempel så visas en frågeaktivitet som är konfigurerad för att rikta sig till män mellan 18 och 30 år och som bor i London.

![](assets/query_sample_1.png)

## Riktning på e-postattribut {#targeting-on-email-attributes}

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

## Målprofiler för vilka leveranser misslyckades av en viss anledning {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

I följande exempel visas en förfrågan som konfigurerats för att filtrera profiler för vilka leveranser som misslyckades på grund av att deras brevlåda var full.  Förfrågan är bara tillgänglig för användare med administrationsrättigheter och som tillhör **[!UICONTROL All (all)]** organisationsenheterna (se [det här avsnittet](../../administration/using/organizational-units.md)).

1. Markera **[!UICONTROL Delivery logs]**-resursen för att filtrera direkt i leveransloggs-tabellen (se [Använda andra resurser än måldimensioner](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Dra **[!UICONTROL Nature of failure]**-filtret i förfrågan.

   ![](assets/query_sample_failure2.png)

1. Välj typ av fel som du vill rikta dig mot.  I vårt fall **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Målprofiler som inte kontaktats under de senaste 7 dagarna {#targeting-profiles-not-contacted-during-the-last-7-days}

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
