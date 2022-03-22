---
title: DataModel-prenumerationshändelse
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 6%

---

# Prenumerationshändelse (nms:rtEvent)

## Objektbeskrivning

<table>
    <tr>
        <th>Namn</th>
        <th>Etikett</th>
        <th>Typ (längd)</th>
        <th>Uppräkningsvärden</th>
    </tr>
    <tr>
        <td>PKey</td>
        <td>Huvudresurs-ID</td>
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>ctx</td>
        <td>Händelsekontext</td>
        <td>artikel </td>
        <td> </td>
    </tr>
    <tr>
        <td>e-post</td>
        <td>E-post</td>
        <td>sträng (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>E-postformat</td>
        <td>uppräkning (byte) </td>
        <td>
            <ul>
            <li>Text - text - 1</li>
            <li>HTML - html - 2</li>
            <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
            <li>Okänd - okänd - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoryId</td>
        <td>ID för arkiverad händelse</td>
        <td>heltal </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Mobile</td>
        <td>sträng (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>string </td>
        <td> </td>
    </tr>
</table>

## Filter

Per e-post (via e-post)

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

Efter status eller typ (byStatusOrType)

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
