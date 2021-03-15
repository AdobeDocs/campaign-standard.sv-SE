---
solution: Campaign Standard
product: campaign
title: Felsökning
description: Lär dig hur du felsöker problem när du delar resurser.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Utlösare
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 1%

---


# Felsökning{#troubleshooting}

Fel kan påträffas vid användning av integreringen med huvudtjänsten Audience Manager eller People.

I så fall måste du kontrollera att följande element är korrekt konfigurerade:

* **Externa konton**

   Kontrollera att följande externa S3-konton är korrekt konfigurerade i **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**. De nämnda S3-servrarna bör ha konfigurerats under etableringen.

   * **[!UICONTROL importSharedAudience]**: S3-konto för att importera målgrupper.
   * **[!UICONTROL exportSharedAudience]**: S3-konto för export av målgrupper.

* **Delade datakällor**

   I **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** kontrollerar du att den delade datakällan är korrekt inställd.

   **[!UICONTROL Priority]** används när du har definierat flera datakällor. Prioriteten avgör vilken datakälla som ska användas för att matcha alias som tas emot i den definierade ordningen. **[!UICONTROL Priority]** behövs bara för implementering av utlösare.

   Kontrollera att avstämningsnyckeln är korrekt. Det är det hash-kodade/krypterade värdet för det här fältet som används för att exportera och importera målgrupper.

   Om det deklarerade ID:t hashas eller krypteras kontrollerar du att samma parametrar/krypteringsalgoritmer används på din webbplats.

   Endast en krypteringsalgoritm stöds: AES i CBC-läge med en nyckelstorlek på 128, 192 eller 256 bitar, med PKCS-utfyllnad.

   Om AES-krypteringsalgoritmen är markerad måste följande ytterligare fält anges korrekt:

   * **Krypteringsnyckel** för AES
   * **Kryptering IV**  (initieringsvektor) för AES
   * **Kanal**  (e-post/SMS/annan): I det här fältet kan du dekryptera e-postadresser och SMS-nummer direkt. Kontrollera att avstämningsnyckeln matchar inställningen för fältet **Kanal**. Om du väljer Annat kommer denna specifika dekryptering inte att ske och avstämningsnyckeln används för att stämma av data.

   Experience Cloud målgrupper kanske inte delas eftersom det tekniska arbetsflödet har stoppats eller pausats. Du kommer åt arbetsflödet **[!UICONTROL Import shared audience]** genom att klicka direkt på alternativet **[!UICONTROL Show ImportShared Audience workflow]** i datakällan.

Det kan inträffa att vissa data saknas när en målgrupp delas via personbastjänsten eller när en målgrupp importeras. Det är bara poster som ID:t (&#39;besökar-ID&#39; eller &#39;Deklarerat ID&#39;) kunde förenas med profildimensionen som överförs. ID:n från People core service segments som inte känns igen av Adobe Campaign importeras inte.
