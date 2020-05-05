---
title: Kom igång med Campaign Standard-administration
description: Adobe Campaign innehåller en komplett uppsättning administrationsverktyg. Lär dig hur du hanterar dina användare och konfigurerar dina kanaler.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 40bb454d13de14658bfc30a6454a1a896bf3ad70

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

De olika Adobe Campaign-administratörsåtgärderna utförs via den meny som är tillgänglig när du klickar på Adobe Campaign-logotypen i det övre vänstra hörnet. **[!UICONTROL Administration]** Den här delen av gränssnittet kan bara nås av funktionsadministratörer för plattformen.

De olika menyerna är:

* [Användare och säkerhet](../../administration/using/about-access-management.md): På den här menyn kan du hantera åtkomst till plattformen (användare, roller, säkerhetsgrupper, enheter).
* [Kanaler](../../administration/using/about-channel-configuration.md): Den här menyn grupperar de tekniska parametrar som är länkade till de olika plattformskanalerna (e-post, SMS) samt typologi och karantänhantering.
* [Programinställningar](../../administration/using/external-accounts.md): På den här menyn kan du konfigurera olika programelement (externa konton, alternativ, tekniska arbetsflöden).
* [Utveckling](../../developing/using/data-model-concepts.md): På den här menyn kan du hantera anpassade resurser och komma åt diagnostikverktyg.
* [Förekomstinställningar](../../administration/using/branding.md): På den här menyn definierar du dina olika varumärken och konfigurerar deras inställningar (logotyp, hantering av spårning, URL-domän för att komma åt landningssidorna, osv.).
* [Distribution](../../automating/using/managing-packages.md): Den här menyn grupperar alternativen för paketimport och -export.
* [Kundstatistik](../../audiences/using/active-profiles.md): Adobe Campaign innehåller en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen.
* [Sekretessverktyg](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html): På den här menyn kan du skapa GDPR-åtkomst och ta bort begäranden och spåra deras utveckling.

## Användare och säkerhet {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Bjud in användare att komma åt programmet och hantera **säkerhetsgrupper**, som är uppsättningar användare som delar samma roller och rättigheter inom organisationen. Som standard erbjuder Adobe Campaign en uppsättning **roller** som gör att du kan definiera enhetsbehörigheter som tilldelats användare och användargrupper. I kombination med **organisationsenheter** ger roller användarna en filtrerad vy av gränssnittet och definierar deras åtkomst till de olika funktionerna.

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

Konfigurera **mobilappar** för att kunna skicka meddelanden i appen och push-meddelanden med SDK:er för Adobe Experience Platform och konfigurera **transaktionsmeddelanden** genom att skapa och konfigurera händelser.

Läs mer:

* [Om kanalkonfiguration](../../administration/using/about-channel-configuration.md)
* [Konfigurera e-postkanal](../../administration/using/configuring-email-channel.md)
* [Konfigurera SMS-kanal](../../administration/using/configuring-sms-channel.md)
* [Konfigurera ett mobilprogram](../../administration/using/configuring-a-mobile-application.md)
* [Konfigurera transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md)

## Programinställningar {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard innehåller olika programelement som kan konfigureras efter behov.

Konfigurera **externa konton** som används för att ansluta Adobe Campaign till externa servrar. Få tillgång till målmappningar i Campaign Standard och övervaka plattformen med **tekniska arbetsflöden**.

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
* [Dokumentation för kontrollpanelen](https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html)
