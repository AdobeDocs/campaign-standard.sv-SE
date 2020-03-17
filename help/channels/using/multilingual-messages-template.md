---
title: Mallar för flerspråkiga meddelanden
description: Lär dig definiera och köra flerspråkiga e-post-/SMS-leveranser via en enda leverans baserat på det automatiskt segmenterade kundspråk du föredrar. Rapportera resultatet av varje leverans till språk och individuella nivåer.
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Mallar för flerspråkiga meddelanden {#multilingual-messages-template}

En flerspråkig mall är en specifik mall för hantering av flerspråkiga meddelanden. Den här typen av mall är tillgänglig för ****E-post** och **SMS-meddelanden** och kan användas i fristående läge, i ett arbetsflöde eller i en återkommande leverans.

I de flerspråkiga funktionsmallarna baseras språkhanteringen på varianter. **Varje variant representerar ett språk**. Adobe Campaign Standard kan konfigurera maximalt 40 varianter.

Adobe Campaign har ett standardspråk som är inställt på **EN**. Standardspråket kan ändras till en annan variant men ska aldrig tas bort.

När du skapar en mall kan du lägga till antalet varianter som motsvarar antalet språk som behövs i meddelandet.

Så här skapar du en SMS- eller e-postmall:

1. Duplicera en befintlig flerspråkig mall (SMS eller e-post).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Du kan också ändra en befintlig standardmall i en flerspråkig mall genom att klicka på **[!UICONTROL Initialize content variant]** knappen i mallegenskaperna.

1. Ändra egenskaperna för att anpassa etikett, spårning osv.
1. Ändra antalet önskade varianter genom att klicka på variantplattan. Variantfönstret visas

   ![](assets/multi_template_variants.png)

   Du kan lägga till eller ta bort varianter. Om du vill lägga till en variant fyller du i **[!UICONTROL New content variant]** fönstret.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Ta inte bort&quot;standardvarianten&quot; eftersom det är varianten som skickas till profiler utan en slutförd föredragen språkparameter.

1. Anpassa etikettvarianten om det behövs och klicka på **[!UICONTROL Confirm]**.
1. Du kan också lägga till innehåll direkt för varje variant.

Du kan nu skapa ett e-postmeddelande eller ett SMS-meddelande baserat på den här flerspråkiga mallen.

**Relaterade ämnen:**

* [Skapa ett flerspråkigt e-postmeddelande](../../channels/using/creating-a-multilingual-email.md)
* [Skapa profiler](../../audiences/using/creating-profiles.md)
