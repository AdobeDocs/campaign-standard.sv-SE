---
title: Komma igång med e-postdesignern
description: Bygg e-postinnehåll med e-post-Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 47f53290-2190-4181-bcd5-e60287189c41
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 4%

---

# Komma igång med e-postdesignern {#quick-start}

I e-postmeddelandet från Designer finns fyra sätt att skapa e-postmeddelanden.

Du kan skapa ett e-postmeddelande [som börjar om i e-postmeddelandet Designer](#without-existing-content):

1. Du kan **skapa ett e-postmeddelande från en tom arbetsyta** genom att enkelt lägga till struktur- och innehållskomponenter och anpassa deras innehåll för att skicka en leverans snabbt. Du kan också hantera formatelement helt. Om du vill ha mer information kan du [komma igång snabbt](#from-scratch-email) eller läsa den [fullständiga dokumentationen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Du kan **skapa ett e-postmeddelande från en färdig mall** genom att välja en mall och skapa ditt nya e-postinnehåll härifrån. [Läs mer](#building-content-from-an-out-of-the-box-template)

Du kan också skapa ett e-postmeddelande [med befintligt innehåll](#with-existing-content):

1. Du kan **konvertera ett befintligt HTML-innehåll** (skapat externt eller i den äldre redigeraren). [Läs mer](#converting-an-html-content)
1. Du kan **importera ett befintligt HTML-innehåll** direkt i kompatibilitetsläge. [Läs mer](#compatibility-mode)

| Utan innehåll | Med innehåll |
|---|---|
| [Skapa ett e-postmeddelande från grunden](#from-scratch-email) | [Konverterar befintligt HTML-innehåll](#converting-an-html-content) |
| [Skapa innehåll från en mall som inte är installerad](#building-content-from-an-out-of-the-box-template) | [Importera en befintlig HTML](#compatibility-mode) |

## Utforma e-postmeddelanden med redigeraren {#without-existing-content}

>[!NOTE]
>
>I båda dessa strategier är det viktigt att du fyller i ämnesraden innan du skickar e-postmeddelandet. Lär dig hur du [lägger till en ämnesrad](#add-a-subject-line).

### Skapa ett e-postmeddelande från grunden {#from-scratch-email}

Du kan enkelt skapa e-postmeddelanden, lägga till komponenter och anpassa deras innehåll för att snabbt skicka en leverans. Du kan anpassa formatalternativen efter ditt innehåll om det behövs. Mer information om hur du hanterar formatinställningar och infogade attribut finns i [Redigera e-postformat](../../designing/using/styles.md).

1. Skapa ett mejl.
1. Stäng hemsidan.

### Lägga till en ämnesrad {#add-a-subject-line}

Ärenderader är obligatoriska när du skickar e-post. Mer information finns i [Definiera ämnesraden i ett e-postmeddelande](../../designing/using/subject-line.md).

1. Gå till fliken **[!UICONTROL Properties]** på e-posthemsidan för Designer (nås via hemikonen) och fyll i avsnittet **[!UICONTROL Subject]**.

![](assets/subject-line-quick-start.png)

### Lägga till strukturkomponenter {#add-structure-components}

Strukturkomponenter definierar layouten för e-postmeddelandet. Mer information finns i [Definiera strukturen för ett e-postmeddelande](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

Dra och släpp komponenter för den layout som du vill använda i Strukturkomponenter.

>[!NOTE]
>
>Du kan välja olika innehållslayouter som läggs till i e-postmeddelandet.

![](assets/structure-components-quick-start.png)

### Lägga till innehållskomponenter {#add-content-components}

Du kan lägga till flera innehållskomponenter i e-postmeddelandet, till exempel bild, text och knappar. Mer information finns i [Innehållskomponenter](../../designing/using/designing-from-scratch.md#about-content-components).

* **Bild**

   1. I **Innehållskomponenter** drar och släpper du en bild i en av strukturkomponenterna.
   1. Klicka på **Bläddra**.
   1. Välj bildfilen på datorn.

  ![](assets/browse-image-quick-start.png)

* **Text med personalisering**

   1. I **Innehållskomponenter** drar och släpper du text i en av strukturkomponenterna.
   1. Klicka på komponenten och ange texten.
   1. Om du vill lägga till ett anpassningsfält klickar du på **Infoga anpassningsfält** i verktygsfältet.
   1. Markera det fält som du behöver, t.ex. Förnamn.

  ![](assets/edit-text-quick-start.png)

* **HTML**

   1. I **Innehållskomponenter** drar och släpper du HTML i en av strukturkomponenterna.
   1. Klicka på **Visa källkoden**.
   1. Ange HTML innehåll.
   1. Klicka på **Spara**.

  ![](assets/html-component-source-code.png)

  Om du är bekant med HTML kan du kopiera och klistra in HTML-koden från den ursprungliga sidfoten med innehållskomponenten **[!UICONTROL Html]**. Mer information finns i [Om innehållskomponenter](../../designing/using/designing-from-scratch.md#about-content-components).

  ![](assets/des_loading_compatible_fragment_9.png)

### Utforma e-postkomponenten

Du kan justera din e-poststil, till exempel genom att ändra utfyllnaden för en komponent. Mer information om hur du hanterar formatinställningar och infogade attribut finns i [Redigera e-postformat](../../designing/using/styles.md).

1. Klicka på din **textkomponent**.
1. Gå till **Utfyllnad** till höger på paletten.
1. Klicka på låsikonen om du vill bryta synkroniseringen mellan parametrarna längst upp, längst ned eller till höger och vänster.
1. Justera **Utfyllnaden** efter behov.
1. Klicka på **Spara**.

![](assets/padding-quick-start.png)

Nu kan du spara och skicka e-postmeddelanden.

### Bygga innehåll från en färdig mall {#building-content-from-an-out-of-the-box-template}

Ni kan skapa ett e-postmeddelande utifrån färdiga mallar, som välkomstmeddelanden, nyhetsbrev och e-postmeddelanden om återengagemang och personalisera dem.

1. Skapa ett e-postmeddelande och öppna innehållet i det. Mer information finns i [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md).
1. Klicka på hemikonen för att komma åt startsidan för **[!UICONTROL Email Designer]**.
1. Klicka på fliken **[!UICONTROL Templates]**.
1. Välj en färdig HTML-mall.
De olika mallarna innehåller olika kombinationer av olika typer av element. Mallar av typen &quot;Ludd&quot; har till exempel marginaler medan mallar av typen &quot;Astro&quot; inte har några. Mer information finns i [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates).
1. Gå till fliken **[!UICONTROL Properties]** på e-posthemsidan för Designer (nås via hemikonen) och fyll i avsnittet **[!UICONTROL Subject]**.
1. Du kan kombinera dessa element för att skapa ett antal e-postvarianter. Du kan till exempel duplicera ett e-postavsnitt genom att markera en strukturkomponent och klicka på **[!UICONTROL Duplicate]** i det sammanhangsberoende verktygsfältet.
1. Du kan flytta runt elementen med hjälp av den blå pilen till vänster om du vill dra en strukturkomponent under eller över en annan. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Du kan också flytta runt komponenter för att ändra ordningen på varje strukturelement. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Ändra innehållet i varje element efter dina behov: bilder, text, länkar.
1. Anpassa formatalternativen till innehållet om det behövs. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).

## Använda befintligt e-postinnehåll {#with-existing-content}

Om du vill skapa ett ramverk med modulära mallar och fragment som kan kombineras för återanvändning i flera e-postmeddelanden bör du överväga att konvertera e-postmeddelandet till en Designer-mall för e-post.

### Konverterar HTML-innehåll {#converting-an-html-content}

Det här är ett snabbt sätt att konvertera HTML-e-post till e-postkomponenter i Designer. Mer information om det här avsnittet finns i [Konvertera HTML-innehåll](../../designing/using/using-existing-content.md#converting-an-html-content).

>[!CAUTION]
>
>Det här avsnittet är till för användare som känner till HTML-kod.

>[!NOTE]
>
>Kompatibilitetsläget är precis som kompatibilitetsläget redigerbart för en HTML-komponent med begränsade alternativ: du kan bara utföra en version på plats.


### Importera och redigera ett e-postmeddelande från HTML {#compatibility-mode}

När du överför ett innehåll måste det innehålla specifik taggning för att vara helt kompatibelt och redigerbart med WYSIWYG-redigeraren i e-postprogrammet för Designer.

Mer information om hur du konverterar ett befintligt e-postmeddelande till ett e-postkompatibelt Designer-e-postmeddelande finns i [det här avsnittet](../../designing/using/using-existing-content.md#compatibility-mode).
