---
title: Organisationsenheter
description: Definiera användarnas åtkomstnivåer med hjälp av organisationsenheter.
page-status-flag: never-activated
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Organisationsenheter{#organizational-units}

## Om enheter {#about-units}

Varje objekt och användare av plattformen är länkade till en organisationsenhet. Den här enheten gör att en hierarkisk struktur kan definieras för att ge användarna en filtrerad vy. En användares enhet definierar sin åtkomstnivå för olika plattformsobjekt.

>[!IMPORTANT]
>
>Om en användare inte är länkad till någon enhet kan den användaren inte ansluta till Adobe Campaign. Om du vill begränsa åtkomsten för en viss användare eller grupp av användare ska du inte länka den till **[!UICONTROL All]** enheten.
>
>Organisationsenheten tilldelas som standard till **[!UICONTROL All (all)]****[!UICONTROL Administrators]** säkerhetsgruppen. Den är skrivskyddad och kan inte ändras.

En användare har skrivskyddad åtkomst till alla objekt i de överordnade enheterna. Han har läs- och skrivåtkomst till alla sina objekt i sin enhet och sina underordnade enheter. En användare har inte åtkomst till objekt i parallella grenar.

Som standard är bara **[!UICONTROL All]** enheterna tillgängliga.

När användaren tilldelas en organisationsenhet används alltid den här enheten på de objekt som användaren skapade.

![](assets/user_management_2.png)

>[!NOTE]
>
>När en användare finns i flera grupper som är länkade till olika enheter används vissa regler. Mer information finns i avsnittet [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md) .

## Skapa och hantera enheter {#creating-and-managing-units}

Med organisationsenheter kan du filtrera instansen beroende på vilken organisation användarna är länkade till. Den här enheten kan representera en region, ett land eller till och med ett varumärke i din instans.

Här har vi tidigare skapat säkerhetsgrupper med olika roller för två användare: en användare tilldelas säkerhetsgrupperna Administratörer och Geometrixx, den andra användaren tillhör säkerhetsgrupperna Standard och Geometrixx Clothes Se [Skapa en säkerhetsgrupp och tilldela användare](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) för det fullständiga exemplet.

Vi måste nu skapa organisationsenheterna för säkerhetsgrupperna Geometrixx Clothes och Geometrixx:

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Klicka **[!UICONTROL Create]** för att börja konfigurera din organisationsenhet.

   ![](assets/manage_units_1.png)

1. Ändra standardvärdet **[!UICONTROL Label]** och **[!UICONTROL ID]** till Geometrixx.
1. Länka sedan den här enheten till en överordnad enhet. Här, vi valde **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Klicka slutligen på **[!UICONTROL Create]** för att börja tilldela din nya organisationsenhet till säkerhetsgruppen.
1. Följ samma procedur för Geometrixx Clothes-enheten, förutom att dess överordnade enhet måste vara den tidigare skapade enheten, Geometrixx.

   ![](assets/manage_units_3.png)

För att se effekten av att tilldela olika enheter till olika säkerhetsgrupper kommer användaren som tilldelats administratörs- och Geometrixx-grupperna att skapa två e-postmallar för att se vad den andra användaren som tilldelats standardanvändare och Geometrixx-färger kan eller inte kan komma åt.

1. På den avancerade menyn väljer du **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplicera en befintlig mall och anpassa den efter behov. Mer information finns i avsnittet [Om mallar](../../start/using/marketing-activity-templates.md) .
1. När mallen skapas väljer du **[!UICONTROL Edit properties]** ikonen för att tilldela enheter till mallen.

   ![](assets/manage_units_6.png)

1. Välj organisationsenhet på den **[!UICONTROL Access authorization]** nedrullningsbara menyn.

   Här ska vi skapa en mall med den tidigare skapade organisationsenheten Geometrixx.

   ![](assets/manage_units_5.png)

1. Följ samma procedurer för att skapa den andra mallen som tilldelats den tidigare skapade organisationsenheten Geometrixx Clothes.

Användaren som är tilldelad standardanvändar- och Geometrixx-färggrupperna kan se båda mallarna. På grund av organisationsenheternas hierarkiska struktur har han läs- och skrivåtkomst till mallen som är länkad till enheten Geometrixx Clothes och endast skrivskyddad åtkomst till mallen som är länkad till enheten Geometrixx.

![](assets/manage_units_7.png)

Eftersom enheten för Geometrixx-kläder är en underordnad enhet till Geometrixx visas följande meddelande när användaren försöker ändra mallen Geometrixx:

![](assets/manage_units_8.png)

Organisationsenheter kan begränsa åtkomsten till olika funktioner som profiler. Om våra Geometrixx-kunder till exempel har åtkomst till fliken **[!UICONTROL Profiles]** , kan de få tillgång till och ändra profilerna med hjälp av organisationsenheten Geometrixx Clothes.

Profilerna med organisationsenheten Geometrixx blir skrivskyddade, men följande fel visas om användaren försöker ändra en profil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitionsprofiler {#partitioning-profiles}

Om din organisation behöver isolera profilerna som kontaktas av alla dina olika varumärken kan du partitionera profilerna efter deras organisationsenheter.

Som standard är organisationsenhetsfälten inte tillgängliga i dina profiler och behöver läggas till.

Det går inte att komma åt profiler utan organisationsenheter.

>[!IMPORTANT]
>
>Vi rekommenderar att du lägger till det här alternativet innan du importerar några profiler. Om du redan har importerat din kunddatabas måste du uppdatera den för att kunna ange organisationsenhetsvärden för de redan importerade profilerna.

1. På den avancerade menyn, via Adobe Campaign-logotypen, väljer du **Administration > Utveckling > Anpassade resurser**.
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

