---
title: Funktioner för prediktivt användarengagemang
description: Lär dig hur du använder prediktiv sändningstid och engagemangsbedömning.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: ai-powered-emails
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 0%

---


# Optimera design och leverans med AI-baserade e-postmeddelanden{#journey-ai}

## Kom igång med AI-baserade e-postmeddelanden{#journey-ai-ovv}

Med Campaign kan ni optimera utformningen och leveransen av kundresor för att förutse varje enskild individs engagemang. Med Journey AI som bas kan Adobe Campaign analysera och förutsäga öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska engagemangsmått.

**Maskinininlärningsmodeller**

Adobe Campaign Standard erbjuder två nya Machine Learning-modeller: **Predictive Send Time Optimizations** and **Predictive Engagement Scoring**. Dessa två modeller kallas tillsammans för Journey AI, som är en klass maskininlärningsmodeller som är specifika för att designa och leverera bättre kundresor.

* **Prediktiv optimering** av sändningstid: Optimering av prediktiv sändningstid förutser vilken som är den bästa sändningstiden för varje mottagarprofil för e-postöppningar eller -klick. För varje mottagarprofil anger poängen den bästa sändningstiden för varje veckodag och vilken veckodag som är bäst att skicka för bästa resultat.

* **Prediktiv poängsättning**: Prediktiv poängsättning för engagemang förutser sannolikheten för att en mottagare engagerar sig i ett meddelande samt sannolikheten för att avanmäla sig inom 7 dagar efter nästa e-postutskick. Sannolikheten delas in ytterligare i grupper beroende på den specifika risken för bortfall, mellan och under. Under dessa omständigheter ger modellen även riskpercentilrangen så att kunderna kan förstå var en viss kunds rangordning är jämfört med andra.

>[!NOTE]
> **Förutsättningar **
>
>Den här funktionen är inte tillgänglig som en del av produkten. Implementeringen kräver att Adobe Consulting är engagerat. Kontakta din Adobe-representant om du vill veta mer.
>
>Funktionen krävde separat användning av ett Azure-lagringsutrymme som kunden måste tillhandahålla.

## Prediktiv optimering av sändningstid{#predictive-send-time}

### Optimera klick och öppningar{#about-predictive-send-time}

Optimering av prediktiv sändningstid förutser vilken som är den bästa sändningstiden för varje mottagarprofil för e-postöppningar och -klick. För varje mottagarprofil anger poängen den bästa sändningstiden för varje veckodag och vilken veckodag som är bäst att skicka för bästa resultat.

I modellen Predictive Send Time Optimization finns det två undermodeller:
* Förutsägbar öppningstid är den bästa tidpunkt då ett meddelande måste skickas till kunden för att maximera öppningen
* Förutsägbar klickningstid är den bästa tidpunkten då ett meddelande måste skickas till kunden för att maximera klickningarna

**Modellindata**: Leveransloggar, spårningsloggar och profilattribut (ej PII)

**Modellutdata**: Bästa tillfället att skicka ett meddelande (för öppningar och klick)


Utdatainformation

* Beräkna den bästa tidpunkten på dagen för att skicka ett e-postmeddelande för de kommande 7 dagarna med 1 timmes intervall (t.ex.: 9:00, 10:00, 11:00)
* Modellen anger den bästa tiden inom 7 dagar för att skicka e-postmeddelandet
* Varje optimal tid beräknas två gånger: en gång för att maximera öppningsfrekvensen och en gång för att maximera klickfrekvensen
* 16 fält ges (14 för veckodagar och 2 för hela veckan):
   * det bästa tillfället att skicka ett e-postmeddelande för att optimera klick för måndag - värden mellan 0 och 23
   * det bästa tillfället att skicka ett e-postmeddelande för att optimera öppningar för måndag - värden mellan 0 och 23
   * det bästa tillfället att skicka ett e-postmeddelande för att optimera antalet klick för tisdag - värden mellan 0 och 23
   * ...
   * det bästa tillfället att skicka ett e-postmeddelande för att optimera klick för söndag - värden mellan 0 och 23
   * det bästa tillfället att skicka ett e-postmeddelande för att optimera öppningar för söndag - värden mellan 0 och 23
   * ...
   * den bästa dagen att skicka ett e-postmeddelande för att optimera öppningarna för hela veckan - måndag till söndag
   * det bästa tillfället att skicka ett e-postmeddelande för att optimera öppningar för hela veckan - värden mellan 0 och 23

>[!NOTE]
>
>Dessa prediktiva funktioner gäller endast för e-postleveranser.
>
>Modellen behöver minst en månads data för att ge ett bra resultat.


### Åtkomst till profilpoäng{#access-predictive-send-time-scores}

När maskininlärningsfunktionerna har implementerats i Campaign berikas profildata med nya flikar med sina bästa poäng för att öppna/klicka. Mätvärdena beräknas av Journey AI och hämtas till Campaign med hjälp av tekniska arbetsflöden.

För att få tillgång till dessa mätvärden måste du:

1. Öppna en profil och klicka på knappen Redigera.

1. Klicka på fliken **Skicka tidspoäng genom att klicka** eller **Skicka tidspoäng genom att öppna** .

Som standard ger profilpoängen den bästa tiden på dagen för varje veckodag och den bästa totala tiden i veckan.

![](assets/do-not-localize/SendTimeScore.png)

### Skicka meddelanden vid den bästa tidpunkten{#use-predictive-send-time}

För att e-postmeddelandena ska gå ut vid den optimala tidpunkten per profil måste leveransen schemaläggas med alternativet **[!UICONTROL Send at a custom date defined by a formula]**.
Lär dig hur du beräknar sändningsdatumet [i det här avsnittet](../../sending/using/computing-the-sending-date.md).

Formeln måste fyllas i med den angivna bästa tiden för den aktuella dagen när leveransen ska gå ut.

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



## Prediktiv poängsättning av engagemang {#predictive-scoring}

Med prediktiv poängsättning för engagemang kan ni:

* **Välj en målgrupp**: genom att använda frågeaktiviteten kan du välja målgruppen som ska interagera med ett visst meddelande
* **Exkludera en målgrupp**: genom att använda frågeaktiviteten kan du ta bort målgruppen för att avbryta prenumerationen
* **Anpassa**: personalisera meddelanden baserat på nivå av engagemang (mycket engagerade användare får ett annat budskap än de som inte är engagerade)

I den här modellen används flera poäng för att ange:

* **Open Engagement Score / Click Engagement Score**: det här värdet matchar sannolikheten för att en prenumerant ska interagera med ett visst meddelande (öppna eller klicka). Värdena kan ligga mellan 0,0 och 1,0.
* **Sannolikhet för** avprenumeration: det här värdet matchar sannolikheten för att mottagaren avbeställer e-postkanalen när ett e-postmeddelande är öppet. Värdena kan ligga mellan 0,0 och 1,0.
* **Bevarandenivå**:  det här värdet rangordnar användare på tre nivåer: låg, medel och hög. Hög beständighet mot varumärket och lågt värde som troligen kommer att leda till att prenumerationen avbryts.
* **Percentilnivå för kvarhållande**: Profilrangordning i termer av sannolikhet för prenumeration. Värdena kan ligga mellan 0,0 och 1,0. Om kundlojaliteten till exempel är 0,953 stannar den här mottagaren troligtvis kvar med varumärket och är mindre benägen att avbryta prenumerationen än 95,3 % av alla mottagare.

>[!NOTE]
>
>Dessa prediktiva funktioner gäller endast för e-postleveranser.
>
>Modellen behöver minst en månads data för att ge ett bra resultat.


**Modellindata**: Leveransloggar, spårningsloggar och specifika profilattribut

**Modellutdata**: Ett profilattribut som beskriver profilens poäng och kategori


### Använda engagemangspoängen för e-postkanalen

För att få tillgång till dessa mätvärden måste du:

1. Öppna en profil och klicka på knappen Redigera.

1. Klicka på fliken **Engagement Scores för e-postkanal** .

Genom att använda en frågeaktivitet i ett arbetsflöde kan du använda poängen för att optimera målgruppen.

Med villkoren för **kvarhållningsnivå** :

![](assets/do-not-localize/predictive_score_query.png)























