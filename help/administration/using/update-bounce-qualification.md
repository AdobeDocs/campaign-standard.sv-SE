---
title: Uppdatera studskvalificering efter ett avbrott hos en internetleverantör
description: Lär dig hur du uppdaterar studskompetens efter ett avbrott i en Internet-leverantör.
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Uppdatera studskompetens efter ett ISP-avbrott {#update-bounce-qualification.md}

## Kontext

Om en Internet-leverantör skulle råka ut kan e-postmeddelanden som skickas via Campaign inte levereras till mottagaren: dessa e-postmeddelanden markeras felaktigt som studsar.

I december 2020 resulterade ett globalt problem på Gmail i att vissa e-postmeddelanden som skickades till giltiga Gmail-e-postadresser felaktigt studsades som ogiltiga e-postadresser av Gmail-servrar med följande studssvar: *&quot;550-5.1.1 E-postkontot som du försökte nå finns inte.&quot;*

Google har uppgett att de Gmail-avbrott och -avbrott som orsakade problemet började 14 december kl. 6:55 och upphörde kl. 18:09 EST den 15 december. Vår dataanalys visade också en mycket kort topp i Gmail-studsar kl. 02:06 EST den 16 december, där majoriteten inträffar den 15 december mellan kl. 2:00 EST och kl. 18.30 EST.

>[!NOTE]
>
>Du kan kontrollera Google Workspace Status Dashboard på [den här sidan](https://www.google.com/appsstatus#hl=en&amp;v=status).


Med hjälp av standardlogik för studshantering har Adobe Campaign automatiskt lagt till de här mottagarna i karantänlistan med **[!UICONTROL Status]**-inställningen **[!UICONTROL Quarantine]**. För att korrigera detta måste du uppdatera karantäntabellen i Campaign genom att hitta och ta bort de här mottagarna, eller ändra deras **[!UICONTROL Status]** till **[!UICONTROL Valid]** så att de tas bort i nattrensningsarbetsflödet.

Om du vill hitta de mottagare som påverkades av Gmail-problemet, eller om det skulle inträffa igen med någon annan Internet-leverantör, läser du instruktionerna nedan.

## Process som ska uppdateras

Du måste köra en fråga i karantäntabellen för att filtrera bort alla Gmail-mottagare (eller andra ISP-mottagare) som eventuellt påverkades av driftsavfallet så att de kan tas bort från karantänlistan och inkluderas i framtida e-postleveranser för kampanjer.

Baserat på tidsramen för incidenten är nedanstående de rekommenderade riktlinjerna för frågan.

>[!IMPORTANT]
>
>Dessa datum/tider baseras på EST (Eastern Standard Time Zone). Justera efter instansens tidszon.

För Campaign-instanser med SMTP-studssvarsinformation i fältet **[!UICONTROL Error text]** i karantänlistan:

* **Feltext (karantänstext)** innehåller &quot;550-5.1.1 E-postkontot som du försökte nå finns inte&quot; OCH **Feltexten (karantänstext)** innehåller &quot;support.google.com&quot; **
* **Uppdatera status (@lastModified)** den 12/14/2020 6:55:00
* **Uppdatera status (@lastModified)** den 12/16/2020 6:00:00

När du har en lista över berörda mottagare kan du antingen ange statusen **[!UICONTROL Valid]** så att de tas bort från karantänlistan av arbetsflödet i **[!UICONTROL Database cleanup]** eller bara ta bort dem från tabellen.

**Relaterade ämnen:**
* [Förstå leveransfel](../../sending/using/understanding-delivery-failures.md)
* [E-poststudsar](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
