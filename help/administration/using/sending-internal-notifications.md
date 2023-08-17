---
title: Skicka interna meddelanden
description: Lär dig skicka systemmeddelanden i realtid till dina Adobe Campaign-användare
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Skicka interna meddelanden{#sending-internal-notifications}

Adobe Campaign ger dig möjlighet att få meddelanden om viktiga systemaktiviteter direkt i programmet. Realtidsmeddelanden håller berörda intressenter informerade och ger användarna möjlighet att direkt agera på aktivitetsmeddelanden inifrån programmet. Resultatet för teamen är avancerad flexibilitet, effektivitet och smidigare genomförande av kampanjer.

![](assets/pulse_3.png)

Du kan konfigurera meddelanden för följande objekt:

* **[!UICONTROL A/B Test emails]**: e-postskaparen och modifieraren/modifierarna meddelas om att en variant har valts (automatiskt läge) eller att en variant måste väljas (manuellt läge). Om du klickar på meddelandet visas motsvarande e-postadress. Meddelanden aktiveras som standard i den färdiga A/B-testmallen. Om du vill inaktivera dem redigerar du egenskaperna för e-postmeddelandet eller e-postmallen och avmarkerar kryssrutan under **Allmänt > Meddelanden**. Mer information om A/B Test-e-post finns i [Skapa ett AB-test](../../channels/using/designing-an-a-b-test-email.md). Mer information om e-postegenskaper finns i [Lista över e-postegenskaper](../../administration/using/configuring-email-channel.md#list-of-email-properties).

  ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: varje medlem i den valda säkerhetsgruppen meddelas (e-post och meddelanden i appen) när ett arbetsflöde är felaktigt. Om du klickar på meddelandet eller på e-postlänken visas motsvarande arbetsflöde. Meddelanden inaktiveras som standard i den färdiga arbetsflödesmallen. Om du vill aktivera dem redigerar du egenskaperna för arbetsflödes- eller arbetsflödesmallen och lägger till en säkerhetsgrupp under **Allmänt > Körning > Felhantering > Supervisors**. Mer information om säkerhetsgrupper finns i [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md). Mer information om arbetsflödesegenskaper finns i [Egenskaper för arbetsflöde](../../automating/using/managing-execution-options.md).

  ![](assets/pulse_1.png)
