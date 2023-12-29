---
title: Avprenumerationshändelse för DataModel
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 0%

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
