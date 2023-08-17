---
title: Synkronisera med Starta tekniskt arbetsflöde Frågor och svar
description: Vanliga frågor om det tekniska arbetsflödet i Adobe Launch
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Vanliga frågor och svar om taggar i Adobe Experience Platform-synkronisering {#syncwithlaunch-faq}

Du kan importera taggens mobila egenskaper till Adobe Campaign Standard via **[!UICONTROL Sync with Launch]** dedikerat tekniskt arbetsflöde. Mer information finns i [page](../../administration/using/technical-workflows.md)

I avsnittet nedan visas vanliga frågor om synkroniseringen.

## Jag skapade en taggegenskap (som inte är administratör för organisationsenhet ALL). Mitt program är i tillståndet Ready to Configure i Adobe Campaign, men jag kan inte öppna/konfigurera det. {#configuring-property}

Det är bara administratören av organisationsenheten ALL som kan konfigurera mobilprogram i Adobe Campaign Standard. När programmet har konfigurerats kan endast användare i den tilldelade organisationsenheten redigera det. Mer information om organisationsenhet finns i [page](../../administration/using/organizational-units.md).

## Jag kan inte redigera ett konfigurerat mobilprogram i Adobe Campaign Standard och mobilprogram är i skrivläge. {#read-mode-mobile-app}

Kontrollera organisationsenheten för mobilprogrammet i **[!UICONTROL Access Authorization]** -avsnitt. Endast användare av den tilldelade organisationsenheten kan redigera det mobila programmet.

Mer information om organisationsenhet finns i [page](../../administration/using/organizational-units.md).

## Jag är administratör med organisationsenheten ALL i Adobe Campaign Standard, men jag kan inte konfigurera mobilprogram. {#org-unit-mobile}

En administratör med organisationsenheten inställd på ALL bör ha behörighet till alla taggegenskaper för att konfigurera mobilprogrammet.

Mer information om organisationsenhet finns i [page](../../administration/using/organizational-units.md).

## Jag skapade en tagg för mobil, men min egenskap syns inte i Adobe Campaign Standard. {#visibility-mobile-property}

1. Kontrollera att Adobe Campaign Standard-tillägget är installerat i egenskapen mobile i användargränssnittet för datainsamling.

1. Kontrollera att slutpunkterna för instansen är korrekt konfigurerade i tillägget.

1. Kontrollera att Launch_URL_Campaign eller NmsServer_URL är korrekta.

1. Kontrollera sedan att synkroniseringen är klar med **[!UICONTROL syncWithLaunch]** tekniskt arbetsflöde.

## Hur kontrollerar jag om synkroniseringen mellan Adobe Campaign och taggar i Adobe Experience Platform har slutförts? {#sync-campaign-launch}

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Öppna **[!UICONTROL syncWithLaunch]** arbetsflöde.

1. Kontrollera om arbetsflödet har avslutats utan fel.

1. Kontrollera i loggarna att arbetsflödessynkroniseringen är aktiverad och slutförd.

## Jag återställer nyckeln för ett konfigurerat tagg-mobilprogram. Hur konfigurerar du om nyckeln igen i användargränssnittet för datainsamling? {#configuring-pkey}

1. Öppna egenskapen mobile i användargränssnittet för datainsamling.

1. Ange en ny URL i Adobe Campaign Standard-tillägget som PKey återställdes för.

1. Spara den och låt arbetsflödet synkroniseras.

1. När synkroniseringen är klar öppnar du egenskapen mobile i användargränssnittet för datainsamling.

1. Ange rätt URL i det Adobe Campaign Standard-tillägg som PKey återställdes för.

1. Spara den och låt arbetsflödessynkroniseringen köras igen.

1. Endast då visas egenskapen i **[!UICONTROL Ready to Configure]** i Adobe Campaign och kan nu konfigureras.

## Jag vill konfigurera en mobil egenskap i Adobe Campaign. Måste jag vänta på att det tekniska arbetsflödet ska synkroniseras mellan taggar i Adobe Experience Platform och Adobe Campaign?

Du kan köra arbetsflödet direkt:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Öppna **[!UICONTROL syncWithLaunch]** arbetsflöde.

1. Klicka på **[!UICONTROL Scheduler]** aktivitet och välj **[!UICONTROL Immediate execution]**.
