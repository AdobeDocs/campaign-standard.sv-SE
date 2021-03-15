---
solution: Campaign Standard
product: campaign
title: DataModel
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 6%

---


# Service (nms:service)

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
                  <td>builtIn</td>
                  <td>Inbyggt programobjekt</td>
                  <td>boolesk </td>
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
                  <td>cusPrice</td>
                  <td>Pris</td>
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
                  <td>end</td>
                  <td>Slutdatum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geografisk enhet</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>historik</td>
                  <td>Prenumerationshistorik</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Är extern resurs</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Mall</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>Etikett</td>
                  <td>sträng (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Senast ändrad</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>limitedDuration</td>
                  <td>Begränsad varaktighet</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Datum</td>
                  <td>datum (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Kanal</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Mobil (SMS) - sms - 1</li>
                        <li>E-post - e-post - 0</li>
                        <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>läge</td>
                  <td>Läge</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Virusvirus - virus - 1</li>
                        <li>Nyhetsbrev - nyhetsbrev - 0</li>
                        <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Ändrad av</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>sträng (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Organisationsenhet</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>Tjänsteetikett</td>
                  <td>sträng (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Startdatum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>Startsida för prenumeration</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>Bekräftelse på prenumeration</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prenumerationer</td>
                  <td>Prenumerationer</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>Måldimension</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mall (tjänst)</td>
                  <td>Tjänstmall</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatyrbild</td>
                  <td>Miniatyrbild</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Tjänst</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Unsubscription landing page</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>Bekräftelse på avprenumeration</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>Giltighetstid</td>
                  <td>tal </td>
                  <td> </td>
               </tr>
            </table>

## Filter

Tillgängligt under angiven period (perPlanning)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>datum</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>datum</td>
    </tr>
</table>

Efter kanaltyp (byChannel)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>kanal</td>
<td>uppräkning</td>
</tr>
</table>

Efter namn eller etikett (byText)

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

Efter målresurs (byTargetResource)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>