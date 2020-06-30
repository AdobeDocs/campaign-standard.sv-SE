---
title: Konfigurerar filterdefinition
description: Identifiera filterfunktionen för att hantera stora datauppsättningar.
page-status-flag: never-activated
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cabe064632c9c2e3de93bc1cff6fa217b4fdf3e6
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# Konfigurerar filterdefinition{#configuring-filter-definition}

På fliken **[!UICONTROL Filter definition]** kan du skapa avancerade filter som användare kan komma åt direkt när de skapar komplexa frågor, till exempel när de definierar en målgrupp.

Det här steget är inte obligatoriskt eftersom du fortfarande kan fylla i resursen och komma åt dess data via arbetsflöden, målgrupper och REST API.

![](assets/custom_resource_filter-definition.png)

Dessa filter används i frågeredigeraren i form av förkonfigurerade regler. Med dem kan du begränsa antalet steg som krävs för att få önskad konfiguration, vilket kan vara särskilt bra för upprepad segmentering.

Du kan till exempel skapa ett filter som gör det möjligt att markera alla transaktioner som är större än ett visst belopp under de senaste tre månaderna.

För att kunna göra detta måste du utöka **[!UICONTROL Profiles]** resursen och definiera ett filter som länkar till en transaktionstabell (som du tidigare har skapat) med en regel som anger att transaktionspriset måste vara större än eller lika med en given parameter och att transaktionsdatumet måste ligga inom ett intervall som motsvarar de senaste tre månaderna.

1. Se till att du skapar och publicerar ett transaktionsregister. Se [Skapa eller utöka resursen](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Den här proceduren använder exemplet på en anpassad transaktionsregister. I ditt fall kan du anpassa den efter dina affärsbehov.

1. Innan du definierar ett filter som är relaterat till transaktionsregistret i **[!UICONTROL Profiles]** resursen måste du definiera länken till det här registret och publicera ändringarna. Se [Definiera länkar med andra resurser](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) och [Uppdatera databasstrukturen](../../developing/using/updating-the-database-structure.md).
1. Markera transaktionsregistret på fliken **[!UICONTROL Definition]** i det nya filtrets definitionsskärm.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. Dra transaktionsregistret till arbetsytan i **[!UICONTROL Add a rule - Profiles/Transactions]** fönstret. I nästa fönster som visas markerar du det fält som du vill använda.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. Markera rutan **[!UICONTROL Optional parameter settings]** i **[!UICONTROL Add a rule - Transactions]** fönstret **[!UICONTROL Switch to parameters]** .

   I **[!UICONTROL Filter conditions]** väljer du **[!UICONTROL Greater than or equal to]** operatorn . Ange ett namn i **[!UICONTROL Parameters]** fältet och klicka på plustecknet för att skapa den nya parametern.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Bekräfta ändringarna. Definitionen motsvarar ett konfigurerbart fält som användaren måste fylla i senare för att köra frågan.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Kombinera den här regeln med en annan regel som anger att transaktionsdatumet måste ligga inom ett intervall som motsvarar de senaste tre månaderna.

   ![](assets/custom_resource_filter-definition_example.png)

1. Välj den kategori som filtret ska visas i.

   ![](assets/custom_resource_filter-definition_category.png)

1. Ändra beskrivningen och etiketten på fliken **[!UICONTROL Parameters]** i filterdefinitionsskärmen för att tydligt ange filterföremålet för användarna. Den här informationen visas i frågeredigeraren.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Om du definierar flera konfigurerbara fält kan du ändra i vilken ordning de visas i gränssnittet.

1. Spara ändringarna och publicera resurserna. Mer information finns i avsnittet [Uppdatera databasstrukturen](../../developing/using/updating-the-database-structure.md) .

När **[!UICONTROL Profiles]** resurstillägget har publicerats visas det här filtret under fliken Kortkommandon i [frågeredigeringsgränssnittet](../../automating/using/editing-queries.md) .

På så sätt kan användaren enkelt definiera sin målgrupp när han eller hon skapar ett e-postmeddelande som ska skickas till alla kunder som spenderat mer än en viss mängd de senaste tre månaderna.

![](assets/custom_resource_filter-definition_email-audience.png)

I stället för att själva konfigurera den behöver de bara ange önskat värde i dialogrutan som visas.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

När ett filter har konfigurerats kan du använda det från Campaign Standard-API:er med den här syntaxen:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Mer information finns i dokumentationen [till](../../api/using/filtering.md#custom-filters)Campaign Standards-API:erna.
