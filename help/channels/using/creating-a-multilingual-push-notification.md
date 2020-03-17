---
title: Skapa ett flerspråkigt push-meddelande
description: Skapa flerspråkiga push-meddelanden som riktar sig till användarna på de språk och i de regioner de föredrar.
page-status-flag: never-activated
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# Skapa ett flerspråkigt push-meddelande{#creating-a-multilingual-push-notification}

## Om flerspråkig push-meddelanden {#about-multilingual-push-notification}

Anpassa innehållet i push-meddelanden genom att skicka meddelanden baserat på de språk och regioner användarna föredrar. Du kan importera innehållsvarianter för flerspråkiga push-meddelanden direkt i innehållsredigeraren och skicka ett flerspråkigt push-meddelande i en enda leverans.

Den här funktionen utnyttjar antingen önskade språk som anges i mottagarnas profiler eller systemspråkinställningen för mobilappsprenumeranter beroende på leveransmallen som används för push-meddelanden. Om språkinställningen inte fylls i för en viss användare använder systemet standardvarianten som definieras när ett flerspråkigt push-meddelande skapas. Mer information om hur du hanterar dina profiler och prenumeranter finns i den här [handboken](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Följ de här stegen om du vill använda flerspråkiga innehållsvarianter för leverans av push-meddelanden:

* [Steg 1: Överför variant av flerspråkigt innehåll](#step-1--upload-multilingual-content-variant)
* [Steg 2: Förhandsgranska och färdigställa ett push-meddelande med flerspråkiga innehållsvarianter](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Steg 3: Skicka och analysera flerspråkig leverans av push-meddelanden](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Steg 1: Överför variant av flerspråkigt innehåll {#step-1--upload-multilingual-content-variant}

Innan vi personaliserar ditt flerspråkiga push-meddelande måste vi först överföra innehållsvarianterna i en flerspråkig leveransmall och skapa leveransen.

>[!NOTE]
>
>Du kan också hoppa över det här steget om du vill skapa en variant manuellt för varje språkvariant.

1. Klicka på **[!UICONTROL Marketing activities]** knappen och **[!UICONTROL Create]** markera sedan **[!UICONTROL Push notification]**.
1. Välj mallen **[!UICONTROL Send multilingual push to Campaign profiles]** om du vill ange Adobe Campaign-profiler som prenumererar på ditt mobilprogram eller mallen som mål **[!UICONTROL Send multilingual push to app subscriber]** att skicka ett push-meddelande till alla användare som har valt att ta emot meddelanden från ditt mobilprogram.

   ![](assets/multivariant_push_2.png)

1. Ange dina egenskaper för push-meddelanden och välj din mobilapp i **[!UICONTROL Associate a Mobile App to a delivery]** fältet.

   Observera att listrutan kommer att visa både SDK V4- och SDK-program för Adobe Experience Platform.

1. I **[!UICONTROL Audiences]** fönstren kan du finjustera målgruppen genom att dra och släppa frågor.

   Vilka frågor som läggs till beror på den valda mallen: om du väljer **[!UICONTROL Send multilingual push to Campaign profiles]** mallen kan du fråga kända mottagare av ditt mobilprogram. Om du väljer **[!UICONTROL Send multilingual push to app subscriber]** mall kan du fråga alla prenumeranter på ett visst program som har valt det.
   >[!NOTE]
   >
   >Om ni riktar er till målgrupper med specifika språk måste ni ange alla målspråk i CSV-filen.

   ![](assets/push_notif_audience.png)

1. Dra och släpp filen i **[!UICONTROL Manage Content Variants]** fönstret eller välj en fil på datorn.

   Filen måste vara UTF8-kodad och ha en viss layout som du kan hitta genom att klicka på **[!UICONTROL Download the sample file]** alternativet. Du bör också använda rätt syntax för nationella värden. Mer information om filformat och vilka språk som stöds finns i den här [tekniken](https://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. När du har överfört filen fylls språkvarianterna automatiskt i på **[!UICONTROL Variants]** fliken. Observera att du kan ange en **[!UICONTROL Default variant]** i filen som ska vara standardvariant av innehåll om inget önskat språk har angetts för målanvändaren.

   ![](assets/multivariant_push_5.png)

1. På fliken **[!UICONTROL Variant selection]** finns ett skript som du kan använda för att avgöra vilka språkinställningar som ska användas beroende på leveransmallen. Det här är ett skript som inte finns i kartongen och som inte kräver att du gör några ändringar.
1. Om du vill lägga till fler varianter som inte finns i den importerade filen kan du göra det genom att klicka på **[!UICONTROL Add an element]** knappen och lägga till så många nya språkvarianter som behövs.

   Genom att lägga till andra varianter än de som överförts från filen kommer inget innehåll att länkas till det här språket. Du måste redigera innehållet direkt på kontrollpanelen för leverans.

   ![](assets/multivariant_push_6.png)

1. Klicka **[!UICONTROL Create]** när konfigurationen är klar. Du kan alltid gå tillbaka till **[!UICONTROL Content variant]** fönstret och göra några ändringar från kontrollpanelen för leverans.

   ![](assets/multivariant_push_8.png)

Nu kan du börja personalisera ditt flerspråkiga push-meddelande.

## Steg 2: Förhandsgranska och färdigställa ett push-meddelande med flerspråkiga innehållsvarianter {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

När du har överfört filen som innehåller innehållsvarianter kan du nu förhandsgranska de olika varianterna från leveransen av push-meddelanden.

Det går också att skapa och redigera fler varianter utöver de som har överförts från filen.

1. I fönstret från kontrollpanelen för leveranser kan du förhandsgranska ditt push-meddelandeinnehåll beroende på vilket språk du väljer i listrutan. **[!UICONTROL Content]**

   ![](assets/multivariant_push_7.png)

1. Om ingen innehållsvariant har angetts för ett visst språk klickar du på klockikonen under förhandsvisningen för att börja lägga till innehåll i den här språkvarianten.

   Genom att klicka på **[!UICONTROL Content]** fönstret representerar push-meddelandet innehållet från det språk som valts i listrutan. Ändringar som görs i det här fönstret påverkar bara ett språk.

1. Du kan också klicka på en innehållsvariant för att anpassa den ytterligare, till exempel med personaliseringsfält.

   Mer information om hur du anpassar push-meddelanden finns i det här [avsnittet](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Klicka i **[!UICONTROL Content variant]** fönstret om du vill lägga till eller ta bort språkvarianter.

   Observera att om du lägger till ett nytt språk måste du manuellt lägga till innehåll i push-meddelandet som är länkat till det tillagda språket.

   ![](assets/multivariant_push_10.png)

Din flerspråkiga push-meddelandeleverans är nu klar att skickas.

## Steg 3: Skicka och analysera flerspråkig leverans av push-meddelanden {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Dina flerspråkiga innehållsvariantmeddelanden kan nu skickas till dina användare.

1. Klicka på **[!UICONTROL Prepare]** knappen för att börja förbereda sändningen.
1. När färdigställandet är klart utan varningar kan du klicka på **[!UICONTROL Confirm]** knappen för att börja skicka ditt flerspråkiga tryck.

   ![](assets/multivariant_push_12.png)

1. När du har skickat push-meddelandet klickar du på **[!UICONTROL Reports]** ikonen och analyserar **[!UICONTROL Dynamic reports]** om leveransen lyckades.

   ![](assets/multivariant_push_13.png)

1. Välj **[!UICONTROL Push notification report]**.
1. Dra och släpp **[!UICONTROL Variant]** dimensionen på panelen för att börja filtrera data.

   ![](assets/multivariant_push_11.png)

Nu kan du mäta effekten av den flerspråkiga push-meddelandeleveransen på mottagarna.

**Relaterade ämnen:**

* [Rapport om push-meddelanden](../../reporting/using/push-notification-report.md)
* [Skicka ett push-meddelande inom ett arbetsflöde](../../automating/using/push-notification-delivery.md)
* [Att nå flerspråkiga målgrupper med ett och samma arbetsflöde](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
