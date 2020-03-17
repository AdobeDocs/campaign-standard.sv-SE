---
title: DataModel
description: Läs mer om datamodellen
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

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