---
title: Office 365 ATP inschakelen - SharePoint, OneDrive, & Teams
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
description: Meer informatie over het inschakelen van ATP voor SharePoint, OneDrive en Teams, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7708697f191107176173f2bfaced576c024954c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036726"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.

[Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) beschermt uw organisatie tegen het per ongeluk delen van schadelijke bestanden. Wanneer een kwaadaardig bestand wordt gedetecteerd, wordt dat bestand geblokkeerd, zodat niemand het kan openen, kopiëren, verplaatsen of delen totdat verdere acties zijn uitgevoerd door het beveiligingsteam van de organisatie. Lees dit artikel om ATP in te schakelen voor SharePoint, OneDrive en Teams, stel waarschuwingen in om op de hoogte te worden gesteld van gedetecteerde bestanden en vervolgstappen uit te voeren.

Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

|Rol|Waar/hoe toegewezen|
|---------|---------|
|globale beheerder|De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organisatiebeheer|Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen

**Controleer voordat u met deze procedure begint of de controlelogboekregistratie al is ingeschakeld voor uw Microsoft 365-omgeving.** Dit wordt meestal gedaan door iemand die de rol Controlelogboeken heeft toegewezen in Exchange Online. Zie [Zoeken in het controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

1. Ga [https://protection.office.com](https://protection.office.com)naar en meld je aan met je werk- of schoolaccount.

2. Kies in het beveiligingscentrum & compliance in het linkernavigatiedeelvenster onder \> **Bedreigingsbeheer**de optie Veilige **bijlagen** **beleid** .

   ![Kies in het Security & \> Compliance Center het beleid voor bedreigingsbeheer](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.

   ![Geavanceerde bedreigingsbeveiliging inschakelen voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Klik op **Opslaan**.

5. Bekijk (en bewerk, indien van toepassing, het [beleid voor veilige bijlagen van](set-up-atp-safe-attachments-policies.md) uw organisatie en het beleid voor veilige [koppelingen](set-up-atp-safe-links-policies.md).

6. (Aanbevolen) Voer als globale beheerder of SharePoint Online-beheerder de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter _DisallowInfectedFileDownload_ ingesteld op *true.*

   - Als u de parameter instelt op *true* blokkeert alle acties (behalve Delete) voor gedetecteerde bestanden. Mensen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.

   - Als u de parameter instelt op *valse* blokken, behalve Verwijderen en downloaden. Mensen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.

7. Geef u tot 30 minuten de tijd om uw wijzigingen te verspreiden naar alle Microsoft 365-datacenters.

8. (Aanbevolen) Ga over tot het instellen van waarschuwingen voor gedetecteerde bestanden.

Zie [Microsoft 365 beheren met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)voor meer informatie over het gebruik van PowerShell met Microsoft 365.

Zie Wat moet u doen wanneer een kwaadaardig bestand [wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als kwaadaardig wordt gedetecteerd.

## <a name="set-up-alerts-for-detected-files"></a>Waarschuwingen instellen voor gedetecteerde bestanden

Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als kwaadaardig is geïdentificeerd, u een waarschuwing instellen.

1. Kies **waarschuwingen** \> beheren **van waarschuwingen**in het [beveiligingscentrum & Compliance Center](https://protection.office.com).

2. Kies **Nieuw waarschuwingsbeleid**.

3. Geef een naam op voor de waarschuwing. U bijvoorbeeld schadelijke bestanden typen in bibliotheken.

4. Typ een beschrijving voor de waarschuwing. U bijvoorbeeld Beheerders op de hoogte brengen wanneer schadelijke bestanden worden gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.

5. Ga in de sectie **Deze waarschuwing verzenden wanneer...** het volgende doet:

   a. Kies **gedetecteerde malware in bestand in**de lijst **Activiteiten.**

   b. Laat het veld **Gebruikers** leeg.

6. Selecteer in de sectie **Deze waarschuwing verzenden naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligingslezers die een melding moeten ontvangen wanneer een kwaadaardig bestand wordt gedetecteerd.

7. Klik op **Opslaan**.

Zie [Activiteitswaarschuwingen maken in het Security & Compliance Center](../../compliance/create-activity-alerts.md)voor meer informatie over waarschuwingen.

## <a name="next-steps"></a>Volgende stappen

1. [Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

2. [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
