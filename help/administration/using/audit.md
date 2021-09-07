---
solution: Campaign Standard
product: campaign
title: Granskningsspår
description: Övervaka åtgärder och händelser med granskningsspår för kampanjer
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Access Management
role: Admin
level: Experienced
exl-id: 4a4c14da-d842-4f65-821a-ca9e73a94adc
source-git-commit: a12b87d93e3badbf31f88c9f0f48b981e206d8b9
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%

---

# Granskningskedja {#audit}

**[!UICONTROL Audit trail]** ger dig tillgång till den fullständiga historiken för ändringar som gjorts i din instans.

**[!UICONTROL Audit trail]** i realtid innehåller en omfattande lista över åtgärder och händelser som inträffar i din Adobe Campaign Standard-instans. Det innehåller ett självbetjäningssätt att komma åt en datahistorik som kan hjälpa dig att besvara frågor som: vad som hände med dina arbetsflöden, anpassade resurser och alternativ, vem som senast uppdaterade dem eller vad användarna gjorde i instansen.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** består av tre komponenter:

* **Granskningsspår** för anpassade resurser: kontrollera aktiviteten och senast gjorda ändringar av anpassade resurser.

   Mer information om **[!UICONTROL Custom resources]** finns på den här [sidan](../../developing/using/key-steps-to-add-a-resource.md).

* **Granskningsspår** för arbetsflöde: kontrollera aktiviteten och den senaste ändringen av arbetsflödena, och dessutom status för dina arbetsflöden, som:

   * Skapad
   * Ändrad
   * Borttagen
   * Start av arbetsflöde
   * Pausa arbetsflöde
   * Stoppa arbetsflöde
   * Starta om arbetsflödet
   * Rensa arbetsflöde
   * Simulera arbetsflöde
   * Arbetsflödesaktivering
   * Arbetsflöde - omedelbart stopp
   * Starta om arbetsflödet med samma användare
   * Kommandot Starta om okänt arbetsflöde

   Mer information om **[!UICONTROL Workflows]** finns på den här [sidan](../../automating/using/get-started-workflows.md).

* **Alternativ granskningsspår**: kontrollera aktiviteten och senast gjorda ändringar av alternativen.

   Mer information om **[!UICONTROL Options]** finns på den här [sidan](../../administration/using/about-campaign-standard-settings.md).

Observera att som standard är kvarhållningsperioden 30 dagar.

## Åtkomst till granskningsspår {#audit-access}

Så här kommer du åt instansens granskningsspår:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]** på den avancerade menyn.

   ![](assets/audit-trail.png)

1. Fönstret **[!UICONTROL Audit trail]** öppnas med listan över dina enheter. Adobe Campaign Standard granskar åtgärderna för att skapa, redigera och ta bort för arbetsflöden, alternativ och anpassade resurser.

   På **[!UICONTROL Search]**-menyn kan du filtrera din entitet på:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: Entitetens typ mellan Alla, Arbetsflöde, Anpassad resurs och Alternativ.
   * **[!UICONTROL Entity name]**: ID för arbetsflöde, alternativ eller anpassad resurs

   ![](assets/audit-trail_2.png)

1. Välj en av enheterna om du vill veta mer om de senaste ändringarna.

1. Fönstret Granskningsenhet ger dig mer detaljerad information om den valda enheten, till exempel:

   * **[!UICONTROL Entity]**: ID för arbetsflöde, alternativ eller anpassad resurs.
   * **[!UICONTROL Action]**: Senaste åtgärd utförd på den här entiteten.
   * **[!UICONTROL Changed by]**: Användarnamn för den senaste personen som senast ändrade den här entiteten.
   * **[!UICONTROL Changed date]**: Datum för den senaste åtgärden som utfördes på den här entiteten.
   * **[!UICONTROL Content]**: Kodblock som ger dig mer information om exakt vad som har ändrats i din enhet.

   I det här exemplet ser vi att arbetsflödet WKF110 startades den 26 augusti av den här instansens affärsadministratör.

   ![](assets/audit-trail_3.png)

## Aktivera/inaktivera granskningsspår {#enable-disable-audit}

Granskningsspårning kan enkelt aktiveras eller inaktiveras för en viss aktivitet.

För att göra detta:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** på den avancerade menyn.

   ![](assets/audit-trail_4.png)

1. Välj något av följande alternativ beroende på vilken enhet du vill inaktivera:

   * **[!UICONTROL XtkAudit_Workflows]** för att hantera granskningsspår för arbetsflöden.
   * **[!UICONTROL XtkAudit_Option]** för att hantera granskningsspår för alternativ.
   * **[!UICONTROL XtkAudit_CusResource]** för att hantera granskningsspår för anpassade resurser.
   * **[!UICONTROL XtkAudit_Enable_All]** alternativ för att hantera granskningsspår för varje enhet.

      >[!NOTE]
      >
      >Om alternativet **[!UICONTROL XtkAudit_Enable_All]** är 0 inaktiveras funktionen **[!UICONTROL Audit trail]** helt, oavsett andra individuella alternativvärden.
   ![](assets/audit-trail_5.png)

1. På din **[!UICONTROL Options]**-sida anger du värdet 0 för **[!UICONTROL Value (integer)]** om du vill inaktivera **[!UICONTROL Audit trail]** eller till 1 för att aktivera det.

   ![](assets/audit-trail_6.png)

1. Klicka på **[!UICONTROL Save]**.