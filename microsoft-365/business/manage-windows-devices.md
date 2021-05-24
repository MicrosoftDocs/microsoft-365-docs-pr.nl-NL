---
title: Domain-joined Windows 10 devices to be managed by Microsoft 365 for business
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Lees hoe u in Microsoft 365 enkele stappen lokale active-directory-apparaten Windows 10 kunt beveiligen.
ms.openlocfilehash: ec80159bdceffd8a13d09a297a2acc1b78c9b1b3
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636081"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Schakel domeingevoegde Windows 10 apparaten in om te worden beheerd door Microsoft 365 Business Premium

Als uw organisatie on-premises Windows Server Active Directory gebruikt, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, met behoud van toegang tot on-premises resources waarvoor lokale verificatie vereist is.
Als u deze beveiliging wilt instellen, kunt u verbonden **hybride Azure AD-apparaten implementeren.** Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Kijken: Hybride Azure Active Directory configureren

In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de stappen die volgen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Voordat u begint

- Gebruikers synchroniseren met Azure AD met Azure AD Verbinding maken.
- Voltooi Azure AD Verbinding maken organisatie-eenheid (OU) synchroniseren.
- Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben om Microsoft 365 Business Premium.

Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.

## <a name="1-verify-mdm-authority-in-intune"></a>1. MDM Authority verifiëren in Intune

Ga naar [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en selecteer op Microsoft Intune pagina Apparaatinschrijving **en** zorg  er op de pagina Overzicht voor dat **MDM-autoriteit** **Intune is.**

- Als **MDM-autoriteit** **Geen** is, klikt u op **de MDM-autoriteit** om deze in te stellen **op Intune.**
- Als MDM-autoriteit **Microsoft Office 365 is,** gaat u naar Apparaten registreren en gebruikt u het dialoogvenster **MDM-autoriteit** toevoegen aan de rechterkant om  >   **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit** toevoegen is alleen beschikbaar als **de MDM-autoriteit** is ingesteld op Microsoft Office 365). 

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Controleren of Azure AD is ingeschakeld voor het deelnemen aan computers

- Ga naar het beheercentrum bij en selecteer Azure Active Directory (selecteer Alles tonen als Azure Active Directory niet zichtbaar is) in de lijst <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Beheercentra.**  
- Ga in **Azure Active Directory beheercentrum** naar Azure Active Directory **,** kies **Apparaten** en vervolgens **Apparaatinstellingen.**
- Controleren **of gebruikers kunnen deelnemen aan apparaten met Azure AD** is ingeschakeld 
    1. Als u alle gebruikers wilt inschakelen, stelt u alles **in.**
    2. Als u specifieke gebruikers wilt inschakelen, stelt u De optie **Geselecteerd in om** een specifieke groep gebruikers in te stellen.
        - Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)
        - Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Controleren of Azure AD is ingeschakeld voor MDM

- Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer Eindpunt **managemen** t (selecteer **Alles tonen** als Endpoint Manager niet zichtbaar is) 
- Ga in **Microsoft Endpoint Manager beheercentrum** naar **Apparaten**  >  **Windows**  >  **Windows Automatische**  >  inschrijving.
- Controleer of MDM-gebruikersbereik is ingeschakeld.

    1. Als u alle computers  wilt registreren, stelt u Alles in om automatisch alle gebruikerscomputers in te schrijven die zijn verbonden met Azure AD en nieuwe computers wanneer de gebruikers een werkaccount toevoegen aan Windows.
    2. Instellen op **Sommige** om de computers van een specifieke groep gebruikers in te schrijven.
        -  Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)
        -  Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.

## <a name="4-create-the-required-resources"></a>4. De vereiste resources maken 

Het uitvoeren van de vereiste taken voor het configureren van hybride [Azure AD-join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) die is gevonden in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-module. Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en groepsbeleid gemaakt en geconfigureerd.

U kunt deze module installeren door het volgende aan teroepen vanuit een exemplaar van PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> U wordt aangeraden deze module te installeren op de Windows Server met Azure AD-Verbinding maken.

Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, roept u de cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) aan. U hebt uw globale Microsoft 365 Business Premium nodig bij het uitvoeren van deze taak. Wanneer u klaar bent om de resources te maken, roept u het volgende aan:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Met de eerste opdracht wordt een verbinding tot stand brengen met de Microsoft-cloud en wanneer u daarom wordt gevraagd, geeft u uw Microsoft 365 Business Premium globale beheerdersreferenties op.

## <a name="5-link-the-group-policy"></a>5. Het groepsbeleid koppelen

1. Klik in de GPMC (Group Policy Management Console) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer Een bestaand *GPO koppelen...* in het contextmenu.
2. Selecteer het beleid dat is gemaakt in de bovenstaande stap en klik vervolgens op **OK.**

## <a name="get-the-latest-administrative-templates"></a>De nieuwste beheersjablonen downloaden

Als u het beleid Automatische MDM-inschrijving inschakelen niet ziet met **standaardReferenties** voor Azure AD, is dit mogelijk omdat de ADMX niet is geïnstalleerd voor Windows 10, versie 1803 of hoger. Als u het probleem wilt oplossen, volgt u deze stappen (Opmerking: de meest recente MDM.admx is compatibel met achteruit):

1.  Downloaden: [Beheersjablonen (.admx) voor Windows 10 update van oktober 2020 (20H2)](https://www.microsoft.com/download/102157).
2.  Installeer het pakket op een domeincontroller.
3.  Navigeer, afhankelijk van de versie met beheersjablonen, naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.
4.  Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad **naar PolicyDefinitions.**
5.  Kopieer de **map PolicyDefinitions** naar uw SYSVOL-share, standaard op **C:\Windows\SYSVOL\domain\Policies.** 
    -   Als u van plan bent een centraal beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van PolicyDefinitions toe.
6.  Als u meerdere domeincontrollers hebt, wacht u totdat SYSVOL is gerepliceerd totdat het beleid beschikbaar is. Deze procedure werkt ook voor elke toekomstige versie van de beheersjablonen.

Op dit moment kunt u het beleid Automatische **MDM-registratie** inschakelen zien met de standaardreferenties van Azure AD.

## <a name="related-content"></a>Verwante onderwerpen

[Domeingebruikers synchroniseren met Microsoft 365](manage-domain-users.md) (artikel)\
[Een groep maken in het beheercentrum](../admin/create-groups/create-groups.md) (artikel)\
[Zelfstudie: Hybride Azure Active Directory voor beheerde domeinen configureren](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (artikel)