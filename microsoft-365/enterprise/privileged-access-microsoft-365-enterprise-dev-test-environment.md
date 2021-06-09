---
title: Bevoorrecht toegangsbeheer voor uw Microsoft 365 voor bedrijfstestomgeving
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
description: Gebruik deze testlaboratoriumhandleiding om bevoorrecht toegangsbeheer in te Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126415"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Bevoorrecht toegangsbeheer voor uw Microsoft 365 voor bedrijfstestomgeving

*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*

In dit artikel wordt beschreven hoe u bevoorrecht toegangsbeheer configureert om de beveiliging in uw Microsoft 365 voor ondernemingstestomgeving te verhogen.

Het configureren van priviledged access management bestaat uit drie fasen:
- [Fase 1: uw Microsoft 365 voor bedrijfstestomgeving](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Bevoorrecht toegangsbeheer configureren](#phase-2-configure-privileged-access-management)
- [Fase 3: controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 voor bedrijfstestomgeving

Als u het beheer van geprivilegieerde toegang op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u bevoorrecht toegangsbeheer wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Voor het testen van bevoorrecht toegangsbeheer is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een Active Directory Domain Services-forest. Het is hier beschikbaar als een optie, zodat u het beheer van geprivilegieerde toegang kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Bevoorrecht toegangsbeheer configureren

Configureer in deze fase een groep goedkeurders en schakel geprivilegieerde toegangsbeheer in voor uw Microsoft 365 voor bedrijfstestomgeving. Zie Geprivilegieerd toegangsbeheer voor meer informatie en een overzicht van bevoorrecht [toegangsbeheer.](../compliance/privileged-access-management-overview.md)

Als u geprivilegieerde toegang in uw organisatie wilt instellen en gebruiken, voert u de volgende stappen uit.

#### <a name="step-1-create-an-approvers-group"></a>[Stap 1: De groep van een goedkeurder maken](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Voordat u bevoorrechte toegang gaat gebruiken, bepaalt u wie de goedkeuringsinstantie heeft voor inkomende aanvragen voor toegang tot verhoogde en bevoorrechte taken. Alle gebruikers die deel uitmaken van de groep Goedkeurders kunnen toegangsaanvragen goedkeuren. Als u bevoorrechte toegang wilt gebruiken, moet u een beveiligingsgroep met e-mail maken in Microsoft 365. Geef in uw testomgeving de nieuwe beveiligingsgroep de naam 'Privileged Access Approvers' en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere testlaboratorstappen.

#### <a name="step-2-enable-privileged-access"></a>[Stap 2: Geprivilegieerde toegang inschakelen](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Geprivilegieerde toegang moet expliciet worden ingeschakeld in Microsoft 365 met de standaardgroep voor goedkeurder en moet een set systeemaccounts bevatten die u wilt uitsluiten van het besturingselement toegangsbeheer voor bevoorrechte toegang. Zorg ervoor dat u geprivilegieerde toegang in uw organisatie inschakelen voordat u fase 3 van deze handleiding start.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: controleren of goedkeuring vereist is voor verhoogde en bevoorrechte taken

Controleer in deze fase of het beleid voor geprivilegieerde toegang werkt en dat gebruikers goedkeuring nodig hebben om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Test de mogelijkheid om een taak uit te voeren DIE NIET is gedefinieerd in een beleid voor geprivilegieerde toegang

Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboekregel te maken. De [taak New-JournalRule](/powershell/module/exchange/new-journalrule) is momenteel niet gedefinieerd in een beleid voor geprivilegieerde toegang voor uw organisatie.

1. Open en meld u op uw lokale computer aan bij de Exchange Online Externe PowerShell-module bij **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell-module** met het globale beheeraccount voor uw testomgeving.

1. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Een nieuw beleid voor geprivilegieerde toegang maken voor de New-JournalRule taak

>[!NOTE]
>Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, moet u de stappen volgen om de groep van een goedkeurder met de naam 'Privilege Access Approvers' te maken om geprivilegieerde toegang in uw testomgeving in te stellen.

1. Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com) met referenties van het account Globale beheerder voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingen**  >  **beveiligingsinstellingen &**  >  **privacyprivilegetoegang.**

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer **Beleid configureren** en selecteer **vervolgens Beleid toevoegen.**

5. Selecteer of voer in de vervolgkeuzevelden de volgende waarden in:

    **Beleidstype**: Taak

    **Beleidsbereik:** Exchange

    **Beleidsnaam**: Nieuwe logboekregel

    **Goedkeuringstype**: Handmatig

    **Goedkeuringsgroep:** Privileged Access Approvers

6. Selecteer **Maken** en selecteer **vervolgens Sluiten.** Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld. Zorg ervoor dat het beleid volledig is ingeschakeld voordat u de goedkeuringsvereiste in de volgende stap test.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testgoedkeuringsvereiste voor New-JournalRule taak die is gedefinieerd in een beleid voor geprivilegieerde toegang

1. Open en meld u op uw lokale computer aan bij de externe PowerShell Exchange Online-module van **Microsoft Corporation** Microsoft Exchange Online  >  **Externe PowerShell-module** met behulp van het globale beheeraccount voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. De fout 'Onvoldoende machtigingen' weergeven in Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Toegang aanvragen om een nieuwe logboekregel te maken met de New-JournalRule taak

1. Meld u aan bij het [Microsoft 365 beheercentrum](https://admin.microsoft.com) met het account Globale beheerder voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingen**  >  **beveiligingsinstellingen &**  >  **privacyprivilegetoegang.**

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer **Nieuwe aanvraag.** Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:

    **Aanvraagtype**: Taak

    **Aanvraagbereik**: Exchange

    **Aanvraag voor**: Nieuwe logboekregel

    **Duur (uren)**: 2

    **Opmerkingen:** Machtigingen aanvragen voor het maken van een nieuwe logboekregel

5. Selecteer **Opslaan** en selecteer **vervolgens Sluiten.** Uw aanvraag wordt per e-mail naar de groep van de goedkeurder verzonden.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aanvraag voor geprivilegieerde toegang goedkeuren voor het maken van een nieuwe logboekregel

1. Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) met de referenties voor gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep 'Privileged Access Approvers' in uw testomgeving).

2. Ga in het beheercentrum naar **Instellingen**  >  **beveiligingsinstellingen &**  >  **privacyprivilegetoegang.**

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer de aanvraag in behandeling en selecteer goedkeuren om **toegang** te verlenen tot het account voor globale beheerders om een nieuwe logboekregel te maken. Het globale beheeraccount (de gebruiker die hier om verzoekt) ontvangt een e-mailbevestiging dat goedkeuring is verleend.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Test het maken van een nieuwe logboekregel met geprivilegieerde toegang die is goedgekeurd voor de New-JournalRule taak

1. Open en meld u op uw lokale computer aan bij de Exchange Online Externe PowerShell-module bij **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell-module** met het globale beheeraccount voor uw testomgeving.

1. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Bekijk dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

## <a name="next-step"></a>Volgende stap

Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)
