---
title: Testa e-postmeddelanden med målprofiler
description: Lär dig hur du testar meddelanden med målprofiler och ersättningsadresser.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Control Groups
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 4%

---

# Testa e-postmeddelanden med målprofiler {#testing-message-profiles}

## Översikt {#overview}

Utöver [testprofiler](../../audiences/using/managing-test-profiles.md) kan du testa ett e-postmeddelande genom att placera dig själv i positionen för en av målprofilerna. På så sätt kan du få en exakt representation av meddelandet som profilen kommer att få (anpassade fält, dynamisk och personlig information, inklusive ytterligare data från arbetsflöden..).

>[!IMPORTANT]
>
>Med den här funktionen kan du skicka en profils personuppgifter till externa e-postadresser. Kom ihåg att när du kör förfrågningar om användaruppgifter (GDPR och CCPA) i Campaign Standard VERKSTÄLLS INTE den förfrågan externt.

De huvudsakliga stegen är följande:

1. Konfigurera meddelandet och starta **förberedelsefasen**.
1. **Välj en eller flera profiler** bland de profiler som meddelandet riktar sig till.
1. Associera med varje profil med en **ersättningsadress** som korrektur ska skickas till.
1. (valfritt) För varje profil definierar du ett **prefix** som ska läggas till på korrekturämnesraden.
1. **Förhandsgranska** i e-post-Designer hur meddelandet visas för profilerna.
1. Skicka korrektur.

   >[!IMPORTANT]
   >
   >Korrektur bearbetas av [!DNL Campaign Standard] som standardleveranser. Om du skickar korrektur med hjälp av profilersättning läggs poster till i leverans- och spårningsloggarna för de valda profilerna.

![](assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

## Välja profiler och ersättningsadresser {#selecting-profiles}

Om du vill använda målprofiler för testning måste du först markera dem och sedan definiera ersättningsadresserna som ska ta emot korrekturen. Du kan antingen [välja specifika profiler](#selecting-individual-profiles) bland målprofilerna eller [importera profiler från en befintlig publik](#importing-from-audience).

>[!NOTE]
>
>Du kan välja högst 100 profiler för testning.

### Markera enskilda profiler {#selecting-individual-profiles}

1. Kontrollera att meddelandeförberedelsen fungerar i meddelandekontrollpanelen och klicka sedan på **[!UICONTROL Audience]**-blocket.

   ![](assets/substitution_preparation.png)

1. Klicka på knappen **[!UICONTROL Create element]** på fliken **[!UICONTROL Profile substitutions]** för att välja de profiler som ska användas för testning.

   ![](assets/substitution_tab.png)

1. Klicka på knappen för profilval för att visa listan över profiler som meddelandet riktar sig till.

   ![](assets/substitution_recipient_selection.png)

1. Välj den profil som ska användas för testning, ange önskad ersättningsadress i fältet **[!UICONTROL Address]** och klicka sedan på **[!UICONTROL Confirm]**. Alla korrektur för profilen skickas till den här e-postadressen i stället för till den som definierats i databasen för den här profilen.

   Om du vill lägga till ett specifikt prefix till korrekturens ämnesrad fyller du i fältet **[!UICONTROL Subject line prefix]**.

   >[!NOTE]
   >
   >Ämnesradens prefix kan innehålla upp till 500 tecken.

   ![](assets/substitution_address.png)

   Prefixet visas enligt nedan:

   ![](assets/substitution_prefixsample.png)

1. Profilen läggs till i listan, med tillhörande ersättningsadress och prefix. Upprepa stegen ovan för alla profiler som du vill använda för testning och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Om du vill skicka ett korrektur till flera ersättningsadresser för samma profil måste du lägga till profilen så många gånger som behövs.

   I exemplet nedan skickas korrekturet baserat på profilen Sven Svensson till två olika ersättningsadresser:

   ![](assets/substitution_multiple_addresses.png)

1. När du har definierat alla profiler och ersättningsadresser kan du testa meddelandet genom att skicka ett korrektur. Om du vill göra det klickar du på knappen **[!UICONTROL Test]** och väljer den testtyp som ska utföras.

   Observera att om ingen testprofil har lagts till i meddelandemålet är alternativen **[!UICONTROL Email rendering]** och **[!UICONTROL Proof + Email rendering]** inte tillgängliga.  Mer information om hur du skickar korrektur finns i [det här avsnittet](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Om du ändrar något i meddelandet måste du starta meddelandeförberedelsen igen. I annat fall återspeglas inte ändringarna i korrekturet.

### Importera profiler från en målgrupp {#importing-from-audience}

Med Campaign Standard kan du importera en hel grupp profiler som du kan använda för testning. På så sätt kan du till exempel skicka en hel uppsättning meddelanden till en unik e-postadress med olika profiler som mål.

Om din målgrupp redan har konfigurerats med adresskolumner och prefixkolumner kan du dessutom importera den här informationen på fliken **[!UICONTROL Profile substitutions]**. Ett exempel på publikimport med ersättningsadresser finns i [det här avsnittet](#use-case).

>[!NOTE]
>
>När du importerar en målgrupp markeras bara de profiler som motsvarar meddelandemålet och läggs till på fliken **[!UICONTROL Profile substitutions]**.

Så här importerar du profiler som ska användas för testning från en målgrupp:

1. Kontrollera att meddelandeförberedelsen har slutförts i meddelandekontrollpanelen och klicka sedan på **[!UICONTROL Audience]**-blocket.

   ![](assets/substitution_preparation.png)

1. På fliken **[!UICONTROL Profile substitutions]** klickar du på **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Välj den målgrupp som ska användas och ange sedan ersättningsadressen och det prefix som ska användas för korrekturet som skickas till målgruppen.

   >[!NOTE]
   >
   >Ämnesradens prefix kan innehålla upp till 500 tecken.

   ![](assets/substitution_audience_define.png)

   Om ersättningsadresserna och/eller prefixen som ska användas redan har definierats för din målgrupp väljer du alternativet **[!UICONTROL From Audience]** och anger sedan den kolumn som ska användas för att hämta informationen.

   ![](assets/substitution_fromaudience.png)

1. Klicka på knappen **[!UICONTROL Import]**. Profilerna från målgruppen som motsvarar meddelandemålet läggs till på fliken **[!UICONTROL Profile substitution]**, samt tillhörande ersättningsadresser och prefix.

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>Om du importerar samma målgrupp en gång till, med olika ersättningsadresser och/eller prefix, läggs profilerna till i listan utöver de som fanns vid den tidigare importen.

## Förhandsgranska meddelandet med målprofiler

>[!NOTE]
>
>Förhandsgranskning är endast tillgängligt med e-post-Designer.

Om du vill kunna förhandsgranska meddelanden med målprofiler måste du se till att du har lagt till de här profilerna i listan **[!UICONTROL Profile substitution]** (se [Definiera profiler och ersättningsadresser](#selecting-profiles)).

Om du vill använda anpassningsfält i meddelandet måste de läggas till **innan** som meddelandeförberedelsen startas. I annat fall tas de inte med i förhandsgranskningen. Därför måste du starta meddelandeförberedelsen igen om några ändringar görs i personaliseringsfälten.

Så här förhandsgranskar du meddelanden med hjälp av profilersättning:

1. Klicka på ögonblicksbilden av innehållet i meddelandekontrollpanelen för att öppna meddelandet i e-postens Designer.

   ![](assets/substitution_preview_access.png)

1. Välj fliken **[!UICONTROL Preview]** och klicka sedan på **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Klicka på fliken **[!UICONTROL Profile Substitution]** för att visa ersättningsprofiler som har lagts till för testning.

   Markera de profiler som du vill använda för förhandsgranskning och klicka sedan på **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. En förhandsgranskning av meddelandet visas. Använd pilarna för att navigera mellan de valda profilerna.

   ![](assets/substitution_preview.png)

## Användningsfall {#use-case}

I det här fallet vill vi skicka ett personligt nyhetsbrev via e-post till en uppsättning specifika profiler. Innan vi skickar nyhetsbrevet vill vi förhandsgranska det med några av målprofilerna och skicka korrektur till interna e-postadresser som är definierade i en extern fil.

De viktigaste stegen för detta är följande:

1. Skapa målgruppen som ska användas för testning.
1. Bygg ett arbetsflöde för målprofiler och skicka nyhetsbrevet.
1. Konfigurera meddelandets profilersättningar.
1. Förhandsgranska meddelandet med målprofiler.
1. Skicka korrektur

### Steg 1: Skapa målgruppen som ska användas för testning

1. Förbered filen som ska importeras för att skapa målgruppen. I det här fallet bör den innehålla den ersättningsadress som ska användas för korrekturet och ett prefix som ska läggas till i korrekturets ämnesrad.

   I det här exemplet får e-postadressen&quot;oliver.vaughan@internal.com&quot; ett bevis på meddelandet som riktar sig till profilen med e-postadressen&quot;john.doe@mail.com&quot;. JD-prefixet läggs till i korrekturets ämnesrad.

   ![](assets/substitution_uc1.png)

1. Bygg arbetsflödet för att skapa en målgrupp utifrån filen. Lägg till och konfigurera aktiviteterna nedan för att göra detta:

   * **[!UICONTROL Load file]**-aktivitet: Importerar CSV-filen (mer information om den här aktiviteten finns i [det här avsnittet](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]**-aktivitet: Länkar information från filen till information från databasen. I det här exemplet använder du profilens e-postadress som avstämningsfält (mer information om den här aktiviteten finns i [det här avsnittet](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]**-aktivitet: Skapar en målgrupp baserat på den importerade filen (mer information om den här aktiviteten finns i [det här avsnittet](../../automating/using/save-audience.md)).

   ![](assets/substitution_uc2.png)

1. Kör arbetsflödet och gå sedan till fliken **[!UICONTROL Audiences]** för att kontrollera att målgruppen har skapats med den önskade informationen.

   I det här exemplet består publiken av tre profiler. Var och en av dem är länkad till en e-postadress som ersätter korrekturet, med ett prefix som ska användas på korrekturets ämnesrad.

   ![](assets/substitution_uc3.png)

### Steg 2: Bygg ett arbetsflöde för målprofiler och skicka nyhetsbrevet

1. Lägg till **[!UICONTROL Query]**- och **[!UICONTROL Email delivery]**-aktiviteter och konfigurera dem sedan efter dina behov (se avsnitten [Fråga](../../automating/using/query.md) och [E-postleverans](../../automating/using/email-delivery.md)).

   ![](assets/substitution_uc4.png)

1. Kör arbetsflödet och kontrollera att meddelandeförberedelsen lyckas.

### Steg 3: Konfigurera fliken Profilersättning för meddelandet

1. Öppna aktiviteten **[!UICONTROL Email delivery]**. Klicka på blocket **[!UICONTROL Audience]** i meddelandekontrollpanelen.

   ![](assets/substitution_uc5.png)

1. Välj fliken **[!UICONTROL Profile substitutions]** och klicka sedan på **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. I fältet **[!UICONTROL Audience]** väljer du den målgrupp som skapats från filen.

   ![](assets/substitution_uc7.png)

1. Definiera ersättningsadressen och ämnesradsprefixet som ska användas när korrektur skickas.

   Om du vill göra det väljer du alternativet **[!UICONTROL From audience]** och markerar sedan kolumnen från målgruppen som innehåller informationen.

   ![](assets/substitution_uc8.png)

1. Klicka på knappen **[!UICONTROL Import]**. Profiler från målgruppen läggs till i listan, med tillhörande ersättningsadresser och ämnesradprefix.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >I vårt fall är alla profiler från målgruppen riktade till aktiviteten **[!UICONTROL Query]**. Om en av dessa profiler inte ingick i meddelandemålet läggs den inte till i listan.

### Steg 4: Förhandsgranska meddelandet med målprofiler

1. Klicka på ögonblicksbilden av innehållet i meddelandekontrollpanelen för att öppna meddelandet i e-postens Designer.

   ![](assets/substitution_uc10.png)

1. Välj fliken **[!UICONTROL Preview]** och klicka sedan på **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Klicka på fliken **[!UICONTROL Profile Substitution]** för att visa ersättningsprofiler som har lagts till tidigare.

   Markera de profiler som du vill använda för förhandsgranskning och klicka sedan på **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. En förhandsgranskning av meddelandet visas. Använd pilarna för att navigera mellan de valda profilerna.

   ![](assets/substitution_uc_previewprofile.png)

### Steg 5: Skicka korrektur

1. Klicka på knappen **[!UICONTROL Test]** i meddelandekontrollpanelen och bekräfta sedan.

   ![](assets/substitution_uc_sendproof.png)

1. Korrektur skickas enligt inställningarna på fliken **[!UICONTROL Profile substitutions]**.

   ![](assets/substitution_uc_proofs.png)

## Självstudievideo {#video}

I den här videon visas hur du kan testa dina e-postmeddelanden med hjälp av profilersättning.

>[!VIDEO](https://video.tv.adobe.com/v/32368?quality=12)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
