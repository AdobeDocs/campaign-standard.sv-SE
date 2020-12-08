---
solution: Campaign Standard
product: campaign
title: 'Förteckning över komponenter '
description: Här finns en lista med alla komponenter som finns i     Dynamiska rapporter och definitioner.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 6fffc6a3574c71c01f1e07ff4e6e6aa194479079
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 1%

---


# Förteckning över komponenter {#list-of-components}

Mer information om kompatibilitet mellan dimensioner och mått finns i den här [tabellen](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Om två komponenter inte är kompatibla visas värdet **Ingen** i cellen.

[![image](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimensioner {#dimensions}

Tabellen nedan visar en lista över de dimensioner som används i rapporter och deras definitioner.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Webbläsare<br /> </td> 
   <td> Webbläsare som meddelandet öppnades eller klickades på.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign<br /> </td> 
   <td> Etikett och ID för din kampanj.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ort<br /> </td> 
   <td> Ort registrerad i mottagarens profil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Land/region<br /> </td> 
   <td> Land registrerat i mottagarens profil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leverans<br /> </td> 
   <td> Etikett och ID för leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enhet<br /> </td> 
   <td> Enhet från vilken e-post/SMS/push-meddelandet öppnades/visades/klickades.<br /> </td> 
  </tr> 
  <tr> 
   <td> Felorsak<br /> </td> 
   <td> Typer av fel som orsakade studsar för varje leverans, t.ex. okänd användare, ogiltig domän eller brevlåda full.<br /> </td> 
  </tr> 
  <tr> 
   <td> Kön<br /> </td> 
   <td> Mottagarens kön, t.ex. man eller kvinna. Om genusfältet är tomt i mottagarens profil är värdet inget.<br /> </td> 
  </tr> 
  <tr> 
   <td> Meddelandeåtgärder i appen<br /> </td> 
   <td> Åtgärder för meddelandet i appen som levererats, t.ex. åtgärder för knapp 1 eller 2 eller uppsägningar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Meddelandetyp<br /> </td> 
   <td> Kanal som används för leverans, till exempel e-post, SMS, push-meddelanden eller In-App.<br /> </td> 
  </tr> 
  <tr> 
   <td> Namn på mobilapp<br /> </td> 
   <td> Mobilprogrammets namn<br /> </td> 
  </tr> 
  <tr> 
   <td> Plattform<br /> </td> 
   <td> Plattform för enheten som meddelandet öppnades/visades/klickades på.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profil<br /> </td> 
   <td> Grupperar om färdiga och anpassade profilfält som skapats under profilresurstillägget. Mer information finns på <a href="../../developing/using/key-steps-to-add-a-resource.md">sidan</a> eller i det här <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exemplet</a>.<br /> Observera att data för den här dimensionen hämtas så snart den anpassade resurs som är länkad till profilfältet publiceras.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push-plattform<br /> </td> 
   <td> Plattform för enheten som push-meddelandet öppnades från, till exempel iOS eller Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mottagardomän<br /> </td> 
   <td> Domän som används för att öppna e-postmeddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Återkommande leverans<br /> </td> 
   <td> Etikett och ID för den återkommande leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avsändardomän<br /> </td> 
   <td> Domän som används för att skicka e-postmeddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avsändarens IP<br /> </td> 
   <td> IP som används för att skicka e-postmeddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Läge<br /> </td> 
   <td> Läge registrerat i mottagarens profil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Spårnings-URL<br /> </td> 
   <td> URL som användaren klickade på i meddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Kategori för spårnings-URL<br /> </td> 
   <td> Kategori som tilldelats spårnings-URL:en.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL-etikett för spårning<br /> </td> 
   <td> Etikett som ges till URL:en, till exempel spegelsida, kontakta oss eller öppna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transaktionsleverans<br /> </td> 
   <td> Etikett och ID för transaktionsleveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variant<br /> </td> 
   <td> Variant av e-postmeddelandet vid A/B-testning.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Mått {#metrics}

Tabellerna nedan ger dig en lista över de mätvärden som används i rapporter och deras definitioner beroende på leveranstyp.

### Mätvärden för e-post och SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> På blockeringslista<br /> </td> 
   <td> Antal mottagare som har deklarerat ett e-postmeddelande som skräppost eller skräppost.<br /> </td> 
  </tr> 
  <tr> 
   <td> Blockeringslista<br /> </td> 
   <td> Procentandel leveranser som är markerade på blockeringslista.<br /> </td> 
  </tr> 
  <tr> 
   <td> studsar + fel<br /> </td> 
   <td> Totalt antal fel som sammanställts under leverans och automatisk returbearbetning i relation till totalt antal skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Studsa + felfrekvens<br /> </td> 
   <td> Procentandel e-postmeddelanden som studsade jämfört med e-postmeddelanden som skickades.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klicka på<br /> </td> 
   <td> Antal gånger som ett innehåll klickades i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klicka igenom hastigheten<br /> </td> 
   <td> Procentandel klick i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levererat<br /> </td> 
   <td> Antal meddelanden som har skickats i relation till totalt antal skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveransfrekvens<br /> </td> 
   <td> Procentandel meddelanden som skickades.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hård studs<br /> </td> 
   <td> Totalt antal permanenta fel, t.ex. fel e-postadress.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hård studsfrekvens<br /> </td> 
   <td> Procentandel leveranser som misslyckades på grund av permanenta fel.<br /> </td> 
  </tr> 
  <tr> 
   <td> Spegelsida<br /> </td> 
   <td> Antal mottagare som klickade på länken för spegelsidan.<br /> </td> 
  </tr> 
  <tr> 
   <td> Spegelvänd sidhastighet<br /> </td> 
   <td> Procentandel klick på spegelsidlänken jämfört med totalt antal leveransmeddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Erbjud klickningar<br /> </td> 
   <td> Antal gånger som ett erbjudande klickades på i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Erbjud klickfrekvens<br /> </td> 
   <td> Andel klick i ett erbjudande.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppna<br /> </td> 
   <td> Antal gånger ett meddelande öppnades i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppen kurs<br /> </td> 
   <td> Procentandel öppnade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Behandlad/skickad<br /> </td> 
   <td> Totalt antal försändelser för leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Karantän<br /> </td> 
   <td> Antal meddelanden som studsade och resulterade i adressens karantän.<br /> </td> 
  </tr> 
  <tr> 
   <td> Karantänsats<br /> </td> 
   <td> Procent av karantän jämfört med skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avvisad<br /> </td> 
   <td> Antal meddelanden som klassificerats som skräppost av SMTP-servrar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avvisad hastighet<br /> </td> 
   <td> Procentandel av meddelanden som markerats som avvisade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mjuk studs<br /> </td> 
   <td> Totalt antal tillfälliga fel, t.ex. en fullständig inkorg.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mjuk studsfrekvens<br /> </td> 
   <td> Procentandel leveranser som misslyckades på grund av temporär orsak.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika klick<br /> </td> 
   <td> Antal mottagare som klickat på ett innehåll i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika öppningar<br /> </td> 
   <td> Antal mottagare som öppnade leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avbeställningsfrekvens<br /> </td> 
   <td> Procentandel av mottagarens avanmälan jämfört med de meddelanden som levererats.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avbeställ<br /> </td> 
   <td> Antal klick på länken för att avbryta prenumerationen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mätvärden för push-meddelanden {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> studsar + fel<br /> </td> 
   <td> Totalt antal fel som sammanställts under leveransen i relation till totalt antal skickade meddelanden, t.ex. fel från MCPNS eller provider.<br /> </td> 
  </tr> 
  <tr> 
   <td> Studsa + felfrekvens<br /> </td> 
   <td> Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klicka på<br /> </td> 
   <td> Antal gånger ett push-meddelande har levererats till enheten och användaren klickat på det. Användaren ville antingen visa meddelandet, som sedan flyttas till Push Open tracking, eller stänga det.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klicka igenom hastigheten<br /> </td> 
   <td> Procentandel användare som interagerade med push-meddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levererat<br /> </td> 
   <td> Antal push-meddelanden som har skickats, i relation till totalt antal skickade push-meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveransfrekvens<br /> </td> 
   <td> Procentandel push-meddelanden som har skickats.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br /> </td> 
   <td> Antal gånger ett push-meddelande har levererats till enheten och lämnats orört i meddelandecentret. I de flesta fall bör imponeringsnumret motsvara det levererade numret. Detta garanterar att enheten fick meddelandet och vidarebefordrade informationen till servern.<br /> </td> 
  </tr> 
  <tr> 
   <td> Behandlad/skickad<br /> </td> 
   <td> Totalt antal skickade push-meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppna<br /> </td> 
   <td> Totalt antal push-meddelanden som levererats till enheten och användaren klickat på för att öppna appen. Det här liknar kommandot Push Click, men Push Open aktiveras inte om meddelandet stängs.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppen kurs<br /> </td> 
   <td> Procentandel öppna push-meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika klick<br /> </td> 
   <td> Antal gånger en unik användare interagerar med push-meddelandet, t.ex. klickar på meddelandet eller knappen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika intryck<br /> </td> 
   <td> Antal visningar per mottagare.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika öppningar<br /> </td> 
   <td> Antal mottagare som öppnade leveransen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mätvärden i appen {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Levererat<br /> </td> 
   <td> Totalt antal meddelanden i appen som levererats till enheten av tjänsteleverantören.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br /> </td> 
   <td> Totalt antal meddelanden i appen som visas av mottagarna beroende på om utlösarvillkoret uppfylls.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klicka i appen <br /> </td> 
   <td> Totalt antal mottagare som klickat på Knapp 1 eller Knapp 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klickfrekvens i appen<br /> </td> 
   <td> Procentandel användare som klickade på Knapp 1 eller Knapp 2 jämfört med användare som såg meddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inaktivering i appen<br /> </td> 
   <td> Totalt antal meddelanden som mottagare stängde antingen genom att klicka på stängningsknappen eller genom automatisk stängning.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avdragsfrekvens i appen<br /> </td> 
   <td> Procentandel av meddelanden i appen som mottagarna avvisade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Behandlad/skickad<br /> </td> 
   <td> Totalt antal meddelanden i appen som skickats från Adobe Campaign som en del av leveransprocessen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika intryck<br /> </td> 
   <td> Antal visningar av en unik mottagare.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika klickningar i appen<br /> </td> 
   <td> Antal gånger som mottagare klickat på Knapp 1 eller Knapp 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika uppsägningar i appen<br /> </td> 
   <td> Antal gånger som mottagarna har stängt ett meddelande i appen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segment {#segments}

>[!NOTE]
>
>Som standard är **[!UICONTROL Exclude proof]**-segmentet redan valt för att filtrera rapporter, men det kan ändras vid behov.

Tabellen nedan ger dig en lista över de segment som används i rapporter och deras definitioner.

<table> 
 <thead> 
  <tr> 
   <th> Segment<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Ålder: Boomer 1<br /> </td> 
   <td> Mottagare från 1946 till 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Boomer 2<br /> </td> 
   <td> Mottagare från 1955 till 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Från 18 till 25<br /> </td> 
   <td> Mottagare mellan 18 och 25 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Från 26 till 30<br /> </td> 
   <td> Mottagare mellan 26 och 30 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Från 31 till 40<br /> </td> 
   <td> Mottagare mellan 31 och 40 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Från 41 till 50<br /> </td> 
   <td> Mottagare mellan 41 och 50 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Generation X<br /> </td> 
   <td> Mottagare från 1966 till 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Generation Y (tusendels)<br /> </td> 
   <td> Mottagare från 1977 till 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Generation Z<br /> </td> 
   <td> Mottagare från 1995 till idag.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Större än 50<br /> </td> 
   <td> Mottagare vars ålder är större än 50.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Mindre än 25<br /> </td> 
   <td> Mottagare vars ålder är mindre än 25.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Mindre än 30<br /> </td> 
   <td> Mottagare vars ålder är mindre än 30.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Mindre än 40<br /> </td> 
   <td> Mottagare vars ålder är mindre än 40.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Mindre än 50<br /> </td> 
   <td> Mottagare vars ålder är mindre än 50.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Tyst generering<br /> </td> 
   <td> Mottagare födda 1945 eller tidigare.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alla besök<br /> </td> 
   <td> Alla mottagare<br /> </td> 
  </tr> 
    <tr> 
   <td> Uteslut korrektur<br /> </td> 
   <td> Uteslut korrektur från rapporter<br /> </td> 
  </tr> 
 </tbody> 
</table>

