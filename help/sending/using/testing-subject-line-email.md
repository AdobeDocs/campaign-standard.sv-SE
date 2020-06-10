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
source-git-commit: 343ea01229779a32919bd68fd15e0c7ff6863353
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 0%

---

# Testa ämnesraden i ett e-postmeddelande {#testing-a-subject}


## Om prediktiv ämnesrad {#about-predictive-subject-line}

När du redigerar ett e-postmeddelande kan du testa olika ämnesrader och få en uppskattning av öppningsfrekvensen innan du skickar det.

Den här funktionen är inaktiverad som standard. Den aktiveras när den första modellen importeras. En modell är resultatet av utbildning av data som är specifika för en viss bransch. Med hjälp av modeller kan systemet förutsäga öppningsfrekvensen för e-postmeddelanden när en ny ämnesrad skickas.

>[!NOTE]
>
>Den här funktionen är tillgänglig för e-postmeddelanden och för databaser som endast innehåller engelskt innehåll. Den tränade modellen blir inkonsekvent och ger felaktiga resultat om instansen innehåller e-post på andra språk. Alternativet som gör att du kan testa ett ämne är bara synligt om det redan finns en modell på din instans.

Mer information om hur du importerar modeller finns i det här [avsnittet](#importing-models).

## Testa ämnesraden {#testing-subject-line}

Följ stegen nedan för att testa ämnesraden:

1. Skapa eller öppna din e-post.
1. Öppna innehållet och ange ämnet för e-postmeddelandet i motsvarande inmatningsfält.
1. Klicka på **[!UICONTROL Test subject]** knappen för att öppna **[!UICONTROL Test your subject line]** fönstret. Du kan fortfarande redigera ämnet från det här fönstret.
1. Välj rätt modell som ska beaktas för den öppna tariffförutsägelsen. Flera modeller finns tillgängliga, var och en för en viss bransch. Mer information om hur du använder modeller finns i det här [avsnittet](#importing-models).
1. Klicka på **[!UICONTROL Test]**.

Därefter analyseras ditt ämne.

>[!NOTE]
>
>Om ämnesraden är för kort kan den inte analyseras och ett felmeddelande visas.

Flera indikatorer beräknas och en uppsättning verktyg visas som hjälp:

* **Förväntad öppningsfrekvens**: I det här diagrammet får du en uppfattning om den öppna frekvens du kan förvänta dig för e-postmeddelandet med det aktuella ämnet.
* **Ämneslängd**: Med den här indikatorn kan du se om objektets aktuella längd är korrekt eller om det behöver vara längre eller kortare.
* **Färgade ord**: När du testar ämnet är ord som markeras med grönt de ord som bidrar mest till att öka förutsägbarheten för den öppna frekvensen. Ord som markeras med rött är de ord som bidrar minst till att öka förutsägelsen om den öppna frekvensen. Om du lägger till eller tar bort ord i ämnet ändras de markerade orden.
* **Categories and word suggestions**: Towards the lower part of the window, a number of relevant categories for the selected model are displayed. Dessa kategorier sorteras efter prioritetsordning och du kan se om ditt ämne innehåller ord som är kopplade till det via en bocksymbol. Varje kategori innehåller en uppsättning föreslagna ord som kan användas i ditt ämne för att göra det mer relevant och öka den öppna frekvensen. Dessa ord är de ord som används oftast i en viss kategori.

>[!NOTE]
>
>Personaliseringsfält och skiljetecken tas bort från ämnesanalysen. När det gäller dynamisk/villkorlig text betraktas alla varianter som en ämnesrad.

![](assets/predictive_subject_line_example.png)

## Importera modeller {#importing-models}

Som standard körs ingen modell på Adobe Campaign-servern. Det finns två sätt att hämta en modell och aktivera funktionen:

* Du kan utbilda en lokal modell från data i dina tidigare e-postmeddelanden.
* Du kan importera förutbildade modeller som är specifika för vissa branscher (medicinska, etc.) med [paketimportfunktionen](../../automating/using/managing-packages.md) .

### Utbilda en lokal modell {#training-local-model}

* Om du redan använder Adobe Campaign kommer den lokala modellen att automatiskt utbildas i de meddelanden som du redan har skickat.
* Om du inte har använt Adobe Campaign tidigare kan du extrahera en CSV-fil från ditt tidigare system/ESP som innehåller fyra kolumner: datum, ämne, öppning, skickat. Det gör du genom att gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** och följa instruktionerna på efterföljande skärmar. När ämnesöverföringen är klar importerar du en lokal modell enligt beskrivningen nedan. The local model is automatically trained with the data you uploaded.
* If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a [pre-trained model](#pre-trained-models) or wait until you have enough delivery data in your system to train a local model. The system will automatically determine whether your current data set contains enough data to recognize patterns and to train the model.

>[!NOTE]
>
>There is no defined number of subject lines needed to train your own model. For more on this, see [Troubleshooting](#troubleshooting).
>
>You can only have one trained model on your instance.

To train a local model:
1. Hämta subjectLineTraining.xml [här](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) och använd funktionen för [paketimport](../../automating/using/managing-packages.md) för att överföra den till Adobe Campaign-instansen. A technical workflow will automatically do the training for you.
1. Första gången du vill utbilda en modell kan en administratör tvinga fram en start från menyn **[!UICONTROL SubjectLine Training workflow]** > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** **[!UICONTROL Workflows]** .
1. Once a model has been uploaded and trained, the feature is automatically activated and a new option appears next to the subject line field of your messages.
1. Then, the technical workflow will automatically continue to train your model every week.

### Importing pre-trained models {#pre-trained-models}

To access these models, click [here](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). Använd [paketimportfunktionen](../../automating/using/managing-packages.md) för att överföra en modell till din Adobe Campaign-instans.

De modeller som är tillgängliga för användning är:

* Kosmetisk industri: subjectInsightCosmetic.xml
* Stormarknadsindustrin: subjectInsightSupermarket.xml
* Medical industry: subjectInsightMedical.xml
* Förlaga till tåg: subjectlineTraining.xml.

Dessa modeller kan inte tränas.

Once a model has been uploaded, the feature is automatically activated and a new option appears next to the subject line field of your messages.

>[!NOTE]
>
>Importing and generating trained models can only be performed by an administrator.

## Felsökning {#troubleshooting}

Prediktiv ämnesrad är en maskininlärningsprocess som tar hänsyn till alla ämnesrader som du har överfört med sina öppna frekvenser. På så sätt kan systemet förutsäga öppningsfrekvensen för ett e-postmeddelande när en ny ämnesrad skickas.

Om du vill kunna utbilda din egen modell måste ämnesraderna vara olika och får inte innehålla dubbletter, oavsett hur många ämnesrader som används för att utbilda din modell.

The quality of the subject lines is essential. Om det inte finns tillräckligt med kvalitetsdata för att bearbeta, eller om alla föregående ämnesrader är för lika, kommer systemet inte att kunna utbilda modellen och du kan få ett felmeddelande. Det innebär att din befintliga uppsättning med poster inte kan ge ett tillförlitligt prediktivt förslag.

I det här fallet bör du granska de data du överför och se till att ämnesraderna är tillräckligt varierade för att effektivt kunna utbilda din modell.

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
