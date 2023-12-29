---
title: Funktioner för förutsägande användarengagemang
description: Läs om hur du använder förutsägande sändningstider och engagemangsbedömning.
audience: sending
content-type: reference
topic-tags: ai-powered-emails
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: e1cb04e6-eb38-4bcc-b071-321cc11ccc7e
source-git-commit: 75628ed8a2f9b21def23e5b257a3592e1a721536
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 47%

---

# Funktioner för förutsägande användarengagemang {#journey-ai}

Med Campaign kan du optimera designen och leveransen av kundresor för att förutse varje enskild individs engagemang. Med hjälp av AI och maskininlärning kan Adobe Campaign Scoring (Send-Time Optimization) och Predictive Engagement Scoring analysera och förutse öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska interaktionsvärden.

>[!IMPORTANT]
>
>Den här funktionen är inte tillgänglig som en del av produkten. För implementering krävs att Adobe Consulting används. Kontakta din Adobe-representant för mer information.

Adobe Campaign erbjuder två nya Machine Learning-modeller: **Prediktiv optimering av sändningstid** och **Poängberäkning för prediktiv engagemang**. Dessa två modeller är maskininlärningsmodeller som är specifika för att designa och leverera bättre kundresor.

* **Prediktiv optimering av sändningstid** anger vilken som är den bästa sändningstiden för varje mottagarprofil för e-postöppningar eller -klick och för push-meddelanden-öppningar. För varje mottagarprofil anger poängen den bästa sändningstiden för varje veckodag och vilken veckodag som är bäst att använda för bästa resultat.

* **Prediktiv poängsättning av engagemang**: anger sannolikheten för att en mottagare ska få ett meddelande samt sannolikheten för att avanmäla sig inom 7 dagar efter nästa e-postutskick. Sannolikheten för detta delas upp ytterligare i grupper efter den förväntade nivån av engagemang med ert innehåll: högt, medelhögt eller lågt. Dessa modeller ger också en percentil för avbruten risk för kunderna för att förstå var en viss kunds rangordning är i förhållande till andra.

## Prediktiv optimering av sändningstid{#predictive-send-time}

Med prediktiv optimering av sändningstid förutspås vilken som är den bästa sändningstiden för varje mottagarprofil för e-postöppningar eller -klick och för push-meddelanden-öppningar. För varje mottagarprofil anger poängen den bästa sändningstiden för varje veckodag och vilken veckodag som är bäst att använda för bästa resultat.

I modellen Predictive Send-Time Optimization finns det två undermodeller:

* **Prediktiv sändningstid för öppning** är den bästa tidpunkten då ett meddelande måste skickas till kunden för att maximera öppnandet

* **Prediktiv sändningstid för klickning** är den bästa tidpunkten då ett meddelande måste skickas till kunden för att maximera klickningarna

**Indata från modellen**: leveransloggar, spårningsloggar och profilattribut (ej PII)

**Utdata från modellen**: bästa tillfället att skicka ett meddelande (för öppningar och klick)

Information om utdata

* Beräknar den bästa tidpunkten på dagen för att skicka ett e-postmeddelande för inom 7 dagar av veckan med 1 timmes intervall (t.ex. 09:00, 10:00, 11:00)
* Modellen visar den bästa dagen i veckan och den bästa timmen på den dagen
* Varje optimal tid beräknas två gånger: en gång för att maximera öppningsfrekvensen och en gång för att maximera klickfrekvensen
* 16 fält ges (14 för veckodagar och 2 för hela veckan):

* Bästa tillfället att skicka ett e-postmeddelande för att optimera klick för måndag - värden mellan 0 och 23

* Bästa tillfället att skicka ett e-postmeddelande för att optimera öppningar för måndag - värden mellan 0 och 23
* ...
* Bästa tillfället att skicka ett e-postmeddelande för att optimera klick för söndag - värden mellan 0 och 23
* Bästa tillfället att skicka ett e-postmeddelande för att optimera öppningar för söndag - värden mellan 0 och 23
* ...
* Bästa dagen att skicka ett e-postmeddelande för att optimera öppningar för hela veckan - måndag till söndag
* Bästa tillfället att skicka ett e-postmeddelande för att optimera öppningar för hela veckan - värden mellan 0 och 23

>[!NOTE]
>
>Modellen behöver minst en månads data för att ge ett bra resultat.
>
>Dessa prediktiva funktioner gäller endast e-post- och push-kanaler.

När maskininlärningsfunktionerna väl har implementerats i Campaign berikas profildata med nya flikar med bästa poäng för att öppna/klicka. Mätvärdena beräknas och hämtas in i Campaign med hjälp av tekniska arbetsflöden.

För att få tillgång till dessa mätvärden måste du:

1. Öppna en profil och klicka på knappen Redigera.

1. Klicka på fliken **Skicka tidspoäng per klick** eller **Skicka tidspoäng per öppning**.

Som standard ger profilpoängen den bästa tiden på dagen för varje veckodag och den bästa generella tiden i veckan.

![](assets/do-not-localize/SendTimeScore.png)

### Skicka meddelanden vid den bästa tidpunkten{#use-predictive-send-time}

För att e-postmeddelandena ska gå ut vid den optimala tidpunkten per profil måste leveransen schemaläggas med alternativet **[!UICONTROL Send at a custom date defined by a formula]**.

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

## Prediktiv poängsättning för engagemang {#predictive-scoring}

Predictive Engagement Scoring förutser sannolikheten för att en mottagare engagerar sig i ett meddelande samt sannolikheten för att avanmäla sig inom 7 dagar efter nästa e-postutskick.

Sannolikheten för detta delas upp ytterligare i grupper efter den förväntade nivån av engagemang med ert innehåll: högt, medelhögt eller lågt. Dessa modeller ger också en percentil för avbruten risk för kunderna för att förstå var en viss kunds rangordning är i förhållande till andra.

Predictive Engagement Scoring:

* **Välj en målgrupp**: genom att använda frågeaktivitet kan du välja vilken målgrupp som ska interagera med ett visst meddelande
* **Uteslut en målgrupp**: genom att använda frågeaktivitet kan du ta bort den målgrupp som troligen kommer att avbryta prenumerationen
* **Anpassa**: personalisera meddelanden baserat på nivå av engagemang (mycket engagerade användare får ett annat budskap än oengagerade)

I den här modellen används flera olika poäng för att ange:

* **Engagemangsbedömning per öppning/engagemangsbedömning per klick**: det här värdet matchar sannolikheten för att en prenumerant ska interagera med ett visst meddelande (öppna eller klicka). Värdena kan ligga mellan 0,0 och 1,0.
* **Sannolikheten att avbryta prenumerationen**: det här värdet matchar sannolikheten för att mottagaren avbeställer e-postkanalen när ett e-postmeddelande öppnas. Värdena kan ligga mellan 0,0 och 1,0.
* **Bevarandenivå**: det här värdet rankar användare på tre nivåer: låg, medel och hög. Högt värde är mest sannolikt att stanna kvar hos varumärket och lågt värde är mest sannolikt att avbryta prenumerationen.
* **Procentuell rangordning för kvarhållning**: profilrangordning beträffande sannolikheten att avbryta prenumerationen. Värdena kan ligga mellan 0,0 och 1,0. Om kundlojaliteten till exempel är 0,953 stannar den här mottagaren troligtvis kvar med varumärket och är mindre benägen att avbryta prenumerationen än 95,3 % av alla mottagare.

>[!NOTE]
>
>Dessa förutsägande funktioner gäller endast för e-postleveranser.
>
>Modellen behöver minst en månads data för att ge ett bra resultat.

**Indata från modellen**: leveransloggar, spårningsloggar och specifika profilattribut

**Utdata från modellen**: ett profilattribut som beskriver profilens poäng och kategori

För att få tillgång till dessa mätvärden måste du:

1. Öppna en profil och klicka på knappen Redigera.

1. Klicka på fliken **Engagemangsbedömning för e-postkanal** .

Genom att använda en frågeaktivitet i ett arbetsflöde kan du använda poängen för att optimera målgruppen. Med till exempel villkoren för **kvarhållningsnivå**:

![](assets/do-not-localize/predictive_score_query.png)