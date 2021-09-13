---
title: Om direktmeddelanden
description: Upptäck de viktigaste egenskaperna för direktmeddelanden i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
feature: Direct Mail
role: User
level: Intermediate
exl-id: 815b4a0d-0486-4867-b751-b5ca8b643cb9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 98%

---

# Om direktutskick{#about-direct-mail}

Direktmeddelanden är en offlinekanal som gör att du kan anpassa och generera den fil som leverantören av direktmeddelanden behöver.  Det ger dig möjligheten att blanda online- och offline-kanaler i kundresorna.

>[!NOTE]
>
>Den här funktionen är valfri.  Kontrollera licensavtalet.  Rollen **[!UICONTROL Export]** krävs för direktmeddelanden.  Kontakta administratören.

Med onlinekanaler kan du skapa meddelanden (e-post, SMS, leveransmeddelanden för mobilappar etc.)  och skicka dem till din målgrupp direkt från Adobe Campaign.  Med offlinekanaler fungerar det annorlunda.  När du förbereder ett direktutskick genererar Adobe Campaign en fil som innehåller samtliga målprofiler och den valda kontaktinformationen (exempelvis postadress).  Du kan sedan skicka den här filen till din leverantör för direktmeddelanden som i sin tur tar hand om själva utskicket.

I följande avsnitt beskrivs hur du skapar och genererar direktmeddelanden i ett enda steg.  Du kan även inkludera en aktivitet för direktmeddelanden i ett arbetsflöde för att samordna kampanjer som kombinerar online- och offline-kanaler. Mer information om detta hittar du i handboken [Arbetsflöden](../../automating/using/get-started-workflows.md) .

Användarprocessen i Adobe Campaign är som följer:

1. Skapa leveransen
1. Välja målgruppen
1. Definiera innehållet
1. Ange kontaktdatumet
1. Generera filen

**Relaterade ämnen:**

* [Användningsfall: Koppla e-post och direktreklam](../../automating/using/coupling-email-direct-mail.md)

## Rekommendationer {#recommendations}

### Leverantör av direktmeddelanden {#direct-mail-providers}

Först och främst måste ni kontakta er leverantör av direktmeddelanden och ta reda på deras rekommendationer. Identifiera vilken profilinformation som behöver inkluderas i extraheringsfilen så att de kan personalisera kommunikationen och skicka den till målgruppen.  Som exempelvis för- och efternamn, postadress, kampanjkod etc.  Dessa fält läggs till i fliken [Definiera extrahering](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) i direktmeddelandets innehåll.

Kontrollera att du har markerat rutan **[!UICONTROL Address specified]** i profilinformationen.  Om det här alternativet är aktiverat läggs profilen till i målet.  I annat fall utesluts den av en typologiregel under förberedelsefasen (se [Skapa direktmeddelanden](../../channels/using/creating-the-direct-mail.md)).  Glöm inte att uppdatera detta fältet när du importerar profiler.

![](assets/direct_mail_22.png)

### Postadresser {#postal-addresses}

När du lägger till de fält som ska inkluderas i extraheringsfilen är postadressfälten tillgängliga i noden **[!UICONTROL Location]**.

Adobe Campaign innehåller en uppsättning fördefinierade kalkylerade fält som följer de vanligaste normaliseringarna av postadresser. Fälten är tillgängliga i noden **[!UICONTROL Postal address]**.

En adress kan som standard innehålla upp till sex rader. Det första kalkylerade fältet (**[!UICONTROL Line 1]** innehåller förnamn och efternamn. De följande raderna innehåller postadressen och den sista raden innehåller postnumret och ort/stad.

![](assets/direct_mail_23.png)
