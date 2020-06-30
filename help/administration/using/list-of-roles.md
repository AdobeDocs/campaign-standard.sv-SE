---
title: Lista över roller
description: Ta reda på listan med roller som du kan tilldela dina användare.
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 395791e69d0c4c8a888829539338e338387294de
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---


# Lista över roller{#list-of-roles}

Som standard har Adobe Campaign en uppsättning roller som gör att du kan definiera enhetsbehörigheter som tilldelats användare och användargrupper.

I kombination med organisationsenheter ger roller användarna en filtrerad vy av gränssnittet och definierar deras åtkomst till de olika funktionerna.

Mer information finns i tabellen [](/help/administration/using/assets/acs_rights.pdf)Roller och behörigheter, som beskriver vilka funktioner som är tillgängliga i gränssnittet beroende på de valda auktoriseringarna.

[![image](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

Roller kan hanteras på **[!UICONTROL Administration > Users & Security > Roles]** menyn.

Standardrättigheterna är:

* **[!UICONTROL Administration]**: Allmän administrationsrätt.
* **[!UICONTROL Datamodel]**: Rätt att köra publikationer och skapa anpassade resurser.
* **[!UICONTROL Generic import]**: Rätt att köra en generisk import av data. För att detta ska fungera måste du länka **[!UICONTROL Generic import]** rollen till **[!UICONTROL Workflow]** rollen.
* **[!UICONTROL Prepare deliveries]**: Rätt att skapa, ändra, förbereda och ta bort leveranser. Användare med den här rollen kan förbereda leveransen men inte skicka den.
* **[!UICONTROL Start deliveries]**: Rätt att skapa, ändra, förbereda, skicka och ta bort leveranser.
* **[!UICONTROL Workflow]**: Rätt att hantera körningen av arbetsflöden (starta, stoppa, pausa osv.). Användare med den här rollen kan inte skicka en leverans ens i ett arbetsflöde.

**Relaterade ämnen:**

* [Om åtkomsthantering](../../administration/using/about-access-management.md)
* [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md)
