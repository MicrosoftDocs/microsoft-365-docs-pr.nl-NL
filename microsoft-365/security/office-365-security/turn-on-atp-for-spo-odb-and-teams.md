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
description: Beheerders kunnen leren hoe ze Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in kunnen zetten, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 300cb3e004010e8ff22de7393d3f3e039bf8cfdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921142"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen onbedoeld delen van schadelijke bestanden. Zie Veilige bijlagen voor [SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)voor meer informatie.

Dit artikel bevat de stappen voor het in- en configureren van veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de **pagina Veilige bijlagen van ATP** wilt gaan, opent u <https://protection.office.com/safeattachmentv2> .

- Als u Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams wilt  in-  en uit te zetten, moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- & Compliancecentrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- Als u SharePoint Online PowerShell wilt gebruiken om te voorkomen dat [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) personen schadelijke bestanden downloaden, moet u lid zijn van de rollen globale beheerder of [SharePoint-beheerder](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.

- Controleer of auditregistratie is ingeschakeld voor uw organisatie. Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

- Laat de instellingen maximaal 30 minuten van kracht worden.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Stap 1: Gebruik het beveiligings- & compliancecentrum om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments** en klik op **Algemene instellingen.**

2. Ga in **de algemene** instellingen die worden weergegeven naar de instelling Defender in- en uitschakelen voor **Office 365 voor SharePoint, OneDrive en Microsoft Teams.** Verplaats de schakelknop naar rechts Om veilige bijlagen in te schakelen voor ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive en Microsoft Teams.

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Exchange Online PowerShell gebruiken om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams

Als u Liever PowerShell gebruikt om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams, maakt u verbinding met [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en voer u de volgende opdracht uit:

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

U kunt een waarschuwingsbeleid maken waarin u en andere beheerders worden gewaarschuwd wanneer met veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams een schadelijk bestand wordt gedetecteerd. Zie Activiteitswaarschuwingen maken in het beveiligings- & [compliancecentrum voor meer informatie over waarschuwingen.](../../compliance/create-activity-alerts.md)

1. Ga in [het & Compliancecentrum](https://protection.office.com)naar  \> **Waarschuwingenwaarschuwingsbeleid** of open <https://protection.office.com/alertpolicies> .

2. Klik op **de pagina Waarschuwingsbeleid** op **Nieuw waarschuwingsbeleid.**

3. De **wizard Nieuw waarschuwingsbeleid** wordt in een uitvliegende versie geopend. Configureer **op de pagina** Naam uw waarschuwing de volgende instellingen:

   - **Naam:** Typ een unieke en beschrijvende naam. Bijvoorbeeld schadelijke bestanden in bibliotheken.
   - **Beschrijving:** Typ een optionele beschrijving. Zo worden beheerders op de in SharePoint Online, OneDrive of Microsoft Teams gedetecteerde schadelijke bestanden op de website van de beheerder op de lijst geplaatst.
   - **Ernst:** Laat de standaardwaarde **Laag** geselecteerd of selecteer **Gemiddeld** of **Hoog.**
   - **Selecteer een categorie:** Selecteer **Bedreigingsbeheer.**

   Wanneer u klaar bent, klikt u op **Volgende.**

4. Configureer **op de pagina Waarschuwingsinstellingen** maken de volgende instellingen:

   - **Waar wilt u op waarschuwen?: Activiteit is:** Selecteer **Gedetecteerde malware in bestand.**
   - **Hoe wilt u dat de waarschuwing wordt geactiveerd?**: De standaardwaarde verlaten Telkens wanneer een **activiteit overeenkomt met de geselecteerde** regel.

   Wanneer u klaar bent, klikt u op **Volgende.**

5. Configureer op de pagina Uw **geadresseerden** instellen de volgende instellingen:

   - **E-mailmeldingen verzenden:** controleer of deze instelling is geselecteerd. Selecteer in het vak E-mailontvangers een of meer globale beheerders, beveiligingsbeheerders of **beveiligingslezers** die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.
   - **Dagelijkse meldingslimiet:** Laat de standaardwaarde **Geen limiet** geselecteerd.

   Wanneer u klaar bent, klikt u op **Volgende.**

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

- Als u wilt controleren of u veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams hebt ingeschakeld, gebruikt u een van de volgende stappen:

  - Ga in het [beveiligings- & compliancecentrum](https://protection.office.com)naar Atp Safe Attachments  voor bedreigingsbeleid , selecteer Globale instellingen en controleer de waarde van de instelling Defender in- en uitschakelen voor Office \>  \>  **365 voor SharePoint, OneDrive** en Microsoft Teams.

  - Voer in Exchange Online PowerShell de volgende opdracht uit om de eigenschapsinstelling te verifiëren:

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

- Gebruik het [rapport Bedreigingsbeveiliging om](view-email-security-reports.md#threat-protection-status-report) informatie weer te geven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft Teams. U kunt in het bijzonder de **weergave gegevens gebruiken op: de weergave \> Inhouds malware.**