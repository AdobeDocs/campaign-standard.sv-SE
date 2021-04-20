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
source-wordcount: '81'
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
        <td>Mobilnummer</td>
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