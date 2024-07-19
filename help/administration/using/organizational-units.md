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
>Om en användare inte är länkad till någon enhet kan den användaren inte ansluta till Adobe Campaign. Om du vill begränsa åtkomsten för en viss användare eller grupp av användare ska du inte länka den till enheten **[!UICONTROL All]**. Vi rekommenderar att du lägger till alternativet **Åtkomsthanteringsfält** innan du importerar några profiler. Mer information om detta hittar du i det här [avsnittet](../../administration/using/organizational-units.md#partitioning-profiles).
>
>**[!UICONTROL All (all)]** Organisationsenheten tilldelas som standard till **[!UICONTROL Administrators]** säkerhetsgruppen.  Den är skrivskyddad och kan inte ändras.

En användare har skrivskyddad åtkomst till alla objekt i de överordnade enheterna. Den här användaren har läs- och skrivåtkomst till alla objekt i sin enhet och sina underordnade enheter. En användare har inte åtkomst till objekt i parallella grenar.

Som standard är bara **[!UICONTROL All]** enheter tillgängliga.

När användaren tilldelas en organisationsenhet används alltid den här enheten på de objekt som användaren skapade.

![](assets/user_management_2.png)

>[!NOTE]
>
>När en användare finns i flera grupper som är länkade till olika enheter används vissa regler. Mer information finns i avsnittet [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md).

## Skapa och hantera enheter {#creating-and-managing-units}

Med organisationsenheter kan du filtrera instansen beroende på vilken organisation användarna är länkade till. Den här enheten kan representera en region, ett land eller till och med ett varumärke i din instans.

Här har vi tidigare skapat säkerhetsgrupper med olika roller för två användare: en användare har tilldelats säkerhetsgrupperna Administratörer och Geometrixx, den andra användaren tillhör säkerhetsgrupperna Standardanvändare och Geometrixx Se [Skapa en säkerhetsgrupp och tilldela användare](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) för det fullständiga exemplet.

Nu måste vi skapa organisationsenheter för Geometrixx- och Geometrixx säkerhetsgrupper:

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]** på den avancerade menyn för Adobe-kampanjen.
1. Klicka på **[!UICONTROL Create]** för att börja konfigurera din organisationsenhet.

   ![](assets/manage_units_1.png)

1. Ändra standardvärdet **[!UICONTROL Label]** och **[!UICONTROL ID]** till Geometrixx.
1. Länka sedan enheten till en överordnad enhet. Här valde vi **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Klicka slutligen på **[!UICONTROL Create]** för att börja tilldela din nya organisationsenhet till säkerhetsgruppen.
1. Följ samma procedur för enheten Geometrixx, förutom att dess överordnade enhet måste vara den tidigare skapade enheten, Geometrixx.

   ![](assets/manage_units_3.png)

För att se effekten av att tilldela olika enheter till olika säkerhetsgrupper skapar den användare som tilldelats administratörs- och Geometrixx-grupperna två e-postmallar för att se vad den andra användaren som tilldelats standardanvändare och Geometrixx kan eller inte kan komma åt.

1. Välj **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]** på den avancerade menyn.
1. Duplicera en befintlig mall och anpassa den efter behov. Mer information finns i avsnittet [Om mallar](../../start/using/marketing-activity-templates.md).
1. När mallen skapas väljer du ikonen **[!UICONTROL Edit properties]** för att tilldela enheter till mallen.

   ![](assets/manage_units_6.png)

1. Välj organisationsenhet i listrutan **[!UICONTROL Access authorization]**.

   Här ska vi skapa en mall med den tidigare skapade Geometrixx för organisationsenheter.

   ![](assets/manage_units_5.png)

1. Följ samma procedurer för att skapa den andra mallen som tilldelats den tidigare skapade organisationsenheten för Geometrixx.

Användare som är tilldelade grupperna **Standardanvändare** och **Geometrixx** kan se båda mallarna. På grund av organisationsenheternas hierarkiska struktur har de läs- och skrivåtkomst till den mall som är länkad till Geometrixx Color-enheten och endast skrivskyddad åtkomst till den mall som är länkad till Geometrixx.

![](assets/manage_units_7.png)

Eftersom Geometrixx Clothes-enheten är en underordnad enhet till Geometrixx visas följande meddelande när användare försöker ändra Geometrixx:

![](assets/manage_units_8.png)

Organisationsenheter kan begränsa åtkomsten till olika funktioner som profiler. Om våra användare av Geometrixx Clinters till exempel har åtkomst till fliken **[!UICONTROL Profiles]** kan de få fullständig åtkomst till och ändra profilerna med organisationsenheten för Geometrixx.

Profilerna med organisationsenheten kommer att vara skrivskyddade, men följande fel visas om användare försöker ändra en Geometrixx: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitionsprofiler {#partitioning-profiles}

>[!IMPORTANT]
>
>Vi rekommenderar att du lägger till det här alternativet innan du importerar några profiler eftersom användare inte kan komma åt profiler utan organisationsenheter.
>
>Om du redan har importerat din kunddatabas måste du uppdatera den för att kunna ange organisationsenhetsvärden för de redan importerade profilerna.

Om din organisation behöver isolera profilerna som kontaktas av alla dina olika varumärken kan du partitionera profilerna efter deras organisationsenheter.

Som standard är organisationsenhetsfälten inte tillgängliga i dina profiler och behöver läggas till.

1. På den avancerade menyn, via Adobe Campaign logotyp, väljer du **Administration > Utveckling > Anpassade resurser**.
1. Välj **Profil** eller skapa en ny anpassad resurs för att utöka profilerna. Mer information om hur du utökar profilerna finns på [sidan](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Markera rutan **Lägg till åtkomstbehörighetshanteringsfält** om du vill lägga till organisationsenheter i tillägget **Profil**.

   ![](assets/user_management_9.png)

1. Klicka på **[!UICONTROL Save]**.
1. Uppdatera strukturen genom att publicera om anpassade resurser. Mer information om publiceringsprocessen finns i avsnittet [Uppdatera strukturen](../../developing/using/updating-the-database-structure.md).

Fältet Organisationsenhet läggs till i dina profiler i avsnittet **[!UICONTROL Access authorization]**.

![](assets/user_management_10.png)

**Relaterade ämnen**:

* [Om enheter](../../administration/using/organizational-units.md#about-units)
* [Om åtkomsthantering](../../administration/using/about-access-management.md)
