---
title: Kom igång med administration av Campaign Standard
description: Lär dig mer om hantering av användare och behörigheter, riktlinjer för övervakning, kanalspecifika konfigurationer och riktlinjer för programinställningar
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 12%

---

# Kom igång med administration av Campaign Standard {#about-administrating-adobe-campaign}

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

Observera att administratörsanvändare även kan använda Campaign-kontrollpanelen för att hantera inställningar och spåra användningen för var och en av dina instanser. Mer information om detta hittar du i den [dedikerade dokumentationen](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=sv).

## Menyn Administration {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

De olika administratörsåtgärderna för Adobe Campaign utförs via menyn **[!UICONTROL Administration]** som är tillgänglig när du klickar på Adobe Campaign logotyp i det övre vänstra hörnet. Den här delen av gränssnittet kan bara nås av funktionsadministratörer för plattformen.

De olika menyerna är:

* [Användare och säkerhet](../../administration/using/about-access-management.md): På den här menyn kan du hantera åtkomst till plattformen (användare, roller, säkerhetsgrupper, enheter).
* [Kanaler](../../administration/using/about-channel-configuration.md): Den här menyn grupperar de tekniska parametrar som är länkade till de olika plattformskanalerna (e-post, mobil) samt typologi och karantänhantering.
* [Programinställningar](../../administration/using/external-accounts.md): På den här menyn kan du konfigurera olika programelement (externa konton, alternativ, tekniska arbetsflöden).
* [Utveckling](../../developing/using/data-model-concepts.md): På den här menyn kan du hantera dina anpassade resurser och komma åt diagnostikverktyg.
* [Instansinställningar](../../administration/using/branding.md): På den här menyn definierar du dina olika varumärken och konfigurerar deras inställningar (logotyp, hantering av spårning, URL-domän för åtkomst till landningssidorna, osv.).
* [Distribution](../../automating/using/managing-packages.md): Den här menyn grupperar alternativen för paketimport och export.
* [Kundstatistik](../../audiences/using/active-profiles.md): Adobe Campaign tillhandahåller en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen.
* [Sekretessverktyg](../../start/using/privacy-management.md): På den här menyn kan du skapa GDPR-åtkomst och ta bort begäranden och spåra deras utveckling.

## Användare och säkerhet {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Bjud in användare att komma åt programmet och hantera **säkerhetsgrupper**, som är uppsättningar användare som delar samma roller och rättigheter inom organisationen. Som standard erbjuder Adobe Campaign en uppsättning **roller** som gör att du kan definiera enhetsauktoriseringar som tilldelats användare och användargrupper. I kombination med **organisationsenheter** ger roller användarna en filtrerad vy av gränssnittet och definierar deras åtkomst till de olika funktionerna.

Med Campaign-standarden kan ni också övervaka säkerhetsrelaterad information. Du kan hämta information om dataexport som utförs av användare via skärmen **[!UICONTROL Export audits]** och använda skärmen **[!UICONTROL Licenses]** för att övervaka alla installerade Campaign-licenser inom organisationen, samt annan information, till exempel versionsnummer, frisläppningsversion och avtalsvillkor.

Läs mer:

* [Hantering av användare](../../administration/using/users-management.md)
* [Organisationsenheter](../../administration/using/organizational-units.md)
* [Lista över roller](../../administration/using/list-of-roles.md)
* [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md)
* [Granska exportloggar](../../administration/using/auditing-export-logs.md)
* [Licenser](../../administration/using/licenses.md)

## Kanalkonfiguration {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Alla kommunikationskanaler i Adobe Campaign måste vara korrekt konfigurerade för att effektivt kunna skicka meddelanden.,Med menyn **[!UICONTROL Channel]** kan du hantera de tekniska parametrar som är länkade till de olika kanalerna.

Konfigurera olika **e-post**-parametrar: bearbetningsregler för studsar, karantän, e-postegenskaper och routningsparametrar, typoregler. Definiera routningskonfigurationer och egenskaper för **SMS**-kanalen samt för SMS-kodning och format.

Konfigurera **mobilprogram** för att kunna skicka meddelanden i appen och push-meddelanden med Adobe Experience Platform SDK:er.

Läs mer:

* [Om kanalkonfiguration](../../administration/using/about-channel-configuration.md)
* [Konfigurera e-postkanal](../../administration/using/configuring-email-channel.md)
* [Konfigurera SMS-kanal](../../administration/using/configuring-sms-channel.md)
* [Konfigurera en mobilapplikation](../../administration/using/configuring-a-mobile-application.md)

## Programinställningar {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standarden innehåller olika programelement som kan konfigureras efter dina behov.

Konfigurera **externa konton** som används för att ansluta Adobe Campaign till externa servrar. Få åtkomst till målmappningar för Campaign Standarder och övervaka plattformen med **tekniska arbetsflöden**.

Definiera ett eller flera **varumärken** för din organisation och konfigurera sändning av **realtidsmeddelanden** i programmet om det finns viktiga systemaktiviteter.

Läs mer:

* [Om inställningar i Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Externa konton](../../administration/using/external-accounts.md)
* [Målmappningar i Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Varumärke](../../administration/using/branding.md)
* [Skicka interna meddelanden](../../administration/using/sending-internal-notifications.md)
