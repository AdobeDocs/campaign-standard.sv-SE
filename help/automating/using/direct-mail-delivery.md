---
title: Leverans av direktmeddelanden
description: Med aktiviteten Direktleverans av e-post kan du konfigurera sändning av ett direktmeddelande eller återkommande direktmeddelanden i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: directMail,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c7854b7b-f955-47ce-99d6-86b3186fd297
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 93%

---

# Leverans av direktutskick{#direct-mail-delivery}

## Beskrivning {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

Med **[!UICONTROL Direct mail delivery]**-aktiviteten kan du konfigurera och förbereda en fil som innehåller profildata som du vill använda för en kampanj för direktmeddelanden. Det kan vara en direktreklam som bara används en gång eller en återkommande direktreklam.

* **Standard** direktreklam skickas en gång.
* **Återkommande** Med hjälp av e-post kan du skicka samma direktreklam flera gånger till olika mål under en angiven period. Du kan samla leveranser per period för att få rapporter som motsvarar dina behov.

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL Direct mail delivery]** används vanligtvis för att automatisera förberedelsen av en fil som innehåller profildata. Den här filen kan sedan skickas till en partner/leverantör som ansvarar för utskicket.

När du är kopplad till en schemaläggare kan du definiera återkommande direktmeddelanden.

Mottagare av direktmeddelanden definieras i nästa led av aktiviteten i samma arbetsflöde, via målaktiviteter som frågor, skärningspunkter, o.s.v. Profiler vars utskicksadress inte anges utesluts automatiskt när direktmeddelanden förbereds.

Förberedelsen av meddelande utlöses enligt arbetsflödets körningsparametrar. Från kontrollpanelen för meddelanden kan du välja om du vill begära en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

**Relaterade ämnen:**

* [Användningsexempel: Koppla e-post och direktreklam](../../automating/using/coupling-email-direct-mail.md)
* [Om direktutskick](../../channels/using/about-direct-mail.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Direct mail delivery]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png)-knappen från aktivitetens snabbåtgärder. Den här knappen är specifik för kanalaktiviteterna. Du kommer åt egenskaperna för direktmeddelanden via åtgärdsfältet på kontrollpanelen för direktmeddelanden.

1. Välj sändningsläget för direktmeddelanden:

   * **[!UICONTROL Direct mail]**: Direktmeddelandet skickas en gång. Här kan du ange om du vill lägga till en utgående övergång till aktiviteten. De olika övergångstyperna beskrivs närmare i steg 7 i den här proceduren.
   * **[!UICONTROL Recurring direct mail]**: Direktmeddelandet skickas flera gånger, enligt den frekvens som definieras i en **[!UICONTROL Scheduler]**-aktivitet. Välj aggregeringsperioden för utskicken. Detta gör att du kan gruppera om alla meddelanden som inträffar under den angivna perioden i ett enda direktmeddelande som också kallas för **Återkommande körning** och som kan nås från programmets lista över marknadsföringsaktiviteter.

     Om du till exempel har ett återkommande födelsedags-e-postmeddelande, som bearbetas varje dag, kan du välja att samla in varje månad. Detta gör att du kan få rapporter om leveransen månadsvis, även om e-postmeddelandet bearbetas varje dag.

     >[!NOTE]
     >
     >För återkommande direktmeddelanden skapas en ny fil vid varje körning av arbetsflödet. Den valda aggregeringsperioden har ingen effekt på det här beteendet.

1. Välj en typ av direktmeddelande. Typerna av direktmeddelanden kommer från mallar som definieras på menyn **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Ange de allmänna egenskaperna för direktmeddelandet. Du kan även bifoga den till en befintlig kampanj. Etiketten för arbetsflödets leveransaktivitet uppdateras med etiketten för direktmeddelanden.
1. Definiera innehållet i direktmeddelanden. Se avsnittet om [innehållsredigering](../../designing/using/personalization.md).
1. Som standard innehåller aktiviteten **[!UICONTROL Direct mail delivery]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL Direct mail delivery]**-aktivitet går du till fliken **[!UICONTROL General]** med de avancerade aktivitetsalternativen (knappen ![](assets/dlv_activity_params-24px.png) i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången. Övergången innehåller den fil som genereras av aktiviteten för direktmeddelanden och råpopulationen som togs emot av aktiviteten för direktmeddelanden.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som direktmeddelandet ska skickas till. Målmedlemmarna uteslöts under förberedelse av direktmeddelande (karantän, ogiltig adress, o.s.v.) är undantagna från denna övergång. Övergången innehåller även filen som genereras av direktmeddelandet.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till kontrollpanelen för direktmeddelanden. Endast dess innehåll kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via kontrollpanelen för meddelanden, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]**-alternativet. Om du avmarkerar det här alternativet skickas meddelanden utan föregående meddelande när förberedelsen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Länkarna i rutan för sammanfattning av direktmeddelanden ger dig direktåtkomst till kopplade element (arbetsflöde, kampanj, överordnad leverans om det finns ett återkommande direktmeddelanden).

![](assets/wkf_display_parent_elements_direct_mail.png)

Körningarna av återkommande leveranser maskeras som standard. Om du vill visa dem markerar du **[!UICONTROL Show recurring executions]**-alternativet i marknadsföringsaktiviteternas sökpanel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

I de överordnade leveranserna, via listan över marknadsföringsaktiviteter eller direkt via de associerade återkommande körningarna, kan du visa det totala antalet skickade meddelanden som har bearbetats (enligt den aggregeringsperiod som angavs när **[!UICONTROL Direct mail delivery]**-aktiviteten konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]**-block genom att markera ![](assets/wkf_dlv_detail_button.png)-knappen.

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
