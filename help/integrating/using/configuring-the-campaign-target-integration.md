---
title: Konfigurera integrering av Campaign-Target
description: Lär dig hur du konfigurerar Adobe Target-integreringen så att den börjar använda dynamiskt innehåll i Adobe Campaign.
page-status-flag: never-activated
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Konfigurera integrering av Campaign-Target{#configuring-the-campaign-target-integration}

Integrationen mellan Adobe Campaign och Adobe Target gör att ni kan infoga dynamiskt innehåll i era leveranser.

En konfiguration krävs först i Adobe Campaign för att använda integreringsfunktionerna med Adobe Target och måste hanteras av den funktionella administratören.

Följande element krävs för den här proceduren:

* En Adobe Experience Cloud-klient
* En Adobe Target-klient
* En Adobe Target-ruta har angetts för att upprätta anslutningen till Adobe Campaign

1. På den avancerade menyn, via Adobe Campaign-logotypen i det övre vänstra hörnet, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Om du vill konfigurera server- och klientalternativ för Adobe Target fyller du i följande fält i enlighet med detta:

   * **[!UICONTROL TNT_TenantName]**: namnet på Adobe Target-innehavaren. Värdet motsvarar namnet på Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Adobe Target-server som används för integrering. Det här alternativet finns redan som standard. Värdet motsvarar Adobe Target **[!UICONTROL Server Domain]** följt av värdet **/m2** . Till exempel: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Dina användare kan nu lägga till dynamiska bilder i en leverans med Adobe Target.
