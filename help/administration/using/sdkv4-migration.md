---
title: Migrering av SDK v4-mobilprogram till Adobe Experience Platform SDK
description: Lär dig hur du migrerar ditt mobilprogram från SDK v4 till Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 620ae1adc6f804e90c10daeb5fa4df42ce106885
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---

# Så här migrerar du din mobilapplikation från SDK v4 till Adobe Experience Platform SDK {#sdkv4-migration}


Stödet för Adobe Experience Platform Mobile version 4 SDK upphör den 31 augusti 2021. Om du fortfarande använder den här äldre versionen av SDK måste du uppdatera din implementering med Adobe Experience Platform SDK **före slutet av juni 2024**. Lär dig hur du migrerar till Adobe Experience Platform SDK i den här artikeln.

>[!IMPORTANT]
>
> Läs dokumentet noggrant innan du startar migreringen av ditt SDK V4-mobilprogram till Adobe Experience Platform SDK.

## Om SDK V4-migrering

Adobe Campaign Standard behandlar mobilapplikationer med SDK V4 som separata applikationer jämfört med de som använder Adobe Experience Platform SDK.

När du har uppgraderat Adobe SDK-versionen från v4 till Adobe Experience Platform måste mobilapplikationer fortsätta använda befintliga prenumerationsdata och kampanjer. Därför krävs en migrering.

>[!NOTE]
>
> På den här sidan dokumenteras migreringen av ett SDK v4-mobilprogram till ett nyskapat Adobe Experience Platform SDK-program. Dina SDK v4-mobilprogram kommer inte att sammanfogas med ett Adobe Experience Platform SDK-mobilprogram med en **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Vad som inte ändras efter migreringen |
|:-:|
| Befintliga leveranser och kampanjer som använder den migrerade SDK V4-applikationen påverkas inte. |
| Namnet på mobilprogrammet ändras inte. |
| Plattformsautentiseringsuppgifterna för iOS och Android behålls. |
| Alla som prenumererar på programmet och deras data kommer att behållas. |
| Det befintliga SDK v4-mobilprogrammet fortsätter att skicka data (PII-data, prenumerations- och tokeninformation) till Adobe Campaign Standard. |
| **[!UICONTROL Organizational unit]** för mobilprogrammet förblir densamma. |

| Vad som kommer att ändras efter migreringen |
|:-:|
| Mobilprogrammet är tillgängligt i **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Före migreringen var den tillgänglig i **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| **[!UICONTROL Collect PII Endpoint]** för programmet ändras. Äldre **[!UICONTROL Collect PII Endpoint]** fortsätter att arbeta, skickade data går inte förlorade. |
| Programmet kommer att vara knutet till en tagg **[!UICONTROL Mobile Property]**. Det kommer att bearbetas som ett nytt mobilprogram. |
| Det ursprungliga Adobe Experience Platform SDK-programmet som användes vid migreringen kommer inte att finnas som ett separat program. Endast det migrerade SDK v4-programmet är tillgängligt. |

## Migrera ditt mobilprogram från SDK v4 till Adobe Experience Platform SDK {#how-to-migrate}

Innan du migrerar bör du beakta följande rekommendationer:

* Migreringsprocessen är oåterkallelig.
* Du bör inte köra migrering av flera program samtidigt. Du bör också se till att migreringen av ett program inte aktiveras av flera fönster samtidigt.
* Innan migreringen kontrollerar du att du har tilldelats **[!UICONTROL Organizational unit]** för det mobilprogram som du vill migrera och för det Adobe Experience Platform-program som du använder för migrering.
* Efter migreringen blir programmet ett Adobe Experience Platform SDK-program. Dess ändringar kommer att länkas till motsvarande tagg **[!UICONTROL Mobile Property]**.

1. Skapa en ny **[!UICONTROL Mobile property]** i användargränssnittet för datainsamling. Mer information finns i [dokumentationen](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** på den avancerade menyn och öppnar arbetsflödet i **[!UICONTROL syncWithLaunch]**. Kontrollera om arbetsflödet har avslutats utan fel.

1. När arbetsflödet har slutförts kontrollerar du om mobilprogrammet är tillgängligt i Adobe Campaign Standard och är i läget **[!UICONTROL Ready to Configure]** på menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

   ![](assets/aep_v4_2.png)

1. I **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]** väljer du det SDK V4-program som du vill migrera.

1. Klicka på fliken **[!UICONTROL Mobile application migration to AEP SDK]**.  

   ![](assets/aep_v4_3.png)

1. I listrutan **[!UICONTROL Select AEP SDK mobile application to merge current application with]** väljer du det Adobe Experience Platform SDK-mobilprogram som tidigare skapats.

1. Klicka på **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Klicka på **[!UICONTROL Ok]** i fönstret **[!UICONTROL Migration application]**.

   ![](assets/aep_v4_5.png)

1. Fönstret för slutförande visas. Klicka på **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. På listsidan för Adobe Experience Platform SDK-kanaler kontrollerar du att ditt tidigare V4-mobilprogram är inställt på **[!UICONTROL Ready To Configure]**.

1. Välj ditt mobilprogram och klicka på **[!UICONTROL Save]** för att slutföra migreringen.

Efter den här migreringen kommer prenumeranter som samlats in via V4-versionen av mobilprogrammet och nya prenumeranter som samlats in via AEP-versionen av mobilprogrammet att vara tillgängliga i den migrerade applikationen.

Om du vill skilja på de två olika typerna av prenumeranter kan du lägga till ett nytt anpassat fält av typen **[!UICONTROL Text]** när du utökar den anpassade resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** som `sdkversion` eller `appVersion` till exempel. Mer information om hur du utökar en anpassad resurs finns på [sidan](../../developing/using/creating-or-extending-the-resource.md).
Du måste sedan konfigurera den associerade taggen **[!UICONTROL Mobile property]** för att skicka det här anpassade fältvärdet i Samla in PII-anropet och ändra din mobilprogramskonfiguration i enlighet med detta.

## Vanliga frågor och svar  {#faq}

### F: I SDK v4-mobilprogrammet är migreringen av mobilprogram till Adobe Experience Platform SDK-fliken inte synlig. {#tab-not-visible}

S: På den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]** kontrollerar du värdet för alternativet **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**. Den ska vara inställd på 1 och aktiverad som standard. Administratören kan ha inaktiverat det manuellt.

![](assets/aep_v4_1.png)

### F: Från fliken för migrering av mobilprogram till Adobe Experience Platform SDK visas meddelandet Inga data. {#no-data}

S: Endast berättigade program av din **[!UICONTROL Organizational unit]** visas i listan. Kontrollera att du har rätt Adobe Experience Platform-program för migreringen. **[!UICONTROL Property Status]** för ditt Adobe Experience Platform-program ska anges till **[!UICONTROL Ready to Configure]** och **[!UICONTROL Mobile app migration status]** anges till **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### F: Varför kan inte Adobe Experience Platform SDK-programmet med den konfigurerade egenskapsstatusen användas för migrering? {#property-status}

S: Migreringsprocessen bevarar SDK v4-prenumeranterna och -attributen. Det sparar bara taggrelaterad information från Adobe Experience Platform SDK-programmet. Prenumeranter och andra data från Adobe Experience Platform SDK-programmet kommer att gå förlorade. För att undvika dataförluster är endast Adobe Experience Platform SDK-program med **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** berättigade till migrering.

### F: Efter migreringen, var hittar jag mitt tidigare SDK v4-mobilprogram? {#v4-app-not-visible}

S: Mobilprogrammet efter migreringen visas på den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### F: Efter migreringen, var hittar jag mitt nyskapade Adobe Experience Platform SDK-program? {#aep-not-visible}

S: Det nyskapade Adobe Experience Platform SDK-programmet som används för migreringen finns inte som ett separat program. Endast det migrerade SDK v4-programmet är tillgängligt.

### F: Om den mobila programenheten SDK v4 är inställd på A (underordnad till organisationsenheten ALL) och Adobe Experience Platform SDK är inställd på ALL. Hur migrerar jag mitt mobilprogram? {#v4-org-unit}

S: Administratörer av **[!UICONTROL Organizational unit]** ALL har behörighet att hantera båda mobilprogrammen och ansvarar för migreringen.

### F: Om mobilappen SDK v4 är inställd på A och Adobe Experience Platform SDK är inställd på B (en jämställd enhet i organisationsenheten A). Hur migrerar jag mitt mobilprogram? {#aep-org-unit}

S: Adobe Experience Platform SDK-programmet är en resurs på samma nivå som **[!UICONTROL Organizational unit]** och mobilprogrammet är inte synligt för användare av **[!UICONTROL Organizational unit]** A. Mobilappen är tillgänglig för administratörerna av **[!UICONTROL Organizational unit]** ALL, men vi rekommenderar inte dessa administratörer att migrera mobilappen.
I det här fallet bör du flytta dina mobilprogram i samma **[!UICONTROL Organizational unit]** eller i en **[!UICONTROL Organizational unit]** med en överordnad länk.
Mer information om **[!UICONTROL Organizational unit]** finns i det här [avsnittet](../../administration/using/organizational-units.md).

### F: Från din mobilprogramsida för Adobe Experience Platform SDK (migrerad från ditt v4-mobilprogram), under listrutan Push channel settings (Inställningar för push-kanal), visas ingen information som överföringsdatum/namn för Android-nyckeln eller iOS-certifikatet {#no-information-v5}

S: Systemet lagrar inte den här informationen när SDK V4-mobilprogrammet skapas. När du migrerar ditt SDK V4-mobilprogram till ett Adobe Experience Platform SDK-mobilprogram kommer ditt migrerade mobilprogram inte heller att ha den här typen av information. Så snart en användare laddar upp ett nytt iOS-certifikat eller en Android-nyckel kommer de olika uppgifterna för nyckeln eller certifikatet att lagras och visas korrekt i listrutan **[!UICONTROL Push channel settings]**.
