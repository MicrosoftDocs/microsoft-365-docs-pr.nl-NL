---
title: Aan de slag met Privileged Access Management
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Gebruik dit artikel voor meer informatie over het inschakelen en configureren van bevoorrecht toegangsbeheer in Office 365.
ms.openlocfilehash: 13b600c60e1b9c88285ee58efcf80a7ff5ea17fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226117"
---
# <a name="get-started-with-privileged-access-management"></a>Aan de slag met Privileged Access Management

Dit onderwerp begeleidt u bij het inschakelen en configureren van bevoorrecht toegangsbeheer in uw organisatie. U kunt de Microsoft 365-beheercentrum of Exchange PowerShell gebruiken om bevoorrechte toegang te beheren en te gebruiken.

## <a name="before-you-begin"></a>Voordat u begint

Voordat u aan de slag gaat met privileged access management, moet u uw Microsoft 365 [en](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) eventuele invoegtoepassingen bevestigen. Als u toegang wilt krijgen tot en gebruik wilt maken van bevoorrecht toegangsbeheer, moet uw organisatie een van de volgende abonnementen of invoegtoepassingen hebben:

- Microsoft 365 E5 (betaalde of proefversie)
- Microsoft 365 E3 abonnement (of Office 365 E3 + Enterprise Mobility and Security E3-abonnement) + de Microsoft 365 E5 Compliance-invoegabonnement
- Elk Microsoft 365, Office 365, Exchange, SharePoint of OneDrive voor Bedrijven abonnement + de Microsoft 365 E5 Insider Risk Management-invoeging
- Microsoft 365 A5 (betaalde of proefversie)
- Microsoft 365 A3 abonnement (of Office 365 A3 + Enterprise Mobility and Security A3-abonnement) + de Microsoft A5 Compliance-invoeging
- Een Microsoft 365, Office 365, Exchange, SharePoint of OneDrive voor education-abonnement + de Microsoft 365 A5 Insider Risk Management-invoeging
- Office 365 Enterprise E5-abonnement (betaalde of proefversie)
- Office 365 Enterprise E3-abonnement + de Office 365 Advanced Compliance-invoegabonnement (niet meer beschikbaar voor nieuwe abonnementen, zie opmerking)

Gebruikers die een bevoorrechte toegangsbeheerverzoek indienen en beantwoorden, moeten een van de bovenstaande licenties krijgen toegewezen.

> [!IMPORTANT]
> Office 365 Advanced Compliance wordt niet meer als zelfstandig abonnement verkocht. Wanneer huidige abonnementen verlopen, moeten klanten overstappen op een van de bovenstaande abonnementen, die dezelfde of aanvullende compliancefuncties bevatten.

Als u geen bestaand Office 365 Enterprise E5-abonnement hebt en u bevoorrecht toegangsbeheer wilt proberen, kunt u [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) toevoegen aan uw bestaande Office 365-abonnement [of](https://www.microsoft.com/microsoft-365/enterprise) u registreren voor een proefversie van Microsoft 365 Enterprise E5.

## <a name="enable-and-configure-privileged-access-management"></a>Bevoorrecht toegangsbeheer in- en configureren

Volg deze stappen om geprivilegieerde toegang in uw organisatie in te stellen en te gebruiken:

- [Stap 1: De groep van een goedkeurder maken](privileged-access-management-configuration.md#step1)

    Voordat u toegang tot bevoegdheden gaat gebruiken, bepaalt u wie goedkeuringsinstantie nodig heeft voor inkomende aanvragen voor toegang tot verhoogde en bevoorrechte taken. Elke gebruiker die deel uitmaakt van de groep Goedkeurders, kan toegangsaanvragen goedkeuren. Deze groep is ingeschakeld door een beveiligingsgroep met e-mail te maken in Office 365.

- [Stap 2: Geprivilegieerde toegang inschakelen](privileged-access-management-configuration.md#step2)

    Geprivilegieerde toegang moet expliciet zijn ingeschakeld in Office 365 met de standaard goedkeurdergroep, inclusief een set systeemaccounts die u wilt uitsluiten van het besturingselement voor toegangsbeheer voor bevoorrechte toegang.

- [Stap 3: Een toegangsbeleid maken](privileged-access-management-configuration.md#step3)

    Als u een goedkeuringsbeleid maakt, kunt u de specifieke goedkeuringsvereisten definiëren voor afzonderlijke taken. De goedkeuringstypeopties zijn **Automatisch** of **Handmatig.**

- [Stap 4: Aanvragen voor geprivilegieerde toegang indienen/goedkeuren](privileged-access-management-configuration.md#step4)

    Wanneer deze optie is ingeschakeld, moeten voor bevoorrechte toegang goedkeuringen worden verleend voor een taak die een gekoppeld goedkeuringsbeleid heeft gedefinieerd. Voor taken die zijn opgenomen in een goedkeuringsbeleid, moeten gebruikers toegangsgoedkeuring aanvragen en worden verleend om over machtigingen te kunnen vragen die nodig zijn om de taak uit te voeren.

Nadat goedkeuring is verleend, kan de verzoekende gebruiker de beoogde taak uitvoeren en wordt de taak geautoriseerd en uitgevoerd namens de gebruiker. De goedkeuring blijft geldig voor de gevraagde duur (standaardduur is 4 uur), waarbij de aanvraager de beoogde taak meerdere keren kan uitvoeren. Al deze uitvoeringen worden geregistreerd en beschikbaar gesteld voor beveiligings- en compliancecontrole.

> [!NOTE]
> Als u Exchange Management PowerShell wilt gebruiken om geprivilegieerde toegang in te schakelen en te configureren, volgt u de stappen in Verbinding maken naar [Exchange Online PowerShell met](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) meervoudige verificatie om verbinding te maken met Exchange Online PowerShell met uw Office 365-referenties. U hoeft geen meervoudige verificatie in te schakelen voor uw organisatie om de stappen te gebruiken om geprivilegieerde toegang in te schakelen terwijl u verbinding maakt met Exchange Online PowerShell. Als u verbinding maakt met meervoudige verificatie, wordt een OAuth-token gemaakt dat wordt gebruikt door bevoorrechte toegang voor het ondertekenen van uw aanvragen.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Stap 1: De groep van een goedkeurder maken

1. Meld u aan [bij Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties voor een beheerdersaccount in uw organisatie.

2. Ga in het beheercentrum naar **Groepen**  >  **een groep toevoegen.**

3. Selecteer **beveiligingsgroep met e-mail** en vul vervolgens de  velden **Naam,** E-mailadres groep **en** Beschrijving voor de nieuwe groep in.

4. Sla de groep op. Het kan enkele minuten duren voordat de groep volledig is geconfigureerd en in de Microsoft 365-beheercentrum.

5. Selecteer de groep nieuwe goedkeurder en selecteer **Bewerken om** gebruikers aan de groep toe te voegen.

6. Sla de groep op.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Stap 2: Geprivilegieerde toegang inschakelen

### <a name="in-the-microsoft-365-admin-center"></a>In het Microsoft 365-beheer Center

1. Meld u aan [bij Microsoft 365-beheer center met](https://admin.microsoft.com) referenties voor een beheerdersaccount in uw organisatie.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  

3. Schakel het **besturingselement Goedkeuringen vereisen voor bevoorrechte taken** in.

4. Wijs de groep goedkeurder toe die u in stap 1 hebt gemaakt als de **groep Standaardkeurders.**

5. **Opslaan** en **sluiten.**

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Als u geprivilegieerde toegang wilt inschakelen en de groep van de goedkeurder wilt toewijzen, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Voorbeeld:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> De functie Systeemaccounts wordt beschikbaar gesteld om ervoor te zorgen dat bepaalde automatiseringen binnen uw organisaties kunnen werken zonder afhankelijk te zijn van geprivilegieerde toegang, maar het wordt aanbevolen dat dergelijke uitsluitingen bijzonder zijn en dat deze worden toegestaan, regelmatig moeten worden goedgekeurd en gecontroleerd.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Stap 3: Een toegangsbeleid maken

U kunt maximaal 30 beleidsregels voor geprivilegieerde toegang voor uw organisatie maken en configureren.

### <a name="in-the-microsoft-365-admin-center"></a>In het Microsoft 365-beheer Center

1. Meld u aan [bij Microsoft 365-beheer center met](https://admin.microsoft.com) referenties voor een beheerdersaccount in uw organisatie.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer **Beleid configureren** en selecteer **Beleid toevoegen.**

5. Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:

    **Beleidstype**: Taak, Rol of Rollengroep

    **Beleidsbereik:** Exchange

    **Beleidsnaam:** Selecteren uit het beschikbare beleid

    **Goedkeuringstype**: Handmatig of Automatisch

    **Goedkeuringsgroep**: Selecteer de groep goedkeurders die is gemaakt in stap 1

6. Selecteer **Maken** en vervolgens **Sluiten.** Het kan enkele minuten duren voordat het beleid volledig is geconfigureerd en ingeschakeld.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Als u een goedkeuringsbeleid wilt maken en definiëren, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Voorbeeld:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Stap 4: Aanvragen voor geprivilegieerde toegang indienen/goedkeuren

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Hoogteautorisatie aanvragen om bevoorrechte taken uit te voeren

Aanvragen voor bevoorrechte toegang zijn geldig tot 24 uur nadat de aanvraag is ingediend. Als de aanvragen niet zijn goedgekeurd of geweigerd, verlopen de aanvragen en wordt de toegang niet goedgekeurd.

#### <a name="in-the-microsoft-365-admin-center"></a>In het Microsoft 365-beheer Center

1. Meld u aan [bij Microsoft 365-beheer center](https://admin.microsoft.com) met uw referenties.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer **Nieuwe aanvraag.** Selecteer in de vervolgkeuzevelden de juiste waarden voor uw organisatie:

    **Aanvraagtype**: Taak, Rol of Rollengroep

    **Aanvraagbereik**: Exchange

    **Aanvraag voor**: Selecteren uit het beschikbare beleid

    **Duur (uren)**: Aantal uren van aangevraagde toegang. Er is geen limiet voor het aantal uren dat kan worden aangevraagd.

    **Opmerkingen**: Tekstveld voor opmerkingen met betrekking tot uw toegangsaanvraag

5. Selecteer **Opslaan** en vervolgens **Sluiten.** Uw aanvraag wordt per e-mail naar de groep van de goedkeurder verzonden.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Voer de volgende opdracht uit in Exchange Online PowerShell om een goedkeuringsaanvraag te maken en in te dienen bij de groep van de goedkeurder:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Voorbeeld:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Status van hoogte-aanvragen weergeven

Nadat een goedkeuringsaanvraag is gemaakt, kan de status van de aanvraag voor hoogte worden gecontroleerd in het beheercentrum of in Exchange Management PowerShell met behulp van de bijbehorende aanvraag-id.

#### <a name="in-the-microsoft-365-admin-center"></a>In de Microsoft 365-beheercentrum

1. Meld u aan [bij Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw referenties.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen** Beveiliging &  >  **Privacy**  >  **privileged access**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer **Weergave om** ingediende aanvragen te filteren op Status **in** behandeling, Goedgekeurd, **Geweigerd** of **Klantenvergrendeling.** 

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Voer de volgende opdracht uit in Exchange Online PowerShell om de status van een goedkeuringsaanvraag voor een specifieke aanvraag-id weer te geven:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Voorbeeld:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Goedkeuring van een aanvraag voor verhogingsautorisatie

Wanneer een goedkeuringsaanvraag wordt gemaakt, ontvangen leden van de relevante groep goedkeurder een e-mailmelding en kunnen ze de aanvraag goedkeuren die is gekoppeld aan de aanvraag-id. De aanmelder wordt via een e-mailbericht op de hoogte gesteld van de goedkeuring of weigering van de aanvraag.

#### <a name="in-the-microsoft-365-admin-center"></a>In de Microsoft 365-beheercentrum

1. Meld u aan [bij Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw referenties.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen** Beveiliging &  >  **Privacy**  >  **privileged access**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer een lijst met aanvragen om de details te bekijken en actie te ondernemen op de aanvraag.

5. Selecteer **Goedkeuren** om de aanvraag goed te keuren of selecteer **Weigeren om** de aanvraag te weigeren. Eerder goedgekeurde aanvragen kunnen toegang intrekken door **Intrekken te selecteren.**

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Voer de volgende opdracht uit in PowerShell om een aanvraag voor hoogtetoestemming goed te Exchange Online:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Voorbeeld:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Als u een machtigingsaanvraag voor hoogte-verhoging wilt weigeren, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Voorbeeld:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Een beleid voor geprivilegieerde toegang verwijderen in Office 365

Als dit niet meer nodig is in uw organisatie, kunt u een beleid voor geprivilegieerde toegang verwijderen.

### <a name="in-the-microsoft-365-admin-center"></a>In de Microsoft 365-beheercentrum

1. Meld u aan [bij Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties voor een beheerdersaccount in uw organisatie.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen** Beveiliging &  >  **Privacy**  >  **privileged access**.

3. Selecteer **Toegangsbeleid en -aanvragen beheren.**

4. Selecteer **Beleid configureren.**

5. Selecteer het beleid dat u wilt verwijderen en selecteer Beleid **verwijderen.**

6. Selecteer **Sluiten**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Als u een beleid voor geprivilegieerde toegang wilt verwijderen, moet u de volgende opdracht uitvoeren in Exchange Online Powershell:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Bevoorrechte toegang uitschakelen in Office 365

Indien nodig kunt u bevoorrecht toegangsbeheer voor uw organisatie uitschakelen. Als u geprivilegieerde toegang uit kunt uitschakelen, worden geen bijbehorend goedkeuringsbeleid of goedkeuringsgroepen verwijderd.

### <a name="in-the-microsoft-365-admin-center"></a>In de Microsoft 365-beheercentrum

1. Meld u aan [bij Microsoft 365-beheercentrum](https://admin.microsoft.com) met referenties voor een beheerdersaccount in uw organisatie.

2. Ga in het beheercentrum naar **Instellingen**  >  **Organisatie Instellingen**  >  **Beveiligings- & privacyprivilegetoegang.**  >  

3. Schakel het **besturingselement Goedkeuringen vereisen voor bevoorrechte toegang** in.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Als u geprivilegieerde toegang wilt uitschakelen, moet u de volgende opdracht uitvoeren in Exchange Online Powershell:

```PowerShell
Disable-ElevatedAccessControl
```
