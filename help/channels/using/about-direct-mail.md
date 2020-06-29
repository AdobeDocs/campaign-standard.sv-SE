---
title: Om direktreklam
description: Upptäck de viktigaste särdragen hos direktreklamkanalen i Adobe Campaign.
page-status-flag: never-activated
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---


# Om direktreklam{#about-direct-mail}

Direktreklam är en offlinekanal som gör att du kan anpassa och generera den fil som direktreklamleverantörer behöver. Det ger er möjlighet att blanda online- och offlinekanaler i era kundresor.

>[!NOTE]
>
>Den här funktionen är valfri. Kontrollera licensavtalet. Rollen krävs **[!UICONTROL Export]** för direktreklam. Kontakta administratören.

Med onlinekanaler kan du skapa meddelanden (e-post, SMS, mobilappsleverans osv.) och skicka dem till er målgrupp direkt från Adobe Campaign. Med offlinekanaler är det annorlunda. När du förbereder en direktutskick genererar Adobe Campaign en fil med alla målprofiler och den valda kontaktinformationen (till exempel postadress). Du kan sedan skicka den här filen till din direktreklamleverantör som tar hand om själva sändningen.

I följande avsnitt beskrivs hur du skapar och genererar direktreklam i ett enda steg. Du kan även inkludera en direktreklamaktivitet i ett arbetsflöde för att samordna kampanjer som kombinerar online- och offlinekanaler. Mer information finns i handboken [Arbetsflöden](../../automating/using/get-started-workflows.md) .

Användarprocessen i Adobe Campaign är följande:

1. Skapa leveransen
1. Välja målgrupp
1. Definiera innehållet
1. Ange kontaktdatum
1. Genererar filen

**Relaterade ämnen:**

* [Användningsfall: Koppla e-post och direktreklam](../../automating/using/coupling-email-direct-mail.md)

## Rekommendationer {#recommendations}

### Direktreklam {#direct-mail-providers}

Först och främst måste ni kontakta er direktreklamleverantör och samla in deras rekommendationer. Identifiera vilken profilinformation som behöver inkluderas i extraheringsfilen så att de kan personalisera kommunikationen och skicka den till målgruppen. Till exempel för- och efternamn, postadress, kampanjkod osv. Dessa fält läggs till på fliken [Definiera extrahering](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) av direktpostens innehåll.

Kontrollera att du har markerat **[!UICONTROL Address specified]** rutan i profilinformationen. Om det här alternativet är aktiverat läggs profilen till i målet. I annat fall utesluts den av en typologiregel under förberedelsefasen (se [Skapa direktreklam](../../channels/using/creating-the-direct-mail.md)). Glöm inte att uppdatera det här fältet när du importerar profiler.

![](assets/direct_mail_22.png)

### Postadresser {#postal-addresses}

När du lägger till de fält som ska inkluderas i extraheringsfilen är postadressfälten tillgängliga i **[!UICONTROL Location]** noden.

Adobe Campaign erbjuder en uppsättning fördefinierade beräknade fält som följer de vanligaste normaliseringarna av postadresser. Fälten är tillgängliga i **[!UICONTROL Postal address]** noden.

En adress kan som standard innehålla upp till sex rader: det första beräknade fältet (**[!UICONTROL Line 1]** innehåller förnamn och efternamn, de följande raderna innehåller postadressen (väg, osv.) och den sista raden innehåller postnumret och ort eller stad.

![](assets/direct_mail_23.png)
