---
title: Beleid ter preventie van gegevensverlies (DLP) beheren | Microsoft Docs
description: Overzicht van het beheren van het beleid ter preventie van gegevensverlies voor PowerApps.
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 158abc3969090e081df41b6b52036d71b6949150
ms.sourcegitcommit: f236364ecb06dd86244cd9a607c31e0d716912e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/22/2018
---
# <a name="manage-data-loss-prevention-dlp-policies"></a>Beleid ter preventie van gegevensverlies (DLP) beheren
De gegevens van een organisatie zijn essentieel om succes te behalen. Gegevens moeten dus te allen tijde beschikbaar zijn om beslissingen te kunnen nemen, maar ze moeten ook worden beveiligd zodat ze niet worden gedeeld met doelgroepen die er geen toegang toe zouden mogen hebben. U kunt hiertoe in PowerApps een beleid ter preventie van gegevensverlies (DLP) instellen waarmee wordt bepaald met welke consumentenconnectors zakelijke gegevens mogen worden gedeeld. Een organisatie die gebruikmaakt van PowerApps wil bijvoorbeeld niet dat de zakelijke gegevens uit SharePoint automatisch worden gepubliceerd op Twitter.

Om DLP-beleid te maken, bewerken of verwijderen moet u gemachtigd zijn als omgevingsbeheerder of als tenantbeheerder voor Azure Active Directory. Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie.

Zie [Snelstartgids: een beleid ter preventie van gegevensverlies (DLP) maken](create-dlp-policy.md) voor instructies over het maken van een DLP-beleid.

## <a name="find-a-dlp-policy"></a>Een DLP-beleid zoeken
1. Meld u aan bij het beheercentrum op [https://admin.powerapps.com]([https://admin.powerapps.com).
2. Tik of klik in het navigatiedeelvenster op **Gegevensbeleid**. Als u een lange lijst met beleidsregels hebt, zoekt u het gewenste DLP-beleid via het vak **Zoeken**.

    ![](./media/prevent-data-loss/data-policies.png)

## <a name="edit-a-dlp-policy"></a>Een DLP-beleid bewerken
1. Klik of tik in de lijst met beleidsregels op het potloodpictogram naast het beleid dat u wilt bewerken.

    ![Aanmelden](./media/prevent-data-loss/3.png)
2. Breng de wijzigingen aan en klik of tik op **Beleid opslaan**.

    > [!NOTE]
    > DLP-beleid voor omgevingen kan tenant-breed DLP-beleid niet overschrijven.
    >
    >

    Als u de wijzigingen wilt bekijken, zoekt u het DLP-beleid in de lijst met beleidsregels en klikt of tikt u op het beleid om de bijbehorende eigenschappen te bekijken.

## <a name="delete-a-dlp-policy"></a>Een DLP-beleid verwijderen
1. Klik of tik in de lijst met beleidsregels op het prullenbakpictogram naast het beleid dat u wilt verwijderen.

    ![Aanmelden](./media/prevent-data-loss/3-delete.png)
4. Klik of tik in het bevestigingsdialoogvenster op **Verwijderen**.

    Het beleid wordt verwijderd en wordt niet meer weergegeven in de lijst met beleidsregels ter preventie van gegevensverlies.

## <a name="next-steps"></a>Volgende stappen
* [Meer informatie over omgevingen](environments-administration.md)
* [Meer informatie over Microsoft PowerApps](../maker/canvas-apps/getting-started.md)
