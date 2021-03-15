---
solution: Campaign Standard
product: campaign
title: Konfigurera skärmdefinitionen
description: Lär dig hur du definierar nya Adobe Campaign-skärmar baserat på resursdatastrukturen.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 99%

---


# Konfigurera skärmdefinitionen{#configuring-the-screen-definition}

När du skapar en resurs eller lägger till nya fält till en befintlig resurs kan du definiera hur de ska visas i gränssnittet.

Det här steget är inte obligatoriskt eftersom du fortfarande kan fylla i resursen och komma åt datan via arbetsflöden, målgrupper och REST API.

På fliken **[!UICONTROL Screen definition]** kan du:

* Lägg till åtkomst till den anpassade resursen i navigeringsrutan
* Anpassa hur listan med element som utgör resursen presenteras
* Definiera hur detaljvyn för varje element i resursen visas

## Aktivera åtkomst från navigeringsmenyn {#enabling-access-from-the-navigation-menu}

Om du vill att resursen ska ha en dedikerad skärm kan du göra den tillgänglig via navigeringsmenyn.

1. Öppna avsnittet **[!UICONTROL Navigation]** från resursens **[!UICONTROL Screen definition]**-flik.
1. Markera rutan **[!UICONTROL Add an entry in the 'Client data' section]** om du vill tillåta åtkomst till den här resursen från navigeringsrutan.

   ![](assets/schema_extension_19.png)

Resursen visas som en underpost i avsnittet **[!UICONTROL Client data]**.

## Definiera standardlistkonfigurationen {#defining-the-default-list-configuration}

I avsnittet **[!UICONTROL List configuration]** om skärmdefinitionen kan du definiera kolumner och information som ska visas som standard i översikten för en resurs.

1. Markera rutan **[!UICONTROL Customize the list configuration]** för att definiera hur resursens kolumner ska visas.
1. Använd knappen **[!UICONTROL Create element]** för att välja ett fält bland dem som du har skapat.
1. Fältet som skapas visas i listan. Du kan redigera etiketten och dess bredd.

   ![](assets/schema_extension_20.png)

1. I avsnittet **[!UICONTROL Simple search]** markerar du **[!UICONTROL Specify the fields to be taken into account in the search]** för att definiera vilka fält som ska ingå i sökningen.

   >[!IMPORTANT]
   >
   >Den här konfigurationen ersätter de fält som används i standardsökningen.

1. I avsnittet **[!UICONTROL Advanced filtering]** markerar du rutan **[!UICONTROL Add search fields]** för att lägga till fler fält utanför det enkla sökfältet. Om du t.ex. väljer datumfältet i de fält som du har skapat, kan användaren göra en sökning som bara hänvisar till datumet.
1. Du kan ändra fältordningen för de två söktyperna.
1. Om du vill göra en avancerad sökning kan du lägga till fält som länkar till en kopplad resurs. Dessa filter visas på den genererade skärmens **[!UICONTROL Search]**-meny.

Översiktsskärmen för resursen är nu definierad.

## Definiera detaljskärmens konfiguration {#defining-the-detail-screen-configuration}

I avsnittet **[!UICONTROL Detail screen configuration]** om skärmdefinitionen kan du definiera de kolumner och den information som ska visas på detaljskärmen för varje element i resursen.

1. Visa upp avsnittet **[!UICONTROL Detail screen configuration]** och kontrollera **[!UICONTROL Define a detail screen]** för att konfigurera skärmen som motsvarar varje element i resursen. Om du inte markerar den här rutan är detaljvyn för den här resursens element inte tillgänglig.
1. Du kan lägga till alla fält från din anpassade resurs med ett klick. Klicka på ![](assets/addallfieldsicon.png)-ikonen eller använd knappen **[!UICONTROL Add an element]** för att göra detta.
1. Välj ett element från de som skapats för den här resursen och ange en fälttyp:

   * **[!UICONTROL Input field]**: är ett redigerbart fält.
   * **[!UICONTROL Value]**: är ett skrivskyddat fält.
   * **[!UICONTROL List]**: är en tabell.
   * **[!UICONTROL Separator]**: delar upp elementen i kategorier.

   ![](assets/schema_extension_23.png)

1. Det element som läggs till visas i listan. Du kan redigera etiketten för den.

   ![](assets/schema_extension_22.png)

1. Lägg till så många **[!UICONTROL Separator]** som behövs för att dela upp elementen i olika kategorier.

   På så sätt kan du visa avgränsare för att bättre ordna dina fönster.

   ![](assets/schema_extension_25.png)

Detaljskärmen för resursen har nu konfigurerats.

## Åtgärder i dataavsnittet {#actions-on-data-section}

Med de här inställningarna kan du visa ett kontrollfält på den anpassade resursskärmen. Det finns tre alternativ:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: Med det här alternativet kan du aktivera skapande av resurselement. Användaren kan därför lägga till fler poster.

   >[!NOTE]
   >
   >Du måste först aktivera detaljskärmen som är kopplad till resursen för att göra det här alternativet tillgängligt.

* **[!UICONTROL Authorize duplicating]**: Med det här alternativet kan du aktivera dubblettposter som är kopplade till den anpassade resursen.
* **[!UICONTROL Authorize deleting]**: Med det här alternativet kan du aktivera borttagning av poster som är kopplade till den anpassade resursen.
