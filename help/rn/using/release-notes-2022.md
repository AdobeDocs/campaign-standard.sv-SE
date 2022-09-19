---
title: Versionsinformation för 2022
description: Den här sidan innehåller alla versioner av Adobe Campaign Standard under 2022.
feature: Overview
role: User
level: Beginner
source-git-commit: 20a59e064afeb93a2a6260439b09790692971071
workflow-type: ht
source-wordcount: '1098'
ht-degree: 100%

---

# Versionsinformation för 2022{#release-notes-2022}

## Version 22.2 – juni 2022 {#june-2022}

**Förbättringar**

* **Adobes meddelandetjänst** – Campaign innehåller Adobes meddelandetjänst, som gör det möjligt för Experience Cloud-lösningar att avisera användare i Experience Cloud om aktiviteter som är viktiga för dem att känna till. Från och med version 22.2 har användarupplevelsen förbättrats: meddelanden prioriteras och produktgenererade meddelanden skiljs från statusmeddelanden i Adobe. När meddelandet dessutom hänvisar till ett specifikt arbetsflöde kan du nu komma åt motsvarande arbetsflöde direkt från e-postmeddelandet eller aviseringen i produkten.  Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

<!--
* **Optimization in Workflow startup** - Adobe has added a new capability which can tune the number of workflows that start around the same time. This would help prevent CPU spikes that could have led to service interruptions or downtime. Adobe would enable it after 22.2 release. There is no further action item on customer regarding the same.
-->

* **Tillgänglighet** – Adobe har gjort många tillgänglighetskorrigeringar för att förbättra programmets övergripande användarvänlighet. Dessa funktioner är för närvarande bara aktiverade för en uppsättning tidiga användare och kommer att introduceras för alla kunder i framtida versioner. Exempel på tillgänglighetsförbättringar inkluderar:

   * Kontrollera att det finns en synlig fokusindikator för fokuserbara element på varje skärm
   * Skapa landmärken för sidor för enklare navigering
   * Lägga till namn, roll, värde och tillstånd för många kontroller
   * Åtgärda problem med dynamisk fokusordning på huvudskärmar


**Felkorrigeringar**

* Korrigerade ett problem med det tekniska arbetsflödet för fakturering på grund av ett dubblettnyckelfel. (CAMP-51029)
* Lade till den saknade webbläsarkategorin Microsoft Edge i spårningsrapporter. De kategoriserades tidigare med Microsoft Chrome-öppningar. (CAMP-51165)
* Korrigerade ett problem med GDPR-begäranden som inte tog bort data från underordnade tabeller. (CAMP-48276)
* Korrigerade ett fel i e-postdesignern som gjorde att synlighetsvillkoret för ett fragment inte sparades i en transaktionsmeddelandemall. (CAMP-50338)
* Korrigerade ett problem i Campaign-rapporter som gjorde att datumintervallet inte kunde beaktas. (CAMP-50991)
* Korrigerade ett fel som gjorde att schemalagda e-postmeddelanden misslyckades: leveransanalysen kunde inte starta eftersom leveransen fortfarande hade statusen &quot;Nytt försök väntar&quot;. (CAMP-50302)
* Korrigerade ett problem i e-postdesignern vid förhandsgranskning av ett e-postmeddelande med en profilersättning. (CAMP-49312)
* Korrigerade ett problem med tomt värde i anpassade uppräkningar: när du skapar en anpassad resurs med ett fält som är en textuppräkning och bara innehåller ett värde, ställs det här värdet nu in som standard så att du kan skapa en fråga i det här fältet som en enkel begäran. (CAMP-50606)


## Version 22.1 – februari 2022 {#feb-2022}

**Nyheter**

<table> 
<thead> 
<tr> 
<th> <strong>Säkerhetsuppdatering för säkerhetssårbarheter i Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j har åtgärdat de rapporterade sårbarheterna i version 2.17.1 av Apache log4j. Adobe Campaign Standard använder Apache log4j och i den här versionen ingår den senaste Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Säkerhetskorrigeringar**

* Ny mekanism för URL-signering för spårning ingår i den här versionen. Den föregående mekanismen hade inaktiverats för att förhindra ett problem som gjorde att vissa giltiga, signerade spårningslänkar blockerades felaktigt efter att ha modifierats av tredjeparts säkerhetsverktyg. (CAMP-48983)

**Förbättringar**

* Förbättrad bearbetning av rapporteringsdata för att undvika överbelastning av systemet. (CAMP-47578)
* När du har skickat meddelanden i appen kan du nu välja att inaktivera leveransen. På så sätt kan du ta bort leveransen utan att förlora några rapporteringsdata. (CAMP-48469)
* För att förhindra problem kan användare inte längre använda samma namn för en anpassad tabellkolumn som den som används för den automatiska primärnyckeln i databasen. `"<dataType><resourceName>Id"`. (CAMP-49358)
* Du kan nu övervaka leveransen och spåra jobbloggar med den nya rullgardinsmenyn **Jobbhistorik** från kontrollpanelen för dina meddelanden. [Läs mer](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* Förbättrad stabilitet och databashälsa genom att minska antalet döda tupler när ett stort antal meddelanden skickas över alla kanaler över tiden. (CAMP-49755, CAMP-49792, CAMP-49849)
* För att säkerställa att databasanslutningar uppdateras automatiskt i händelse av databaskrasch eller omstart, har förbättringar implementerats i Campaign Mail Transfer Agent (MTA). (CAMP-48063)
* Ett nytt spårningsalternativ **Använd spårningspixel överst i e-postmeddelandet** har lagts till i e-postegenskaperna så att du kan flytta spårningspixeln överst i e-postmeddelandet i stället för längst ned. (CAMP-49672)

**Felkorrigeringar**

* Åtgärdade ett problem med alternativet **Skicka rapport nu** i dynamiska rapporter: PDF-genereringsjobben misslyckades med leveranser inklusive multivarianter. (CAMP-49120)
* Åtgärdade ett problem som hindrade användare från att uppdatera eller koppla bort Adobe Experience Manager-innehåll (AEM) från sina Adobe Campaign Standard-leveranser när ett duplicerat innehåll i AEM delade samma nyckel (cq:uuid). (CAMP-49161)
* Åtgärdade ett fel vid åtkomst till en instans där sidor inte laddades, leveranser inte kunde öppnas eller pågående ändringar inte kunde sparas. (CAMP-50195)
* Åtgärdade ett problem som förhindrade att leveransvarningskriterier kunde öppnas om fältet **Leveransfilter** som tillämpas av detta kriterium inte fylldes i. (CAMP-49093)
* Åtgärdade ett problem vid redigering av knappen **Sekundär** i leveranser i appen som förhindrade att ändringar togs i beaktande. (CAMP-50250)
* Åtgärdade ett fel i japanska instanser som hindrade användare från att välja Flera gånger om dagen som **Körningsfrekvens** i aktiviteten i **Schemaläggare**. (CAMP-50247)
* Åtgärdade ett problem när du arbetade i ett japanskt användargränssnitt som visade ett felmeddelande när du valde en tid i en aktivitet i Schemaläggare. (CAMP-49289)
* Åtgärdade ett fel med rapporter om push-meddelanden som visade avvisade push-meddelanden som **öppnat** istället för **visat**. (CAMP-45980)
* Åtgärdade ett problem som kunde leda till fel när en rapport öppnades. (CAMP-49222)
* Åtgärdade ett problem som kunde leda till att e-postförberedelsen misslyckades efter att ha tagit bort en länk till AEM-innehåll. (CAMP-49877)
* Återförsöksmekanismen har förbättrats för leveranser, inklusive innehåll som importerats från en URL, för att åtgärda olika problem. [Läs mer](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Åtgärdade ett problem som uppstod efter att ett nytt filter skapades i en anpassad resurs och sedan användes som en avstämningsnyckel på en landningssida. Om den anpassade resursen publicerades igen togs filtret bort från listan över tillgängliga avstämningsnycklar för landningssidan. (CAMP-49516)
* Åtgärdade ett problem på landningssidor vid användning av dynamiska villkor med kryssrutor. (CAMP-48604)
* Fixade ett problem som uppstod i en **Fråga**-aktivitet när filtervillkoret &quot;On or before October&quot; användes. När du arbetade från en instans inställd på en europeisk tidszon visade den valda månaden för filtret september i stället för oktober på grund av ett problem när tidszonen konverterades. (CAMP-48602)
* För att optimera leveransmöjligheterna skickar Adobe Campaign nu e-postmeddelanden med 7-bitars kodning i stället för 8-bitars. Detta förhindrar mellanliggande reläer från att ogiltigförklara DKIM-signaturen, vilket kan påverka meddelandenas äkthet. (CAMP-49016)
* Prestanda vid duplicering av målgrupper har förbättrats för att undvika problem när man arbetar med stora målgrupper. (CAMP-49639)
* Åtgärdade ett problem som kunde hindra ett anpassat filter från att visa rätt resultat när det användes i en **Fråga**-aktivitet. (CAMP-49417)
* Åtgärdade ett fel som visade ett felmeddelande när ett fragment skulle användas i en leverans med kommatecken i namnet. Problemet har åtgärdats, kommatecken kan nu användas i fragmentnamn. (CAMP-49216)

