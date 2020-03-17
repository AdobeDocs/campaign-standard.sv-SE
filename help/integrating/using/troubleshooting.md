---
title: Felsökning
description: Lär dig hur du felsöker problem när du delar resurser.
page-status-flag: never-activated
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Felsökning{#troubleshooting}

Fel kan påträffas vid användning av integreringen med Audience Manager eller People core service.

I så fall måste du kontrollera att följande element är korrekt konfigurerade:

* **Externa konton**

   I **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]** kontrollerar du att följande externa S3-konton är korrekt konfigurerade. De nämnda S3-servrarna bör ha konfigurerats under etableringen.

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
   * **Kryptering IV** (initieringsvektor) för AES
   * **Kanal** (e-post/SMS/annan): I det här fältet kan du dekryptera e-postadresser och SMS-nummer direkt. Kontrollera att avstämningsnyckeln matchar inställningen för fältet **Kanal** . Om du väljer Annat kommer denna specifika dekryptering inte att ske och avstämningsnyckeln används för att stämma av data.
   Experience Cloud-målgrupper kanske inte delas eftersom det tekniska arbetsflödet har stoppats eller pausats. Du kommer åt **[!UICONTROL Import shared audience]** arbetsflödet genom att klicka direkt på **[!UICONTROL Show ImportShared Audience workflow]** alternativet i datakällan.

Det kan inträffa att vissa data saknas när en målgrupp delas via personbastjänsten eller när en målgrupp importeras. Endast poster som ID:t (&quot;besökar-ID&quot; eller&quot;Deklarerat ID&quot;) kunde förenas med profildimensionen överförs. ID:n från People core service segments som inte känns igen av Adobe Campaign importeras inte.
