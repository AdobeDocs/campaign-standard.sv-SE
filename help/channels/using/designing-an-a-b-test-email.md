---
title: Designa ett A/B-testmeddelande
description: Upptäck A/B-testfunktionen och följ de här stegen för att skapa ett e-postmeddelande från en A/B-testmall i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
feature: Email
role: User
level: Beginner
exl-id: 07cbf39c-4f53-49b1-8e85-c6df39f014b5
source-git-commit: 2adead5903eb2710207d7aeaaa85418bd616ca5d
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 95%

---

# Designa ett A/B-testmeddelande{#designing-an-a-b-test-email}

Med A/B-testfunktionen i Adobe Campaign kan du definiera två till tre e-postvarianter. Varje variant skickas till populationsprover för att fastställa vilket som ger bäst resultat. När det är fastställt skickas därefter den vinnande varianten till den återstående populationen.

Du kan välja att ändra e-postmeddelandets innehåll, ämne eller avsändare.

>[!NOTE]
>
>A/B-tester av e-post som skapats i Adobe Experience Manager är inte möjliga.

## Skapa ett A/B-testmeddelande {#creating-an-a-b-test-email}

Ett A/B-test kan skapas med hjälp av standardguiden för att skapa e-post, till vilken ett A/B-testkonfigurationssteg läggs till. Hur du skapar ett standardmejl beskrivs i avsnittet [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md).

I det specifika sammanhanget för ett A/B-test:

1. Skapa ett nytt e-postmeddelande från en av de tre specifika A/B-testmallarna, beroende på vilket element du vill variera:

   * A/B-test på avsändare
   * A/B-test på innehåll
   * A/B-test på motivet

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Uppföljnings- och A/B-testmallar är dolda som standard. Markera A/B-testrutan till vänster (**[!UICONTROL Filter]**-sidopanelen) för att visa dem.

1. Definiera de allmänna egenskaperna och målgruppen för e-postmeddelandet, precis som för ett vanligt e-postmeddelande. Se avsnittet [Skapa målgrupper](../../audiences/using/creating-audiences.md).
1. Definiera A/B-testparametrarna i det fjärde steget i guiden Skapa:

   * **[!UICONTROL Number of variants]**: Du kan välja att använda två eller tre varianter. Om du väljer tre varianter kan det här alternativet inte ändras efter att det här steget har bekräftats i guiden.
   * **[!UICONTROL Winning strategy]**: Välj det kriterium som ska användas för att bestämma vinnande variant.
   * **[!UICONTROL Target breakdown]**: Välj vilken procentandel av målet som ska ta emot varje variant. Den återstående procentandelen får den vinnande varianten när den har bestämts. Målprofilerna väljs slumpmässigt.

      >[!NOTE]
      >
      >Om den totala befolkningen är mindre än 50 kB måste varje variant motsvara minst 10 % av den totala befolkningen.

   * **[!UICONTROL Winner sending method]**: Välj om du vill att den vinnande varianten ska skickas automatiskt när den har bestämts eller om du vill bekräfta att den ska skickas till den återstående populationen manuellt.
   * **[!UICONTROL Test duration]**: Ange testets varaktighet. Den vinnande varianten bestäms automatiskt efter denna varaktighet. Du kan välja vinnande variant manuellt före testets slut från e-postkontrollpanelen.

      Testet måste vara minst en timme för att alla spårningsdata ska kunna samlas in och tas med i beräkningen så att den vinnande varianten kan väljas.
   ![](assets/ab_parameters.png)

1. När A/B-testparametrarna har definierats, går du vidare till nästa steg i guiden och definierar e-postinnehållet. Du kan definiera flera ämnen, flera avsändarnamn eller flera olika innehåll beroende på vilken mall du har valt. Använd karusellen för att navigera mellan elementets olika varianter. Mer information finns i avsnittet [Innehållsredigeraren](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/create_ab_testing2.png)

1. Bekräfta att du har skapat e-postmeddelandet. E-postkontrollpanelen visas då.
1. Schemalägg sändningen. Det definierade datumet anger början på A/B-testet.
1. Kontrollera de A/B-testparametrar som visas i **[!UICONTROL A/B test parameters]**-blocket. Du kan ändra dem upp tills du bekräftar att du har skickat testet (steg 9) genom att markera blocket.

   ![](assets/create_ab_testing3.png)

1. Förbered e-postmeddelandet för att analysera målet och antalet meddelanden som ska skickas. Gå till avsnittet [Förbereda sändningen](../../sending/using/preparing-the-send.md).
1. Innan du skickar A/B-testet ska du kontrollera din e-post genom att skicka korrekturläsningar.
1. När förberedelsen är klar ska du bekräfta att testet har skickats. När A/B-testparametrarna har bekräftats kan de inte ändras.

   A/B-testet startar på det datum som anges i **[!UICONTROL Schedule]**. Du kan följa förloppet med **[!UICONTROL A/B test]**- och **[!UICONTROL Deployment]**-blocken.

   Du kan när som helst välja vinnande variant manuellt om du vill förkorta testperioden.

   När testningen är klar visas en sammanfattningstabell i **[!UICONTROL A/B Test]**-blocket, vilket gör att du kan visa de olika indikatorerna för de olika varianterna som har testats.

1. Om du har valt **[!UICONTROL Send after confirmation]** som sändningsmetod måste du välja vinnande variant manuellt för att kunna skicka den till den återstående populationen. Om du har valt **[!UICONTROL Automatic]** skickas den vinnande varianten automatiskt till den återstående populationen så snart som den har fastställts av systemet.

   >[!NOTE]
   >
   >Om det är oavgjort måste den vinnande varianten väljas manuellt. Du kan meddela e-postskaparen och modifieraren/modifierarna att en variant har valts eller måste väljas. Se [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

Din e-post är nu definierad och skickad. Du har åtkomst till loggarna och rapporterna för att mäta hur framgångsrik kampanjen är.

## Om A/B-testindikatorer {#about-a-b-test-indicators}

I kontrollpanelen för e-postmeddelanden finns flera indikatorer som hjälper dig att mäta ditt A/B-test: Antal klick, öppningar, studsningar, o.s.v.

Observera att **[!UICONTROL Estimated recipient reactivity]**-indikatorn är en frekvens som jämför antalet mottagare som klickade mot antalet mottagare som öppnade e-postmeddelandet. Om till exempel 10 mottagare öppnade e-postmeddelandet och 5 mottagare klickade på det, är reaktiviteten 50 %.
