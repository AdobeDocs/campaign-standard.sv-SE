---
solution: Campaign Standard
product: campaign
title: Organisationsenheter
description: Definiera användarnas åtkomstnivåer med hjälp av organisationsenheter.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 3%

---


# Organisationsenheter{#organizational-units}

## Om enheter {#about-units}

Varje objekt och användare av plattformen är länkade till en organisationsenhet. Den här enheten gör att en hierarkisk struktur kan definieras för att ge användarna en filtrerad vy. En användares enhet definierar sin åtkomstnivå för olika plattformsobjekt.

>[!IMPORTANT]
>
>Om en användare inte är länkad till någon enhet kommer den användaren inte att kunna ansluta till Adobe Campaign. Om du vill begränsa åtkomsten för en viss användare eller grupp av användare ska du inte länka den till **[!UICONTROL All]** enheten.
>
>**[!UICONTROL All (all)]** Organisationsenheten tilldelas som standard till **[!UICONTROL Administrators]** säkerhetsgruppen.  Den är skrivskyddad och kan inte ändras.

En användare har skrivskyddad åtkomst till alla objekt i de överordnade enheterna. Han har läs- och skrivåtkomst till alla sina objekt i sin enhet och sina underordnade enheter. En användare har inte åtkomst till objekt i parallella grenar.

Som standard är bara **[!UICONTROL All]** enheterna tillgängliga.

När användaren tilldelas en organisationsenhet används alltid den här enheten på de objekt som användaren skapade.

![](assets/user_management_2.png)

>[!NOTE]
>
>När en användare finns i flera grupper som är länkade till olika enheter används vissa regler. Mer information finns i avsnittet [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md) .

## Skapa och hantera enheter {#creating-and-managing-units}

Med organisationsenheter kan du filtrera instansen beroende på vilken organisation användarna är länkade till. Den här enheten kan representera en region, ett land eller till och med ett varumärke i din instans.

Här har vi tidigare skapat säkerhetsgrupper med olika roller för två användare: en användare tilldelas säkerhetsgrupperna Administratörer och Geometrixx, den andra användaren tillhör säkerhetsgrupperna Standard användare och Geometrixx Se [Skapa en säkerhetsgrupp och tilldela användare](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) för det fullständiga exemplet.

Nu måste vi skapa organisationsenheter för Geometrixx- och Geometrixx säkerhetsgrupper:

1. På Adobe-kampanjens avancerade meny väljer du **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Klicka **[!UICONTROL Create]** för att börja konfigurera din organisationsenhet.

   ![](assets/manage_units_1.png)

1. Ändra standardinställningen **[!UICONTROL Label]** och **[!UICONTROL ID]** till Geometrixx.
1. Länka sedan den här enheten till en överordnad enhet. Här, vi valde **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Klicka slutligen på **[!UICONTROL Create]** för att börja tilldela din nya organisationsenhet till säkerhetsgruppen.
1. Följ samma procedur för enheten Geometrixx Clothes, förutom att dess överordnade enhet måste vara den tidigare skapade enheten, Geometrixx.

   ![](assets/manage_units_3.png)

För att se effekten av att tilldela olika enheter till olika säkerhetsgrupper skapar den användare som tilldelats administratörs- och Geometrixx-grupperna två e-postmallar för att se vad den andra användaren som tilldelats standardanvändare och Geometrixx kan eller inte kan komma åt.

1. På den avancerade menyn väljer du **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplicera en befintlig mall och anpassa den efter behov. For more on this, refer to the [About templates](../../start/using/marketing-activity-templates.md) section.
1. När mallen skapas väljer du **[!UICONTROL Edit properties]** ikonen för att tilldela enheter till mallen.

   ![](assets/manage_units_6.png)

1. Välj organisationsenhet på den **[!UICONTROL Access authorization]** nedrullningsbara menyn.

   Här ska vi skapa en mall med den tidigare skapade Geometrixx för organisationsenheter.

   ![](assets/manage_units_5.png)

1. Följ samma procedurer för att skapa den andra mallen som tilldelats den tidigare skapade organisationsenheten för Geometrixx.

Användaren som är tilldelad standardgrupperna för användare och Geometrixx kan se båda mallarna. På grund av organisationsenheternas hierarkiska struktur har han läs- och skrivåtkomst till den mall som är länkad till Geometrixx Color-enheten och endast skrivskyddad åtkomst till den mall som är länkad till Geometrixx.

![](assets/manage_units_7.png)

Eftersom enheten för Geometrixx är en underordnad enhet till Geometrixx visas följande meddelande när användaren försöker ändra Geometrixx:

![](assets/manage_units_8.png)

Organisationsenheter kan begränsa åtkomsten till olika funktioner som profiler. Om t.ex. våra Geometrixx-användare har åtkomst till fliken **[!UICONTROL Profiles]** kan de få fullständig åtkomst till och ändra profilerna med organisationsenheten för Geometrixx.

Profilerna med organisationsenheten för Geometrixx kommer att vara skrivskyddade, men följande fel visas om användaren försöker ändra en profil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitionsprofiler {#partitioning-profiles}

Om din organisation behöver isolera profilerna som kontaktas av alla dina olika varumärken kan du partitionera profilerna efter deras organisationsenheter.

Som standard är organisationsenhetsfälten inte tillgängliga i dina profiler och behöver läggas till.

Det går inte att komma åt profiler utan organisationsenheter.

>[!IMPORTANT]
>
>Vi rekommenderar att du lägger till det här alternativet innan du importerar några profiler. Om du redan har importerat din kunddatabas måste du uppdatera den för att kunna ange organisationsenhetsvärden för de redan importerade profilerna.

1. På den avancerade menyn, via Adobe Campaign logotyp, väljer du **Administration > Utveckling > Anpassade resurser**.
1. Välj **Profil** eller skapa en ny anpassad resurs för att utöka profilerna.
1. Markera rutan **Lägg till åtkomstbehörighetshanteringsfält** för att lägga till organisationsenheterna i **profiltillägget** .

   ![](assets/user_management_9.png)

1. Klicka på **[!UICONTROL Save]**.
1. Uppdatera strukturen genom att publicera om anpassade resurser. Mer information om publiceringsprocessen finns i [Uppdatera avsnittet Struktur](../../developing/using/data-model-concepts.md) .

Fältet Organisationsenhet läggs till i dina profiler i **[!UICONTROL Access authorization]** -avsnittet.

![](assets/user_management_10.png)

**Relaterade ämnen**:

* [Om enheter](../../administration/using/organizational-units.md#about-units)
* [Om åtkomsthantering](../../administration/using/about-access-management.md)

