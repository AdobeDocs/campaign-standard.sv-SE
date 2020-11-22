---
solution: Campaign Standard
product: campaign
title: DataModel
description: Läs mer om datamodellen
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '53'
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