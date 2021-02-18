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
description: Beheerders kunnen onder meer lezen hoe ze veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in kunnen stellen, inclusief het instellen van waarschuwingen voor gedetecteerde bestanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286367"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Met Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams wordt uw organisatie beschermd tegen het onbedoeld delen van schadelijke bestanden. Zie Veilige bijlagen voor [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)en Microsoft Teams voor meer informatie.

Dit artikel bevat de stappen voor het inschakelen en configureren van veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de pagina Veilige **bijlagen met ATP wilt** gaan, opent u <https://protection.office.com/safeattachmentv2> .

- Als u veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams wilt  in te  schakeln, moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- & Compliancecentrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- Als u SharePoint Online PowerShell wilt gebruiken om te voorkomen dat [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) personen schadelijke bestanden downloaden, moet u lid zijn van de rollen van de globale beheerder of [van SharePoint-beheerders](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.

- Controleer of auditlogregistratie is ingeschakeld voor uw organisatie. Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

- Het duurt maximaal 30 minuten voordat de instellingen van kracht worden.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Stap 1: Het beveiligings- & gebruiken om veilige bijlagen in te schakel voor SharePoint, OneDrive en Microsoft Teams

1. Ga in het & compliancecentrum naar  Veilige bijlagen van ATP voor risicobeheer en klik \>  \> op **Globale instellingen.**

2. In de **globale instellingen** die worden weergegeven, gaat u naar de instelling Defender voor **Office 365 voor SharePoint, OneDrive** en Microsoft Teams in bedrijf nemen. Zet de schakelaar naar rechts om Veilige bijlagen in te schakelen voor ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive en Microsoft Teams.

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Exchange Online PowerShell gebruiken om veilige bijlagen in te zetten voor SharePoint, OneDrive en Microsoft Teams

Als u liever PowerShell gebruikt om veilige bijlagen in te voeren voor SharePoint, OneDrive en Microsoft Teams, maakt u verbinding met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en voer u de volgende opdracht uit:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Zie [Set-AtpPolicyForO365 voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)syntaxis- en parameterinformatie.

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Stap 2: (Aanbevolen) Gebruik SharePoint Online PowerShell om te voorkomen dat gebruikers schadelijke bestanden downloaden

Standaard kunnen gebruikers geen schadelijke bestanden openen, verplaatsen, kopiëren of delen die door ATP worden gedetecteerd. Ze kunnen echter wel schadelijke bestanden verwijderen en downloaden.

Als u wilt voorkomen dat gebruikers schadelijke bestanden downloaden, maakt u [verbinding met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voer u de volgende opdracht uit:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Opmerkingen**:

- Deze instelling is van invloed op zowel gebruikers als beheerders.
- Schadelijke bestanden kunnen nog steeds worden verwijderd.

Zie [Set-SPOTenant voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Stap 3 (aanbevolen) Gebruik het beveiligings- & voor het maken van een waarschuwingsbeleid voor gedetecteerde bestanden

U kunt een waarschuwingsbeleid maken dat u en andere beheerders waarschuwt wanneer met veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams een schadelijk bestand wordt gedetecteerd. Zie Activiteitswaarschuwingen maken in het beveiligings- & compliancecentrum voor meer [informatie over waarschuwingen.](../../compliance/create-activity-alerts.md)

1. Ga in [het & Compliancecentrum](https://protection.office.com)naar **Waarschuwingsbeleid** \> **voor** waarschuwingen of <https://protection.office.com/alertpolicies> open.

2. Klik op **de pagina Waarschuwingsbeleid** op **Nieuw waarschuwingsbeleid.**

3. De **wizard Nieuw waarschuwingsbeleid** wordt in een fly out geopend. Configureer **de volgende instellingen op de** pagina Uw waarschuwing een naam geven:

   - **Naam:** typ een unieke en beschrijvende naam. Bijvoorbeeld schadelijke bestanden in bibliotheken.
   - **Beschrijving:** typ een optionele beschrijving. Beheerders krijgen bijvoorbeeld een e-mail wanneer er schadelijke bestanden worden aangetroffen in SharePoint Online, OneDrive of Microsoft Teams.
   - **Ernst:** laat de standaardwaarde **Laag** geselecteerd of selecteer **Normaal** of **Hoog.**
   - **Selecteer een categorie:** **Risicobeheer selecteren.**

   Klik op Volgende wanneer u klaar **bent.**

4. Configureer **de volgende instellingen op** de pagina Waarschuwingsinstellingen maken:

   - **Waarvoor wilt u een waarschuwing ontvangen?: Activiteit is:** Selecteer **Gedetecteerde malware in bestand.**
   - **Hoe wilt u dat de waarschuwing wordt geactiveerd?**: Laat de standaardwaarde staan telkens wanneer een **activiteit overeenkomt met de geselecteerde** regel.

   Klik op Volgende wanneer u klaar **bent.**

5. Configureer **de volgende instellingen op de** pagina Geadresseerden instellen:

   - **E-mailmeldingen verzenden:** controleer of deze instelling is geselecteerd. Selecteer in het vak E-mailontvangers een of meer globale beheerders, beveiligingsbeheerders of **beveiligingslezers** die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.
   - **Dagelijkse meldingslimiet:** laat de standaardwaarde **Geen limiet** geselecteerd.

   Klik op Volgende wanneer u klaar **bent.**

6. Controleer **de instellingen op de pagina** Uw instellingen en klik in een van de secties op Bewerken om wijzigingen aan te brengen. 

   In de sectie Wilt u het beleid meteen in ingeschakeld **laten?** Laat de standaardwaarde **Ja, schakel** deze meteen in.

   Klik op Voltooien wanneer u **klaar bent.**

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Beveiligings- & PowerShell gebruiken om een waarschuwingsbeleid te maken voor gedetecteerde bestanden

Als u liever PowerShell gebruikt om hetzelfde waarschuwingsbeleid te maken als in de vorige sectie is beschreven, maakt u verbinding met [security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) en voer u de volgende opdracht uit:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Opmerking:** de _standaardwaarde Ernst_ is laag. Als u normaal of hoog wilt opgeven, moet u de parameter _Ernst_ en de waarde opnemen in de opdracht.

Zie [New-ActivityAlert voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

- Als u wilt controleren of veilige bijlagen zijn ingeschakeld voor SharePoint, OneDrive en Microsoft Teams, gebruikt u een van de volgende stappen:

  - Ga in het [& Compliancecentrum](https://protection.office.com)voor  beveiligingsinstellingen naar Veilige bijlagen van ATP-beleid voor bedreigingsbeheer, selecteer algemene instellingen en controleer de waarde van de instelling Defender voor \>  \>  **Office 365 voor SharePoint, OneDrive** en Microsoft Teams in te stellen.

  - Voer in Exchange Online PowerShell de volgende opdracht uit om de eigenschapsinstelling te controleren:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parameterinformatie.

- Als u wilt controleren of het downloaden van schadelijke bestanden door personen is geblokkeerd, opent u SharePoint Online PowerShell en voer u de volgende opdracht uit om de waarde van de eigenschap te controleren:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Zie [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)voor gedetailleerde syntaxis- en parameterinformatie.

- Als u wilt controleren of u een waarschuwingsbeleid voor gedetecteerde bestanden hebt geconfigureerd, gebruikt u een van de volgende stappen:

  - Ga in het & Compliancecentrum naar  Het beleid voor waarschuwingenwaarschuwingen selecteer het waarschuwingsbeleid \>  \> en controleer de instellingen.

  - Vervang in & Compliancecentrum PowerShell de naam van het waarschuwingsbeleid, voer de volgende opdracht uit en controleer \<AlertPolicyName\> de eigenschapswaarden:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Zie [Get-ActivityAlert voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)

- Gebruik het [statusrapport Risicobeveiliging om](view-email-security-reports.md#threat-protection-status-report) informatie weer te geven over gedetecteerde bestanden in SharePoint, OneDrive en Microsoft Teams. U kunt de weergavegegevens gebruiken **op: de weergave \> Malware** van inhoud.
