---
title: Operators | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de operators in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 07/24/2017
ms.author: gregli
ms.openlocfilehash: 9dce0ac36cd16faaa9c8b9a0b34d15eff086ab2e
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="operators-and-data-types-in-powerapps"></a>Operators en gegevenstypen in PowerApps
Sommige van deze operators zijn afhankelijk van de taal van de auteur.  Zie [Global apps](../global-apps.md) voor meer informatie.

| Symbool | Type | Syntaxis | Beschrijving |
| --- | --- | --- | --- |
| **,** |Eigenschapselectie |**Slider1.Value<br>Color.Red<br>Acceleration.X** |Hiermee wordt een eigenschap opgehaald uit een [tabel](../working-with-tables.md), besturingselement, [signaal](signals.md) of opsomming.  Voor achterwaartse compatibiliteit kan ook **!** worden gebruikt. |
| **,**<br>[of **,** [afhankelijk van de taal](../global-apps.md)] |Decimaal scheidingsteken |**1.23**<br>[of **1,23**, afhankelijk van de taal] |Scheidingsteken tussen de hele en gedeeltelijke delen van een getal.  Het teken is afhankelijk van de taal. |
| **( )** |Haakjes |**Filter(T, A &lt; 10)**<br><br>**(1 + 2) * 3** |Dwingt een volgorde af en groepeert subexpressies in een grotere expressie |
| **+** |Rekenkundige operators |**1 + 2** |Optellen |
| **-** |&nbsp; |**2 - 1** |Aftrekken en ondertekenen |
| **\*** |&nbsp; |**2 * 3** |Vermenigvuldigen |
| **/** |&nbsp; |**2 / 3** |Delen (zie ook de functie **[Mod](function-mod.md)**) |
| **^** |&nbsp; |**2 ^ 3** |Machtsverheffing, vergelijkbaar met de functie **[Power](function-numericals.md)** |
| **%** |&nbsp; |**20%** |Percentage (vergelijkbaar met &quot;* 1/100&quot;) |
| **=** |Vergelijkingsoperators |**Prijs = 100** |Gelijk aan |
| **&gt;** |&nbsp; |**Prijs &gt; 100** |Groter dan |
| **&gt;=** |&nbsp; |**Prijs &gt;= 100** |Groter dan of gelijk aan |
| **&lt;** |&nbsp; |**Prijs &lt; 100** |Kleiner dan |
| **&lt;=** |&nbsp; |**Prijs &lt;= 100** |Kleiner dan of gelijk aan |
| **&lt;&gt;** |&nbsp; |**Prijs &lt;&gt; 100** |Niet gelijk aan |
| **&amp;** |Operator voor tekenreekssamenvoeging |**&quot;hello&quot; &amp; &quot; &quot; &amp; &quot;world&quot;** |Zorgt ervoor dat meerdere tekenreeksen continu worden weergegeven |
| **&amp;&amp;** of **And** |Logische operators |**Prijs &lt; 100 &amp;&amp; Slider1.Value = 20**<br>of **Prijs&lt; 100 And Slider1.Value = 20** |Logische combinatie, vergelijkbaar met de functie **[And](function-logicals.md)** |
| **&#124;&#124;** of **Or** |&nbsp; |**Price &lt; 100 &#124;&#124; Slider1.Value = 20** of **Price &lt; 100 Or Slider1.Value = 20** |Logische scheiding, vergelijkbaar met de functie **[Or](function-logicals.md)** |
| **!** of **Not** |&nbsp; |**!(Price &lt; 100)** of **Not (Price &lt; 100)** |Logische negatie, vergelijkbaar met de functie **[Not](function-logicals.md)** |
| **exactin** |[Lidmaatschapsoperators](#in-and-exactin-operators) |**Gallery1.Selected exactin SavedItems** |Hoort bij een [verzameling](../working-with-data-sources.md#collections) of tabel |
| **exactin** |&nbsp; |**&quot;Windows&quot; exactin “Om vensters weer te geven in het Windows-besturingssysteem...”** |Subtekenreekstest (hoofdlettergevoelig) |
| **in** |&nbsp; |**Gallery1.Selected in SavedItems** |Hoort bij een verzameling of tabel |
| **in** |&nbsp; |**&quot;De&quot; in &quot;Het toetsenbord en de monitor...&quot;** |Subtekenreekstest (niet hoofdlettergevoelig) |
| **@** |[Ondubbelzinnigheidsoperator](#disambiguation-operator) |**MyTable[@fieldname]** |Veldondubbelzinnigheid |
| **@** |&nbsp; |**[@MyVariable]** |Algemene ondubbelzinnigheid |
| **,**<br>[of **;** [afhankelijk van de taal](../global-apps.md)] |Lijstscheidingsteken |**If( X < 10, "Low", "Good" )**<br>**{ X: 12, Y: 32 }**<br>**[ 1, 2, 3 ]**<br>[of **If( X < 10; "Low"; "Good" )<br>{ FirstName: "Jane"; LastName: "Doe" }<br>[ 1; 2; 3 ]** ] |Scheidt: <ul><li>argumenten in functieaanroepen</li><li>velden in een [record](../working-with-tables.md#elements-of-a-table)</li><li>records in een [waardetabel](../working-with-tables.md#inline-syntax)</li></ul>.  Dit teken is afhankelijk van de taal. |
| **;**<br>[of **;;** [afhankelijk van de taal](../global-apps.md)] |Formulekoppeling |**Collect(T, A); Navigate(S1, &quot;&quot;)**<br>[of **Collect(T; A);; Navigate(S1; &quot;&quot;)**] |Afzonderlijke aanroepen van functies in de gedragseigenschappen.  De koppelingsoperator is afhankelijk van de taal. |
| **Bovenliggend** |[Parent-operator](#parent-operator) |**Parent.Fill** |Toegang tot de eigenschappen van een besturingselementcontainer |
| **ThisItem** |[ThisItem-operator](#thisitem-operator) |**ThisItem.FirstName** |Toegang tot de velden van het besturingselement Galerie of Formulier |

## <a name="in-and-exactin-operators"></a>De operators in en exactin
U kunt de operators **[in](operators.md#in-and-exactin-operators)** en **[exactin](operators.md#in-and-exactin-operators)** gebruiken om een tekenreeks te zoeken in een [gegevensbron](../working-with-data-sources.md), zoals een verzameling of een geïmporteerde tabel. Met de operator **[in](operators.md#in-and-exactin-operators)** zoekt u overeenkomsten, onafhankelijk van het gebruik van hoofdletters, en met de operator **[exactin](operators.md#in-and-exactin-operators)** worden overeenkomsten gezocht met precies hetzelfde hoofdlettergebruik. Hier volgt een voorbeeld:

1. Importeer of maak een verzameling met de naam **Inventory** en geef deze weer in een galerie, zoals wordt beschreven in de eerste procedure in [Tekst en afbeeldingen weergeven in een galerie](../show-images-text-gallery-sort-filter.md).
2. Stel de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op deze formule:
   <br>**Filter(Inventory, "E" in ProductName)**
   
    De galerie bevat alle producten behalve Callisto omdat de naam van dat product de enige naam is die niet de letter bevat die u hebt opgegeven.
3. Stel de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op deze formule:
   <br>**Filter(Inventory, "E" exactin ProductName)**
   
    In de galerie wordt alleen Europa weergegeven omdat dit de enige naam is die de letter bevat die u hebt opgegeven, met het opgegeven hoofdlettergebruik.

## <a name="thisitem-operator"></a>ThisItem-operator
U kunt gegevens in de besturingselementen **[Galerie](../controls/control-gallery.md)**, **[Formulier bewerken](../controls/control-form-detail.md)** en **[Weergaveformulier](../controls/control-form-detail.md)** weergeven door deze te binden aan een tabel of verzameling.  Deze besturingselementen vormen een container voor andere kaarten en besturingselementen.  Elke kaart en elk besturingselement in de container kan toegang verkrijgen tot de gebonden gegevens, namelijk via de operator **[ThisItem](operators.md#thisitem-operator)**.   

U gebruikt de operator **[ThisItem](operators.md#thisitem-operator)** om de gegevens[kolom](../working-with-tables.md#columns) op te geven die elke kaart of elk besturingselement bestuurt. De operator in de productgalerie voor [het weergeven van tekst en afbeeldingen in een galerie](../show-images-text-gallery-sort-filter.md) gaf bijvoorbeeld aan dat de afbeeldingsbesturingselement het productontwerp moest weergeven, het bovenste label de productnaam moest weergeven en het onderste label het aantal eenheden op voorraad moest weergeven.

Bij geneste galerieën verwijst **[ThisItem](operators.md#thisitem-operator)** naar de binnenste galerie-items. Ervan uitgaande dat de rijvelden in de binnenste en buitenste galerieën geen conflict veroorzaken, kunt u ook de namen van de niet-gekwalificeerde velden (kolommen( rechtstreeks gebruiken. Met deze aanpak staat u toe dat regels in een binnenste galerie verwijzen naar de items uit een buitenste galerie.

## <a name="parent-operator"></a>Parent-operator
Sommige besturingselementen fungeren als host voor andere besturingselementen. De besturingselementen **[Scherm](../controls/control-screen.md)**, **[Galerie](../controls/control-gallery.md)**, **[Kaart](../controls/control-card.md)**, **[Formulier bewerken](../controls/control-form-detail.md)** en **[Weergaveformulier](../controls/control-form-detail.md)** zijn bijvoorbeeld allemaal containers voor besturingselementen. Het besturingselement dat als host fungeert, wordt ook wel het 'bovenliggende' besturingselement genoemd.

Er kan op basis van naam naar alle besturingselementen in PowerApps worden verwezen, waar dan ook in de app. **Screen1** kan de naam zijn van een scherm in uw app. Als u de achtergrondkleur van dit scherm wilt ophalen, kunt u **Screen1.Fill** gebruiken.

Bij de besturingselementen op dit scherm is er nog een andere optie. Zij kunnen gebruikmaken van een relatieve verwijzing: **Parent.Fill**. De operator **[Parent](operators.md#parent-operator)** verwijst naar het besturingselement dat als host fungeert voor dit besturingselement, waardoor het beschikbaar wordt voor al diens eigenschappen. Het gebruik van **[Parent](operators.md#parent-operator)** is handig omdat deze operator niet afhankelijk is van de naam van het besturingselement. U kunt een containerbesturingselement kopiëren en plakken zonder dat u verwijzingen binnen container hoeft aan te passen. Met deze operator wordt de relatie tussen onder- en bovenliggende besturingselementen ook duidelijker bij het lezen van formules.

## <a name="disambiguation-operator"></a>Ondubbelzinnigheidsoperator
Sommige functies maken [recordbereiken](../working-with-tables.md#record-scope) voor toegang tot de velden van een tabel tijdens het verwerken van elke record, zoals **Filter**, **AddColumns** en **Sum**.  Veldnamen waarbij het recordbereik is toegevoegd, overschrijven dezelfde namen elders in de app.  Als dit gebeurt, kunt u nog steeds toegang krijgen tot waarden buiten het recordbereik met de operator voor ondubbelzinnigheid **@**:

* Als u toegang wilt krijgen tot waarden van geneste recordbereiken, gebruikt u de operator **@** met de naam van de tabel die wordt bewerkt met behulp van het patroon ***Tabel *[@* Veldnaam*]**.  
* Als u toegang wilt krijgen tot globale waarden, zoals gegevensbronnen, verzamelingen en contextvariabelen, gebruikt u het patroon **[@*Objectnaam*]** (zonder een tabelaanduiding).

Zie het gesprek over [recordbereik](../working-with-tables.md#record-scope) voor meer informatie en voorbeelden.

