---
title: Spåra meddelanden
description: Lär dig hur du spårar hur leveransmottagarna fungerar.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 21%

---

# Spåra meddelanden{#tracking-messages}

## Om spårning {#about-tracking}

Tack vare spårningsfunktionerna i Adobe Campaign kan du spåra hur mottagarna beter sig. För att göra detta använder Adobe Campaign sessionscookies och permanenta cookies.

Du kan informera användare om att dina webbplatser är utrustade med verktyg för webbspårning via en auktoriseringsbegäran (som visas på sidan till exempel) med en kryssruta för att godkänna användningen av cookies, eller lägga till en banderoll högst upp på den första sidan som de landar på, osv. Popup-fönster bör undvikas eftersom de ofta blockeras av webbläsare.

Spårningsinformation finns tillgänglig för varje kontakt i databasen till **[!UICONTROL integrated customer profiles]**. Mer information om detta finns i [det här avsnittet](../../audiences/using/integrated-customer-profile.md).

Adobe Campaign använder två typer av cookies.

* En sessionscookie (nlid). Detta innehåller identifieraren för e-postmeddelandet som skickas till kontakten (broadlogId) och identifieraren för meddelandemallen (deliveryId). Den läggs till när kontakten klickar på en URL som ingår i ett e-postmeddelande som skickas av Adobe Campaign och låter dig spåra deras beteende på webben. Denna sessionscookie raderas automatiskt när webbläsaren stängs. Kontakten kan konfigurera sin webbläsare så att den inte tillåter cookies.
* En cookie som delas mellan Adobe Experience Cloud lösningar. På så sätt kan du identifiera de användare som interagerar med Experience Cloud när de besöker en webbplats. Beskrivningen av denna cookie är tillgänglig [här](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html).

Spårning med Adobe Campaign Standard ger åtkomst till följande funktioner:

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="villkor" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../administration/using/push-tracking.md"><img width="60px" alt="villkor" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="villkor" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="villkor" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="villkor" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>E-postspårning</td>
<td>Penselspårning</td>
<td>Spårade URL:er</td>
<td>Spårningsloggar</td>
<td>Spårningsrapport</td>
</tr>
</table>

## Spårningsloggar {#tracking-logs}

The **[!UICONTROL Tracking logs]** På -fliken visas spårningshistoriken för leveransen. På den här fliken visas spårningsinformation för skickade meddelanden, t.ex. alla URL:er som har spårats av Adobe Campaign. Spårningsinformationen på den här fliken uppdateras var 10:e minut.

>[!NOTE]
>
>Om spårning inte är aktiverat för en leverans visas inte den här fliken. Spårningsloggar finns tillgängliga för **e-post** och **push-meddelande** endast kanaler.

![](assets/tracking_logs.png)

I exemplet ovan:

* Meddelandet öppnades.
* Klicka på länken för spegelsidan.
* Klicka på den anpassade länken&quot;LÄS MER&quot;.

I **[!UICONTROL Type]** -kolumn är de möjliga värdena:

* **[!UICONTROL Email click]**: mottagarna klickade på en anpassad länk.
* **[!UICONTROL Mirror page]**: mottagaren klickade på en länk till spegelsidan.
* **[!UICONTROL Open]**: mottagaren öppnade e-postmeddelandet.
* **[!UICONTROL Opt-out]**: mottagaren klickade på en länk för att avbryta prenumerationen.

>[!NOTE]
>
>För **push-meddelande** kanaler spåras bara klickningar på mobilmeddelanden. I så fall blir värdet **[!UICONTROL Click on mobile notification]**.

Mer information om hur du infogar spårningslänkar finns i [den här sidan](../../designing/using/links.md#inserting-a-link).

The **[!UICONTROL Tracking indicators]** rapporten innehåller nyckelindikatorer för spårning av beteenden efter att e-postmeddelanden har tagits emot. Se denna [sida](../../reporting/using/tracking-indicators.md) för mer information om detta.

## Spårade URL:er {#tracked-urls}

The **[!UICONTROL Tracked URLs]** På fliken grupperas URL:erna i det skickade meddelandet, inklusive deras URL-typ och deras käll-URL.

![](assets/sending_delivery6.png)

Mer information om att spåra länkar finns i [det här avsnittet](../../designing/using/links.md#about-tracked-urls).
