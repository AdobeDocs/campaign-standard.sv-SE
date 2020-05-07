---
title: Anropa en resurs med en sammansatt identifieringsnyckel
description: Lär dig hur du anropar en resurs med en sammansatt identifieringsnyckel
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---


# Anropa en resurs med en sammansatt identifieringsnyckel{#calling-a-resource-using-a-composite-identification-key}

I vissa fall kan du behöva definiera en identifieringsnyckel som består av två fält för en resurs. När identifieringsnyckeln har konfigurerats måste du konfigurera en filterdefinition för att kunna anropa resursen med den här identifieringsnyckeln, antingen från gränssnittet i Campaign Standard eller API:erna.

I det här fallet har **profilresursen** utökats med det anpassade fältet **&quot;CRM ID&quot;** och **&quot;category&quot;** . Vi skapar en identifieringsnyckel för profilresursen som består av dessa två fält. Sedan konfigurerar vi en filterdefinition så att vi kan komma åt profilresursen med hjälp av identifieringsnyckeln.

De huvudsakliga stegen för det här användningsexemplet är:

1. Konfigurera identifieringsnyckeln för profilresursen baserat på de två fälten.
1. Konfigurera filterdefinitionen för att kunna anropa profilresursen med hjälp av dess identifieringsnyckel.
1. Anropa profilresursen från gränssnittet eller från APis.

Relaterade ämnen:

* [Skapa eller utöka resursen](../../developing/using/creating-or-extending-the-resource.md)
* [Definiera identifieringsnycklar](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [REST API:er för Campaign Standard](../../api/using/get-started-apis.md)

## Steg 1: Konfigurera identifieringsnyckeln{#step-1-configure-the-identification-key}

>[!NOTE]
> Globala koncept för konfiguration av identifieringsnycklar beskrivs i [det här avsnittet](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Innan du konfigurerar identifieringsnyckeln måste du kontrollera att resursen har utökats med de önskade fälten och att den har publicerats. For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. Gå till menyn **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** och öppna sedan **[!UICONTROL Profile]** resursen.

   ![](assets/uc_idkey1.png)

1. Klicka på **[!UICONTROL Identification keys]** knappen i **[!UICONTROL Create element]** avsnittet.

   ![](assets/uc_idkey2.png)

1. Lägg till de två anpassade fälten &quot;CRM ID&quot; och &quot;Category&quot; och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Om du vill visa de två anpassade fälten i profilens gränssnitt konfigurerar du **[!UICONTROL Screen definition]** fliken. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. Nu kan du konfigurera filterdefinitionen så att den kan anropa resursen med hjälp av dess identifieringsnyckel.

## Steg 2: Konfigurera filterdefinitionen{#step-2-configure-the-filter-definition}

>[!NOTE]
> Globala koncept för konfiguration av filterdefinitioner beskrivs i [det här avsnittet](../../developing/using/configuring-filter-definition.md).

1. Klicka på **[!UICONTROL Filter definition]** fliken **[!UICONTROL Add an element]** och ange sedan filterdefinitionens etikett och ID.

1. Redigera filterdefinitionens egenskaper för att konfigurera dess regler.

   ![](assets/uc_idkey4.png)

1. Dra och släpp den tabell som innehåller de fält som används i identifieringsnyckeln till arbetsytan.

   ![](assets/uc_idkey5.png)

1. Markera det första fältet som används i identifieringsnyckeln (&quot;CRM-ID&quot;) och aktivera sedan **[!UICONTROL Switch to parameters]** alternativet.

   ![](assets/uc_idkey6.png)

1. I **[!UICONTROL Filter conditions]** avsnittet behåller du **[!UICONTROL Equal]** operatorn, definierar parameterns namn och klickar på plustecknet för att skapa den.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > När du har klickat på plusknappen genereras parameternamnet automatiskt. Observera den här informationen eftersom du behöver den för att använda filtret från API:erna.

1. Upprepa stegen ovan med alla fält som utgör identifieringsnyckeln (&quot;kategori&quot;) och spara sedan ändringarna.

   ![](assets/uc_idkey8.png)

1. Filterdefinitionen är nu konfigurerad. Du kan publicera resursen så att filtret är tillgängligt.

## Steg 3: Anropa resursen baserat på dess identifieringsnyckel{#step-3-call-the-resource-based-on-its-identification-key}

När identifieringsnyckeln och filterdefinitionen har konfigurerats kan du använda dem för att anropa resursen, antingen från standardgränssnittet för Campaign eller från REST-API:er.

Om du vill använda filterdefinitionen från gränssnittet använder du en **[!UICONTROL Query]** aktivitet i ett arbetsflöde (se [det här avsnittet](../../automating/using/query.md)). Filtret är sedan tillgängligt i den vänstra rutan.

![](assets/uc_idkey9.png)

Om du vill använda filterdefinitionen från Campaign Standard REST API:er använder du syntaxen nedan:

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Om du vill anropa ett kundfilter använder du prefixet &quot;by&quot; följt av det filternamn som definierats när filterdefinitionen konfigurerades i [steg 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

I det här fallet skulle syntaxen för att hämta en profil från kategorin &quot;vår&quot; med CRM-ID:t &quot;123456&quot; vara:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Mer information finns i dokumentationen för [Campaign Standard REST APIs](../../api/using/filtering.md).