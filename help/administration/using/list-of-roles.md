---
title: Lista över roller
description: Ta reda på listan med roller som du kan tilldela dina användare.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 84%

---

# Lista över roller{#list-of-roles}

Adobe Campaign erbjuder som standard en uppsättning roller som du kan använda för att definiera enhetsbehörigheter som tilldelas användare och användargrupper.

I kombination med organisationsenheter ger roller användarna en filtrerad vy av gränssnittet och definierar deras åtkomst till de olika funktionerna.

Roller kan hanteras på **[!UICONTROL Administration > Users & Security > Roles]**-menyn.

Standardrättigheterna är:

* **[!UICONTROL Administration]**: Allmän administrationsrätt.

   >[!NOTE]
   >
   >Om du behöver arbeta med Experience Cloud-utlösare måste du ha **[!UICONTROL Administration]**-rättigheten för att kunna komma åt Experience Cloud-utlösarmenyn. Mer information om utlösare för Experience Cloud finns på den här [sidan](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: Rätt att köra publikationer och skapa anpassade resurser.
* **[!UICONTROL Generic import]**: Rätt att köra en generisk import av data. Du måste koppla **[!UICONTROL Generic import]**-rollen till **[!UICONTROL Workflow]**-rollen för att detta ska fungera.
* **[!UICONTROL Prepare deliveries]**: Rätt att skapa, ändra, förbereda och ta bort leveranser. Användare med den här rollen kan förbereda leveransen, men kan inte skicka den.
* **[!UICONTROL Start deliveries]**: Rätt att skapa, ändra, förbereda, skicka och ta bort leveranser.
* **[!UICONTROL Workflow]**: Rätt att hantera körningen av arbetsflöden (starta, stoppa, pausa, o.s.v.). Användare med den här rollen kan inte skicka en leverans – inte ens i ett arbetsflöde.

Mer information finns i tabellen [Roller och behörigheter](/help/administration/using/assets/acs_rights.pdf), som beskriver vilka funktioner som är tillgängliga i gränssnittet beroende på de valda auktoriseringarna.

[![image](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

**Relaterade ämnen:**

* [Om åtkomsthantering](../../administration/using/about-access-management.md)
* [Hantera grupper och användare](../../administration/using/managing-groups-and-users.md)
