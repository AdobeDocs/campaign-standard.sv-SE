---
solution: Campaign Standard
product: campaign
title: Starta en ny plattform med Adobe Campaign Standard
description: Lär dig hur du konfigurerar en ny plattform samtidigt som du bibehåller domänens och IP-adressens anseende med Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Starta en ny plattform{#starting-new-platform}

Det är viktigt att du behåller domänens och IP-adressens anseende. Här är några råd om hur du skapar en ny plattform.

Att börja skicka e-postmeddelanden på en ny plattform är ett känsligt steg eftersom plattformen inte har någon användarhistorik och inget anseende (när de avsändande IP-adresserna aldrig har använts för detta ändamål). Internetleverantörer misstänker naturligtvis IP-adresser som aldrig har använts för att skicka e-post och som plötsligt börjar skicka stora volymer e-posttrafik. Det innebär att skräppost i allmänhet använder&quot;okända&quot; IP-adresser (adresser som aldrig har lagts till i blockeringslista) för att skicka så många meddelanden som möjligt innan de upptäcks.

Du kan inte förvänta dig att uppnå driftshastighet i form av utdata i början av produktionsfasen. Du bör inte heller försöka skicka meddelanden i den här hastigheten eftersom det kan leda till att internetleverantörerna blockerar sändningsadresserna och allvarligt äventyrar resten av startfasen.

Det händer ofta att en plattform startas när en adresslista används för första gången och som kanske inte är fullständigt kvalificerad. Om du skickar till ogiltiga adresser eller till honeypoadresser kommer detta att bidra till att minska plattformens anseende.
* Om du har en lista med ogiltiga adresser är det bäst att importera den till karantäntabellen (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) innan du skickar den första gången. Mer information finns i [det här avsnittet](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Om du ändå vill ange de ogiltiga adresserna är det bäst att göra detta när plattformens rykte väl har etablerats och bitvis för att &quot;tona ned&quot; användningen av dåliga adresser över tiden.

Sammanfattning av de principer som ska följas vid starten:
* **Konfigurera en dedikerad** underdomän i Campaign som är specifik för e-postkampanjer som skickas från Adobe.
* **Importera ogiltiga/inaktiva adresser till karantäntabellen**  (om du har den här informationen).
* **Begränsa leveransflödet** (teknisk inställning: begränsa antalet matriser).
* **Öka volymen som skickas** progressivt: inte för hela databasen från början, utan lägger till en extra del av listan varje gång du skickar. Detta bör göra att du kan öka volymen i varje steg och samtidigt minska den totala hastigheten för ogiltiga adresser.
* **Skicka meddelanden regelbundet**: I viss utsträckning är det bättre att skicka små tagningar regelbundet i stället för stora kampanjer sporadiskt.
* **Övervaka leveransrapporterna** noggrant: högfelsindikatorer kan innebära att en teknisk inställning är dåligt konfigurerad.
