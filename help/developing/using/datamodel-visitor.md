---
title: DataModel Visitor
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---

# Besökare (nms:visitor)

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
        <td>kommentar</td>
        <td>Referentkommentar</td>
        <td>sträng (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>skapad</td>
        <td>Skapad</td>
        <td>datum </td>
        <td> </td>
    </tr>
    <tr>
        <td>createdBy (userBase)</td>
        <td>Skapad av</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>leverans (leverans)</td>
        <td>Leverans</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID för den senaste leveransen</td>
        <td>heltal </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Beskrivning</td>
        <td>sträng (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>e-post</td>
        <td>E-post</td>
        <td>sträng (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>Externt ID</td>
        <td>sträng (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Förnamn</td>
        <td>sträng (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>Vidarebefordra url</td>
        <td>sträng (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Geografisk enhet</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Senast ändrad</td>
        <td>datum </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>Efternamn</td>
        <td>sträng (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Ändrad av</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Organisationsenhet</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>ursprung</td>
        <td>Ursprung</td>
        <td>uppräkning (byte) </td>
        <td>
            <ul>
            <li>Odefinierad - odefinierad - 0</li>
            <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>mottagare (mottagare)</td>
        <td>Identifierad profil</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>receiveId</td>
        <td>Profil-ID</td>
        <td>heltal </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>E-postadress för referent</td>
        <td>sträng (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Förnamn för referent</td>
        <td>sträng (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>Referens-ID</td>
        <td>heltal </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Efternamn för referent</td>
        <td>sträng (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referenceRcp (mottagare)</td>
        <td>Referent</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>Etikett</td>
        <td>sträng (255)</td>
        <td> </td>
    </tr>
</table>

## Filter

Efter efternamn, förnamn eller e-post (efterText)</p>

<table>
        <tr>
        <th>Namn</th>
        <th>Typ</th>
        </tr>
        <tr>
        <td>text</td>
        <td>string</td>
        </tr>
    </table>
