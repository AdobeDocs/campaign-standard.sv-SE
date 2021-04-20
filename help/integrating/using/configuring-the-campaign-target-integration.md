---
solution: Campaign Standard
product: campaign
title: Konfigurera Campaign-Target-integration
description: Lär dig hur du konfigurerar Adobe Target-integreringen så att du kan börja använda dynamiskt innehåll i Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Konfigurera Campaign-Target-integration{#configuring-the-campaign-target-integration}

Tack vare integreringen mellan Adobe Campaign och Adobe Target kan du infoga dynamiskt innehåll i leveransen.

En konfiguration behövs först i Adobe Campaign för att använda integreringsfunktionerna med Adobe Target och måste hanteras av den funktionella administratören.

Följande element krävs för den här proceduren:

* En Adobe Experience Cloud-klient
* En Adobe Target-klient
* En Adobe Target-ruta har angetts för att upprätta anslutningen till Adobe Campaign

1. På den avancerade menyn, via Adobe Campaign logotyp i det övre vänstra hörnet, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Om du vill konfigurera server- och klientalternativ för Adobe Target fyller du i följande fält i enlighet med detta:

   * **[!UICONTROL TNT_TenantName]**: namnet på Adobe Target-klienten. Detta värde motsvarar namnet på Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Adobe Target-server som används för integrering. Det här alternativet finns redan som standard. Detta värde motsvarar Adobe Target **[!UICONTROL Server Domain]**, följt av värdet **/m2**. Till exempel: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Användarna kan nu lägga till dynamiska bilder i en leverans med Adobe Target.
