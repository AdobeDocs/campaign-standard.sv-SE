---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 10%

---

# Tidig versionsinformation {#new-release}

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 22.1 – februari 2022 {#feb-2022}


**Nyheter**


<table> 
<thead> 
<tr> 
<th> <strong>Säkerhetsuppdatering för Apache Log4j Security Vulnerabilities</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j har åtgärdat de rapporterade säkerhetsluckorna i version 2.17.1 av Apache log4j. Adobe Campaign Standard använder Apache log4j och i den här versionen ingår den senaste versionen av Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Säkerhetskorrigeringar**

* Ny mekanism för URL-signering för spårning som ingår i den här versionen. Den tidigare funktionen hade inaktiverats för att förhindra ett problem som orsakade att vissa giltiga signerade spårningslänkar blockerades felaktigt efter att ha ändrats av säkerhetsverktyg från tredje part. (CAMP-48983)

**Förbättringar**

* Förbättrad bearbetning av rapportdata för att undvika överbelastning av systemet. (CAMP-47578)
* När du har skickat meddelanden i appen kan du nu välja att inaktivera leveransen. På så sätt kan du ta bort leveransen utan att förlora några rapportdata. (CAMP-48469)
* För att förhindra problem kan användare inte längre använda samma namn för en anpassad tabellkolumn som den som används för den automatiska primärnyckeln i databasen. `"<dataType><resourceName>Id"`. (CAMP-49358)
* Nu kan du övervaka leveransen och spåra jobbloggar med nya **Jobbhistorik** nedrullningsbar meny från meddelandets kontrollpanel. (CAMP-49840)
* Förbättrad stabilitet och databashälsa genom att minska antalet döda tupplar när ett stort antal meddelanden skickas över alla kanaler över tiden. (CAMP-49755, CAMP-49792, CAMP-49849)
* För att databasanslutningarna ska uppdateras automatiskt om databasen kraschar eller startas om har förbättringar implementerats i Campaign Mail Transfer Agent (MTA). (CAMP-48063)


**Felkorrigeringar**

* Ett problem med **Skicka rapporten nu** i Dynamiska rapporter: PDF-genereringsjobben misslyckades med leveranser inklusive multivarianter. (CAMP-49120)
* Ett problem som gjorde att användare inte kunde uppdatera eller bryta länken till Adobe Experience Manager (AEM)-innehåll från sina Adobe Campaign Standard-leveranser när ett duplicerat innehåll i AEM delade samma nyckel (cq:uuid) har åtgärdats. (CAMP-49161)
* Korrigerade ett fel vid åtkomst till en instans där sidorna inte lästes in, leveranser inte kunde öppnas eller väntande ändringar inte kunde sparas. (CAMP-50195)
* Korrigerade ett problem som förhindrade att leveransvarningsvillkor skulle öppnas om fältet **Leveransfilter** som tillämpas enligt detta kriterium inte har fyllts i. (CAMP-49093)
* Ett problem har korrigerats vid redigering av **Sekundär** -knappen i leveranser i appen som förhindrar att ändringar beaktas. (CAMP-50250)
* Korrigerade ett fel i japanska förekomster som hindrade användare att välja flera gånger om dagen som **Körningsfrekvens** i **Schemaläggare** aktivitet. (CAMP-50247)
* Korrigerade ett problem när du arbetade i ett japanskt användargränssnitt som visade ett felmeddelande när du valde en tid i en schemaläggaraktivitet. (CAMP-49289)
* Korrigerat ett fel med push-meddelanderapporter som visade inaktiverade push-meddelanden som **Öppna** i stället för **Impression**. (CAMP-45980)
* Korrigerade ett problem som kunde leda till fel när en rapport öppnades. (CAMP-49222)
* Korrigerade ett problem som kunde leda till att e-postförberedelserna misslyckades efter att en länk till AEM tagits bort. (CAMP-49877)
* För att lösa olika problem har återförsöksmekanismen förbättrats för leveranser inklusive innehåll som importerats från en URL. (CAMP-48888)
* Korrigerade ett problem som uppstod efter att ett nytt filter skapades i en anpassad resurs och sedan användes som en avstämningsnyckel på en landningssida. Om den anpassade resursen publicerades igen togs filtret bort från listan över tillgängliga avstämningsnycklar för landningssidan. (CAMP-49516)
* Korrigerade ett problem på landningssidor vid användning av dynamiska villkor med kryssrutor. (CAMP-48604)
* Ett problem som uppstod i en **Fråga** aktivitet när filtervillkoret &quot;På eller före oktober&quot; används. När du arbetade från en instans inställd på en europeisk tidszon visade den valda månaden för filtret september i stället för oktober på grund av ett problem när tidszonen konverterades. (CAMP-48602)
* För att optimera leveransmöjligheterna skickar Adobe Campaign nu e-postmeddelanden med 7-bitars kodning i stället för 8-bitars. Detta förhindrar att mellanliggande relä gör DKIM-signaturen ogiltig vilket kan påverka meddelandets autenticitet. (CAMP-49016)
* Prestanda vid duplicering av målgrupper har förbättrats för att undvika problem när man arbetar med stora målgrupper. (CAMP-49639)
* Ett problem som kunde förhindra att ett anpassat filter visade rätt resultat när det användes i en **Fråga** aktivitet. (CAMP-49417)
* Korrigerade ett fel som visade ett felmeddelande när ett fragment skulle användas i en leverans med kommatecken i dess namn. Problemet har lösts, kommatecken kan nu användas i fragmentnamn. (CAMP-49216)