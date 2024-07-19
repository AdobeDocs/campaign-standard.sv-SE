---
title: Mallar för landningssidor
description: Läs mer om mallar för landningssidor.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 29d1badf-9ce3-470c-9bdc-169586d2e943
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 94%

---

# Om mallar för landningssidor {#landing-page-templates}

Campaign har en uppsättning inbyggda mallar för landningssidor:

* **[!UICONTROL Acquisition]**: Det här är standardmallen för landningssidor, som gör att du kan hämta och uppdatera data i Campaign-databasen.
* **[!UICONTROL Subscription]**: Den här mallen ska användas för att erbjuda prenumerationer på en tjänst.
* **[!UICONTROL Unsubscription]**: Den här mallen kan kopplas från ett e-postmeddelande som skickas till prenumeranter till en tjänst, så att de kan avbryta prenumerationen på tjänsten.
* **[!UICONTROL Denylist]**: Den här mallen ska användas när en profil inte längre vill bli kontaktad av Campaign. Mer information om hantering av blockeringslista finns i [Om deltagande och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

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
