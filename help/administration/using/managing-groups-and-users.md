---
title: Hantera grupper och användare
description: Lär dig hur du skapar säkerhetsgrupper och hanterar användare.
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 09a6e062be32b78fda6b0eb83a6d11ac249b3168
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---


# Hantera grupper och användare{#managing-groups-and-users}

## Om säkerhetsgrupper {#about-security-groups}

Säkerhetsgrupper är uppsättningar användare som delar samma roller och rättigheter inom organisationen.

Användare måste alltid vara länkade till en säkerhetsgrupp. På så sätt kan du tilldela dem specifika roller och organisationsenheter.

För mer information om roller visar tabellerna på följande sida de olika åtgärder som är tillgängliga beroende på en användares roll(er): [Adobe Campaign Standarder](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Standardsäkerhetsgrupper:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Om en användare inte är länkad till någon säkerhetsgrupp kan han/hon inte komma åt Adobe Campaign.

Om du vill begränsa en användares åtkomst ska du inte lägga till Campaign Standarden i användargruppen eftersom den är länkad till **[!UICONTROL All]** organisationsenheten.

>[!NOTE]
>
>Organisationsenheten tilldelas som standard till **[!UICONTROL All (all)]****[!UICONTROL Administrators]** säkerhetsgruppen. Den är skrivskyddad och kan inte ändras.

## Skapa en säkerhetsgrupp och tilldela användare {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Observera att i Admin Console kallas säkerhetsgrupper för profiler.

Du kan skapa egna säkerhetsgrupper om de färdiga grupperna inte räcker för att hantera användarna. De kan hanteras av administratörer som har tillgång till både administrationsmenyerna i Adobe Campaign och Admin Console. Mer information om Admin Console finns i den här [dokumentationen](https://helpx.adobe.com/enterprise/managing/user-guide.html).

Här måste vi först tilldela de två färdiga grupperna Standard-användare och Administratör till våra användare. Dessa säkerhetsgrupper kommer att begränsa vissa funktioner i Adobe Campaign: standardanvändaren har grundläggande åtkomst till Adobe Campaign, medan administratören kan komma åt administrationsmenyerna till exempel.

Observera att alla ändringar som görs i säkerhetsgrupper på Admin Console synkroniseras så snart användare loggar in i Adobe Campaign.

Sedan vill vi skapa en uppsättning säkerhetsgrupper, Geometrixx och Geometrixx, som begränsar åtkomsten beroende på vilka organisationsenheter som finns i vår standardanvändare och administratör.

![](assets/ootb_security_group_1.png)

Du måste först tilldela en av de färdiga säkerhetsgrupperna till dina användare:

1. På Admin Console väljer du din instans och sedan fliken **Användare** .

   ![](assets/manage_security_group_2.png)

1. Klicka på **[!UICONTROL Add user]** knappen och ange användarens e-postadress.
1. Markera instansen på fliken **[!UICONTROL Assign Products]** och markera sedan den **[!UICONTROL Administrators]** säkerhetsgrupp som är klar att användas i listrutan. Detta ger användaren åtkomst till administrationsmenyerna och möjlighet att skapa nästa säkerhetsgrupper.

   ![](assets/ootb_security_group_2.png)

1. Klicka **[!UICONTROL Save]** och följ samma procedurer för att tilldela den **[!UICONTROL Standard Users]** färdiga säkerhetsgruppen till den nya användaren.

   ![](assets/ootb_security_group_3.png)

När dina två användare är anslutna till **[!UICONTROL Administrators]** - och **[!UICONTROL Standard users]** färdiga säkerhetsgrupper som tilldelar roller till våra användare, kan administratörsanvändaren nu skapa de två säkerhetsgrupperna **Geometrixx** och **Geometrixx** som tilldelar våra användare organisationsenheter utöver de färdiga säkerhetsgrupperna.

1. På Admin Console väljer du din instans och sedan fliken **Produkter** .
1. Klicka på knappen **Ny profil** för att skapa **Geometrixx** säkerhetsgrupp.

   ![](assets/create_security_1.png)

1. Skriv in **[!UICONTROL Profile name]** med följande exakta syntax: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** och klicka på **[!UICONTROL Done]**.

   Det valda ID:t används sedan när säkerhetsgruppen skapas i Adobe Campaign.

   >[!NOTE]
   >
   >Om ovanstående syntax inte verkar fungera med en äldre instans måste den ersättas med **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Följ sedan samma procedurer för att skapa säkerhetsgruppen **Geometrixx Clothes** .
1. Tilldela din säkerhetsgrupp till användaren genom att välja **[!UICONTROL Users]** fliken.

   ![](assets/manage_security_group_2.png)

1. Klicka på den tidigare skapade användaren och sedan på ![](assets/managing_security_group_10.png) ikonen i **[!UICONTROL Products]** kategorin.

   Välj **[!UICONTROL Edit products assigned directly]** om du vill börja tilldela användaren en ny säkerhetsgrupp.

   ![](assets/manage_security_group_8.png)

1. På **[!UICONTROL Assign Products]** fliken väljer du instansen och sedan den tidigare skapade Geometrixx för säkerhetsgrupper i listrutan för att tilldela den till administratörsanvändaren.

   Klicka på **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Om en användare finns i flera grupper:

   * De olika gruppernas roller sammanställs. Här finns två olika grupper: en som ska agera på roller och den andra på enheter.
   * Det är den enhet som är högst i hierarkin som ska användas (se exempel i avsnittet [Organisationsenheter](../../administration/using/organizational-units.md) ).
   * Användaren kan inte längre ansluta om enheterna har samma nivå och finns i parallella grenar i hierarkin.

1. Följ samma procedurer när du ska tilldela säkerhetsgruppen Geometrixx Clothes till standardanvändaren.

   ![](assets/manage_security_group_9.png)

De nya säkerhetsgrupperna skapas nu i Admin Console. För att de ska synkas fullständigt måste du också skapa dem i Adobe Campaign.

Administratörsanvändaren måste skapa en uppsättning säkerhetsgrupper som används för att tilldela organisationsenheter: Geometrixx och Geometrixx. Mer information om hur du skapar organisationsenheter finns i [Skapa och hantera enheter](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Klicka på **[!UICONTROL Adobe Campaign]** logotypen i det övre vänstra hörnet och välj sedan **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Skapa en ny säkerhetsgrupp och ange dess **[!UICONTROL Label]** och **[!UICONTROL ID]**.

   ID:t måste vara samma som det som valts i Admin Console.

1. Tilldela organisationsenhet i **[!UICONTROL User access]** fältet. Här tilldelas säkerhetsgruppen Geometrixx **[!UICONTROL All]** organisationsenheten.

   >[!NOTE]
   >
   >Om du tilldelar en färdig säkerhetsgrupp till dina användare måste du återställa organisationsenheten.

   ![](assets/manage_security_group_6.png)

1. Du kan också tilldela roller till din säkerhetsgrupp. I det här fallet behövs inte det här steget eftersom de färdiga säkerhetsgrupperna **[!UICONTROL Administrators]** och **[!UICONTROL Standard users]** används för att tilldela roller.
1. Följ samma procedurer för att skapa de senaste Geometrixx och tilldela organisationsenheten för Geometrixx.

   ![](assets/manage_security_group_7.png)

Dina användare har nu tilldelats en säkerhetsgrupp och kan ansluta till Adobe Campaign.

>[!IMPORTANT]
>
>Om användare tas bort från en säkerhetsgrupp i Admin Console blir de kvar i säkerhetsgruppen Adobe Campaign och kan inte längre logga in i Adobe Campaign. I så fall tar du bort användarens e-postadresser i Admin Console för att förhindra att de får känslig information.

