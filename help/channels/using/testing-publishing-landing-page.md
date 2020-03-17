---
title: Dela en landningssida
description: Lär dig hur du testar och publicerar en landningssida i Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Testa och publicera en landningssida{#testing-publishing--landing-page}

## Om publicering på landningssida {#about-landing-page-publication}

Innan du publicerar en landningssida måste du utföra tester: validera körningen, konfigurera åtkomsten och konfigurera avslutningsdatum för landningssidan. Dessa steg är nödvändiga och måste utföras med försiktighet.

## Testa landningssidan {#testing-the-landing-page-}

Eftersom landningssidan kommer att påverka plattformen och data måste du noga testa hur den fungerar. Så här gör du:

1. Klicka på **[!UICONTROL Test]** knappen i åtgärdsfältet på landningssidan.
1. På testskärmen väljer du en testprofil och en testtjänst om landningssidan ska hantera prenumerationer.

   ![](assets/lp_test_2.png)

1. Ange data i fälten och välj alternativ.
1. Skicka landningssidan och kontrollera uppdateringar i databasen.

   >[!IMPORTANT]
   >
   >När formuläret skickas uppdateras den tjänst och profil som används.

1. Upprepa detta med olika profiler och data.

   Du kan också generera miniatyrbilden för landningssidan från den här skärmen.

>[!NOTE]
>
>Om du vill visa förhandsgranskningen av landningssidan i användargränssnittet för Campaign måste programserverns URL vara säker. I så fall använder du https:// i stället för http:// för att konfigurera den här URL:en när du [konfigurerar varumärket](../../administration/using/branding.md#configuring-and-using-brands).

## Ställa in giltighetsparametrar {#setting-up-validity-parameters}

Av säkerhetsskäl och plattformsprestanda rekommenderar vi att du anger ett förfallodatum i egenskaperna för landningssidan innan du publicerar. På det valda datumet avpubliceras landningssidan automatiskt. Så här gör du:

1. Redigera de egenskaper för landningssidor som du kommer åt via ![](assets/edit_darkgrey-24px.png) knappen på kontrollpanelen för landningssidor.

   ![](assets/lp_edit_properties_button.png)

1. Ange förfallodatum och förfallotid i **[!UICONTROL Publication]** avsnittet: landningssidan kommer automatiskt att avpubliceras det angivna datumet och därför inte längre vara tillgänglig.

   Du kan välja vilken tidszon som ska beaktas för detta datum och denna tid.

1. Definiera en omdirigerings-URL för att dirigera om besökarna när de försöker komma åt en icke-aktiv landningssida.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>Du kan också ange ett distributionsdatum och en distributionstidpunkt: landningssidan kommer då att publiceras automatiskt på det angivna datumet.

## Publicera en landningssida {#publishing-a-landing-page}

När du publicerar en landningssida publiceras den live och besökarna kan komma åt den.

Du kan när som helst avpublicera eller uppdatera och publicera om din landningssida via **[!UICONTROL Publish]** knappen. Om publiceringen misslyckas och du ännu inte har avpublicerat landningssidan, kommer den första versionen att vara online.
