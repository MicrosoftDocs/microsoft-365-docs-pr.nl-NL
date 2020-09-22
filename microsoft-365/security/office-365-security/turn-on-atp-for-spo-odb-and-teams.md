---
title: Office 365 ATP-SharePoint, OneDrive, & teams inschakelen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Meer informatie over het inschakelen van ATP voor SharePoint, OneDrive en teams, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8c8d0f3caa3e717f8193a3c0d6b7bb1d40dab6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201589"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) beschermt uw organisatie per ongeluk om kwaadaardige bestanden te delen. Wanneer een schadelijk bestand wordt gevonden, wordt het bestand geblokkeerd, zodat niemand dit kan openen, kopiëren, verplaatsen of delen totdat verdere acties worden uitgevoerd door het beveiligingsteam van de organisatie. Lees dit artikel om ATP voor SharePoint, OneDrive en teams in te schakelen, waarschuwingsmeldingen in te stellen voor gedetecteerde bestanden en de volgende stappen uit te voeren.

Als u ATP-beleidsregels wilt definiëren (of bewerken), moet aan u de juiste rol zijn toegewezen. In de volgende tabel worden enkele voorbeelden beschreven:

****

|Rol|Where/hoe toegewezen|
|---|---|
|globale beheerder|De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Beheer van organisatie van Exchange Online|Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Voordat u met deze procedure begint, controleert u of logboekregistratie al is ingeschakeld voor uw Microsoft 365-omgeving**. Dit gebeurt meestal door iemand die de rol audit logboeken heeft toegewezen in Exchange Online. Zie [auditlogboek zoeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

1. Ga naar <https://protection.office.com> en meld u aan met uw werk-of schoolaccount.

2. Kies in het gedeelte beveiligings & compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleids** \> **veilige bijlagen**.

   ![Kies in het beveiligings & nalevings centrum de optie beleid voor Threat Management \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams**.

   ![Geavanceerde Bedreigingsbeveiliging inschakelen voor SharePoint Online, OneDrive voor bedrijven en Microsoft teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Klik op **Opslaan**.

5. Bekijk (en, indien nodig, bewerken) het beleid voor [veilige bijlagen](set-up-atp-safe-attachments-policies.md) van uw organisatie en het [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md).

6. Beter Als globale beheerder of een SharePoint Online-beheerder voert u de cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit waarbij de _DisallowInfectedFileDownload_ -parameter is ingesteld op *waar*.

   - Als u de parameter instelt op *True* , worden alle acties (met uitzondering van verwijderen) voor gedetecteerde bestanden geblokkeerd. Personen kunnen geen gevonden bestanden openen, verplaatsen, kopiëren of delen.

   - Als u de parameter instelt op *False* , worden alle acties geblokkeerd, behalve verwijderen en downloaden. Gebruikers kunnen ervoor kiezen het risico te accepteren en een gevonden bestand te downloaden.

7. Maximaal 30 minuten wachten tot de wijzigingen zijn doorgevoerd naar alle Microsoft 365-datacenters.

8. Beter Ga verder met het instellen van waarschuwingen voor gedetecteerde bestanden.

Zie [Microsoft 365 beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)voor meer informatie over het gebruik van PowerShell met microsoft 365.

Zie [wat u moet doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als schadelijk is gedetecteerd.

## <a name="set-up-alerts-for-detected-files"></a>Waarschuwingen instellen voor gedetecteerde bestanden

Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams is herkend als schadelijk, kunt u een melding instellen.

1. Kies in het [beveiligings & nalevings centrum](https://protection.office.com) **waarschuwingen** \> **beheren**.

2. Kies **Nieuw waarschuwings beleid**.

3. Geef een naam op voor de waarschuwing. U kunt bijvoorbeeld schadelijke bestanden in bibliotheken typen.

4. Typ een beschrijving voor de waarschuwing. U kunt bijvoorbeeld een melding van de beheerder doen wanneer er kwaadaardige bestanden zijn gevonden in SharePoint Online, OneDrive of Microsoft teams.

5. Voer de volgende handelingen uit in de sectie **deze melding verzenden wanneer...** :

   a. Kies in de lijst **activiteiten** de optie **malware gevonden in bestand**.

   b. Laat het veld **gebruikers** leeg.

6. Selecteer in de sectie **Deze waarschuwing verzenden naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligings lezers die een bericht moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.

7. Klik op **Opslaan**.

Zie voor meer informatie over waarschuwingen [activiteiten meldingen maken in het beveiligings & nalevings centrum](../../compliance/create-activity-alerts.md).

## <a name="next-steps"></a>Volgende stappen

1. [Informatie over schadelijke bestanden weergeven die zijn gevonden in SharePoint, OneDrive of Microsoft teams](malicious-files-detected-in-spo-odb-or-teams.md)

2. [In quarantaine geplaatste berichten en bestanden als beheerder beheren in Microsoft 365](manage-quarantined-messages-and-files.md)
