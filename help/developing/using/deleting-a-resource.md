---
solution: Campaign Standard
product: campaign
title: Tar bort en resurs
description: 'Lär dig hur du tar bort en resurs '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 14%

---


# Tar bort en resurs{#deleting-a-resource}

Om du vill ta bort en resurs måste den aktuella resursen vara **[!UICONTROL Draft]**. Resursen har statusen **[!UICONTROL Draft]** om:

* Den har precis skapats och har ännu inte publicerats.
* Om den redan har publicerats måste resursen omarbetas.

>[!IMPORTANT]
>
>Att skriva om och ta bort en anpassad resurs är känsliga åtgärder som kan påverka andra resurser. Dessa åtgärder får endast utföras av en expertanvändare.

Så här gör du om utkast och tar bort en publicerad resurs:

1. Välj den resurs som du vill göra om utkast.
1. Klicka på knappen **[!UICONTROL Re-draft]** i åtgärdsfältet.

   ![](assets/schema_extension_uc26.png)

1. Klicka på **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Denna åtgärd är definitiv: resursens databastabell eller -kolumner och deras data tas bort permanent när ändringen publiceras, vilket kan leda till brutna länkar från andra anpassade resurser. Endast resursdefinitionen förblir tillgänglig.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Om du gör om ett utkast för ett tillägg i **Profiles (profil)**-resursen måste du också göra om alla **testprofiler (seedMember)**-tillägg som du har definierat. Mer information om hur du utökar profilresursen finns i [det här avsnittet](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publicera resursen. Mer detaljerad information finns i [Publicera en anpassad resurs](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Resursen försätts sedan i läget **Utkast** och dess aktiveringsstatus är **[!UICONTROL Inactive]**.

1. I **[!UICONTROL List]**-läge kontrollerar du den resurs du vill ta bort och klickar sedan på ikonen ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

Resursen tas bort från datamodellen.

>[!NOTE]
>
>Om ett fält för en anpassad resurs som används för en händelse ändras eller tas bort, kommer motsvarande händelse automatiskt att avpubliceras. Se [Avpublicera en transaktionshändelse](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
