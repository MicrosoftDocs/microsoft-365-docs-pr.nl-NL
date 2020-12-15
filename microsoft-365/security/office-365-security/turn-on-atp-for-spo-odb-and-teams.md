---
title: Microsoft Defender voor Office 365 inschakelen-SharePoint, OneDrive, & teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
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
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682592"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft teams zorgt ervoor dat uw organisatie per ongeluk schadelijke bestanden deelt. Zie [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md)voor meer informatie.

Dit artikel bevat de stappen voor het inschakelen en configureren van ATP voor SharePoint, OneDrive en Microsoft teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de pagina met **veilige bijlage van ATP** wilt gaan, opent u deze <https://protection.office.com/safeattachmentv2> .

- Als u ATP wilt inschakelen voor SharePoint, OneDrive en Microsoft teams, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** in het beveiligings & compliance Center. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- Als u wilt voorkomen dat mensen schadelijke bestanden kunnen downloaden met SharePoint Online PowerShell, moet u lid zijn van de [globale beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) of [SharePoint-beheerders](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) rollen in azure AD.

- Controleer of de logboekregistratie van het controle is ingeschakeld voor uw organisatie. Zie [auditlogboek zoeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

- Maximaal 30 minuten toestaan voordat de instellingen van kracht worden.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Stap 1: gebruik het beveiligings & nalevings centrum om ATP voor SharePoint, OneDrive en Microsoft teams in te schakelen

1. Ga in het beveiligings & nalevings centrum naar veilige bijlagen voor het beleid voor **bedreigings beheer** \>  \> en klik op **globale instellingen**.

2. Ga in de **algemene instellingen** die worden weergegeven naar de instelling **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams** . Zet de wisselknop naar rechts om de ![ ](../../media/scc-toggle-on.png) ATP voor SharePoint, OneDrive en Microsoft teams in te schakelen.

   Wanneer u gereed bent, klikt u op **Opslaan**.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Gebruik Exchange Online PowerShell om ATP voor SharePoint, OneDrive en Microsoft teams in te schakelen

[Maak verbinding met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en voer de volgende opdracht uit als u liever PowerShell wilt gebruiken voor het inschakelen van ATP voor SharePoint, OneDrive en Microsoft teams:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Stap 2: (aanbevolen) SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden

Gebruikers kunnen standaard schadelijke bestanden die zijn gedetecteerd met ATP niet openen, verplaatsen, kopiëren of delen. Ze kunnen echter wel schadelijke bestanden verwijderen en downloaden.

Als u wilt voorkomen dat gebruikers schadelijke bestanden downloaden, [maakt u verbinding met de PowerShell van SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voert u de volgende opdracht uit:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Opmerkingen**:

- Deze instelling is van invloed op gebruikers en beheerders.
- Personen kunnen wel schadelijke bestanden verwijderen.

Zie [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Stap 3 (aanbevolen) gebruik het beveiligings & nalevings centrum voor het maken van een waarschuwings beleid voor gedetecteerde bestanden

U kunt een waarschuwings beleid maken waarmee u op de hoogte wordt gesteld van een kwaadaardige voor SharePoint, OneDrive en Microsoft teams. Zie voor meer informatie over waarschuwingen [activiteiten meldingen maken in het beveiligings & nalevings centrum](../../compliance/create-activity-alerts.md).

1. Ga in het [beveiligings & nalevings centrum](https://protection.office.com)naar  \> **waarschuwings beleid** voor meldingen of open <https://protection.office.com/alertpolicies> .

2. Klik op de pagina met **waarschuwings beleidsregels** op **Nieuw waarschuwings beleid**.

3. De wizard **Nieuw waarschuwings beleid** wordt in één vliegtuig geopend. Configureer de volgende instellingen op de pagina **naam van uw waarschuwing** :

   - **Naam**: Typ een unieke en een beschrijvende naam. Bijvoorbeeld Kwaadwillende bestanden in bibliotheken.
   - **Beschrijving**: Typ een optionele beschrijving. U kunt bijvoorbeeld beheerders een melding sturen wanneer er schadelijke bestanden zijn gevonden in SharePoint Online, OneDrive of Microsoft teams.
   - **Ernst**: Zorg dat de standaardwaarde **laag** is geselecteerd of selecteer **normaal** of **hoog**.
   - **Selecteer een categorie**: Selecteer **risicobeheer**.

   Wanneer u klaar bent, klikt u op **volgende**.

4. Configureer de volgende instellingen op de pagina instellingen voor het **maken van waarschuwingen** :

   - **Waarover wilt u een bericht doorvoeren?: activiteit is**: Selecteer **malware gedetecteerd in bestand**.
   - **Hoe wilt u dat de waarschuwing wordt geactiveerd?**: de standaardwaarde behouden **wanneer er een activiteit met de regel** is geselecteerd.

   Wanneer u klaar bent, klikt u op **volgende**.

5. Configureer de volgende instellingen op de pagina de **geadresseerden instellen** :

   - **E-mail meldingen verzenden**: Controleer deze optie is geselecteerd. Selecteer in het dialoogvenster **e-mail geadresseerden** een of meer globale beheerders, beveiligingsbeheerders of beveiligings lezers die een bericht moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.
   - **Daglimiet voor meldingen**: de standaardwaarde **hoeft niet** te zijn geselecteerd.

   Wanneer u klaar bent, klikt u op **volgende**.

6. Controleer de instellingen op de pagina **uw instellingen controleren** en klik in een van de secties op **bewerken** om wijzigingen door te voeren.

   Laat in het gedeelte **wilt u het beleid direct inschakelen?** de standaardwaarde **Ja, schakel deze optie aan de rechterkant** uit.

   Wanneer u klaar bent, klikt u op **Voltooien**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Beveiligings & naleving in PowerShell gebruiken voor het maken van een waarschuwings beleid voor gedetecteerde bestanden

Als u liever PowerShell gebruikt om hetzelfde waarschuwings beleid te maken zoals wordt beschreven in de vorige sectie, maakt u verbinding met de [beveiliging & nalevings centrum PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) en voert u de volgende opdracht uit:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Opmerking**: de standaardwaarde voor de _Ernst_ is laag. Als u gemiddeld of hoog wilt opgeven, voegt u de parameter voor de _Ernst_ en de waarde in de opdracht toe.

Zie [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

- Voer een van de volgende stappen uit om te controleren of u de ATP hebt ingeschakeld voor SharePoint, OneDrive en Microsoft teams:

  - Ga in het [beveiligings & compliance](https://protection.office.com)naar veilige bijlagen voor het beleid voor **risicobeheer** \>  \> , selecteer **globale instellingen** en controleer de waarde van de instelling **ATP voor SharePoint, OneDrive en Microsoft teams inschakelen** .

  - In Exchange Online PowerShell voert u de volgende opdracht uit om de instelling van de eigenschap te controleren:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.

- Als u wilt controleren of u bent geblokkeerd voor het downloaden van schadelijke bestanden, opent u SharePoint Online PowerShell en voert u de volgende opdracht uit om de waarde van de eigenschap te controleren:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Zie [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis-en parameterinformatie.

- Voer een van de volgende stappen uit om te controleren of u een waarschuwings beleid voor gedetecteerde bestanden hebt geconfigureerd:

  - Ga in het beveiligings & compliance naar waarschuwings beleid voor **waarschuwingen** , \>  \> Selecteer het waarschuwings beleid en controleer de instellingen.

  - In het beveiligings & nalevings centrum voor PowerShell, vervangt u de \<AlertPolicyName\> naam van het waarschuwings beleid, voert u de volgende opdracht uit en controleert u de eigenschapwaarden:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Zie [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)voor gedetailleerde syntaxis-en parameterinformatie.

- Met het [rapport status beveiliging](view-email-security-reports.md#threat-protection-status-report) kunt u informatie weergeven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft teams. Met name kunt u de weergave **gegevens weergeven op: \> schadelijke inhoud** gebruiken.
