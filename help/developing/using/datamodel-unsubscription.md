---
solution: Campaign Standard
product: campaign
title: DataModel
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 5%

---


# Unsubscription Event (nms:rtEvent)

## Objektbeskrivning

<table>
               <tr>
                  <th>Namn</th>
                  <th>Skrivskyddad</th>
                  <th>Typ</th>
                  <th>Obligatoriskt</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Falskt</td>
                  <td>string</td>
                  <td>Falskt</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Falskt</td>
                  <td>artikel</td>
                  <td>Falskt</td>
               </tr>
               <tr>
                  <td>e-post</td>
                  <td>Falskt</td>
                  <td>string</td>
                  <td>Falskt</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Falskt</td>
                  <td>uppräkning</td>
                  <td>Falskt</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Falskt</td>
                  <td>string</td>
                  <td>Falskt</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>string</td>
                  <td>Falskt</td>
               </tr>
            </table>

## Filter

byEmail

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>e-post</td>
    <td>string</td>
    </tr>
</table>

byStatusOrType

<table>
        <tr>
        <th>Namn</th>
        <th>Typ</th>
        </tr>
        <tr>
        <td>status</td>
        <td>uppräkning</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>