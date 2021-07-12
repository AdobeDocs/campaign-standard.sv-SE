---
solution: Campaign Standard
product: campaign
title: Dela en landningssida
description: Lär dig hur du testar och publicerar en landningssida i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
feature: Landningssidor
role: User
level: Intermediate
exl-id: af849377-686f-45b3-bf6e-5069a8966987
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 100%

---

# Testa och publicera en landningssida{#testing-publishing--landing-page}

## Om publicering av landningssida {#about-landing-page-publication}

Innan du publicerar en landningssida så måste du utföra tester som exempelvis validera körningen, konfigurera åtkomsten och konfigurera avslutningsdatum för landningssidan.  Dessa steg är nödvändiga och måste utföras med försiktighet.

## Testa landningssidan {#testing-the-landing-page-}

Eftersom landningssidan kommer att påverka plattformen och data måste du noga testa hur den fungerar.  Så här gör du:

1. Klicka på knappen **[!UICONTROL Test]** i åtgärdsfältet på landningssidan.
1. På testskärmen väljer du en testprofil och en testtjänst om landningssidan ska hantera prenumerationer.

   ![](assets/lp_test_2.png)

1. Ange data i fälten och välj alternativ.
1. Skicka in landningssidan och kontrollera uppdateringar i databasen.

   >[!IMPORTANT]
   >
   >När formuläret skickas uppdateras den tjänst och profil som används.

1. Upprepa detta med olika profiler och data.

Du kan också generera miniatyrbilden för landningssidan på den här skärmen.

>[!NOTE]
>
>Om du vill visa förhandsgranskningen av landningssidan i användargränssnittet för Campaign så måste programserverns URL vara säker.  I sådant fall använder du https:// i stället för http:// för att konfigurera den här URL:en när du [konfigurerar ditt varumärke](../../administration/using/branding.md#configuring-and-using-brands).

## Ställa in giltighetsparametrar {#setting-up-validity-parameters}

Av säkerhetsskäl och för plattformsprestanda rekommenderar vi att du anger ett förfallodatum i egenskaperna för landningssidan innan du publicerar. På det valda datumet avpubliceras landningssidan automatiskt.  Så här gör du:

1. Redigera de egenskaper för landningssidor som du kommer åt via knappen ![](assets/edit_darkgrey-24px.png) i kontrollpanelen för landningssidor.

   ![](assets/lp_edit_properties_button.png)

1. Ange förfallodatum och förfallotid i avsnittet **[!UICONTROL Publication]**. Landningssidan kommer automatiskt att avpubliceras det angivna datumet och då inte längre vara tillgänglig.

   Du kan välja vilken tidszon som ska tas i beaktning för detta datum och tid.

1. Definiera en omdirigerings-URL för att dirigera om besökarna när de försöker komma åt en landningssida som inte är aktiv.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>Du kan också ange ett distributionsdatum och en distributionstid. Landningssidan kommer då att publiceras automatiskt på det angivna datumet.

## Publicera en landningssida {#publishing-a-landing-page}

När du publicerar en landningssida så publiceras den live och besökarna kan komma åt den.

Du kan när som helst avpublicera eller uppdatera och publicera om din landningssida via knappen **[!UICONTROL Publish]**.  Om ompubliceringen misslyckas och du ännu inte har avpublicerat landningssidan så kommer den första versionen att vara online.
