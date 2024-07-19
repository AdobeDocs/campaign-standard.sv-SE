---
title: Lägga till länkar
description: Lär dig hantera länkar med e-post-Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: 146dfea38bd456a5d9200b0632d4aa279b10a7b9
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# Lägga till länkar {#links}

## Infoga en länk {#inserting-a-link}

Med redigeraren kan du anpassa en e-post- eller landningssida genom att infoga länkar i HTML innehållselementen.

Du kan infoga en länk i vilket sidelement som helst: bild, ord, ordgrupp, textblock osv.

>[!NOTE]
>
>Bilderna nedan visar hur du infogar en länk med hjälp av [e-post-Designer](../../designing/using/designing-content-in-adobe-campaign.md) i ett e-postmeddelande.

1. Markera ett element och klicka på **[!UICONTROL Insert link]** i det sammanhangsberoende verktygsfältet.

   ![](assets/des_insert_link.png)

1. Välj den typ av länk som du vill skapa:

   * **Extern länk**: infoga en länk till en extern URL.

     Du kan definiera personalisering för dina URL-adresser. Se [Anpassa URL:er](personalization.md#personalizing-urls).

   * **Landningssida**: ge åtkomst till en Adobe Campaign-landningssida.
   * **Prenumerationslänk**: infoga en länk för att prenumerera på en Adobe Campaign-tjänst.
   * **Avbeställningslänk**: infoga en länk för att avbryta prenumerationen på en Adobe Campaign-tjänst.
   * **Länk som definierar en åtgärd**: definiera en åtgärd när någon klickar på ett element på landningssidan.

     >[!NOTE]
     >
     >Den här typen av länk är bara tillgänglig för landningssidor.

1. Du kan ändra texten som visas för mottagaren.
1. Du kan ange webbläsarbeteende när användaren klickar på länken (till exempel öppna ett nytt fönster).

   >[!NOTE]
   >
   >När du definierar webbläsarbeteendet gäller det bara landningssidor.

1. Spara ändringarna.

När länken har skapats kan du fortfarande ändra den i inställningspanelen. Klicka på pennikonen för att redigera dess parametrar.

![](assets/des_link_edit.png)

När du redigerar ett e-postmeddelande med [e-post-Designer](../../designing/using/designing-content-in-adobe-campaign.md) kan du enkelt komma åt och ändra länkarna som du skapade från tabellen med alla URL:er som finns i e-postmeddelandet. Med den här listan kan du ha en centraliserad vy och hitta varje URL i e-postinnehållet. Mer information finns i [Om spårade URL:er](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>Det går inte att ändra anpassade URL:er som **Spegelsidans URL** eller **länken Avsluta prenumeration** från den här listan. Alla andra länkar kan redigeras.

**Relaterade ämnen**:

* [Infoga ett anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Lägga till innehållsblock](../../designing/using/personalization.md#adding-a-content-block)
* [Definiera dynamiskt innehåll](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Om spårade URL:er {#about-tracked-urls}

Med Adobe Campaign kan du spåra mottagarnas beteende när de klickar på en URL som ingår i ett e-postmeddelande. Se [det här avsnittet](../../sending/using/tracking-messages.md#about-tracking) för mer om spårning.

Ikonen **[!UICONTROL Links]** i åtgärdsfältet visar automatiskt en lista med alla URL:er för ditt innehåll som ska spåras.

![](assets/des_links.png)

>[!NOTE]
>
>Spårning är aktiverat som standard. Den här funktionen är bara tillgänglig för e-postmeddelanden om spårning har aktiverats i Adobe Campaign. Mer information om spårningsparametrar finns i [det här avsnittet](../../administration/using/configuring-email-channel.md#tracking-parameters).

URL, kategori, etikett och spårningstyp för varje länk kan ändras i den här listan. Om du vill redigera en länk klickar du på motsvarande pennikon.

![](assets/des_links_tracking.png)

För varje spårad URL-adress kan du ange spårningsläget till något av följande värden:

* **Spårat**: aktiverar spårning på den här URL:en.
* **Spegelsida**: anser att den här URL:en är en URL för en spegelsida.
* **Aldrig**: Aktiverar aldrig spårning av den här URL:en. Den här informationen sparas: om URL:en visas igen i ett framtida meddelande inaktiveras spårningen automatiskt.
* **Avanmäl dig**: betraktar den här URL:en som en avanmälnings- eller avanmälnings-URL.

![](assets/des_link_tracking_type.png)

Du kan även inaktivera eller aktivera spårning för varje URL.

>[!NOTE]
>
>Som standard spåras alla innehålls-URL:er i Adobe Campaign, förutom länken **Spegelsidans URL** och **Avsluta prenumeration** .

Du kan gruppera om dina URL-adresser genom att redigera fältet **[!UICONTROL Category]**, beroende på vilka URL-adresser som används i meddelandet. Dessa kategorier kan visas som rapporter, till exempel i [URL:er och klicka på strömmar](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

När du skapar en rapport väljer du **[!UICONTROL Dimension]** på fliken **[!UICONTROL Components]** och rullar nedåt i listan för att komma åt spårningskomponenterna. Dra och släpp **[!UICONTROL Tracking URL Category]** till arbetsytan för att visa resultat enligt spårningskategorin för varje klickad URL.

![](assets/des_link_tracking_report.png)

Mer information om hur du skapar anpassade rapporter finns i [det här avsnittet](../../reporting/using/about-dynamic-reports.md).
