---
title: Begära och konfigurera Microsoft Dynamics 365 med Campaign Standard-integrering
description: Lär dig hur du begär och konfigurerar Microsoft Dynamics 365 med Campaign Standard-integrering
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Begär Microsoft Dynamics 365 med Campaign Standard-integrering

För att kunna genomföra integreringen måste du följa stegen nedan.

Observera att denna integrering använder en tredjepartsleverantör, Unifi.  I samband med din supportförfrågan kan Adobe behöva dela din instansinformation i Adobe Campaign med Unifi.

Följ informationen i flödesschemat och flödesschemat nedan för att begära och konfigurera integreringen.

![](assets/provisioning-wf.png)

Information om flödesschema (mappas till steg ovan):

1. Du måste redan ha etablerat Campaign Standard och Microsoft Dynamics 365, med administratörsåtkomst för att kunna börja implementera den här integreringen.

1. Läs den här artikeln och kontrollera meddelanden och konfigurationssteg.

1. Skicka en kontoförfrågan till adobe-support@unifisoftware.com; Unifi kräver följande information när du begär ett konto:
* Användarens förnamn
* Användarens efternamn
* E-postadress
* Företag
* Regionen (Nordamerika, EMEA eller APAC)
* Användningstyp:  Kundtyp (kundanvändare som kommer att använda sina produktionsdata i den här integreringen), eller partnertyp (partnerkonsulter som testar integreringen för att få en bättre förståelse så att de kan hjälpa sina Campaign-kunder) eller intern typ (interna Adobe-användare som testar integreringen för att få en bättre förståelse för lösningen)
* Status för Campaign Standard-data (som börjar med en ren databas eller för att integrera befintliga data)
* Klient-ID för kampanj (se Konfigurera Campaign-integrering, steg 3 för att hämta ditt klient-ID)
* URL för kampanjinstans

Unifi förväntade svarstid: 1 timme under kontorstid i USA (9.00 till 17.00 PST, må-fre, exklusive helgdagar).

1. Slutför efteretableringen av Microsoft Dynamics 365 och Campaign Standard.
Skicka dessutom en anmälan till Adobes kundtjänst (antingen direkt eller via din Adobe-kontakt) så att signeringsflaggan aktiveras i Campaign-instansen. Partners bör kontakta sin Adobe-partner i sandlådeformat, i stället för att kontakta Adobes kundtjänst, för att aktivera funktionsflaggan.
Om du har befintliga data i Campaign som du tänker införliva i integreringen följer du anvisningarna i&quot;Befintliga kampanjdata&quot; och rådfrågar din tekniska kontakt från Adobe innan du fortsätter.

1. Slutför de inledande stegen i Unifi genom att navigera till Unifi, klicka dig igenom startskärmar, fylla i kontoautentiseringsuppgifterna för Dynamics 365 och Campaign Standard och meddela Unifi när de är klara.

1. Unifi kommer att fråga kunden om vilken avanmälningskonfiguration och avanmälningsattributsmappning de vill ha.

1. Kunden anger den valda avanmälningskonfigurationen och avanmälningsattributsmappningen.
Unifi förväntade svarstid: 1 arbetsdag (må-fre, exklusive helgdagar)

1. Konfigurera Unifi genom att granska OTB-mappningar, filter, jobb osv. och vid behov göra ändringar.  Mer information finns i användarhandboken för Unifi.
I det här steget anger du körningsfrekvens för Unifi-scheman
* Ange körningsfrekvensen för scheman i tidslinjen i Unifi, för tidsplanerna &quot;ingress&quot; och &quot;egress&quot; ska du dock köra dessa manuellt en gång innan du ställer in schemafrekvensen
* Följande frekvenser rekommenderas: Ingång (15 minuter), Utress (15 minuter), Borttagningar (en gång om dagen), Opt-Outs (en gång om dagen)

**Vi rekommenderar att du arbetar med Unifi och/eller Adobe-rådgivning (kontakta ditt Adobe-kontoteam) när du konfigurerar Unifi.**

För att möjliggöra integrering mellan Adobe Campaign Standard och Microsoft Dynamics 365 måste kunderna skapa ett användarkonto hos Unifi, en tredjepartsleverantör, enligt beskrivningen i det här dokumentet.   Som slutanvändare av Unifi-systemet ska kunden kontakta Unifi för frågor som rör dataförfrågningar som initierats av kunder i Unifi-systemet.

## Konfigurerar den här integreringen

Tre system måste etableras och konfigureras för den här integreringen: Adobe Campaign Standard, Microsoft Dynamics 365 for Sales och Unifi. Konfigurationsartiklar är länkade nedan.

>[!CAUTION]
>
>För varje system måste dessa steg utföras av en administratör.
>
>Stegen i artiklarna nedan vägleder dig genom att skapa integreringar/registreringar som inbegriper tilldelning av behörigheter och/eller administratörsåtkomst.  Det är ditt ansvar att se till att dessa steg följer företagets regler innan de utförs och att de utförs med omsorg.

I ADOBE CAMPAIGN måste du konfigurera API-åtkomst och konfigurera en ny integrering för Unifi. Läs [den här artikeln](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)för att uppnå detta.

I MICROSOFT DYNAMICS 365 måste du skapa en ny programregistrering och göra det möjligt för en programanvändare att använda integreringen.  Information om hur du konfigurerar Microsoft Dynamics 365 för den här integreringen finns i [den här artikeln](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

I UNIFI måste du konfigurera integrering och konfigurera mappning eller lägga till anpassade attribut. Om du vill konfigurera Unifi för den här integreringen läser du i [den här artikeln](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md).

## Begär support

Om du stöter på problem kan du kontakta Unifi kundsupport: [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net).

Unifi förväntade svarstid: 4 timmar under kontorstid i USA (9.00 till 17.00 PST, må-fre, exklusive helgdagar).

>[!CAUTION]
>
>I samband med din supportbegäran kan Adobe behöva dela din instansinformation för Adobe Campaign med Unifi.