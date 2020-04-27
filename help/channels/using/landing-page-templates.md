---
title: Mallar för landningssidor
description: Läs mer om landningssidmallar.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Om mallar för landningssidor {#landing-page-templates}

Campaign innehåller en uppsättning inbyggda mallar för landningssidor:

* **[!UICONTROL Acquisition]**: det här är standardmallen för landningssidor, som gör att du kan hämta och uppdatera data i Campaign-databasen.
* **[!UICONTROL Subscription]**: den här mallen ska användas för att erbjuda prenumerationer på en tjänst.
* **[!UICONTROL Unsubscription]**: den här mallen kan länkas från ett e-postmeddelande som skickas till prenumeranter på en tjänst, så att de kan avbryta prenumerationen på tjänsten.
* **[!UICONTROL Blacklist]**: den här mallen ska användas när en profil inte längre vill bli kontaktad av Campaign. Mer information om svartlistning finns i [Om deltagande och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Dessa mallar föreslås som standard när en ny landningssida skapas.

![](assets/lp_creation_1.png)

Om du vill komma åt landningssidmallar klickar du på Adobe Campaign-logotypen i det övre vänstra hörnet och väljer **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe rekommenderar att du skapar egna mallar genom att duplicera en inbyggd mall. Vissa parametrar kan bara anges i landningssidmallar och kan inte ändras direkt på landningssidor.

När du skapar en mall rekommenderar vi att du lägger till ett **&#39;type&#39;** -attribut till taggar. Den här informationen bearbetas av redigeraren och hjälper användaren att länka ett databasfält till formulärfältet när webbprogrammet konfigureras.

Exempel på HTML-kod i mallen:

```
<input id="email" type="email" name="email"/>
```

Den officiella listan med type-attribut finns på följande adress: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)