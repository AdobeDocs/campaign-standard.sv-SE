---
title: Mappningsdefinition
description: Lär dig hur du mappar ett fält för Campaign Standard med ett XDM-fält (Experience Data Model).
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Mappningsdefinition {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector är för närvarande en betaversion som kan komma att uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

I det här avsnittet får du lära dig att mappa ett fält för Campaign Standard med ett XDM-fält (Experience Data Model).

För att kunna utföra den här uppgiften måste du:

* en XDM-schemadefinition via gränssnittet eller genom att använda REST API som är associerat med XDM
* en datauppsättning som baseras på XDM-schemadefinitionen

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** och välj posten **[!UICONTROL Data mappings]**.

1. Klicka på **[!UICONTROL Create]** för att starta en ny XDM-mappning.

   ![](assets/aep_createmapping.png)

1. Fyll i de obligatoriska fälten och välj:

   * en **måldimension**: detta är det Campaign Standard schema som ska mappas
   * a **dataset**: Detta är det datapaket som är associerat med ett XDM-schema i Adobe Experience Platform.

>[!NOTE]
>
>För att en batch ska kunna hämtas till kundprofil eller identitetstjänst i realtid måste datamängden vara [aktiverad för kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html).
>
>Om den datauppsättning du väljer redan används i en befintlig datamappning visas en varning om att dina data kan skrivas över på Adobe Experience Platform. Detta kan inträffa när det finns vissa vanliga mottagare i datamappningar som använder samma datamängd.

På följande skärm visas avsnittet **[!UICONTROL Field mappings]** där du kan skapa en ny mappning för varje fält i Campaign Standardens schema.

![](assets/aep_fieldmappings.png)

Med knappen **[!UICONTROL Create new field mapping]** kan du markera Campaign Standarden och motsvarande fältsökvägsuttryck i XDM-schemat.

Om du inte kan hitta något Adobe Campaign Standard-fält kan du använda sökfältet för att söka efter fältet. För närvarande fungerar sökningen endast för fält som är öppna i hierarkin.

![](assets/aep_mapfield.png)

De utökade resurser som definieras i Campaign Standarden mappas som alla inbyggda fält. De definieras i tillägget _customer/default i XDM.

![](assets/aep_fieldscusmapping.png)

Du kan anpassa XDM-tillägget via API:t och definiera ett eget tillägg så att du får bättre kontroll över mappningen.

Mer information om XDM API finns i [API-självstudiekursen för schemaregistret](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

Om du vill mappa ett uppräkningsfält måste du använda uttrycksredigeraren för att definiera varje uppräkningsvärde som motsvarar XDM-värdet. Postaladressfältet måste till exempel definieras som:

![](assets/aep_enummapping.png)

Om XDM-värdet definieras som en uppräkning i XDM-schemat kan du använda den inbyggda EXDM-funktionen som automatiskt ersätter **lif** -syntaxen.

![](assets/aep_enummappingexdm.png)

Om du vill redigera en XDM-mappning öppnar du den, ändrar informationen och sparar den.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Om du för närvarande redigerar ett värde i avsnittet **[!UICONTROL Field mappings]** och sedan klickar utanför fältet, visas inte ändringen i gränssnittet förrän du klickar på knappen **[!UICONTROL Save]** . Det här beteendet inträffar bara en gång när redigeringen på **[!UICONTROL Field Mappings]** är den första redigeringen på sidan.
