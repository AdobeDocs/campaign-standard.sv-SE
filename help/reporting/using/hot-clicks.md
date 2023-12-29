---
title: Snabbklick
description: Med rapporten Hot Click out-of-the-box kan du ta reda på var kunden klickade på leveransen.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Snabbklick{#hot-clicks}

Den här rapporten kan du få åtkomst till via **[!UICONTROL Reports]** i varje leverans- eller transaktionsmeddelande.

![](assets/delivery_reports_hot-clicks_4.png)

Det visar meddelandeinnehållet (HTML och/eller text) med procentandelen klick på varje länk.

![](assets/delivery_reports_10.png)

Om du har skapat dynamiskt innehåll för leveransen kan du visa procentsatserna för varje villkor som du har definierat. Mer information om hur du infogar villkorsstyrt innehåll i en leverans finns i [Definiera dynamiskt innehåll](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Tänk dig att du har skapat en leverans med följande villkor:

* Länken på huvudbilden är annorlunda om mottagaren är en man eller kvinna.
* Du har också lagt till en länk till ett specialerbjudande som bara är synligt för mottagare över 25 år.

När meddelandet har skickats väljer du **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** från kontrollpanelen för leverans.

Som standard är ingen profil vald. Endast klick för mottagare vars kön är okänd och för mottagare som är under 25 år eller vars ålder är okänd visas.

![](assets/delivery_reports_hot-clicks_1.png)

Klicka på knappen **[!UICONTROL Change profile]** och välj en hontestprofil. Om du vill visa klick för män fortsätter du på liknande sätt och väljer en manlig testprofil.

![](assets/delivery_reports_hot-clicks_2.png)

Om du vill visa klick för mottagare över 25 klickar du på **[!UICONTROL Change profile]** och välj en testprofil vars födelsedatum matchar det här villkoret.

Mer information om testprofiler finns i [Om testprofiler](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>Antalet klick på en viss länk är en procentandel av det totala antalet klick för allt villkorat innehåll i en leverans. Om du har definierat dynamiskt innehåll kanske inte summan av procentsatserna som visas för en viss testprofil är lika med 100.

På samma sätt kan du för återkommande leveranser och transaktionsmeddelanden välja den testprofil som motsvarar det dynamiska innehåll som du vill visa, men du kan också visa klickprocenten enligt den valda körningsleveransen.

En körningsleverans är ett icke-åtgärdbart och icke-funktionellt tekniskt meddelande som skapas i följande fall:

* Varje gång en återkommande leverans körs eller uppdateras.

  Om arbetsflödet som hanterar den här leveransen till exempel körs en gång i månaden kommer det att finnas en körningsleverans per månad. Dessutom skapas ytterligare en körningsleverans varje gång innehållet i leveransen uppdateras.

  Mer information om återkommande e-postleveranser finns i [E-postleverans](../../automating/using/email-delivery.md).

* Som standard en gång i månaden för transaktionsmeddelanden, och varje gång som ett transaktionsmeddelande redigeras och publiceras igen.

  Mer information om transaktionsmeddelanden finns i [Komma igång med transaktionsmeddelanden](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Eftersom de spårade URL:ernas ID:n är olika för varje körning, kan inte klickdata aggregeras för alla körningsleveranser för ett visst meddelande. Den kan bara visas för en körningsleverans i taget.

När meddelandet har skickats väljer du **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** från kontrollpanelen för leverans.

Som standard är den senaste körningsleveransen vald. Klicka på **[!UICONTROL Change execution delivery]** om du vill välja en annan.

![](assets/delivery_reports_hot-clicks_3.png)

Endast klickprocenten för den valda leveranskörningen visas.
