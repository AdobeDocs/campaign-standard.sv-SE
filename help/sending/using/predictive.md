---
solution: Campaign Standard
product: campaign
title: Funktioner för förutsägande användarengagemang
description: Läs om hur du använder förutsägande sändningstider och engagemangsbedömning.
audience: sending
content-type: reference
topic-tags: ai-powered-emails
feature: Tidsoptimering för sändning
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 97%

---


# Optimera design och leverans med AI-baserade e-postmeddelanden{#journey-ai}

## Kom igång med AI-baserade e-postmeddelanden{#journey-ai-ovv}

Med Campaign kan du optimera designen och leveransen av kundresor för att förutse varje enskild individs engagemang. Med Journey AI som bas kan Adobe Campaign analysera och förutse öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska engagemangsmått.

**Maskininlärningsmodeller**

Adobe Campaign Standard erbjuder två nya maskininlärningsmodeller: **Förutsägande optimering av sändningstid** och **Förutsägande engagemangsbedömning**. Dessa två modeller kallas tillsammans för Journey AI som är en grupp med maskininlärningsmodeller som är specifika för att designa och leverera bättre kundresor.

* **Förutsägande optimering av sändningstid**: förutsägande optimering av sändningstid förutser vilken som är den bästa sändningstiden för varje mottagarprofil för att generera öppningar eller -klick i e-postmeddelanden. För varje mottagarprofil anger poängen den bästa sändningstiden för varje veckodag och vilken veckodag som är bäst att använda för bästa resultat.

* **Förutsägande engagemangsbedömning**: förutsägande engagemangsbedömning förutser sannolikheten att en mottagare engagerar sig i ett meddelande samt sannolikheten att denne avanmäler sig inom sju dagar efter nästa e-postutskick. Sannolikheten delas in i ytterligare grupper beroende på den specifika risken för bortfall – medel eller låg. Under dessa omständigheter ger modellen även riskbedömningar i procentantal vilket innebär att kunderna kan förstå var en viss kunds rangordning är jämfört med andra.

>[!IMPORTANT]
>Den här funktionen är inte tillgänglig som en del av produkten. För implementering krävs att Adobe Consulting används. Kontakta din Adobe-representant för mer information.
>
>Funktionen kräver att en Azure- eller Amazon S3-lagring som kunden måste tillhandahålla används.

## Förutsägande optimering av sändningstid{#predictive-send-time}

### Optimera klick och öppningar{#about-predictive-send-time}

Förutsägande optimering av sändningstid förutser vilken som är den bästa sändningstiden för varje mottagarprofil för att optimera öppningar och klick i e-postmeddelanden. För varje mottagarprofil anger poängen den bästa sändningstiden för varje veckodag och vilken veckodag som är bäst att använda för bästa resultat.

I modellen Förutsägande optimering av sändningstid finns det två undermodeller:
* Förutsägbar sändningstid för att öppnas är den bästa tidpunkt då ett meddelande ska skickas till kunden för att maximera chansen att det öppnas
* Förutsägbar sändningstid för att klickas på är den bästa tidpunkt då ett meddelande ska skickas till kunden för att maximera chansen att kunden klickar

**Indata från modellen**: leveransloggar, spårningsloggar och profilattribut (ej PII)

**Utdata från modellen**: bästa tillfället att skicka ett meddelande (för öppningar och klick)


Information om utdata

* Beräkna den bästa tidpunkten på dagen för att skicka ett e-postmeddelande. Detta inom 7 dagar i en vecka med 1 timmes intervall (t.ex.: 09:00, 10:00, 11:00)
* Modellen visar den bästa dagen i veckan och den bästa timmen på den dagen
* Varje optimal tid beräknas två gånger: en gång för att maximera öppningsfrekvensen och en gång för att maximera klickfrekvensen
* 16 fält ges (14 för veckodagar och 2 för hela veckan):
   * den bästa tiden att skicka ett e-postmeddelande för att optimera klick för måndag – värden mellan 0 och 23
   * den bästa tiden att skicka ett e-postmeddelande för att optimera öppningar för måndag – värden mellan 0 och 23
   * den bästa tiden att skicka ett e-postmeddelande för att optimera klick för tisdag – värden mellan 0 och 23
   * ...
   * den bästa tiden att skicka ett e-postmeddelande för att optimera klick för söndag – värden mellan 0 och 23
   * den bästa tiden att skicka ett e-postmeddelande för att optimera öppningar för söndag – värden mellan 0 och 23
   * ...
   * den bästa dagen att skicka ett e-postmeddelande för att optimera öppningarna för hela veckan – måndag till söndag
   * den bästa tiden att skicka ett e-postmeddelande för att optimera öppningar för hela veckan – värden mellan 0 och 23

>[!NOTE]
>
>Dessa förutsägande funktioner gäller endast för e-postleveranser.
>
>Modellen behöver minst en månads data för att ge ett bra resultat.


### Åtkomst till profilpoäng{#access-predictive-send-time-scores}

När maskininlärningsfunktionerna väl har implementerats i Campaign berikas profildata med nya flikar med bästa poäng för att öppna/klicka. Mätvärdena beräknas av Journey AI och hämtas av Campaign med hjälp av tekniska arbetsflöden.

För att få tillgång till dessa mätvärden måste du:

1. Öppna en profil och klicka på knappen Redigera.

1. Klicka på fliken **Skicka tidspoäng per klick** eller **Skicka tidspoäng per öppning**.

Som standard ger profilpoängen den bästa tiden på dagen för varje veckodag och den bästa generella tiden i veckan.

![](assets/do-not-localize/SendTimeScore.png)

### Skicka meddelanden vid den bästa tidpunkten{#use-predictive-send-time}

För att e-postmeddelandena ska skickas ut vid den optimala tidpunkten per profil måste leveransen schemaläggas med alternativet **[!UICONTROL Send at a custom date defined by a formula]**.
Läs mer [i det här avsnittet](../../sending/using/computing-the-sending-date.md) om hur du beräknar sändningsdatumet.

Formeln måste fyllas i med den angivna bästa tiden för den aktuella dagen när leveransen ska skickas.

![](assets/do-not-localize/ComputeSendingDate.png)

Exempel på formel:

```
AddHours([currentDelivery/scheduling/@contactDate], 
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>Datamodellen kan vara annorlunda beroende på implementeringen.



## Förutsägande engagemangsbedömning {#predictive-scoring}

Med förutsägande engagemangsbedömning kan du:

* **Välja en målgrupp**: genom att använda frågeaktiviteten kan du välja målgruppen som ska interagera med ett visst meddelande
* **Exkludera en målgrupp**: genom att använda frågeaktiviteten kan du ta bort målgruppen för att avbryta prenumerationen
* **Anpassa**: personalisera meddelanden baserat på nivå av engagemang (mycket engagerade användare får ett annat budskap än de som inte är engagerade)

I den här modellen används flera olika poäng för att ange:

* **Engagemangsbedömning per öppning/engagemangsbedömning per klick**: det här värdet matchar sannolikheten för att en prenumerant ska interagera med ett visst meddelande (öppna eller klicka). Värdena kan ligga mellan 0,0 och 1,0.
* **Sannolikheten att avbryta prenumerationen**: det här värdet matchar sannolikheten för att mottagaren avbeställer e-postkanalen när ett e-postmeddelande öppnas. Värdena kan ligga mellan 0,0 och 1,0.
* **Kvarhållningsnivå**: det här värdet rangordnar användare på tre nivåer: låg, medel och hög. Högt värde är mest sannolikt att stanna kvar hos varumärket och lågt värde är mest sannolikt att avbryta prenumerationen.
* **Procentuell rangordning för kvarhållning**: profilrangordning beträffande sannolikheten att avbryta prenumerationen. Värdena kan ligga mellan 0,0 och 1,0. Om kundlojaliteten till exempel är 0,953 stannar den här mottagaren troligtvis kvar med varumärket och är mindre benägen att avbryta prenumerationen än 95,3 % av alla mottagare.

>[!NOTE]
>
>Dessa förutsägande funktioner gäller endast för e-postleveranser.
>
>Modellen behöver minst en månads data för att ge ett bra resultat.


**Indata från modellen**: leveransloggar, spårningsloggar och specifika profilattribut

**Utdata från modellen**: ett profilattribut som beskriver profilens poäng och kategori


### Använda engagemangsbedömningen för e-postkanalen

För att få tillgång till dessa mätvärden måste du:

1. Öppna en profil och klicka på knappen Redigera.

1. Klicka på fliken **Engagemangsbedömning för e-postkanal** .

Genom att använda en frågeaktivitet i ett arbetsflöde kan du använda poängen för att optimera målgruppen.

Med till exempel villkoren för **kvarhållningsnivå**:

![](assets/do-not-localize/predictive_score_query.png)























