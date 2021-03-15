---
solution: Campaign Standard
product: campaign
title: Synkronisera med Starta tekniskt arbetsflöde Frågor och svar
description: Vanliga frågor om det tekniska arbetsflödet i Launch.
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Instansinställningar
role: Administratör
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---


# Vanliga frågor och svar om startsynkronisering i Adobe {#syncwithlaunch-faq}

Du kan importera mobila egenskaper för Adobe Launch till Adobe Campaign Standard via det dedikerade tekniska arbetsflödet **[!UICONTROL Sync with Launch]**. Mer information finns på den här [sidan](../../administration/using/technical-workflows.md)

I avsnittet nedan visas vanliga frågor om synkroniseringen.

## Jag skapade en egenskap i [!DNL Launch] (icke-administratör för Org-unit ALL). Mitt program är i tillståndet Ready to Configure i Adobe Campaign, men jag kan inte öppna/konfigurera det. {#configuring-property}

Det är bara administratören av organisationsenheten ALL som kan konfigurera mobilprogram i Adobe Campaign Standard. Endast användare av den tilldelade organisationsenheten kan redigera
program. Mer information om organisationsenhet finns på den här [sidan](../../administration/using/organizational-units.md).

## Jag kan inte redigera ett konfigurerat mobilprogram i Adobe Campaign Standard och mobilprogram är i skrivläge. {#read-mode-mobile-app}

Kontrollera organisationsenheten för mobilprogrammet i **[!UICONTROL Access Authorization]**-avsnittet. Endast användare av den tilldelade organisationsenheten kan redigera det mobila programmet.

Mer information om organisationsenhet finns på den här [sidan](../../administration/using/organizational-units.md).

## Jag är administratör med organisationsenheten ALL i Adobe Campaign Standard, men jag kan inte konfigurera mobilprogram. {#org-unit-mobile}

En administratör med organisationsenheten inställd på ALL bör ha behörighet till alla mobila egenskaper i [!DNL Launch] för att konfigurera mobilprogrammet.

Mer information om organisationsenhet finns på den här [sidan](../../administration/using/organizational-units.md).

## Jag skapade en mobil egenskap i [!DNL Launch] men min egenskap är inte synlig i Adobe Campaign Standard. {#visibility-mobile-property}

1. Kontrollera att Adobe Campaign Standard-tillägget är installerat i egenskapen mobile i [!DNL Launch].

1. Kontrollera att slutpunkterna för instansen är korrekt konfigurerade i tillägget.

1. Kontrollera att Launch_URL_Campaign eller NmsServer_URL är korrekta.

1. Kontrollera sedan att synkroniseringen mellan [!DNL Launch] och Adobe Campaign har slutförts med det tekniska arbetsflödet **[!UICONTROL syncWithLaunch]**.

## Hur kontrollerar jag om synkroniseringen mellan Adobe Campaign och Launch har slutförts? {#sync-campaign-launch}

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** på den avancerade menyn.

1. Öppna arbetsflödet för **[!UICONTROL syncWithLaunch]**.

1. Kontrollera om arbetsflödet har avslutats utan fel.

1. Kontrollera i loggarna att arbetsflödessynkroniseringen är aktiverad och slutförd.

## Jag återställer nyckeln för ett konfigurerat mobilprogram i Launch. Hur konfigurerar du om nyckeln igen i Launch? {#configuring-pkey}

1. Öppna egenskapen mobile i Adobe Launch.

1. Ange en ny URL i Adobe Campaign Standard-tillägget som PKey återställdes för.

1. Spara den och låt arbetsflödet synkroniseras mellan Adobe Campaign och [!DNL Launch].

1. När synkroniseringen är klar öppnar du egenskapen mobile i [!DNL Launch].

1. Ange rätt URL i det Adobe Campaign Standard-tillägg som PKey återställdes för.

1. Spara den och låt arbetsflödessynkroniseringen köras igen.

1. Endast då visas egenskapen i läget **[!UICONTROL Ready to Configure]** i Adobe Campaign och kan nu konfigureras.

## Jag vill konfigurera en mobil egenskap i Adobe Campaign. Måste jag vänta på att det tekniska arbetsflödet ska synkroniseras mellan Adobe Launch och Adobe Campaign?

Du kan köra arbetsflödet direkt:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** på den avancerade menyn.

1. Öppna arbetsflödet för **[!UICONTROL syncWithLaunch]**.

1. Klicka på aktiviteten **[!UICONTROL Scheduler]** och välj **[!UICONTROL Immediate execution]**.
