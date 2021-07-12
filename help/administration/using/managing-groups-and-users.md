---
solution: Campaign Standard
product: campaign
title: Hantera grupper och användare
description: Lär dig hur du skapar säkerhetsgrupper och hanterar användare.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: user,overview;user,main;security,overview;security,main
feature: Åtkomsthantering
role: Admin
level: Experienced
exl-id: 4b9834ab-0f7c-419e-a210-77a018ba874d
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 88%

---

# Hantera grupper och användare{#managing-groups-and-users}

## Om säkerhetsgrupper {#about-security-groups}

Säkerhetsgrupper är uppsättningar av användare som delar samma roller och rättigheter inom organisationen.

Användare måste alltid vara länkade till en säkerhetsgrupp.  På så sätt kan du tilldela dem specifika roller och organisationsenheter.

För mer information om roller visas i tabellen på följande sida möjliga åtgärder som är tillgängliga beroende på en användares roll(er): [Adobe Campaign Standard-auktoriseringar](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en).

De säkerhetsgrupper som finns som standard är:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

>[!IMPORTANT]
>
>Säkerhetsgrupperna **[!UICONTROL Access to the deliverability parameters (Deliverability)]** och **[!UICONTROL Message Center agents (mcExec)]** är endast Adobe internal och ska inte tilldelas till någon användare.

För att få åtkomst till Adobe Campaign måste varje användare tilldelas en säkerhetsgrupp.

Om du vill begränsa en användares åtkomst ska du inte lägga till användaren i användargruppen för Campaign Standard eftersom den redan är länkad till **[!UICONTROL All]** organisationsenheten.

>[!NOTE]
>
>**[!UICONTROL All (all)]** Organisationsenheten tilldelas som standard till **[!UICONTROL Administrators]** säkerhetsgruppen.  Den är skrivskyddad och kan inte ändras.

## Skapa en säkerhetsgrupp och tilldela användare {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>I Admin Console kallas säkerhetsgrupper för profiler.

Du kan skapa egna säkerhetsgrupper om de inbyggda grupperna inte räcker till för att hantera användarna.  De kan hanteras av administratörer som har tillgång till både administrationsmenyer för Adobe Campaign och Admin Console.  Mer information om Admin Console finns i denna [dokumentationen](https://helpx.adobe.com/se/enterprise/managing/user-guide.html).

Här måste vi först tilldela de två inbyggda grupperna Standardanvändare och Administratörer till våra användare.  Dessa säkerhetsgrupper begränsar vissa funktioner i Adobe Campaign. Standardanvändaren har grundläggande åtkomst till Adobe Campaign medan administratören exempelvis kan komma åt administrationsmenyerna.

Alla ändringar som görs i säkerhetsgrupper i Admin Console synkroniseras så snart användarna loggar in på Adobe Campaign.

Sedan skapar vi en uppsättning av säkerhetsgrupper, Geometrixx- och Geometrixx Clothes, som begränsar åtkomsten beroende på organisationsenheterna för vår standardanvändare och administratörer.

![](assets/ootb_security_group_1.png)

Du måste först tilldela dina användare en av de inbyggda säkerhetsgrupperna:

1. I Admin Console väljer du din instans och sedan fliken **Användare** .

   ![](assets/manage_security_group_2.png)

1. Klicka på knapp **[!UICONTROL Add user]** och ange användarens e-postadress.
1. Markera instansen på fliken **[!UICONTROL Assign Products]** och markera sedan den säkerhetsgrupp **[!UICONTROL Administrators]** som är klar att användas i rullgardinslistan.        Detta ger användaren åtkomst till administrationsmenyerna och möjligheten att skapa nästa säkerhetsgrupper.

   ![](assets/ootb_security_group_2.png)

1. Klicka **[!UICONTROL Save]** och följ samma procedurer för att tilldela den nya användaren den **[!UICONTROL Standard Users]** inbyggda säkerhetsgruppen.

   ![](assets/ootb_security_group_3.png)

När de två användarna är anslutna till de inbyggda säkerhetsgrupperna **[!UICONTROL Administrators]** och **[!UICONTROL Standard users]** som tilldelar roller till våra användare, så kan administratören nu skapa de två säkerhetsgrupperna **Geometrixx** och **Geometrixx Clothes** som tilldelar organisationsenheter till våra användare utöver de inbyggda säkerhetsgrupperna.

1. I Admin Console väljer du din instans och sedan fliken **Produkter** .
1. Klicka på knappen **Ny profil** för att skapa säkerhetsgruppen **Geometrixx**.

   ![](assets/create_security_1.png)

1. Skriv in **[!UICONTROL Profile name]** med följande specifika syntax **[!UICONTROL Campaign Standard- instance name - ID of the security group]** och klicka på **[!UICONTROL Done]**.

   Det valda ID:t används sedan när säkerhetsgruppen skapas i Adobe Campaign.

   >[!NOTE]
   >
   >Om ovanstående syntax inte verkar fungera med en äldre instans så måste den ersättas med **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Följ sedan samma procedur för att skapa säkerhetsgruppen **Geometrixx Clothes** .
1. Tilldela din säkerhetsgrupp till användaren genom att välja flik **[!UICONTROL Users]**.

   ![](assets/manage_security_group_2.png)

1. Klicka på den tidigare skapade användaren och sedan på ikonen ![](assets/managing_security_group_10.png) i kategori **[!UICONTROL Products]**.

   Välj **[!UICONTROL Edit products assigned directly]** om du vill tilldela användaren en ny säkerhetsgrupp.

   ![](assets/manage_security_group_8.png)

1. På fliken **[!UICONTROL Assign Products]** väljer du instansen och sedan de säkerhetsgrupper du tidigare skapade i listrutan för att tilldela det till administratörsanvändaren.

   Klicka på **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Om en användare finns i flera grupper:

   * De olika grupprollerna sammanställs.  Här finns två olika grupper: en som ska agera enligt roller och enligt enheter.
   * Den enhet som är högst i hierarkin som används (se exempel i avsnittet [Organisationsenheter](../../administration/using/organizational-units.md) ).
   * Användaren kan inte längre ansluta om enheterna har samma nivå och finns i parallella grenar i hierarkin.

1. Följ samma procedur för att tilldela standardanvändaren säkerhetsgruppen Geometrixx Clothes.

   ![](assets/manage_security_group_9.png)

De nya säkerhetsgrupperna skapas nu i Admin Console.  För att de ska synkas fullständigt måste ni också skapa dem i Adobe Campaign.

Administratörsanvändaren måste skapa en uppsättning av säkerhetsgrupper som används för att tilldela organisationsenheterna Geometrixx och Geometrix Clothes.  Mer information om hur du skapar organisationsenheter hittar du i [Skapa och hantera enheter](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Klicka på logotypen **[!UICONTROL Adobe Campaign]** i det övre vänstra hörnet och välj sedan **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Skapa en ny säkerhetsgrupp och ange dess **[!UICONTROL Label]** och **[!UICONTROL ID]**.

   ID:t måste vara detsamma som det som valts i Admin Console.

1. Tilldela organisationsenhet i fält **[!UICONTROL User access]**.  Här tilldelas säkerhetsgruppen Geometrixx den **[!UICONTROL All]** organisationella enheten.

   >[!NOTE]
   >
   >Om du tilldelar en färdig säkerhetsgrupp till dina användare måste du återställa organisationsenheten.

   ![](assets/manage_security_group_6.png)

1. Du kan också tilldela roller till din säkerhetsgrupp.  I det här fallet behövs inte det här steget eftersom de färdiga säkerhetsgrupperna **[!UICONTROL Administrators]** och **[!UICONTROL Standard users]** används för att tilldela roller.
1. Följ samma procedur för att skapa föregående säkerhetsgrupp Geometrix Clothes och tilldela organisationsenheten Geometrixx Clothes.

   ![](assets/manage_security_group_7.png)

Dina användare har nu tilldelats en säkerhetsgrupp och kan ansluta till Adobe Campaign.

>[!IMPORTANT]
>
>Om användare tas bort från en säkerhetsgrupp i Admin Console är de fortfarande en del av Adobe Campaign säkerhetsgrupp och kan inte längre logga in i Adobe Campaign. I så fall tar du bort användarens e-postadresser i Admin Console för att förhindra att de får känslig information.
