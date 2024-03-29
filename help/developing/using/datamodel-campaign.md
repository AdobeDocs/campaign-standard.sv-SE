---
title: DataModel Campaign
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a63fe730-a6b2-4ae0-93da-9f8ee7824c9f
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 2%

---

# Campaign (nms:campaign)

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
                  <td>verksamhet</td>
                  <td>Verksamhet</td>
                  <td>samling </td>
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
                  <td>desc</td>
                  <td>Beskrivning</td>
                  <td>sträng (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>varaktighet</td>
                  <td>Kampanjens varaktighet</td>
                  <td>tal </td>
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
                  <td>logicalStatus</td>
                  <td>Körningsstatus</td>
                  <td>enumeration (sträng) (255)</td>
                  <td>
                     <ul>
                        <li>Pågår - igång</li>
                        <li>Redigering - utgåva - utgåva</li>
                        <li>Slutförd - avslutad - avslutad</li>
                        <li>Varning - varning - varning</li>
                        <li>Fel - fel - fel</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>program (programBase)</td>
                  <td>Program</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Realtime-rapporter</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Startdatum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>status</td>
                  <td>Status</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Startat - startat - 1</li>
                        <li>Redigering - utgåva - 0</li>
                        <li>Slutförd - färdig - 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mall (kampanj)</td>
                  <td>Kampanjmall</td>
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
                  <td>Campaign</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
            </table>

## Filter

Efter logisk status (byLogicalStatus)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>läge</td>
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

Efter period (efter period)

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
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Efter status (efter stat)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>läge</td>
    <td>uppräkning</td>
    </tr>
</table>

Inkludera kontinuerliga leveranser från en heterogen lista (withContinuous)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>boolesk</td>
    </tr>
</table>

Planerad för angiven period (perPlanering)

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

Presentera under angiven period (efter kalender)

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
