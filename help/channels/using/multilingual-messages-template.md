---
title: Mallar för flerspråkiga meddelanden
description: Lär dig definiera och köra flerspråkiga e-post och SMS-leveranser genom en enda leverans baserat på det automatiskt segmenterade kundspråk som du föredrar. Rapportera resultatet av varje leverans på såväl språknivåer som individuella nivåer.
audience: start
content-type: reference
topic-tags: managing-templates
feature: Multilingual Messages
role: User
level: Intermediate
exl-id: 3d869f31-7dfb-4546-aba5-80a2787e00be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 100%

---

# Mallar för flerspråkiga meddelanden {#multilingual-messages-template}

En flerspråkig mall är en specifik mall för hantering av meddelanden på flera språk. Den här typen av mall är tillgänglig för **e-post** och **SMS-meddelanden** och kan användas i fristående läge, i ett arbetsflöde eller i en återkommande leverans.

I de flerspråkiga funktionsmallarna baseras språkhanteringen på varianter.    **Varje variant representerar ett språk**.  Adobe Campaign Standard kan maximalt konfigurera 40 varianter.

Adobe Campaign har ett standardspråk som är inställt på **EN**.  Standardspråket kan ändras till en annan variant men bör aldrig tas bort.

När du skapar en mall kan du lägga till antalet varianter som motsvarar antalet språk som behövs i meddelandet.

Så här skapar du en mall för SMS eller e-post:

1. Duplicera en befintlig flerspråkig mall (SMS eller e-post).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Du kan också ändra en befintlig standardmall i en flerspråkig mall genom att klicka på knappen **[!UICONTROL Initialize content variant]** i mallegenskaperna.

1. Ändra egenskaperna för att anpassa etikett, spårning etc.

1. Ändra antalet önskade varianter genom att klicka på variant-ikonen.  Fönstret för varianter visas

   ![](assets/multi_template_variants.png)

   Du kan lägga till eller ta bort varianter.  Om du vill lägga till en variant fyller du i **[!UICONTROL New content variant]**-fönstret.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Ta inte bort &quot;standardvarianten&quot; eftersom det är varianten som skickas till profiler utan en vald föredragen språkparameter.

1. Anpassa etikettvarianten om det behövs och klicka på **[!UICONTROL Confirm]**.

1. Du kan också direkt lägga till innehåll för varje variant.

Du kan nu skapa ett e-post eller SMS-meddelande baserat på den här flerspråkiga mallen.

**Relaterade ämnen:**

* [Skapa ett flerspråkigt e-postmeddelande](../../channels/using/creating-a-multilingual-email.md)
* [Skapa profiler](../../audiences/using/creating-profiles.md)
