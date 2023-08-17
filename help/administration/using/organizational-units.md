---
title: Organisationsenheter
description: Definiera användarnas åtkomstnivåer med hjälp av organisationsenheter
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 4%

---

# Organisationsenheter{#organizational-units}

## Om enheter {#about-units}

Varje objekt och användare av plattformen är länkade till en organisationsenhet. Den här enheten gör att en hierarkisk struktur kan definieras för att ge användarna en filtrerad vy. En användares enhet definierar sin åtkomstnivå för olika plattformsobjekt.

>[!IMPORTANT]
>
>Om en användare inte är länkad till någon enhet kan den användaren inte ansluta till Adobe Campaign. Om du vill begränsa åtkomsten för en viss användare eller grupp av användare ska du inte länka den till **[!UICONTROL All]** enhet. Vi rekommenderar att du lägger till alternativet **Åtkomst till behörighetshanteringsfält** innan du importerar några profiler. Mer information om detta hittar du i det här [avsnittet](../../administration/using/organizational-units.md#partitioning-profiles).
>
>**[!UICONTROL All (all)]** Organisationsenheten tilldelas som standard till **[!UICONTROL Administrators]** säkerhetsgruppen.  Den är skrivskyddad och kan inte ändras.

En användare har skrivskyddad åtkomst till alla objekt i de överordnade enheterna. Den här användaren har läs- och skrivåtkomst till alla objekt i sin enhet och sina underordnade enheter. En användare har inte åtkomst till objekt i parallella grenar.

Som standard är bara **[!UICONTROL All]** enheter är tillgängliga.

När användaren tilldelas en organisationsenhet används alltid den här enheten på de objekt som användaren skapade.

![](assets/user_management_2.png)

>[!NOTE]
>
>När en användare finns i flera grupper som är länkade till olika enheter används vissa regler. Mer information finns i [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md) -avsnitt.

## Skapa och hantera enheter {#creating-and-managing-units}

Med organisationsenheter kan du filtrera instansen beroende på vilken organisation användarna är länkade till. Den här enheten kan representera en region, ett land eller till och med ett varumärke i din instans.

Här har vi tidigare skapat säkerhetsgrupper med olika roller för två användare: en användare har tilldelats säkerhetsgrupperna Administratörer och Geometrixx, den andra användaren tillhör säkerhetsgrupperna Standardanvändare och Geometrixx Se [Skapa en säkerhetsgrupp och tilldela användare](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) i det fullständiga exemplet.

Nu måste vi skapa organisationsenheter för Geometrixx- och Geometrixx säkerhetsgrupper:

1. På Adobe-kampanjens avancerade meny väljer du **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Klicka **[!UICONTROL Create]** för att börja konfigurera din organisationsenhet.

   ![](assets/manage_units_1.png)

1. Ändra standardinställningen **[!UICONTROL Label]** och **[!UICONTROL ID]** till Geometrixx.
1. Länka sedan enheten till en överordnad enhet. Här väljer vi **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Klicka slutligen **[!UICONTROL Create]** för att börja tilldela din nya organisationsenhet till säkerhetsgruppen.
1. Följ samma procedur för enheten Geometrixx, förutom att dess överordnade enhet måste vara den tidigare skapade enheten, Geometrixx.

   ![](assets/manage_units_3.png)

För att se effekten av att tilldela olika enheter till olika säkerhetsgrupper skapar den användare som tilldelats administratörs- och Geometrixx-grupperna två e-postmallar för att se vad den andra användaren som tilldelats standardanvändare och Geometrixx kan eller inte kan komma åt.

1. Välj på den avancerade menyn **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplicera en befintlig mall och anpassa den efter behov. Mer information finns i [Om mallar](../../start/using/marketing-activity-templates.md) -avsnitt.
1. När mallen skapas väljer du **[!UICONTROL Edit properties]** om du vill tilldela enheter till mallen.

   ![](assets/manage_units_6.png)

1. I **[!UICONTROL Access authorization]** väljer du organisationsenhet.

   Här ska vi skapa en mall med den tidigare skapade Geometrixx för organisationsenheter.

   ![](assets/manage_units_5.png)

1. Följ samma procedurer för att skapa den andra mallen som tilldelats den tidigare skapade organisationsenheten för Geometrixx.

Användare som är tilldelade **Standardanvändare** och **Geometrixx** grupper kan se båda mallarna. På grund av organisationsenheternas hierarkiska struktur har de läs- och skrivåtkomst till den mall som är länkad till Geometrixx Color-enheten och endast skrivskyddad åtkomst till den mall som är länkad till Geometrixx.

![](assets/manage_units_7.png)

Eftersom Geometrixx Clothes-enheten är en underordnad enhet till Geometrixx visas följande meddelande när användare försöker ändra Geometrixx:

![](assets/manage_units_8.png)

Organisationsenheter kan begränsa åtkomsten till olika funktioner som profiler. Om våra användare av Geometrixx till exempel har åtkomst till **[!UICONTROL Profiles]** kommer de att kunna öppna och ändra profilerna helt och hållet med organisationsenheten Geometrixx Clothes.

Profilerna med organisationsenheten för Geometrixx kommer att vara skrivskyddade, men följande fel visas om användare försöker ändra en profil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitionsprofiler {#partitioning-profiles}

>[!IMPORTANT]
>
>Vi rekommenderar att du lägger till det här alternativet innan du importerar några profiler eftersom användare inte kan komma åt profiler utan organisationsenheter.
>
>Om du redan har importerat din kunddatabas måste du uppdatera den för att kunna ange organisationsenhetsvärden för de redan importerade profilerna.

Om din organisation behöver isolera profilerna som kontaktas av alla dina olika varumärken kan du partitionera profilerna efter deras organisationsenheter.

Som standard är organisationsenhetsfälten inte tillgängliga i dina profiler och behöver läggas till.

1. På den avancerade menyn via Adobe Campaign logotyp väljer du **Administration > Utveckling > Anpassade resurser**.
1. Välj **Profil** eller skapa en ny anpassad resurs för att utöka profilerna. Mer information om hur du utökar profilerna finns i [page](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Kontrollera **Lägg till åtkomstbehörighetshanteringsfält** om du vill lägga till organisationsenheter i **Profil** tillägg.

   ![](assets/user_management_9.png)

1. Klicka på **[!UICONTROL Save]**.
1. Uppdatera strukturen genom att publicera om anpassade resurser. Mer information om publiceringsprocessen finns i [Uppdaterar strukturen](../../developing/using/updating-the-database-structure.md) -avsnitt.

Fältet Organisationsenhet läggs till i dina profiler i **[!UICONTROL Access authorization]** -avsnitt.

![](assets/user_management_10.png)

**Relaterade ämnen**:

* [Om enheter](../../administration/using/organizational-units.md#about-units)
* [Om åtkomsthantering](../../administration/using/about-access-management.md)
