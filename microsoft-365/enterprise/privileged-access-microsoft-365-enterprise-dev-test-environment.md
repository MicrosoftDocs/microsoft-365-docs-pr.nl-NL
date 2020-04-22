---
title: Privileged access management voor uw Microsoft 365 Enterprise-testomgeving
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Gebruik deze Test Lab-handleiding om beheer van privileged access uw Microsoft 365 Enterprise-testomgeving in te schakelen.
ms.openlocfilehash: 27f63de138f388b0dcbc1bc896bafcb9abc9ed6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632861"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Privileged access management voor uw Microsoft 365 Enterprise-testomgeving

*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel configureert u beheer van bevoegde toegang om de beveiliging in uw Microsoft 365 Enterprise-testomgeving te verhogen.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen privileged access management op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u privileged access management in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Voor het testen van privileged access management is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest. Het wordt hier als optie aangeboden, zodat u privileged access management testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Privileged Access Management configureren

In deze fase configureert u een groep fiatteurs en schakelt u privileged access management in voor uw Microsoft 365 Enterprise-testomgeving. Zie Privileged access management in Office [365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)voor meer informatie en een overzicht van privileged access management.

Volg de volgende stappen voor het instellen en gebruiken van bevoorrechte toegang in uw organisatie:

- [Stap 1: De groep van een goedkeurder maken](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    Voordat u toegang tot bevoegdheden gaat gebruiken, bepaalt u wie de goedkeuringsinstantie heeft voor binnenkomende aanvragen voor toegang tot verhoogde en bevoorrechte taken. Elke gebruiker die deel uitmaakt van de groep Van de Fiatse goedkeurden, kan toegangsverzoeken goedkeuren. Dit wordt ingeschakeld door een beveiligingsgroep met e-mail te maken in Office 365. Maak een nieuwe beveiligingsgroep met de naam 'Voorkeurstoegangsgoeden' in uw testomgeving en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere testlabhandleidingstappen.

- [Stap 2: Bevoorrechte toegang inschakelen](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    Bevoegde toegang moet expliciet worden ingeschakeld in Office 365 met de standaardgroep voor goedgekeurde accounts en een set systeemaccounts die u wilt uitsluiten van het toegangsbeheer voor toegang met toegang tot toegang. Zorg ervoor dat u bevoorrechte toegang in uw organisatie inschakelt voordat u fase 3 van deze handleiding start.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken

In deze fase controleert u of het beleid voor bevoegde toegang werkt en dat gebruikers goedkeuring nodig hebben om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>De mogelijkheid testen om een taak uit te voeren die NIET is gedefinieerd in een beleid voor bevoegde toegang

Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe Journal-regel te maken. De taak [Nieuw-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) is momenteel niet gedefinieerd in een beleid voor bevoegde toegang voor uw organisatie.

1. Open op uw lokale computer de Exchange Online Remote PowerShell-module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe Journal-regel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Een nieuw toegangsbeleid voor bevoegde toegang maken voor de taak Nieuw-JournalRule

>[!NOTE]
>Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, moet u de stappen volgen om de groep van een goedkeurder met de naam 'Privilege Access-goedkeurders' te maken en bevoorrechte toegang in uw testomgeving in te schakelen.

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties het Global Admin-account voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingenbeveiliging** > & toegang tot**privacybevoegdheden** > **Privileged access**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren**.

4. Selecteer **Beleid configureren** en selecteer Een beleid **toevoegen**.

5. Selecteer of voer in de vervolgkeuzelijst de volgende waarden in:

    **Beleidstype**: Taak

    **Beleidsscope**: Uitwisseling

    **Beleidsnaam**: Nieuwe journaalregel

    **Goedkeuringstype**: Handleiding

    **Goedkeuringsgroep**: Fiatteurs met bevoorrechte toegang

6. Selecteer **Maken** en vervolgens **Sluiten**. Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld. Zorg ervoor dat u de tijd toestaat om het beleid volledig in te schakelen voordat u de goedkeuringsvereiste in de volgende stap test.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Goedkeuringsvereiste testen voor de taak Nieuw-JournalRule die is gedefinieerd in een beleid voor bevoorrechte toegang

1. Open op uw lokale computer de Exchange Online Remote PowerShell-module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van een account globale beheer voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe Journal-regel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Fout 'Onvoldoende machtigingen' weergeven in Exchange Management PowerShell:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Toegang aanvragen om een nieuwe journaalregel te maken met de taak Nieuw-JournalRule

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het global admin-account voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingenbeveiliging** > & toegang tot**privacybevoegdheden** > **Privileged access**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren**.

4. Selecteer **Nieuw verzoek**. Selecteer in de vervolgkeuzelijst de juiste waarden voor uw organisatie:

    **Aanvraagtype**: Taak

    **Aanvraagbereik**: Exchange

    **Aanvraag voor**: Nieuwe journaalregel

    **Duur (uren)**: 2

    **Opmerkingen**: Toestemming vragen om een nieuwe logboekregel te maken

5. Selecteer **Opslaan** en vervolgens **Sluiten**. Uw verzoek wordt via e-mail naar de groep van de goedkeurder gestuurd.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Voorkeurstoegangsaanvraag goedkeuren voor het maken van een nieuwe journaalregel

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep 'Bevoegde toegangs-approvers' in uw testomgeving).

2. Ga in het beheercentrum naar **Instellingenbeveiliging** > & toegang tot**privacybevoegdheden** > **Privileged access**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren**.

4. Selecteer de aanvraag in behandeling en selecteer **Goedkeuren** om toegang te verlenen tot het global admin-account om een nieuwe logboekregel te maken. Een e-mail met een melding waarin wordt bevestigd dat er goedkeuring is verleend, wordt verzonden naar het Global Admin-account (de verzoekende gebruiker).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Een nieuwe logboekregel maken met bevoorrechte toegang die is goedgekeurd voor de taak Nieuw-JournalRule

1. Open op uw lokale computer de Exchange Online Remote PowerShell-module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe Journal-regel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

## <a name="next-step"></a>Volgende stap

Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
