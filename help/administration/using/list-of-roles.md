---
solution: Campaign Standard
product: campaign
title: Lista över roller
description: Ta reda på listan med roller som du kan tilldela dina användare.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 93%

---


# Lista över roller{#list-of-roles}

Adobe Campaign erbjuder som standard en uppsättning roller som du kan använda för att definiera enhetsbehörigheter som tilldelas användare och användargrupper.

I kombination med organisationsenheter ger roller användarna en filtrerad vy av gränssnittet och definierar deras åtkomst till de olika funktionerna.

Mer information finns i tabellen [Roller och behörigheter](/help/administration/using/assets/acs_rights.pdf), som beskriver vilka funktioner som är tillgängliga i gränssnittet beroende på de valda auktoriseringarna.

[![image](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

Roller kan hanteras på **[!UICONTROL Administration > Users & Security > Roles]**-menyn.

Standardrättigheterna är:

* **[!UICONTROL Administration]**: Allmän administrationsrätt.
* **[!UICONTROL Datamodel]**: Rätt att köra publikationer och skapa anpassade resurser.
* **[!UICONTROL Generic import]**: Rätt att köra en generisk import av data. Du måste koppla **[!UICONTROL Generic import]**-rollen till **[!UICONTROL Workflow]**-rollen för att detta ska fungera.
* **[!UICONTROL Prepare deliveries]**: Rätt att skapa, ändra, förbereda och ta bort leveranser. Användare med den här rollen kan förbereda leveransen, men kan inte skicka den.
* **[!UICONTROL Start deliveries]**: Rätt att skapa, ändra, förbereda, skicka och ta bort leveranser.
* **[!UICONTROL Workflow]**: Rätt att hantera körningen av arbetsflöden (starta, stoppa, pausa, o.s.v.). Användare med den här rollen kan inte skicka en leverans – inte ens i ett arbetsflöde.

**Relaterade ämnen:**

* [Om åtkomsthantering](../../administration/using/about-access-management.md)
* [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md)
