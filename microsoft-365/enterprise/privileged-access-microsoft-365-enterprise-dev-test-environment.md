---
title: Privileged access management for your Microsoft 365 for enterprise test environment
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
description: Gebruik deze Test Lab Guide om bevoorrechte toegangsbeheer mogelijk te maken voor uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126415"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Privileged access management for your Microsoft 365 for enterprise test environment

*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 voor Enterprise- als Office 365 Enterprise-testomgevingen.*

In dit artikel wordt beschreven hoe u een bevoorrecht toegangsbeheer configureert om de beveiliging te verhogen in uw Microsoft 365 voor bedrijfstestomgeving.

Bij het configureren van priviledged toegangsbeheer zijn drie fasen nodig:
- [Fase 1: De testomgeving van Microsoft 365 voor ondernemingen bouwen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Bevoorrecht toegangsbeheer configureren](#phase-2-configure-privileged-access-management)
- [Fase 3: Controleren of goedkeuring vereist is voor taken met verhoogde bevoegdheden en bevoegdheden](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Voor een visuele plattegrond van alle artikelen in de Test Lab Guide stack van Microsoft 365 voor ondernemingen gaat u naar [Microsoft 365 for Enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: De testomgeving van Microsoft 365 voor ondernemingen bouwen

Als u een bevoorrecht beheer van de toegang wilt configureren op een lichtgewicht manier met de minimale vereisten, volgt u de instructies in [de Basis basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u bevoorrechte toegangsbeheer wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass Through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Voor het testen van bevoorrechte toegangsbeheer is de gesimuleerde bedrijfstestomgeving niet vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een Active Directory Domain Services-forest. Deze optie is beschikbaar als een optie, zodat u het beheer van bevoorrechte toegang kunt testen en daarmee kunt experimenteren in een omgeving waarin een gewone organisatie wordt vertegenwoordigd.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Bevoorrecht toegangsbeheer configureren

Configureer in deze fase een goedkeurdersgroep en schakel bevoorrechte toegangsbeheer in voor uw Microsoft 365 voor bedrijfstestomgeving. Zie Privileged access management (Bevoorrechte toegangsbeheer) voor meer informatie en een overzicht [van bevoorrecht toegangsbeheer.](../compliance/privileged-access-management-overview.md)

Voer de volgende stappen uit om de toegankelijkheidsrechten in uw organisatie in te stellen en te gebruiken.

#### <a name="step-1-create-an-approvers-group"></a>[Stap 1: De groep goedkeurder maken](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Voordat u de bevoegde toegang gaat gebruiken, moet u bepalen wie goedkeuringsrechten heeft voor inkomende verzoeken voor toegang tot verhoogde en bevoorrechte taken. Alle gebruikers die deel uitmaken van de groep Goedkeurders kunnen toegangsaanvragen goedkeuren. Als u bevoegde toegang wilt gebruiken, moet u een beveiligingsgroep met e-mail maken in Microsoft 365. Geef in uw testomgeving de nieuwe beveiligingsgroep de naam 'Privileged Access Approvers' en voeg de 'Gebruiker 3' toe die eerder is gemaakt in eerdere test lab guide stappen.

#### <a name="step-2-enable-privileged-access"></a>[Stap 2: Bevoorrechte toegang inschakelen](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

De toegang met bepaalde bevoegdheden moet expliciet worden ingeschakeld in Microsoft 365 met de standaard goedkeurdergroep en moet een set systeemaccounts bevatten die u wilt uitsluiten van het toegangsbeheer voor toegang tot bevoorrechte toegang. Zorg ervoor dat u de bevoegde toegang in uw organisatie inschakelen voordat u fase 3 van deze handleiding start.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Controleren of goedkeuring vereist is voor taken met verhoogde bevoegdheden en bevoegdheden

In deze fase controleert u of het toegangsbeleid voor bepaalde bevoegdheden werkt en dat gebruikers goedkeuring moeten hebben om gedefinieerde verhoogde en bevoorrechte taken uit te voeren.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>De mogelijkheid testen om een taak uit te voeren DIE NIET is gedefinieerd in een bevoorrecht toegangsbeleid

Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die in uw testomgeving is geconfigureerd als globale beheerder en probeer een nieuwe logboekregel te maken. De [taak Nieuwe logboekregel](/powershell/module/exchange/new-journalrule) is momenteel niet gedefinieerd in een toegangsbeleid voor bepaalde bevoegdheden voor uw organisatie.

1. Open de externe PowerShell-module van **Microsoft Corporation** Microsoft Exchange Online op uw lokale computer en meld u aan bij de externe  >  **PowerShell-module** van Exchange Online met behulp van het hoofdbeheerdersaccount voor uw testomgeving.

1. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. U kunt zien dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Een nieuw toegangsbeleid voor de New-JournalRule maken

>[!NOTE]
>Als u de stappen 1 en 2 van fase 2 van deze handleiding nog niet hebt voltooid, moet u de stappen volgen om de groep goedkeurders met de naam Bevoegdheden voor toegangsrechten voor goedkeurders te maken om voor uw testomgeving bevoegde toegang te krijgen.

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met de referenties van het globale beheerdersaccount voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingenbeveiliging en**  >  **&**  >  **privacyprivilegetoegang.**

3. Selecteer **Toegangsbeleid en aanvragen beheren.**

4. Selecteer **Beleid configureren** en selecteer **vervolgens Beleid toevoegen.**

5. Selecteer of typ de volgende waarden in de vervolgkeuzevelden:

    **Beleidstype**: Taak

    **Beleidsbereik**: Exchange

    **Beleidsnaam:** Nieuwe logboekregel

    **Goedkeuringstype**: Handmatig

    **Goedkeuringsgroep:** Bevoegde goedkeurders voor toegang

6. Selecteer **Maken** en vervolgens **Sluiten.** Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld. Zorg ervoor dat u de tijd voor het beleid volledig heeft ingeschakeld voordat u in de volgende stap de goedkeuringsvereiste test.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Goedkeuringsvereiste testen voor de New-JournalRule die is gedefinieerd in een bevoorrecht toegangsbeleid

1. Open de externe PowerShell-module van Microsoft **Corporation** Microsoft Exchange Online op uw lokale computer en meld u aan bij de externe  >  **PowerShell-module** van Exchange Online met behulp van het account van de globale beheerder voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Bekijk de fout 'Onvoldoende machtigingen' in Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Toegang aanvragen om een nieuwe logboekregel te maken met New-JournalRule taak

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het globale beheerdersaccount voor uw testomgeving.

2. Ga in het beheercentrum naar **Instellingenbeveiliging en**  >  **&**  >  **privacyprivilegetoegang.**

3. Selecteer **Toegangsbeleid en aanvragen beheren.**

4. Selecteer **Nieuw verzoek.** Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:

    **Aanvraagtype**: Taak

    **Bereik van aanvraag**: Exchange

    **Aanvraag voor:** nieuwe logboekregel

    **Duur (uren)**: 2

    **Opmerkingen:** Machtiging aanvragen om een nieuwe logboekregel te maken

5. Selecteer **Opslaan** en selecteer vervolgens **Sluiten.** Uw aanvraag wordt per e-mail verzonden naar de groep goedkeurder.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Verzoek om toegang met bepaalde bevoegdheden goedkeuren voor het maken van een nieuwe logboekregel

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met de referenties voor Gebruiker 3 in uw testomgeving (lid van de beveiligingsgroep Bevoegde goedkeurders voor toegang in uw testomgeving).

2. Ga in het beheercentrum naar **Instellingenbeveiliging en**  >  **&**  >  **privacyprivilegetoegang.**

3. Selecteer **Toegangsbeleid en aanvragen beheren.**

4. Selecteer de aanvraag in behandeling en selecteer Vervolgens Goedkeuren **om** toegang te verlenen tot het account van de globale beheerder om een nieuwe logboekregel te maken. Het globale beheerdersaccount (de verzoekende gebruiker) ontvangt per e-mail een bevestiging dat goedkeuring is verleend.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Test het maken van een nieuwe logboekregel met bevoegde toegang goedgekeurd voor New-JournalRule taak

1. Open de externe PowerShell-module van **Microsoft Corporation** Microsoft Exchange Online op uw lokale computer en meld u aan bij de externe  >  **PowerShell-module** van Exchange Online met behulp van het hoofdbeheerdersaccount voor uw testomgeving.

1. Maak in Exchange Management PowerShell een nieuwe logboekregel voor uw organisatie:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. U kunt zien dat de nieuwe logboekregel is gemaakt in Exchange Management PowerShell.

## <a name="next-step"></a>Volgende stap

Bekijk aanvullende [functies en mogelijkheden](m365-enterprise-test-lab-guides.md#information-protection) voor gegevensbeveiliging in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)
