---
title: Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for Business
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
description: In een paar stappen leert u hoe u Microsoft 365 kunt inschakelen om lokale Windows 10-apparaten met Active Directory te beveiligen.
ms.openlocfilehash: c9f5a21d993200abcf9ecf1fa236879245e1c153
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939497"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium

Als uw organisatie on-premises Windows Server Active Directory gebruikt, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, met behoud van toegang tot on-premises resources waarvoor lokale verificatie vereist is.
Als u deze beveiliging wilt instellen, kunt u verbonden **hybride Azure AD-apparaten implementeren.** Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.

In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de stappen die volgen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Voordat u aan de slag gaat, moet u de volgende stappen volgen:
- Gebruikers synchroniseren met Azure AD met Azure AD Connect.
- Voltooi de synchronisatie van Azure AD Connect Organizational Unit (OU).
- Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben voor Microsoft 365 Business Premium.

Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.

## <a name="1-verify-mdm-authority-in-intune"></a>1. MDM Authority verifiëren in Intune

Ga naar [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en selecteer op de pagina Microsoft Intune de optie Apparaatinschrijving **en** zorg er op de pagina Overzicht voor dat **MDM-autoriteit** **Intune is.** 

- Als **MDM-autoriteit** **Geen** is, klikt u op **de MDM-autoriteit** om deze in te stellen **op Intune.**
- Als MDM-autoriteit **Microsoft Office 365** is, gaat u naar Apparaten registreren en gebruikt u het dialoogvenster  **MDM-autoriteit** toevoegen aan de rechterkant om  >    **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit** toevoegen is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Controleren of Azure AD is ingeschakeld voor het deelnemen aan computers

- Ga naar het beheercentrum bij en selecteer Azure Active Directory (selecteer Alles tonen als Azure Active Directory niet zichtbaar <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> is) in de **lijst Met beheercentra.**  
- Ga in **het Azure Active Directory-beheercentrum** naar **Azure Active Directory,** kies **Apparaten** en vervolgens **Apparaatinstellingen.**
- Controleren **of gebruikers kunnen deelnemen aan apparaten met Azure AD** is ingeschakeld 
    1. Als u alle gebruikers wilt inschakelen, stelt u alles **in.**
    2. Als u specifieke gebruikers wilt inschakelen, stelt u De optie **Geselecteerd in om** een specifieke groep gebruikers in te stellen.
        - Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)
        - Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Controleren of Azure AD is ingeschakeld voor MDM

- Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  en selecteer **Endpoint Managemen** t (selecteer **Alles tonen** **als Endpoint Manager** niet zichtbaar is)
- Ga in **het Microsoft Endpoint Manager-beheercentrum** naar Automatische inschrijving **voor**  >  **Windows**  >  **Windows-apparaten**  >  .
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
> U wordt aangeraden deze module te installeren op de Windows Server met Azure AD Connect.

Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, roept u de cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) aan. U hebt uw globale beheerdersreferenties voor Microsoft 365 Business Premium nodig bij het uitvoeren van deze taak. Wanneer u klaar bent om de resources te maken, roept u het volgende aan:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Met de eerste opdracht wordt een verbinding tot stand brengen met de Microsoft-cloud en wanneer u daarom wordt gevraagd, geeft u uw globale beheerdersreferenties van Microsoft 365 Business Premium op.

## <a name="5-link-the-group-policy"></a>5. Het groepsbeleid koppelen

1. Klik in de GPMC (Group Policy Management Console) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer Een bestaand *GPO koppelen...* in het contextmenu.
2. Selecteer het beleid dat is gemaakt in de bovenstaande stap en klik vervolgens op **OK.**

## <a name="get-the-latest-administrative-templates"></a>De nieuwste beheersjablonen downloaden

Als u het beleid Automatische MDM-registratie inschakelen niet ziet met behulp van **standaardReferenties** voor Azure AD, is dit mogelijk omdat de ADMX niet is geïnstalleerd voor Windows 10, versie 1803 of hoger. Als u het probleem wilt oplossen, volgt u deze stappen (Opmerking: de meest recente MDM.admx is compatibel met achteruit):

1.  Downloaden: [Beheersjablonen (.admx) voor Windows 10 oktober 2020 Update (20H2)](https://www.microsoft.com/download/102157).
2.  Installeer het pakket op een domeincontroller.
3.  Navigeer, afhankelijk van de versie beheersjablonen, naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 oktober 2020 Update (20H2)**.
4.  Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad **naar PolicyDefinitions.**
5.  Kopieer de **map PolicyDefinitions** naar uw SYSVOL-share, standaard op **C:\Windows\SYSVOL\domain\Policies.** 
    -   Als u van plan bent een centraal beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van PolicyDefinitions toe.
6.  Als u meerdere domeincontrollers hebt, wacht u totdat SYSVOL is gerepliceerd totdat het beleid beschikbaar is. Deze procedure werkt ook voor elke toekomstige versie van de beheersjablonen.

Op dit moment kunt u het beleid Automatische **MDM-registratie** inschakelen zien met de standaardreferenties van Azure AD.

## <a name="related-content"></a>Verwante onderwerpen

[Domeingebruikers synchroniseren met Microsoft 365](manage-domain-users.md) (artikel) Een groep maken in het [beheercentrum](../admin/create-groups/create-groups.md) (artikel) [Zelfstudie: Hybride Azure Active Directory-join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) configureren voor beheerde domeinen (artikel)