---
title: Mallar för landningssidor
description: Läs mer om mallar för landningssidor.
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
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Om mallar för landningssidor {#landing-page-templates}

Campaign har en uppsättning inbyggda mallar för landningssidor:

* **[!UICONTROL Acquisition]**: Det här är standardmallen för landningssidor, som gör att du kan hämta och uppdatera data i Campaign-databasen.
* **[!UICONTROL Subscription]**: Den här mallen ska användas för att erbjuda prenumerationer på en tjänst.
* **[!UICONTROL Unsubscription]**: Den här mallen kan kopplas från ett e-postmeddelande som skickas till prenumeranter till en tjänst, så att de kan avbryta prenumerationen på tjänsten.
* **[!UICONTROL Denylist]**: Den här mallen ska användas när en profil inte längre vill bli kontaktad av Campaign. For more about denylist management, refer to [About opt-in and opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Dessa mallar föreslås som standard när en ny landningssida skapas.

![](assets/lp_creation_1.png)

Om du vill ha åtkomst till mallar för landningssidor klickar du på Adobe Campaign-logotypen i det övre vänstra hörnet och väljer **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe rekommenderar att du skapar egna mallar genom att duplicera en inbyggd mall. Vissa parametrar kan bara anges i mallar för landningssidor och kan inte ändras direkt på landningssidor.

När du skapar en mall rekommenderar vi att du lägger till ett **&quot;type&quot;**-attribut till taggar. Den här informationen bearbetas av redigeraren och hjälper användaren att koppla ett databasfält till formulärfältet när webbprogrammet konfigureras.

Exempel på HTML-kod i mallen:

```
<input id="email" type="email" name="email"/>
```

Den officiella listan med &quot;type&quot;-attribut finns på följande adress: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)

