---
title: Viktiga steg för att skapa en landningssida
description: Lär dig de viktigaste stegen för att konfigurera en landningssida
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Komma igång med landningssidor {#getting-started-with-landing-pages}

## Om landningssidor {#about-landing-pages}

Campaign innehåller landningssidor som är webbformulär som kan användas för att samla in information om era målgrupper, erbjuda prenumerationer på en tjänst, visa data och utöka databasen. Landningssidor kan också användas för att hämta eller uppdatera befintliga profiler.

Landningssidor kan också användas för att konfigurera en mekanism för dubbel anmälan, vilket gör att du kan skydda plattformen från fel eller ogiltiga e-postadresser eller skräppost. Mer information finns i det [dedikerade användningsexemplet](../../channels/using/setting-up-a-double-opt-in-process.md).

De viktigaste stegen när du ställer in landningssidor är följande:

![](assets/lp_steps.png)

På den här sidan hittar du information om vart och ett av de här stegen samt referenser till de dedikerade dokumenten för mer information.

**Relaterade ämnen:**

* [Skapa en video](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html) med självstudiekurser om landningssidor
* [Skapa en tjänst](../../audiences/using/creating-a-service.md)
* [Konfigurera en process för dubbel anmälan](setting-up-a-double-opt-in-process.md)

## Begränsningar för landningssida{#landing-page-limitations}

I avsnittet nedan listas de begränsningar som du bör känna till innan du börjar konfigurera landningssidor.

**Skriva och uppdatera data**

* Landningssidor är begränsade till **[!UICONTROL Profile]** och endast till **[!UICONTROL Subscription]** resurser. Posten kan sparas och uppdateras från **[!UICONTROL Profile]** och en prenumeration/avprenumeration till en **[!UICONTROL Service]**.
Mer information om resurskonfigurationen finns i [Konfigurera resursens datastruktur](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
>En landningssida kan inte visa eller uppdatera data från någon annan resurs än **[!UICONTROL Profile]** och **[!UICONTROL Subscription]**.

**Förinläsning**

* Landningssidan kan inte visa en lista med poster automatiskt, den kan inte visa tjänster som profiler som redan prenumererar på. Mer information om tjänster finns på den här [sidan](../../audiences/using/creating-a-service.md).

* Landningssida med ett förfyllt formulär (data är förinlästa med sidan) kan bara nås via ett e-postmeddelande för Adobe Campaign. Det går inte att komma åt ett sådant formulär från en webbsida.

**Avstämning**

* Avstämningsbeteendet är följande: så snart en matchning hittas avbryts avstämningsprocessen. Det innebär att avstämning bara kan göras för en profilpost och inte för flera poster när det finns dubbletter.

Du vill till exempel skicka följande kundvärvningssida till dina profiler för att uppdatera Campaign-databasen med dina profilers mobilnummer.

![](assets/landing_page_limitation_1.png)

Om en av dina profiler fyller i din landningssida med ny information men redan har en duplicerad profil, kommer den matchande profilen med det tidigaste skapandedatumet att uppdateras eftersom profilerna prioriteras beroende på när de skapades.

Här har bara den första profilen uppdaterats sedan den var den äldsta posten.

![](assets/landing_page_limitation_2.png)

**Testa landningssidor**

* Landningssidor fungerar bara på profiler och inte på testprofiler, vilket innebär att landningssidor inte kan testas som en del av ett e-postkorrektur.

## Steg 1 - Konfigurera landningssidmallen {#configure-the-landing-page-template}

Innan du skapar en landningssida är det första steget att konfigurera en mall för landningssidor som passar dina behov. När mallen är klar kommer alla landningssidor som är baserade på den att förkonfigureras med de önskade parametrarna.

1. På den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** och duplicerar sedan mallen som du vill använda.
1. I mallegenskaperna anger du alla parametrar som landningssidorna måste ha gemensamt. Till exempel: målgruppsdimensionen, sidåtkomstparametrar för identifierade eller ej identifierade besökare, åtgärder som är specifika för en besökares formulärvalidering, varumärket/logotypen som ska användas i innehållet osv. Mer information om landningssidans egenskaper finns i [detta avsnitt](../../channels/using/configuring-landing-page.md)
1. Spara ändringarna.

Mer information om mallar för landningssidor finns i [detta avsnitt](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## Steg 2 - Skapa och konfigurera landningssidan {#create-and-configure-the-landing-page}

Skapa en ny landningssida i ett program eller en kampanj från den mall som definierades i föregående steg.

1. Skapa landningssidan baserat på önskad mall.
1. Ange de allmänna parametrarna för landningssidan (etikett, beskrivning osv.).
1. Du kommer sedan åt kontrollpanelen för landningssidan. Redigera egenskaperna för landningssidan, om det behövs (se [Konfigurera en landningssida](../../channels/using/configuring-landing-page.md)). Som standard är egenskaperna de som konfigurerats i landningssidmallen.
Av säkerhetsskäl och av plattformsprestanda rekommenderar vi att du anger ett förfallodatum i egenskaperna för landningssidan. När du är klar avpubliceras landningssidan automatiskt på det valda datumet. For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Ändringarna gäller endast för den landningssida som redigeras. Om du vill tillämpa dessa ändringar på andra landningssidor kan du utföra dem i en dedikerad mall och sedan skapa andra landningssidor från den mallen.

## Steg 3 - Utforma landningssidan {#design-the-landing-page}

Nu kan du definiera innehållet på landningssidan. Som standard innehåller landningssidan tre sidor som du kan komma åt via rullningspilar: huvudinnehållssidan, en bekräftelsesida och en felsida.

![](assets/lp-steps4.png)

Flera fält konfigureras som standard på varje sida. Om det behövs kan du redigera deras egenskaper och mappning.

Du kan också konfigurera hur bekräftelseknappen fungerar när en profil klickar på den och anpassa innehållet efter dina behov (bild, anpassningsfält osv.). Du kan t.ex. infoga en profils förnamn på bekräftelsesidan på landningssidan och tacka dem för att de har registrerat sig.

Mer information om landningssidans utformning finns i [detta avsnitt](../../channels/using/designing-a-landing-page.md).

## Steg 4 - Testa landningssidan {#test-the-landing-page}

När landningssidan har definierats kan du simulera hur den kommer att köras och bete sig när den är tillgänglig online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>Testerna på landningssidan kan endast utföras med profiler och inte med testprofiler. När formuläret skickas uppdateras den valda profilens data för att vara riktiga. Undvik att ändra riktiga profiler genom att använda en falsk kundprofil.

Om du är nöjd med hur landningssidan fungerar kan du publicera den så att den blir tillgänglig online.

Mer information om hur du testar en landningssida finns i [detta avsnitt](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-).

## Steg 5 - Publicera landningssidan {#publish-the-landing-page}

När testerna har slutförts kan du publicera landningssidan med knappen **[!UICONTROL Publish]** i åtgärdsfältet på instrumentpanelen. Ett övervakningsblock visar publiceringens förlopp och status.

Genom att publicera landningssidan blir den tillgänglig online. När publiceringen är klar kan du alltid uppdatera den: Om du vill göra det måste du publicera det igen efter varje ändring. Du kan också när som helst avpublicera en landningssida så att den inte längre är tillgänglig.

![](assets/lp-steps6.png)

När landningssidan har publicerats är den klar att användas. Du kan sedan införa olika mekanismer som gör att du kan komma åt den för att hämta nya profiler i databasen eller för att få ytterligare information om befintliga profiler.

Mer information om publicering av landningssidor finns i [detta avsnitt](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page).
