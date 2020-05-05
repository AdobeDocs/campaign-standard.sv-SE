---
title: Importera data med importmallar
description: Lär dig hur du samlar in data för att mata in Campaign-databasen.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Importera data med importmallar{#importing-data-with-import-templates}

Genom att importera data kan ni samla in data för att mata in Campaigns databas.

I stället för [arbetsflöden](../../automating/using/get-started-workflows.md)erbjuder Adobe Campaign en förenklad importfunktion som gör att användaren kan hantera vissa typer av import som definierats av en administratör.

Följande princip gäller: en **administratör** definierar och hanterar importmallar (se [Definiera importmallar](../../automating/using/defining-import-templates.md)). Dessa importmallar är sedan tillgängliga för användare med förenklade vyer på menyn **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Dessa användare behöver därför bara välja vilken typ av import de vill utföra och överföra filen med de data som ska importeras. Det arbetsflöde som definieras av administratören körs transparent för användaren, som kan komma åt information om resultatet av importen när den är klar.

>[!NOTE]
>
>Funktionen Importera data kan hanteras av användare med rollerna **[!UICONTROL GENERIC IMPORT (import)]** och **[!UICONTROL WORKFLOW (workflow)]**. Mer information om roller finns i [det här avsnittet](../../administration/using/list-of-roles.md).

Import kan filtreras efter den mall som de kördes från, deras körningsdatum och deras körningsstatus.

1. Klicka på **[!UICONTROL Create]** knappen i importöversikten. Guiden öppnas.
1. Välj vilken typ av import du vill utföra. Importtyperna motsvarar de tillgängliga importmallarna.
1. Hämta vid behov exempelfilen som är länkad till mallen till datorn för att visa de datatyper som förväntas i filen som ska importeras.
1. Hämta filen som innehåller de data som ska importeras i guiden.
1. Starta importen. Guiden stängs och tar dig tillbaka till listan över importer som har utförts med mallen som används.
1. Uppdatera sidan och välj den import du just har utfört för att visa körningsinformationen.

   ![](assets/simplified_import1.png)

Information om importkörningen är nu tillgänglig. Både filen som importerades och filen som innehåller avvisade data (data som inte importerades) kan hämtas till datorn.
