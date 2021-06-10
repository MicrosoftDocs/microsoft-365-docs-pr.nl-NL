---
title: Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Beheerders kunnen leren hoe u Safe bijlagen in kunt SharePoint, OneDrive en Microsoft Teams, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 07aea9551faa280cd51bda1d57f017e0a24028ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204468"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen onbedoeld delen van schadelijke bestanden. Zie Bijlagen voor Safe bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

Dit artikel bevat de stappen voor het in- en configureren van Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de **pagina ATP-Safe bijlagen** wilt gaan, opent u <https://protection.office.com/safeattachmentv2> .

- Als u Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams wilt in- of uit te zetten, moet  u  lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- & Compliancecentrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- Als u SharePoint Online PowerShell wilt gebruiken om te voorkomen dat personen [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) schadelijke bestanden downloaden, moet u lid zijn van de hoofdbeheerder of SharePoint [beheerdersrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.

- Controleer of auditregistratie is ingeschakeld voor uw organisatie. Voor meer informatie, zie [Zoeken in auditlogboeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

- Laat de instellingen maximaal 30 minuten van kracht worden.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Stap 1: Gebruik het beveiligings- & compliancecentrum om Safe bijlagen in te SharePoint, OneDrive en Microsoft Teams

1. Ga in het & Compliancecentrum naar  \>  \> **ATP-Safe** Bijlagen voor bedreigingsbeleid en klik op **Algemene instellingen.**

2. Ga in **de algemene** instellingen die worden weergegeven naar de instelling Defender in Office 365 **voor SharePoint, OneDrive en Microsoft Teams** in. De schakelknop naar rechts verplaatsen Schakel de schakelknop in om Safe bijlagen in te schakelen voor ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive en Microsoft Teams.

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Gebruik Exchange Online PowerShell om Safe bijlagen in te SharePoint, OneDrive en Microsoft Teams

Als u Liever PowerShell gebruikt om Safe-bijlagen in te SharePoint, OneDrive en Microsoft Teams, maakt u verbinding met [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en voer u de volgende opdracht uit:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Stap 2: (Aanbevolen) Gebruik SharePoint Online PowerShell om te voorkomen dat gebruikers schadelijke bestanden downloaden

Gebruikers kunnen schadelijke bestanden die door ATP worden gedetecteerd, standaard niet openen, verplaatsen, kopiëren of delen. Ze kunnen echter schadelijke bestanden verwijderen en downloaden.

Als u wilt voorkomen dat gebruikers schadelijke bestanden downloaden, maakt u [verbinding met SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voer u de volgende opdracht uit:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Opmerkingen**:

- Deze instelling is van invloed op zowel gebruikers als beheerders.
- Personen kunnen nog steeds schadelijke bestanden verwijderen.

Zie [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Stap 3 (Aanbevolen) Gebruik het beveiligings- & compliancecentrum om een waarschuwingsbeleid te maken voor gedetecteerde bestanden

U kunt een waarschuwingsbeleid maken waarin u en andere beheerders worden gewaarschuwd wanneer Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams een schadelijk bestand detecteert. Zie Activiteitswaarschuwingen maken in het beveiligings- & [compliancecentrum voor meer informatie over waarschuwingen.](../../compliance/create-activity-alerts.md)

1. Ga in [het & Compliancecentrum](https://protection.office.com)naar  \> **Waarschuwingenwaarschuwingsbeleid** of open <https://protection.office.com/alertpolicies> .

2. Klik op **de pagina Waarschuwingsbeleid** op **Nieuw waarschuwingsbeleid.**

3. De **wizard Nieuw waarschuwingsbeleid** wordt in een uitvliegende versie geopend. Configureer **op de pagina** Naam uw waarschuwing de volgende instellingen:

   - **Naam:** Typ een unieke en beschrijvende naam. Bijvoorbeeld schadelijke bestanden in bibliotheken.
   - **Beschrijving:** Typ een optionele beschrijving. Beheerders worden bijvoorbeeld op de SharePoint, OneDrive of Microsoft Teams.
   - **Ernst:** Laat de standaardwaarde **Laag** geselecteerd of selecteer **Gemiddeld** of **Hoog.**
   - **Selecteer een categorie:** Selecteer **Bedreigingsbeheer.**

   Wanneer u gereed bent, klikt u op **Volgende**.

4. Configureer **op de pagina Waarschuwingsinstellingen** maken de volgende instellingen:

   - **Waar wilt u op waarschuwen?: Activiteit is:** Selecteer **Gedetecteerde malware in bestand.**
   - **Hoe wilt u dat de waarschuwing wordt geactiveerd?**: De standaardwaarde verlaten Telkens wanneer een **activiteit overeenkomt met de geselecteerde** regel.

   Wanneer u gereed bent, klikt u op **Volgende**.

5. Configureer op de pagina Uw **geadresseerden** instellen de volgende instellingen:

   - **E-mailmeldingen verzenden:** controleer of deze instelling is geselecteerd. Selecteer in het vak E-mailontvangers een of meer globale beheerders, beveiligingsbeheerders of **beveiligingslezers** die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.
   - **Dagelijkse meldingslimiet:** Laat de standaardwaarde **Geen limiet** geselecteerd.

   Wanneer u gereed bent, klikt u op **Volgende**.

6. Controleer op **de pagina** Uw instellingen controleren de instellingen en klik op **Bewerken** in een van de secties om wijzigingen aan te brengen.

   Laat in **de sectie Wilt** u het beleid meteen in- of uit? de standaardwaarde **Ja,** schakel het direct ingeschakeld in.

   Wanneer u klaar bent, klikt u op **Voltooien.**

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Beveiligingsbeleid & Compliance PowerShell gebruiken om een waarschuwingsbeleid te maken voor gedetecteerde bestanden

Als u Liever PowerShell gebruikt om hetzelfde waarschuwingsbeleid te maken als in de vorige sectie, maakt u verbinding met [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) en voer u de volgende opdracht uit:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Opmerking:** De _standaardwaarde Ernst_ is laag. Als u Gemiddeld of Hoog wilt opgeven, moet u de parameter _Ernst_ en de waarde in de opdracht opnemen.

Zie [New-ActivityAlert](/powershell/module/exchange/new-activityalert)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

- Als u wilt controleren of u Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams hebt ingeschakeld, gebruikt u een van de volgende stappen:

  - Ga in het [Beveiligings- & Compliancecentrum](https://protection.office.com)naar ATP Safe Bijlagen voor  \>  \> **bedreigingsbeleid**, selecteer Globale instellingen en controleer de waarde van de instelling Defender in Office 365 voor **SharePoint, OneDrive** en Microsoft Teams.

  - Voer Exchange Online PowerShell de volgende opdracht uit om de eigenschapsinstelling te verifiëren:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Zie [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.

- Als u wilt controleren of u personen hebt geblokkeerd om schadelijke bestanden te downloaden, opent u SharePoint Online PowerShell en voer u de volgende opdracht uit om de eigenschapswaarde te verifiëren:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Zie [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis- en parametergegevens.

- Als u wilt controleren of u een waarschuwingsbeleid voor gedetecteerde bestanden hebt geconfigureerd, gebruikt u een van de volgende stappen:

  - Ga in & Beveiligingscentrum naar Waarschuwingenwaarschuwingsbeleid selecteer het waarschuwingsbeleid  \>  \> en controleer de instellingen.

  - Vervang in & PowerShell van het beveiligingscentrum de naam van het waarschuwingsbeleid, voer de volgende opdracht uit en controleer \<AlertPolicyName\> de eigenschapswaarden:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Zie [Get-ActivityAlert](/powershell/module/exchange/get-activityalert)voor gedetailleerde syntaxis- en parametergegevens.

- Gebruik het [rapport Bedreigingsbeveiligingsstatus](view-email-security-reports.md#threat-protection-status-report) om informatie weer te geven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft Teams. U kunt in het bijzonder de **weergave gegevens gebruiken op: de weergave \> Inhouds malware.**