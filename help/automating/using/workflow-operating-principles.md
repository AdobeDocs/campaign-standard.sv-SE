---
title: Principer för arbetsflödesoperation
description: Lär dig de viktigaste aspekterna av arbetsflöden.
page-status-flag: never-activated
uuid: 85755e85-617b-4a9b-bb30-96ba8333f4f0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Principer för arbetsflödesoperation{#workflow-operating-principles}

Ett arbetsflöde är en **sekvens med konfigurerbara aktiviteter**. Varje aktivitet har en specifik roll i processen. Resultatet av varje aktivitet vidarebefordras till följande aktivitet med en **övergång**, som representeras av en pil.

Den typ av data som utbyts mellan olika aktiviteter kan påverka hur följande aktiviteter konfigureras. Om en ifyllnad till exempel har upprättats före e-postleveransaktiviteten kan den fungera som mål för e-postmeddelandet i fråga.

Du kan öppna aktiviteter för att kontrollera eller redigera parametrar före eller efter att arbetsflödet har körts.

Du kan öppna övergångar för att kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Om du vill få åtkomst till detaljvyn för övergångarna måste du markera **[!UICONTROL Keep interim results]** alternativet i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna.

![](assets/workflow_overview.png)

