---
title: Anropa en resurs med en sammansatt identifieringsnyckel
description: Lär dig hur du anropar en resurs med en sammansatt identifieringsnyckel
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# Anropa en resurs med en sammansatt identifieringsnyckel{#calling-a-resource-using-a-composite-identification-key}

I vissa fall kan du behöva definiera en identifieringsnyckel som består av två fält för en resurs. När identifieringsnyckeln har konfigurerats måste du konfigurera en filterdefinition för att kunna anropa resursen med den här identifieringsnyckeln, antingen från Campaign Standardens gränssnitt eller API:er.

I det här fallet **Profil** resursen har utökats med anpassad **&quot;CRM-ID&quot;** och **&quot;category&quot;** fält. Vi skapar en identifieringsnyckel för profilresursen som består av dessa två fält. Sedan konfigurerar vi en filterdefinition så att vi kan komma åt profilresursen med hjälp av identifieringsnyckeln.

De huvudsakliga stegen för det här användningsexemplet är:

1. Konfigurera identifieringsnyckeln för profilresursen baserat på de två fälten.
1. Konfigurera filterdefinitionen för att kunna anropa profilresursen med hjälp av dess identifieringsnyckel.
1. Anropa profilresursen från gränssnittet eller från APis.

Relaterade ämnen:

* [Skapa eller utöka resursen](../../developing/using/creating-or-extending-the-resource.md)
* [Definiera identifieringsnycklar](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign Standard REST API:er](../../api/using/get-started-apis.md)

## Steg 1: Konfigurera identifieringsnyckeln{#step-1-configure-the-identification-key}

>[!NOTE]
> Globala koncept för konfiguration av identifieringsnycklar beskrivs i [det här avsnittet](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Innan du konfigurerar identifieringsnyckeln måste du kontrollera att resursen har utökats med de önskade fälten och att den har publicerats. Mer information om detta finns i [det här avsnittet](../../developing/using/creating-or-extending-the-resource.md).

1. Gå till **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** öppnar du **[!UICONTROL Profile]** resurs.

   ![](assets/uc_idkey1.png)

1. I **[!UICONTROL Identification keys]** klickar du på **[!UICONTROL Create element]** -knappen.

   ![](assets/uc_idkey2.png)

1. Lägg till de två anpassade fälten &quot;CRM ID&quot; och &quot;Category&quot; och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Konfigurera **[!UICONTROL Screen definition]** -fliken. Mer information om detta finns i [det här avsnittet](../../developing/using/configuring-the-screen-definition.md).

1. Nu kan du konfigurera filterdefinitionen så att den kan anropa resursen med hjälp av dess identifieringsnyckel.

## Steg 2: Konfigurera filterdefinitionen{#step-2-configure-the-filter-definition}

>[!NOTE]
> Globala begrepp för att konfigurera filterdefinitioner finns i [det här avsnittet](../../developing/using/configuring-filter-definition.md).

1. I **[!UICONTROL Filter definition]** flik, klicka **[!UICONTROL Add an element]** anger du filterdefinitionens etikett och ID.

1. Redigera filterdefinitionens egenskaper för att konfigurera dess regler.

   ![](assets/uc_idkey4.png)

1. Dra och släpp den tabell som innehåller de fält som används i identifieringsnyckeln till arbetsytan.

   ![](assets/uc_idkey5.png)

1. Markera det första fältet som används i identifieringsnyckeln (&quot;CRM-ID&quot;) och aktivera sedan **[!UICONTROL Switch to parameters]** alternativ.

   ![](assets/uc_idkey6.png)

1. I **[!UICONTROL Filter conditions]** -avsnittet, behåll **[!UICONTROL Equal]** definierar du sedan parameterns namn och klickar på plustecknet för att skapa det.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > När du har klickat på **+** -knappen genereras parameternamnet automatiskt. Observera den här informationen eftersom du behöver den för att använda filtret från API:erna.

1. Upprepa stegen ovan med alla fält som utgör identifieringsnyckeln (&quot;kategori&quot;) och spara sedan ändringarna.

   ![](assets/uc_idkey8.png)

1. Filterdefinitionen är nu konfigurerad. Du kan publicera resursen så att filtret är tillgängligt.

## Steg 3: Anropa resursen baserat på dess identifieringsnyckel{#step-3-call-the-resource-based-on-its-identification-key}

När identifieringsnyckeln och filterdefinitionen har konfigurerats kan du använda dem för att anropa resursen, antingen från standardgränssnittet för Campaign eller från REST-API:er.

Om du vill använda filterdefinitionen från gränssnittet använder du en **[!UICONTROL Query]** aktivitet i ett arbetsflöde (se [det här avsnittet](../../automating/using/query.md)). Filtret är sedan tillgängligt i den vänstra rutan.

![](assets/uc_idkey9.png)

Om du vill använda filterdefinitionen från Campaign Standardens REST API:er använder du syntaxen nedan:

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Om du vill anropa ett anpassat filter använder du prefixet &quot;by&quot; följt av filternamnet som definierats när du konfigurerar filterdefinitionen i [steg 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

I det här fallet skulle syntaxen för att hämta en profil från kategorin &quot;vår&quot; med CRM-ID:t &quot;123456&quot; vara:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Mer information finns i [Campaign Standard REST API:er - dokumentation](../../api/using/filtering.md).
