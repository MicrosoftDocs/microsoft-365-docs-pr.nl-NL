---
title: Toegangsbeheer met toegangsrechten voor uw testomgeving Microsoft 365 for Enterprise
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
description: Gebruik deze test lab-handleiding om het toegangsbeheer voor uw Microsoft 365 voor Enterprise testomgeving in te schakelen.
ms.openlocfilehash: d8d92aa86076e323e4b5bb5c8eb1385edcac420c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545940"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Toegangsbeheer met toegangsrechten voor uw testomgeving Microsoft 365 for Enterprise

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Aan de hand van de instructies in dit artikel configureert u het toegangsbeheer om het beveiligingsniveau van uw Microsoft 365 voor Enterprise testomgeving te verbeteren.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen een eenvoudig toegangsbeheer wilt configureren met de minimale vereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u het toegangsbeheer voor bevoegdheden in een gesimuleerde onderneming wilt configureren, volgt u de instructies in de [verificatie](pass-through-auth-m365-ent-test-environment.md)procedure.
  
>[!NOTE]
>Voor het testen van het toegangsbeheer is het niet mogelijk de gesimuleerde Enterprise testomgeving te gebruiken, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een AD DS-forest. Dit wordt hier als optie geboden, zodat u het beheer van de toegangsrechten kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: geprivilegieerd toegangsbeheer configureren

In deze fase configureert u een groep goedkeurders en schakelt u het beheer van de juiste toegang in voor uw Microsoft 365 voor Enterprise-testomgeving. Zie [toegangsbeheer](../compliance/privileged-access-management-overview.md)voor meer informatie en een overzicht van toegangsbeheer met bevoegdheden.

Voer de volgende stappen uit om geprivilegieerde toegang in uw organisatie in te stellen en te gebruiken:

- [Stap 1: een groep goedkeurder maken](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    Voordat u bevoegdheden toegang kunt gaan gebruiken, moet u bepalen wie de goedkeuringsbevoegdheid heeft voor binnenkomende verzoeken om toegang te krijgen tot taken met verhoogde bevoegdheid en bevoegdheden. Gebruikers die lid zijn van de groep goedkeurders, kunnen toegangsaanvragen goedkeuren. Dit is ingeschakeld door een beveiligingsgroep met e-mail te maken in Microsoft 365. Maak een nieuwe beveiligingsgroep met de naam ' goedkeurders van toegankelijkheid ' in uw testomgeving, en voeg de ' gebruiker 3 ' toe die eerder is gemaakt in de stappen voor voorafgaand test lab-handleiding.

- [Stap 2: geprivilegieerde toegang inschakelen](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    Geautoriseerde toegang moet expliciet worden ingeschakeld in Microsoft 365 met de standaardgroep goedkeurder en met een reeks systeemaccounts die u wilt uitsluiten van het toegangsbeheer toegangsbeheer. Zorg ervoor dat u de toegang tot uw organisatie hebt ingeschakeld voordat u fase 3 van deze handleiding start.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: controleren of de goedkeuring is vereist voor verhoogde en geprivilegieerde taken

In deze fase dient u te controleren of het beleid voor toegangsrechten en de gebruikers moeten worden goedgekeurd voor het uitvoeren van gedefinieerde, uitgebreide en geprivilegieerde taken.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>De mogelijkheid om een taak uit te voeren die niet is gedefinieerd in een beleid voor toegangsrechten testen

Maak eerst verbinding met Exchange Management PowerShell met de referenties van een gebruiker die is geconfigureerd als globale beheerder in uw testomgeving en probeer een nieuwe logboek regel te maken. De [nieuwe JournalRule-](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) taak is op dit moment niet gedefinieerd in het toegangsbeleid voor uw organisatie.

1. Open op uw lokale computer de naam van de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van het globale beheerdersaccount voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Weergave van de nieuwe logboek regel is gemaakt in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Een nieuw beleid voor toegangsrechten maken voor de nieuwe taak JournalRule

>[!NOTE]
>Als u de stappen 1 en 2 uit fase 2 van deze handleiding nog niet hebt uitgevoerd, moet u de stappen uitvoeren om de groep met bevoegdheden voor het goedkeuren van bevoegdheden te maken en geprivilegieerde toegang in uw testomgeving in te schakelen.

1. Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met behulp van het gebruikersaccount van de globale beheerder voor uw testomgeving.

2. Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.

3. Selecteer **toegangsbeleidsregels en aanvragen beheren**.

4. Selecteer **beleid configureren** en selecteer **een beleid toevoegen**.

5. Selecteer of typ de volgende waarden in de vervolgkeuzelijst:

    **Beleidstype**: taak

    **Beleids bereik**: Exchange

    **Beleidsnaam**: nieuwe logboek regel

    **Goedkeurings type**: handmatig

    **Goedkeuringsgroep**: geautoriseerde toegang goedkeurders

6. Selecteer **maken** en vervolgens **sluiten**. Het kan een paar minuten duren voordat het beleid volledig is geconfigureerd en is ingeschakeld. Zorg ervoor dat het beleid volledig is ingeschakeld voordat u de goedkeurings vereiste gaat testen in de volgende stap.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Goedkeurings vereiste testen voor de nieuwe JournalRule-taak die is gedefinieerd in een toegangsbeleid

1. Open op uw lokale computer, open en meld u aan bij de Microsoft Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van een account van de globale beheerder voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. De fout ' onvoldoende machtigingen ' in Exchange Management PowerShell weergeven:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Toegang aanvragen voor het maken van een nieuwe logboek regel met de taak New-JournalRule

1. Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder voor uw testomgeving.

2. Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.

3. Selecteer **toegangsbeleidsregels en aanvragen beheren**.

4. Selecteer **nieuwe aanvraag**. Selecteer in de vervolgkeuzelijsten de juiste waarden voor uw organisatie:

    **Type aanvraag**: taak

    **Aanvraagbereik**: Exchange

    **Aanvraag voor**: nieuwe logboek regel

    **Duur (uren)**: 2

    **Opmerkingen**: vraagt om toestemming voor het maken van een nieuwe logboek regel

5. Selecteer **Opslaan** en vervolgens **sluiten**. Uw verzoek wordt via e-mail naar de groep van de goedkeurder verzonden.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aanvraag voor toegangsrechten goedkeuren voor het maken van een nieuwe logboek regel

1. Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met behulp van de referenties voor gebruikers 3 in uw testomgeving (lid van de beveiligingsgroep geautoriseerde toegang goedkeurders in uw testomgeving).

2. Ga in het Beheercentrum naar **instellingen**  >  **beveiliging & privacy**  >  **bevoorrechte toegang**.

3. Selecteer **toegangsbeleidsregels en aanvragen beheren**.

4. Selecteer de aanvraag in behandeling en selecteer **goedkeuren** om toegang te verlenen aan het account van de globale beheerder om een nieuwe logboek regel te maken. Een e-mailbericht met de mededeling dat de goedkeuring is verleend, wordt verzonden naar het account van de globale beheerder (de aanvraag voor de gebruiker).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Test het maken van een nieuwe logboek regel met geprivilegieerde toegang goedgekeurd voor de nieuwe taak JournalRule

1. Open op uw lokale computer de naam van de Exchange Online Remote PowerShell-module op **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-module** met behulp van het globale beheerdersaccount voor uw testomgeving.

2. Maak in Exchange Management PowerShell een nieuwe logboek regel voor uw organisatie:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Weergave van de nieuwe logboek regel is gemaakt in Exchange Management PowerShell.

## <a name="next-step"></a>Volgende stap

Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Raadpleeg ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
