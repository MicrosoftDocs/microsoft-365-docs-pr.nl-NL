---
title: Instellen dat aan een domein verbonden Windows 10-apparaten kunnen worden beheerd door Microsoft 365 voor Bedrijven
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Leer in slechts een paar stappen hoe u Microsoft 365 inschakelen om lokale Windows 10-apparaten die lid zijn van Active Directory te beveiligen.
ms.openlocfilehash: 0b597110447272be128bfe1866234ac25a8e67e6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407073"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Instellen dat aan een domein verbonden Windows 10-apparaten kunnen worden beheerd door Microsoft 365 Business Premium

Als uw organisatie on-premises gebruikmaakt van Windows Server Active Directory, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist.
Om deze beveiliging in te stellen, kunt u apparaten implementeren die lid zijn van **Hybride Azure AD.** Deze apparaten zijn verbonden met uw on-premises Active Directory en Azure Active Directory.

In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario. Dit wordt ook beschreven in de volgende stappen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Zorg ervoor dat u deze stappen voltooit voordat u aan de slag gaat:
- Gebruikers synchroniseren met Azure AD met Azure AD Connect.
- Voltooi de synchronisatie van de organisatie-eenheid (OU) van Azure AD Connect.
- Zorg ervoor dat alle domeingebruikers die u synchroniseert, een licentie hebben voor Microsoft 365 Business Premium.

Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.

## <a name="1-verify-mdm-authority-in-intune"></a>1. MDM Authority in Intune verifiëren

Ga naar [Eindpuntenbeheer](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en selecteer op de pagina Microsoft Intune  apparaatinschrijving en ga naar de pagina Overzicht en zorg ervoor dat **MDM-autoriteit** **Intune** is.

- Als **MDM-autoriteit** **Geen** is, klikt u op de **MDM-instantie** om deze in te stellen **op Intune.**
- Als **MDM-autoriteit** **Microsoft Office 365** is, gaat u naar Apparaten registreren en gebruikt u het dialoogvenster MDM-autoriteit toevoegen aan de rechterkant om   >   **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit** toevoegen is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365). 

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Controleren of Azure AD is ingeschakeld voor het deelnemen aan computers

- Ga naar het beheercentrum en selecteer Azure Active Directory (selecteer Alles tonen als Azure Active Directory niet zichtbaar is) in de lijst <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **met beheercentra.**  
- Ga in **het Azure Active Directory-beheercentrum** naar **Azure Active Directory,** kies **Apparaten en** vervolgens **Apparaatinstellingen.**
- Controleren **of Gebruikers apparaten kunnen deelnemen aan Azure AD** is ingeschakeld 
    1. Als u alle gebruikers wilt inschakelen, stelt u alles **in.**
    2. Als u specifieke gebruikers wilt inschakelen, stelt **u deze** optie in op Geselecteerd om een specifieke groep gebruikers in teschakelen.
        - Voeg het gewenste domein dat gebruikers in Azure AD hebben gesynchroniseerd toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)
        - Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in teschakelen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Controleer of Azure AD is ingeschakeld voor MDM

- Ga naar het beheercentrum en selecteer Eindpunt beheren t (selecteer Alles tonen als <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Eindpuntbeheer** niet zichtbaar is) 
- Ga in **het beheercentrum van Microsoft Endpoint Manager** naar **Automatische** inschrijving van  >    >    >  **Windows-apparaten.**
- Controleer of het gebruikersbereik van MDM is ingeschakeld.

    1. Als u alle computers  wilt registreren, stelt u Alles in om automatisch alle gebruikerscomputers te registreren die zijn aangesloten op Azure AD en nieuwe computers wanneer gebruikers een werkaccount toevoegen aan Windows.
    2. Stel in **op Sommige** om de computers van een specifieke groep gebruikers in te schrijven.
        -  Voeg het gewenste domein dat gebruikers in Azure AD hebben gesynchroniseerd toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)
        -  Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in teschakelen.

## <a name="4-create-the-required-resources"></a>4. De vereiste resources maken 

Het uitvoeren van de vereiste taken voor het configureren van hybride [Azure AD-join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) die beschikbaar is in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-module. Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en het groepsbeleid gemaakt en geconfigureerd.

U kunt deze module installeren door het volgende in te stemmen vanuit een exemplaar van PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> U wordt aangeraden deze module te installeren op de Windows-server met Azure AD Connect.

Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, wordt de cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) aanroepen. U hebt uw globale beheerdersreferenties voor Microsoft 365 Business Premium nodig wanneer u deze taak wilt uitvoeren. Wanneer u klaar bent om de bronnen te maken, kunt u het volgende aanroepen:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Met de eerste opdracht wordt een verbinding tot stand brengen met de Microsoft-cloud en wanneer u daarom wordt gevraagd, geeft u uw globale beheerdersreferenties voor Microsoft 365 Business Premium op.

## <a name="5-link-the-group-policy"></a>5. Het groepsbeleid koppelen

1. Klik in de GPMC (Group Policy Management Console) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer Een bestaand groepsbeleidsteam *koppelen...* in het snelmenu.
2. Selecteer het beleid dat in de bovenstaande stap is gemaakt en klik op **OK.**

## <a name="get-the-latest-administrative-templates"></a>De nieuwste beheersjablonen downloaden

Als u het beleid Automatische **MDM-inschrijving** inschakelen met standaard Azure AD-referenties niet ziet, hebt u de ADMX mogelijk niet geïnstalleerd voor Windows 10, versie 1803 of hoger. Volg deze stappen om het probleem op te lossen (opmerking: de nieuwste MDM.admx is compatibel met de terugwaartse versie):

1.  Downloaden: [Beheersjablonen (.admx) voor Windows 10 update van oktober 2020 (20H2).](https://www.microsoft.com/download/102157)
2.  Installeer het pakket op een domeincontroller.
3.  Navigeer, afhankelijk van de versie met beheersjablonen, naar de map: **C:\Program Files (x86)\Microsoft-groepsbeleid\Windows 10 update van oktober 2020 (20H2).**
4.  Wijzig de naam **van de** map Beleidsdefinities in het bovenstaande pad **naar PolicyDefinitions.**
5.  Kopieer de **map PolicyDefinitions** naar uw SYSVOL-share, standaard op **C:\Windows\SYSVOL\domain\Policies.** 
    -   Als u van plan bent om een centraal beleidsopslag te gebruiken voor uw hele domein, voegt u de inhoud van PolicyDefinitions daar toe.
6.  Als u meerdere domeincontrollers hebt, wacht u totdat SYSVOL is gerepliceerd voordat het beleid beschikbaar is. Deze procedure werkt ook voor elke toekomstige versie van de beheersjablonen.

Nu moet u het beleid Automatische MDM-inschrijving inschakelen met beschikbare **Standaard Azure AD-referenties kunnen** zien.
