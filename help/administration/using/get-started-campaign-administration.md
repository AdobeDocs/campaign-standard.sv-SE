---
title: Kom igång med Campaign Standard-administration
description: Upptäck användar- och behörighetshantering, riktlinjer för övervakning, kanalspecifika konfigurationer och riktlinjer för programinställningar.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 14%

---


# Kom igång med Campaign Standard-administration {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menyn Administration</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Användare och säkerhet</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Kanalkonfiguration</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Programinställningar</a></p></td></tr>
</table>

Adobe Campaign är en molnbaserad lösning som ger administratörer olika sätt att konfigurera programmet. Även om infrastrukturkonfigurationen utförs av Adobe kan funktionsadministratörer utföra olika konfigurationsåtgärder som beskrivs nedan.

>[!NOTE]
>
>Om du har frågor eller frågor om implementerings- och konfigurationsfrågor kontaktar du din kontoansvarige på Adobe.

## Menyn Administration {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

De olika administratörsåtgärderna för Adobe Campaign utförs via den meny som är tillgänglig när du klickar på Adobe Campaign logotyp i det övre vänstra hörnet. **[!UICONTROL Administration]** Den här delen av gränssnittet kan bara nås av funktionsadministratörer för plattformen.

De olika menyerna är:

* [Användare och säkerhet](../../administration/using/about-access-management.md): På den här menyn kan du hantera åtkomst till plattformen (användare, roller, säkerhetsgrupper, enheter).
* [Kanaler](../../administration/using/about-channel-configuration.md): Den här menyn grupperar de tekniska parametrar som är länkade till de olika plattformskanalerna (e-post, mobil) samt typologi och karantänhantering.
* [Programinställningar](../../administration/using/external-accounts.md): På den här menyn kan du konfigurera olika programelement (externa konton, alternativ, tekniska arbetsflöden).
* [Utveckling](../../developing/using/data-model-concepts.md): På den här menyn kan du hantera anpassade resurser och komma åt diagnostikverktyg.
* [Förekomstinställningar](../../administration/using/branding.md): På den här menyn definierar du dina olika varumärken och konfigurerar deras inställningar (logotyp, hantering av spårning, URL-domän för att komma åt landningssidorna, osv.).
* [Distribution](../../automating/using/managing-packages.md): Den här menyn grupperar alternativen för paketimport och -export.
* [Kundstatistik](../../audiences/using/active-profiles.md): Adobe Campaign tillhandahåller en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen.
* [Sekretessverktyg](https://helpx.adobe.com/se/campaign/kb/campaign-privacy.html): På den här menyn kan du skapa GDPR-åtkomst och ta bort begäranden och spåra deras utveckling.

## Användare och säkerhet {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Bjud in användare att komma åt programmet och hantera **säkerhetsgrupper**, som är uppsättningar användare som delar samma roller och rättigheter inom organisationen. By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

Med Campaign-standarden kan ni också övervaka säkerhetsrelaterad information. Ni kan hämta information om dataexport som utförs av användare via **[!UICONTROL Export audits]** skärmen och använda **[!UICONTROL Licenses]** skärmen för att övervaka alla installerade Campaign-licenser inom organisationen, samt annan information som versionsnummer, releaseversion och avtalsvillkor.

Läs mer:

* [Hantering av användare](../../administration/using/users-management.md)
* [Organisationsenheter](../../administration/using/organizational-units.md)
* [Lista över roller](../../administration/using/list-of-roles.md)
* [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md)
* [Granska exportloggar](../../administration/using/auditing-export-logs.md)
* [Licenser](../../administration/using/licenses.md)

## Kanalkonfiguration {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Alla kommunikationskanaler i Adobe Campaign måste vara korrekt konfigurerade för att effektivt kunna skicka meddelanden. På **[!UICONTROL Channel]** menyn kan du hantera de tekniska parametrar som är länkade till de olika kanalerna.

Konfigurera olika **e-postparametrar** : bearbetningsregler för studsar, karantän, e-postegenskaper och routningsparametrar, typoregler. Definiera routningskonfigurationer och egenskaper för **SMS** -kanalen samt för SMS-kodning och format.

Konfigurera **mobilappar** för att kunna skicka meddelanden i appen och push-meddelanden med Adobe Experience Platform SDK:er, och konfigurera **transaktionsmeddelanden** genom att skapa och konfigurera händelser.

Läs mer:

* [Om kanalkonfiguration](../../administration/using/about-channel-configuration.md)
* [Konfigurera e-postkanal](../../administration/using/configuring-email-channel.md)
* [Konfigurera SMS-kanal](../../administration/using/configuring-sms-channel.md)
* [Konfigurera ett mobilprogram](../../administration/using/configuring-a-mobile-application.md)
* [Konfigurera transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md)

## Programinställningar {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standarden innehåller olika programelement som kan konfigureras efter dina behov.

Konfigurera **externa konton** som används för att ansluta Adobe Campaign till externa servrar. Få åtkomst till målmappningar för Campaign Standarder och övervaka plattformen med **tekniska arbetsflöden**.

Definiera ett eller flera **varumärken** för din organisation och konfigurera sändning av **realtidsmeddelanden** i programmet i händelse av viktiga systemaktiviteter.

Läs mer:

* [Om Campaign Standard-inställningar](../../administration/using/about-campaign-standard-settings.md)
* [Externa konton](../../administration/using/external-accounts.md)
* [Målmappningar i Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Varumärke](../../administration/using/branding.md)
* [Skicka interna meddelanden](../../administration/using/sending-internal-notifications.md)

## Ytterligare resurser

* [Hantera åtkomsträttigheter för användare (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [Dokumentation för kontrollpanelen](https://docs.adobe.com/content/help/sv-SE/control-panel/using/control-panel-home.html)
