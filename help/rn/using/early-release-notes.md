---
solution: Campaign Standard
product: campaign
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Översikt
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 89514dad1e318f32dafd3d8add664c37b03c8fb7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 45%

---

# Tidig versionsinformation {#new-release}

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).


## Version 21.3 – september 2021 {#release-21-3---sept-2021}


**Nyheter**


<table> 
<thead> 
<tr> 
<th> <strong>Enhetligt Experience Cloud-gränssnitt</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaigns huvudfält har ändrats för att ge dig en enhetlig och förbättrad upplevelse av alla produkter och tjänster i Experience Cloud. Dessa förändringar gör livet enklare – bland annat på följande sätt:</p>
<ul>
<li>Du kan enklare växla mellan olika organisationer och olika applikationer.</li>
<li>Användarhjälpen är förbättrad – Experience League tillförs till produkten, sökresultaten innehåller även resultat från användarforum och videoinnehållet har utökats, vilket ger dig enklare tillgång till mer innehåll som hjälper dig att få ut det mesta av programmet. Vi har också lagt till en funktion för feedback direkt i hjälpmenyn, så att du enklare kan rapportera problem eller dela dina idéer.</li>
<li>Förbättrade meddelanden – listrutan för meddelanden har nu två flikar: en för dina egna produktmeddelanden och en för globala produktmeddelanden.</li>
</ul>
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Granskningsspår</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Med den nya funktionen Granskningsspår kan du i realtid samla in en omfattande lista över åtgärder och händelser som inträffar i Adobe Campaign. Det innehåller ett självbetjäningssätt att komma åt en datahistorik som kan hjälpa dig att besvara frågor som:</p>
<ul>
<li>Vad hände med det här arbetsflödet och vem uppdaterade det senast?</li>
<li>Vilka var de senaste ändringarna?</li>
<li>Vilket var det tidigare tillståndet?</li>
</ul>
<p>Adobe Campaign granskar nu åtgärder för att skapa, redigera och ta bort: arbetsflöden, alternativ, anpassade resurser. Ändringarna av dessa objekt spåras också.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Diagnostikläge för arbetsflöde</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Nu kan du köra Campaign-arbetsflöden i diagnostikläge. I det här läget loggas information som kan hjälpa dig att felsöka körningsproblem. Hela körningsplanen loggas om en arbetsflödesfråga som standard tar mer än en minut.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**Förbättringar**

* När du skapar en återkommande leverans i ett arbetsflöde, som är länkad till ett Adobe Experience Manager-innehåll, kontrolleras statusen för innehållsgodkännande nu innan det skickas.
* Databasanslutningsgränsen är nu justerad mot Campaign-paketet för att undvika anslutningsfel.
* En konsekvenskontroll lades till när index skapades i anpassade resurser och felmeddelandena förbättrades.

**Felkorrigeringar**

* Korrigerade ett timeout-fel vid import av e-postinnehåll från en URL. (CAMP-49054)
* Korrigerade ett fel (-69) som orsakades av sessionens slut vid åtkomst till en URL med bokmärken eller uppdatering av en sida från webbläsaren. (CAMP-49003, CAMP-48930, CAMP-48894)
* Ett problem har korrigerats vid synkronisering av regler från den äldre leveransservern till den nya leveransservern. (CAMP-48923)
* Korrigerade ett problem när en e-postmall med HTML-taggar i e-postdesignern lästes in. (CAMP-48243)
