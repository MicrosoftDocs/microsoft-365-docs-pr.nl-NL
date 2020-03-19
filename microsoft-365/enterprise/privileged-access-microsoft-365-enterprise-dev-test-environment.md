---
title: Beheer van bevoorrechte toegang voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab Guide om mogelijk te maken dat uw Microsoft 365 Enterprise-testomgeving kan worden beheerd door bevoegde toegang.
ms.openlocfilehash: ce637b94333f088d25e479e61ad2a98176a2f7c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808414"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Beheer van bevoorrechte toegang voor uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel configureert u beheer van privileged access om de beveiliging in uw Microsoft 365 Enterprise-testomgeving te verhogen.

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u gewoon privileged access management op een lichtgewicht manier wilt configureren met de minimumvereisten, volg dan de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u beheer van bevoegde toegang wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Voor het testen van beheer van privileged access is niet de gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest. Het wordt hier als optie geleverd, zodat u privileged access management testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Beheer van privileged access configureren

In deze fase configureert u een groep met toekeurders en schakelt u privileged access-beheer in voor uw Microsoft 365 Enterprise-testomgeving. Zie Beheer voor toegang voor bevoegde toegang [in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)voor meer informatie en een overzicht van beheer met bevoorrechte toegang.

Voer de volgende stappen uit om bevoorrechte toegang in te stellen en te gebruiken in uw Office 365-organisatie:

- [Stap 1: De groep van een goedkeurder maken](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    Voordat u toegang tot bevoegdheden gaat gebruiken, bepaalt u wie goedkeuringsinstantie heeft voor binnenkomende verzoeken om toegang tot verhoogde en bevoorrechte taken. Elke gebruiker die deel uitmaakt van de groep van de Fiatrovers, kan toegangsverzoeken goedkeuren. Dit is ingeschakeld door een beveiligingsgroep met e-mail te maken in Office 365. Maak een nieuwe beveiligingsgroep met de naam 'Privileged Access-fiatteurs' in uw testomgeving en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere testlabhandleidingstappen.

- [Stap 2: Bevoorrechte toegang inschakelen](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    Bevoorrechte toegang moet expliciet worden ingeschakeld in Office 365 met de standaardgroep voor goedkeurende goedkeuring en met inbegrip van een reeks systeemaccounts die u wilt uitsluiten van het toegangscontrolebeheer voor bevoegde toegang. Zorg ervoor dat u bevoorrechte toegang in uw Office 365-organisatie inschakelt voordat u fase 3 van deze handleiding start.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken

In deze fase controleert u of het beleid voor bevoorrechte toegang werkt en vereisen gebruikers goedkeuring om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testvermogen om een taak uit te voeren die NIET is gedefinieerd in een beleid voor bevoorrechte toegang

Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboekregel te maken. De taak [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) is momenteel niet gedefinieerd in een beleid voor bevoorrechte toegang voor uw organisatie.

1. Open en meld u op uw lokale computer aan bij de Exchange Online Remote PowerShell Module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Een nieuw beleid voor bevoorrechte toegang maken voor de taak New-JournalRule

>[!NOTE]
>Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, voert u de stappen uit om de groep van een goedkeurder met de naam 'Privilege Access-approvers' te maken en bevoorrechte toegang in uw testomgeving in te schakelen.

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties het Account Globale beheerder voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingen** > **beveiliging & privacybevoorrechte** > **toegang**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren**.

4. Selecteer **Beleid configureren** en selecteer Een beleid **toevoegen**.

5. Selecteer of voer in de vervolgkeuzevelden de volgende waarden in:

    **Beleidstype**: Taak

    **Beleidsbereik**: Exchange

    **Beleidsnaam**: Nieuwe logboekregel

    **Goedkeuringstype**: Handleiding

    **Goedkeuringsgroep**: Privileged Access-bekeurders

6. Selecteer **Maken** en **sluit**. Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld. Zorg ervoor dat u de tijd voor het beleid volledig kan inschakelen voordat u de goedkeuringsvereiste in de volgende stap test.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testgoedkeuringsvereiste voor de taak New-JournalRule gedefinieerd in een beleid voor bevoorrechte toegang

1. Open en meld u op uw lokale computer aan bij de Exchange Online Remote PowerShell Module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

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

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Toegang aanvragen om een nieuwe logboekregel te maken met de taak New-JournalRule

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het Account Globale beheerder voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingen** > **beveiliging & privacybevoorrechte** > **toegang**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren**.

4. Selecteer **Nieuwe aanvraag**. Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:

    **Type aanvraag**: Taak

    **Aanvraagbereik**: Exchange

    **Verzoek om**: Nieuwe journaalregel

    **Duur (uren)**: 2

    **Commentaar**: Toestemming vragen om een nieuwe logboekregel te maken

5. Selecteer **Opslaan** en **sluit.** Uw verzoek wordt via e-mail naar de groep van de goedkeurder gestuurd.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aanvragen voor bevoorrechte toegang goedkeuren voor het maken van een nieuwe logboekregel

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep 'Bevoorrechte toegangs-approvers' in uw testomgeving).

2. Ga in het beheercentrum naar **Instellingen** > **beveiliging & privacybevoorrechte** > **toegang**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren**.

4. Selecteer het in behandeling zijnde verzoek en selecteer **Goedkeuren** om toegang te verlenen tot het account Globale beheerder om een nieuwe logboekregel te maken. Een e-mail met een melding waarin wordt bevestigd dat goedkeuring is verleend, wordt verzonden naar het Global Admin-account (de verzoekende gebruiker).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Een nieuwe logboekregel testen met bevoorrechte toegang die is goedgekeurd voor de taak New-JournalRule

1. Open en meld u op uw lokale computer aan bij de Exchange Online Remote PowerShell Module bij **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** met behulp van het Global Admin-account voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

## <a name="next-step"></a>Volgende stap

Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
