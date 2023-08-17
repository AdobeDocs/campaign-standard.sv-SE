---
title: Lista över komponenter
description: Här finns en lista över alla komponenter som är tillgängliga i Dynamic-rapporter samt deras definitioner.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 1%

---

# Lista över komponenter {#list-of-components}

Mer information om kompatibilitet mellan dimensioner och mätvärden finns i detta [table](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Om två komponenter inte är kompatibla visas värdet i cellen **Ingen**.

[![image](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

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
   <td> Etikett och ID för kampanjen.<br /> </td> 
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
   <td> Typer av fel som orsakade studsar för varje leverans, t.ex. okänd användare, ogiltig domän eller full postlåda.<br /> </td> 
  </tr> 
  <tr> 
   <td> Kön<br /> </td> 
   <td> Mottagarens kön, t.ex. man eller kvinna. Om könsfältet är tomt i mottagarens profil är värdet inget.<br /> </td> 
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
   <td> Plattform för den enhet som meddelandet öppnades/visades/klickades på från.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profil<br /> </td> 
   <td> Grupperar färdiga och anpassade profilfält som skapats med tillägget för profilresurs, för mer information om detta finns i <a href="../../developing/using/key-steps-to-add-a-resource.md">page</a> eller <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exempel</a>.<br /> Observera att data för den här dimensionen hämtas så snart den anpassade resurs som är länkad till profilfältet publiceras.<br /> </td> 
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
   <td> Etikett och ID för återkommande leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avsändardomän<br /> </td> 
   <td> Domän som användes för att skicka e-postmeddelandet.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avsändarens IP-adress<br /> </td> 
   <td> IP som användes för att skicka e-postmeddelandet.<br /> </td> 
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
   <td> Etikett för spårnings-URL<br /> </td> 
   <td> En etikett som skickas till URL:en, till exempel spegelsida, kontakta oss eller öppna.<br /> </td> 
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
   <td> Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Studsa + Felfrekvens<br /> </td> 
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
   <td> Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levererad ränta<br /> </td> 
   <td> Procentandel meddelanden som har skickats.<br /> </td> 
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
   <td> Spegelsidhastighet<br /> </td> 
   <td> Procentandel klick på spegelsidlänken jämfört med totalt antal leveransmeddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Erbjud klickningar<br /> </td> 
   <td> Antal gånger som man klickat på ett erbjudande i en leverans.<br /> </td> 
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
   <td> Antal meddelanden som studsade och resulterade i karantän för adressen.<br /> </td> 
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
   <td> Avvisad ränta<br /> </td> 
   <td> Procentandel av meddelanden som markerats som avvisade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mjuk studsa<br /> </td> 
   <td> Totalt antal tillfälliga fel, till exempel en fullständig inkorg.<br /> </td> 
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
   <td> Unik avprenumeration<br /> </td> 
   <td> Antal mottagare som klickat på länken för att ta bort prenumerationen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avbeställningsfrekvens<br /> </td> 
   <td> Antal unika avprenumerationer jämfört med levererade meddelanden.<br /> </td> 
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
   <td> Totalt antal fel som sammanställts under leveransen i förhållande till totalt antal skickade meddelanden, t.ex. fel från MCPNS eller leverantör.<br /> </td> 
  </tr> 
  <tr> 
   <td> Studsa + Felfrekvens<br /> </td> 
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
   <td> Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levererad ränta<br /> </td> 
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
   <td> Totalt antal push-meddelanden som levererats till enheten och användaren klickat på för att öppna appen. Det här liknar kommandot Push Click (Push-klicka), förutom att Push Open (Push Open) inte aktiveras om meddelandet stängs.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppen kurs<br /> </td> 
   <td> Procentandel öppnade push-meddelanden.<br /> </td> 
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
   <td> Totalt antal meddelanden som mottagarna stängt antingen genom att klicka på stängningsknappen eller genom automatisk stängning.<br /> </td> 
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
   <td> Unika klick i programmet<br /> </td> 
   <td> Antal gånger som mottagare klickat på Knapp 1 eller Knapp 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unika rabatter i appen<br /> </td> 
   <td> Antal gånger som mottagarna har stängt ett meddelande i appen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segment {#segments}

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
   <td> Ålder: boomer 1<br /> </td> 
   <td> Mottagare från 1946 till 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Boomer 2<br /> </td> 
   <td> Mottagare från 1955 till 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: från 18 till 25<br /> </td> 
   <td> Mottagare mellan 18 och 25 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Från 26 till 30<br /> </td> 
   <td> Mottagare mellan 26 och 30 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: från 31 till 40<br /> </td> 
   <td> Mottagare mellan 31 och 40 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: från 41 till 50<br /> </td> 
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
   <td> Ålder: större än 50<br /> </td> 
   <td> Mottagare vars ålder är större än 50.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: mindre än 25<br /> </td> 
   <td> Mottagare vars ålder är mindre än 25 år.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: Mindre än 30<br /> </td> 
   <td> Mottagare vars ålder är mindre än 30.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: mindre än 40<br /> </td> 
   <td> Mottagare vars ålder är mindre än 40.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: mindre än 50<br /> </td> 
   <td> Mottagare vars ålder är mindre än 50.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ålder: tyst generering<br /> </td> 
   <td> Mottagare födda 1945 eller tidigare.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alla besök<br /> </td> 
   <td> Varje mottagare<br /> </td> 
  </tr>
 </tbody> 
</table>
