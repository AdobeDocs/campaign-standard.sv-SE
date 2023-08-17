---
title: Test
description: Testaktiviteten möjliggör en övergång baserat på ett testresultat.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 62a064f7-6d0b-49ca-9834-eccb5bf42496
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 82%

---

# Test{#test}

## Beskrivning {#description}

![](assets/test.png)

**[!UICONTROL Test]**-aktiviteten möjliggör en övergång baserat på ett testresultat.

## Kontext för användning {#context-of-use}

En **Test**-aktivitet aktiverar den första övergången som uppfyller det villkor som är associerat med den.

Om inget villkor är uppfyllt och alternativet **Använd standardövergång** är aktiverat så aktiveras en standardövergång.

![](assets/wkf_test_activity_example.png)

Villkoren kan baseras på **funktioner** eller på **variabler** som exempelvis händelsevariabler som har deklarerats i arbetsflödets **[!UICONTROL External signal]**-aktivitet.

**Relaterade ämnen:**

* [Lista över funktioner](../../automating/using/list-of-functions.md)
* [Anropa ett arbetsflöde med externa parametrar](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Test]**-aktivitet in i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.
1. Definiera attributen för varje villkor:

   När du redigerar **[!UICONTROL Condition]**-fältet så kan du använda två knappar för att anropa händelsevariabler och redigera uttryck som kombinerar variabler och funktioner:

   * ![](assets/extsignal_picker.png): välj händelsvariabeln bland alla variabler som är tillgängliga i arbetsflödet (se [den här sidan](../../automating/using/customizing-workflow-external-parameters.md)).

     Du kan till exempel kontrollera antalet hämtade filer efter en [Filöverföring](../../automating/using/transfer-file.md) aktivitet med **[!UICONTROL filesCount]** variabel.

     ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): redigera uttryck genom att kombinera variabler och funktioner.  Mer information om uttrycksredigeraren finns i [detta avsnittet](../../automating/using/advanced-expression-editing.md).

     ![](assets/wkf_test_activity_variables_expression.png)
