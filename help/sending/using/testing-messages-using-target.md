---
title: Testa e-postmeddelanden med målprofiler
description: Lär dig hur du testar meddelanden med målprofiler och ersättningsadresser.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f0df05a08cc07b7c2a5b8e175177006360e7e7d

---


# Testa e-postmeddelanden med målprofiler {#testing-message-profiles}

## Översikt {#overview}

Utöver att [testa profiler](../../audiences/using/managing-test-profiles.md)kan du testa ett e-postmeddelande genom att placera dig själv i positionen för en av målprofilerna. På så sätt kan du få en exakt representation av meddelandet som profilen kommer att få (anpassade fält, dynamisk och personlig information, inklusive ytterligare data från arbetsflöden..).

>[!NOTE]
>
> Den här funktionen är endast tillgänglig för e-postmeddelanden.

De huvudsakliga stegen är följande:

1. Konfigurera meddelandet och starta **förberedelsefasen** .
1. **Markera en eller flera profiler** bland de profiler som meddelandet riktar sig till.
1. Associera med varje profil med en **ersättningsadress** till vilken korrektur ska skickas.
1. (valfritt) För varje profil definierar du ett **prefix** som ska läggas till på korrekturämnesraden.
1. **Förhandsgranska** i e-postdesignern hur meddelandet visas för profilerna.
1. Skicka korrektur.

Mer information om den globala processen finns i självstudiekursen som finns [här](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html).

>[!IMPORTANT]
>
>Med den här funktionen kan du skicka profilpersonuppgifter till externa e-postadresser. Kom ihåg att när du kör sekretessförfrågningar (GDPR &amp; CCPA) i Campaign Standard kommer denna begäran inte att verkställas externt.

## Välja profiler och ersättningsadresser {#selecting-profiles}

Om du vill använda målprofiler för testning måste du först markera dem och sedan definiera ersättningsadresserna som ska ta emot korrekturen. För att göra detta kan du antingen [välja specifika profiler](#selecting-individual-profiles) bland målprofilerna eller [importera profiler från en befintlig målgrupp](#importing-from-audience).

>[!NOTE]
>
>Du kan välja högst 100 profiler för testning.

### Markera enskilda profiler {#selecting-individual-profiles}

1. Kontrollera att meddelandeförberedelsen fungerar i meddelandekontrollpanelen och klicka sedan på **[!UICONTROL Audience]** blocket.

   ![](assets/substitution_preparation.png)

1. Klicka på **[!UICONTROL Profile substitutions]** knappen på **[!UICONTROL Create element]** fliken för att välja de profiler som ska användas för testning.

   ![](assets/substitution_tab.png)

1. Klicka på knappen för profilval för att visa listan över profiler som meddelandet riktar sig till.

   ![](assets/substitution_recipient_selection.png)

1. Välj den profil som ska användas för testning, ange önskad ersättningsadress i **[!UICONTROL Address]** fältet och klicka sedan på **[!UICONTROL Confirm]**. Alla korrektur för profilen skickas till den här e-postadressen i stället för till den som definierats i databasen för den här profilen.

   Om du vill lägga till ett specifikt prefix till korrekturens ämnesrad fyller du i **[!UICONTROL Subject line prefix]** fältet.

   ![](assets/substitution_address.png)

   Prefixet visas enligt nedan:

   ![](assets/substitution_prefixsample.png)

1. Profilen läggs till i listan, med tillhörande ersättningsadress och prefix. Upprepa stegen ovan för alla profiler som du vill använda för testning och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Om du vill skicka ett korrektur till flera ersättningsadresser för samma profil måste du lägga till profilen så många gånger som behövs.

   I exemplet nedan skickas korrekturet baserat på profilen Sven Svensson till två olika ersättningsadresser:

   ![](assets/substitution_multiple_addresses.png)

1. När du har definierat alla profiler och ersättningsadresser kan du testa meddelandet genom att skicka ett korrektur. Det gör du genom att klicka på **[!UICONTROL Test]** knappen och sedan välja vilken testtyp som ska utföras.

   Observera att om ingen testprofil har lagts till i meddelandemålet är alternativen **[!UICONTROL Email rendering]** och **[!UICONTROL Proof + Email rendering]** inte tillgängliga.  Mer information om hur du skickar korrektur finns i [det här avsnittet](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Om du ändrar något i meddelandet måste du starta meddelandeförberedelsen igen. I annat fall återspeglas inte ändringarna i korrekturet.

### Importera profiler från en målgrupp {#importing-from-audience}

Med Campaign Standard kan ni importera en målgrupp med profiler som ni kan använda för testning. På så sätt kan du till exempel skicka en hel uppsättning meddelanden till en unik e-postadress med olika profiler som mål.

Om målgruppen redan har konfigurerats med adresskolumnerna och prefixkolumnerna kan du dessutom importera den här informationen på **[!UICONTROL Profile substitutions]** fliken. Ett exempel på publikimport med ersättningsadresser finns i [det här avsnittet](#use-case).

>[!NOTE]
>
>När du importerar en målgrupp markeras bara de profiler som motsvarar meddelandemålet och läggs till på **[!UICONTROL Profile substitutions]** fliken.

Så här importerar du profiler som ska användas för testning från en målgrupp:

1. Kontrollera att meddelandeförberedelsen har slutförts i meddelandekontrollpanelen och klicka sedan på **[!UICONTROL Audience]** blocket.

   ![](assets/substitution_preparation.png)

1. In the **[!UICONTROL Profile substitutions]** tab, click **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Välj den målgrupp som ska användas och ange sedan ersättningsadressen och det prefix som ska användas för korrekturet som skickas till målgruppen.

   ![](assets/substitution_audience_define.png)

   Om ersättningsadresserna och/eller prefixen som ska användas redan har definierats för din målgrupp väljer du **[!UICONTROL From Audience]** alternativet och anger sedan den kolumn som ska användas för att hämta informationen.

   ![](assets/substitution_fromaudience.png)

1. Klicka på **[!UICONTROL Import]** knappen. Profilerna från målgruppen som motsvarar meddelandemålet läggs till på **[!UICONTROL Profile substitution]** fliken, samt tillhörande ersättningsadresser och prefix.

>[!NOTE]
>
>Om du importerar samma målgrupp en gång till, med olika ersättningsadresser och/eller prefix, läggs profilerna till i listan utöver de som fanns vid den tidigare importen.

![](assets/substitution_audience_added.png)

## Förhandsgranska meddelandet med målprofiler

>[!NOTE]
>
>Förhandsgranskning är endast tillgängligt med e-postdesignern.

Om du vill kunna förhandsgranska meddelanden med målprofiler måste du se till att du har lagt till de här profilerna i **[!UICONTROL Profile substitution]** listan (se [Definiera profiler och ersättningsadresser](#selecting-profiles)).

Om du vill använda anpassningsfält i meddelandet måste de läggas till **innan** du startar meddelandeförberedelsen. I annat fall beaktas de inte i förhandsgranskningen. Därför måste du starta meddelandeförberedelsen igen om några ändringar görs i personaliseringsfälten.

Så här förhandsgranskar du meddelanden med hjälp av profilersättning:

1. Klicka på ögonblicksbilden av innehållet i meddelandekontrollpanelen för att öppna meddelandet i e-postdesignern.

   ![](assets/substitution_preview_access.png)

1. Markera **[!UICONTROL Preview]** fliken och klicka sedan på **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Klicka på **[!UICONTROL Profile Substitution]** fliken för att visa ersättningsprofiler som har lagts till för testning.

   Markera de profiler som du vill använda för förhandsgranskning och klicka sedan på **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. En förhandsgranskning av meddelandet visas. Använd pilarna för att navigera mellan de valda profilerna.

   ![](assets/substitution_preview.png)

## Använd skiftläge {#use-case}

I det här fallet vill vi skicka ett personligt nyhetsbrev via e-post till en uppsättning specifika profiler. Innan vi skickar nyhetsbrevet vill vi förhandsgranska det med några av målprofilerna och skicka korrektur till interna e-postadresser som är definierade i en extern fil.

De viktigaste stegen för detta är följande:

1. Skapa målgruppen som ska användas för testning.
1. Bygg ett arbetsflöde för målprofiler och skicka nyhetsbrevet.
1. Konfigurera meddelandets profilersättningar.
1. Förhandsgranska meddelandet med målprofiler.
1. Skicka korrektur.

### Steg 1: Skapa målgruppen som ska användas för testning

1. Förbered filen som ska importeras för att skapa målgruppen. I det här fallet bör den innehålla den ersättningsadress som ska användas för korrekturet och ett prefix som ska läggas till i korrekturets ämnesrad.

   I det här exemplet får e-postadressen&quot;oliver.vaughan@internal.com&quot; ett bevis på meddelandet som riktar sig till profilen med e-postadressen&quot;john.doe@mail.com&quot;. JD-prefixet läggs till i korrekturets ämnesrad.

   ![](assets/substitution_uc1.png)

1. Bygg arbetsflödet för att skapa en målgrupp utifrån filen. Lägg till och konfigurera aktiviteterna nedan för att göra detta:

   * **[!UICONTROL Load file]** aktivitet: Importerar CSV-filen (mer information om den här aktiviteten finns i [det här avsnittet](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]** aktivitet: Länkar information från filen till information från databasen. I det här exemplet använder vi profilens e-postadress som avstämningsfält (mer information om den här aktiviteten finns i [det här avsnittet](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** aktivitet: Skapar en målgrupp baserat på den importerade filen (mer information om den här aktiviteten finns i [det här avsnittet](../../automating/using/save-audience.md)).
   ![](assets/substitution_uc2.png)

1. Kör arbetsflödet och gå sedan till **[!UICONTROL Audiences]** fliken för att kontrollera att målgruppen har skapats med önskad information.

   I det här exemplet består publiken av tre profiler. Var och en av dem är länkad till en e-postadress som ersätter korrekturet, med ett prefix som ska användas på korrekturets ämnesrad.

   ![](assets/substitution_uc3.png)

### Steg 2: Bygg ett arbetsflöde för målprofiler och skicka nyhetsbrevet

1. Lägg till **[!UICONTROL Query]** och **[!UICONTROL Email delivery]** konfigurera aktiviteter efter dina behov (se avsnitten [Fråga](../../automating/using/query.md) och [E-postleverans](../../automating/using/email-delivery.md) ).

   ![](assets/substitution_uc4.png)

1. Kör arbetsflödet och kontrollera att meddelandeförberedelsen lyckas.

### Steg 3: Konfigurera fliken Profilersättning för meddelandet

1. Öppna **[!UICONTROL Email delivery]** aktiviteten. Klicka på **[!UICONTROL Audience]** blocket i meddelandekontrollpanelen.

   ![](assets/substitution_uc5.png)

1. Markera **[!UICONTROL Profile substitutions]** fliken och klicka sedan på **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. I **[!UICONTROL Audience]** fältet väljer du den målgrupp som skapas från filen.

   ![](assets/substitution_uc7.png)

1. Definiera ersättningsadressen och ämnesradsprefixet som ska användas när korrektur skickas.

   Det gör du genom att markera **[!UICONTROL From audience]** alternativet och sedan markera kolumnen som innehåller informationen.

   ![](assets/substitution_uc8.png)

1. Klicka på **[!UICONTROL Import]** knappen. Profiler från målgruppen läggs till i listan, med tillhörande ersättningsadresser och ämnesradprefix.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >I vårt fall är alla profiler från målgruppen riktade till **[!UICONTROL Query]** aktiviteten. Om en av dessa profiler inte ingick i meddelandemålet läggs den inte till i listan.

### Steg 4: Förhandsgranska meddelandet med målprofiler

1. Klicka på ögonblicksbilden av innehållet i meddelandekontrollpanelen för att öppna meddelandet i e-postdesignern.

   ![](assets/substitution_uc10.png)

1. Markera **[!UICONTROL Preview]** fliken och klicka sedan på **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Klicka på **[!UICONTROL Profile Substitution]** fliken för att visa ersättningsprofilerna som har lagts till tidigare.

   Markera de profiler som du vill använda för förhandsgranskning och klicka sedan på **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. En förhandsgranskning av meddelandet visas. Använd pilarna för att navigera mellan de valda profilerna.

   ![](assets/substitution_uc_previewprofile.png)

### Steg 5: Skicka korrektur

1. Klicka på **[!UICONTROL Test]** knappen i meddelandekontrollpanelen och bekräfta sedan.

   ![](assets/substitution_uc_sendproof.png)

1. Korrektur skickas enligt inställningarna på **[!UICONTROL Profile substitutions]** fliken.

   ![](assets/substitution_uc_proofs.png)
