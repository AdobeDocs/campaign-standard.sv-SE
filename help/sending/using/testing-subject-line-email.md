---
title: Testa ämnesraden i ett e-postmeddelande
description: Läs om hur du definierar ämnesraden för ett e-postmeddelande i e-postdesignern.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e61796376a14c279d38107905275172be0dd12d

---

# Testa ämnesraden i ett e-postmeddelande {#testing-a-subject}

Följ stegen nedan för att testa ämnesraden:

1. Skapa eller öppna din e-post.
1. Öppna innehållet och ange ämnet för e-postmeddelandet i motsvarande inmatningsfält.
1. Klicka på **[!UICONTROL Test subject]** knappen för att öppna **[!UICONTROL Test your subject line]** fönstret. Du kan fortfarande redigera ämnet från det här fönstret.
1. Välj rätt modell som ska beaktas för den öppna tariffförutsägelsen. Flera modeller finns tillgängliga, var och en för en viss bransch.
1. Klicka på **[!UICONTROL Test]**.

Därefter analyseras ditt ämne.

>[!NOTE]
>
>Om ämnesraden är för kort kan den inte analyseras och ett felmeddelande visas.

Flera indikatorer beräknas och en uppsättning verktyg visas som hjälp:

* **Förväntad öppningsfrekvens**: I det här diagrammet får du en uppfattning om den öppna frekvens du kan förvänta dig för e-postmeddelandet med det aktuella ämnet.
* **Ämneslängd**: Med den här indikatorn kan du se om objektets aktuella längd är korrekt eller om det behöver vara längre eller kortare.
* **Färgade ord**: När du testar ämnet är ord som markeras med grönt de ord som bidrar mest till att öka förutsägbarheten för den öppna frekvensen. Ord som markeras med rött är de ord som bidrar minst till att öka förutsägelsen om den öppna frekvensen. Om du lägger till eller tar bort ord i ämnet ändras de markerade orden.
* **Kategorier och ordförslag**: I fönstrets nedre del visas ett antal relevanta kategorier för den valda modellen. Dessa kategorier sorteras efter prioritetsordning och du kan se om ditt ämne innehåller ord som är kopplade till det via en bocksymbol. Varje kategori innehåller en uppsättning föreslagna ord som kan användas i ditt ämne för att göra det mer relevant och öka den öppna frekvensen. Dessa ord är de ord som används oftast i en viss kategori.

>[!NOTE]
>
>Personaliseringsfält och skiljetecken tas bort från ämnesanalysen. När det gäller dynamisk/villkorlig text betraktas alla varianter som en ämnesrad.

![](assets/predictive_subject_line_example.png)

## Importera modeller {#importing-models}

Som standard körs ingen modell på Adobe Campaign-servern. Det finns två sätt att hämta en modell och aktivera funktionen:

* Du kan utbilda en lokal modell från data i dina tidigare e-postmeddelanden:

   * Om du redan använder Adobe Campaign kommer den lokala modellen automatiskt att utbildas i de meddelanden som du redan har skickat.
   * Om du inte har använt Adobe Campaign tidigare kan du extrahera en CSV-fil från ditt tidigare system/ESP som innehåller fyra kolumner: datum, ämne, öppning, skickat. Det gör du genom att gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** och följa instruktionerna på efterföljande skärmar. När ämnesöverföringen är klar importerar du en lokal modell enligt beskrivningen nedan. Den lokala modellen utbildas automatiskt med de data du överförde.
   * Om du inte har använt Adobe Campaign tidigare och inte kan hämta en CSV-fil enligt beskrivningen ovan kan du använda en förtränad modell eller vänta tills du har tillräckligt med leveransdata i systemet för att utbilda en lokal modell. Systemet avgör automatiskt om din aktuella datauppsättning innehåller tillräckligt med data för att identifiera mönster och utbilda modellen.

      >[!NOTE]
      >
      >Det finns inget definierat antal ämnesrader som behövs för att utbilda din egen modell. För att kunna utbilda den måste ämnesraderna vara olika och inte ha några dubbletter. Om det inte finns tillräckligt med data för att bearbeta modellen kommer systemet inte att kunna utbilda modellen. Du kan bara ha en tränad modell i din instans.
   Om du vill utbilda en lokal modell hämtar du subjectLineTraining.xml [här](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) och använder funktionen för [paketimport](../../automating/using/managing-packages.md) för att överföra den till Adobe Campaign-instansen. Ett tekniskt arbetsflöde gör automatiskt utbildningen åt dig.

   Första gången du vill utbilda en modell kan en administratör tvinga fram en start från menyn **[!UICONTROL SubjectLine Training workflow]** > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** **[!UICONTROL Workflows]** .

   När en modell har överförts och tränats aktiveras funktionen automatiskt och ett nytt alternativ visas bredvid ämnesraden i dina meddelanden.

   Sedan fortsätter det tekniska arbetsflödet automatiskt att utbilda din modell varje vecka.

* Du kan importera förutbildade modeller som är specifika för vissa branscher (medicinska, etc.) med [paketimportfunktionen](../../automating/using/managing-packages.md) . Om du vill få tillgång till de här modellerna klickar du [här](https://support.neolane.net/webApp/extranetLogin) och går till **[Hämtningscenter]**. Dessa modeller kan inte tränas.

   När en modell har överförts aktiveras funktionen automatiskt och ett nytt alternativ visas bredvid ämnesraden i dina meddelanden.

>[!NOTE]
>
>Import och generering av utbildade modeller kan endast utföras av en administratör.

De modeller som är tillgängliga för användning är:

* Kosmetisk industri: subjectInsightCosmetic.xml
* Stormarknadsindustrin: subjectInsightSupermarket.xml
* Medicinsk industri: subjectInsightMedical.xml
* Förlaga till tåg: subjectlineTraining.xml.
