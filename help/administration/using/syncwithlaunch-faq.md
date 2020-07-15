---
title: Om åtkomsthantering
description: Hantera Adobe Campaign-operatorer med roller, grupper och organisationsenheter.
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---


# SyncWithLaunch Technical workflow FAQ {#syncwithlaunch-faq}

Arbetsflödet gör det möjligt att automatiskt importera alla mobilegenskaper i Adobe Launch till Adobe Campaign Standard. **[!UICONTROL Sync with Launch]**

Mer information finns på den här [sidan](../../administration/using/technical-workflows.md).

>[!NOTE]
>
>Du måste skicka in en anmälan till Adobes kundtjänst (antingen direkt eller via din Adobe-kontakt) för att aktivera det **[!UICONTROL syncWithLaunch]** tekniska arbetsflödet i Campaign-instansen.

## Jag skapade en egenskap i [!DNL Launch] (icke-administratör för Org-unit ALL). Mitt program är i tillståndet Ready to Configure i Adobe Campaign, men jag kan inte öppna/konfigurera det. {#configuring-property}

Det är bara administratören av organisationsenheten ALL som kan konfigurera mobilprogram i Adobe Campaign Standarden. När programmet har konfigurerats kan endast användare i den tilldelade organisationsenheten redigera det. Mer information om organisationsenhet finns på den här [sidan](../../administration/using/organizational-units.md).

## Jag kan inte redigera ett konfigurerat mobilprogram i Adobe Campaign Standard och mobilprogram är i skrivläge. {#read-mode-mobile-app}

Kontrollera organisationsenheten för mobilprogrammet i **[!UICONTROL Access Authorization ]** avsnittet. Endast användare av den tilldelade organisationsenheten kan redigera det mobila programmet.

Mer information om organisationsenhet finns på den här [sidan](../../administration/using/organizational-units.md).

## Jag är administratör med organisationsenheten ALL i Adobe Campaign Standard, men jag kan inte konfigurera mobilprogram. {#org-unit-mobile}

En administratör med organisationsenheten inställd på ALL bör ha behörighet till alla mobila egenskaper i [!DNL Launch] för att konfigurera mobilprogrammet.

Mer information om organisationsenhet finns på den här [sidan](../../administration/using/organizational-units.md).

## Jag skapade en mobil egenskap i, [!DNL Launch] men min egenskap syns inte i Adobe Campaign Standarden. {#visibility-mobile-property}

1. Kontrollera att Adobe Campaign Standarden är installerad i egenskapen mobile i [!DNL Launch].

1. Kontrollera att slutpunkterna för instansen är korrekt konfigurerade i tillägget.

1. Kontrollera att Launch_URL_Campaign eller NmsServer_URL är korrekta.

1. Kontrollera sedan att synkroniseringen mellan [!DNL Launch] och Adobe Campaign är klar med det **[!UICONTROL syncWithLaunch]** tekniska arbetsflödet.

## Hur kontrollerar jag om synkroniseringen mellan Adobe Campaign och Launch har slutförts? {#sync-campaign-launch}

1. På den avancerade menyn i Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Öppna **[!UICONTROL syncWithLaunch]** arbetsflödet.

1. Kontrollera om arbetsflödet har avslutats utan fel.

1. Kontrollera i loggarna att arbetsflödessynkroniseringen är aktiverad och slutförd.

## Jag återställer nyckeln för ett konfigurerat mobilprogram i Launch. Hur konfigurerar du om nyckeln igen i Launch? {#configuring-pkey}

1. Öppna egenskapen mobile i Adobe Launch.

1. Ange en ny URL i det Adobe Campaign Standard-tillägg som PKey återställdes för.

1. Spara den och låt arbetsflödet synkroniseras mellan Adobe Campaign och [!DNL Launch].

1. När synkroniseringen är klar öppnar du egenskapen mobile i [!DNL Launch].

1. Ange rätt URL i det Adobe Campaign Standard-tillägg som PKey återställdes för.

1. Spara den och låt arbetsflödessynkroniseringen köras igen.

1. Endast då visas egenskapen i **[!UICONTROL Ready to Configure]** läget Adobe Campaign och kan nu konfigureras.

## Jag vill konfigurera en mobil egenskap i Adobe Campaign. Måste jag vänta på att det tekniska arbetsflödet ska synkroniseras mellan Adobe Launch och Adobe Campaign?

Du kan köra arbetsflödet direkt:

1. På den avancerade menyn i Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Öppna **[!UICONTROL syncWithLaunch]** arbetsflödet.

1. Klicka på **[!UICONTROL Scheduler]** aktiviteten och välj **[!UICONTROL Immediate execution]**.
