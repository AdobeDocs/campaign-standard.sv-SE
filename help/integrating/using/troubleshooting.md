---
title: Felsöka integreringsproblem
description: Lär dig hur du felsöker problem när du delar resurser.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Felsökning{#troubleshooting}

Fel kan påträffas vid användning av integreringen med huvudtjänsten Audience Manager eller People.

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
   * **Kryptering IV** (Initialiseringsvektor) för AES
   * **Kanal** (E-post/SMS/Annat): I det här fältet kan du dekryptera e-postadresser och SMS-nummer direkt. Kontrollera att avstämningsnyckeln matchar inställningen för **Kanal** fält. Om du väljer Annat kommer denna specifika dekryptering inte att ske och avstämningsnyckeln används för att stämma av data.

  Experience Cloud målgrupper kanske inte delas eftersom det tekniska arbetsflödet har stoppats eller pausats. Öppna **[!UICONTROL Import shared audience]** genom att klicka direkt på **[!UICONTROL Show ImportShared Audience workflow]** i datakällan.

Det kan inträffa att vissa data saknas när en målgrupp delas via personbastjänsten eller när en målgrupp importeras. Det är bara poster som ID:t (&#39;besökar-ID&#39; eller &#39;Deklarerat ID&#39;) kunde förenas med profildimensionen som överförs. ID:n från People core service segments som inte känns igen av Adobe Campaign importeras inte.
