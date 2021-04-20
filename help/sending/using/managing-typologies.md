---
solution: Campaign Standard
product: campaign
title: Hantera typologier
description: Lär dig hur du använder typologier.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 99%

---


# Hantera typologier {#managing-typologies}

## Om typologier {#about-typologies}

Typologier är en uppsättning regler som gör att du kan kontrollera giltigheten för ditt meddelande innan du skickar iväg det.  Exempelvis när: Meddelandeinnehållet inte är tomt, det finns en avprenumeration eller vid exkludering av dubbletter etc.

Typologier finns i menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .  Som standard är en standardtypologi tillgänglig i programmet.  Beroende på dina behov kan du skapa egna typologier eller ändra befintliga.

![](assets/typologies-list.png)

För varje typologi listar **[!UICONTROL Typology rules]**-avsnittet den uppsättning regler som körs när typologin används i ett meddelande.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Om du vill ha mer information om en av typologireglerna dubbelklickar du på den.    Regeln visas i skrivskyddat läge.

## Skapa en typologi {#creating-a-typology}

Följ dessa steg för att skapa en ny typologi:

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**-menyn.

1. Listan över typologier visas här.  Klicka på knappen **[!UICONTROL Create]**.

   ![](assets/typologies-create.png)

1. Definiera typologin **[!UICONTROL Label]** och klicka sedan på knappen **[!UICONTROL Add an element]** för att välja de typologiregler som du vill ha med i den.  Mer information om typologiregler hittar du i [det här avsnittet](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >I fältet **[!UICONTROL IP affinity]** kan du hantera tillhörigheterna enligt din konfiguration.  Dessa definieras i instansens konfigurationsfil.  Kontakta administratören om du vill använda tillhörigheterna.

1. Klicka **[!UICONTROL Create]** för att bekräfta valet.  Din typologi kan nu användas i meddelanden.

## Applicera typologier i meddelanden {#applying-typologies-to-messages}

När du associerar en typologi med ett meddelande eller en meddelandemall kommer de typologiregler som ingår i typologin att köras för att kontrollera meddelandets giltighet.

>[!NOTE]
>
>Varje meddelande eller meddelandemall kan endast tilldelas en enda typologi.

Följ dessa steg för att länka en typologi till ett meddelande:

1. Öppna meddelandeegenskaperna.  Notera att meddelandemallar är tillgängliga via navigeringsmenyn **[!UICONTROL Resources]** > **[!UICONTROL Templates]**.

1. I avsnittet **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** väljer du den typologi som ska länkas till meddelandet.

   ![](assets/typology_message.png)

1. Klicka på **[!UICONTROL Confirm]**.

   Den valda typologin är nu länkad till meddelandet.  Alla tillhörande typologiregler kommer att köras för att kontrollera meddelandets giltighet.
