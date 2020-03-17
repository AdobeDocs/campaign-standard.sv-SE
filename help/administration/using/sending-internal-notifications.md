---
title: Skicka interna meddelanden
description: Lär dig hur du skickar systemmeddelanden i realtid till Adobe Campaign-användare.
page-status-flag: never-activated
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Skicka interna meddelanden{#sending-internal-notifications}

Med Adobe Campaign kan ni få meddelanden om viktiga systemaktiviteter direkt i programmet. Realtidsmeddelanden håller berörda intressenter informerade och ger användarna möjlighet att direkt agera på aktivitetsmeddelanden inifrån programmet. Resultatet för teamen är avancerad flexibilitet, effektivitet och smidigare genomförande av kampanjer.

![](assets/pulse_3.png)

Du kan konfigurera meddelanden för följande objekt:

* **[!UICONTROL A/B Test emails]**: e-postskaparen och modifieraren/modifierarna meddelas om att en variant har valts (automatiskt läge) eller att en variant måste väljas (manuellt läge). Om du klickar på meddelandet visas motsvarande e-post. Meddelanden aktiveras som standard i den färdiga A/B-testmallen. Om du vill inaktivera dem redigerar du egenskaperna för e-postmeddelandet eller e-postmallen och avmarkerar kryssrutan under **Allmänt > Meddelanden**. Mer information om A/B Test-e-post finns i [Skapa ett AB-test](../../channels/using/designing-an-a-b-test-email.md). Mer information om e-postegenskaper finns i [Lista över e-postegenskaper](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: varje medlem i den valda säkerhetsgruppen meddelas (e-post och meddelanden i appen) när ett arbetsflöde är felaktigt. Om du klickar på meddelandet eller på e-postlänken visas motsvarande arbetsflöde. Meddelanden inaktiveras som standard i den färdiga arbetsflödesmallen. Om du vill aktivera dem redigerar du egenskaperna för arbetsflödes- eller arbetsflödesmallen och lägger till en säkerhetsgrupp under **Allmänt > Körning > Felhantering > Tillsynsorgan**. Mer information om säkerhetsgrupper finns i [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md). Mer information om arbetsflödesegenskaper finns i [Arbetsflödesegenskaper](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

