---
title: Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 voor bedrijven
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
description: Meer informatie over het inschakelen van Microsoft 365 om lokale Windows 10-apparaten met Actieve Directory in slechts een paar stappen te beschermen.
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533780"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 Business Premium

Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.
Als u deze beveiliging wilt instellen, u **hybride azure ad-apparaten**implementeren. Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.

In deze video worden de stappen beschreven voor het instellen van dit voor het meest voorkomende scenario, dat ook wordt beschreven in de volgende stappen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Voordat u aan de slag gaat, moet u de volgende stappen uitvoeren:
- Gebruikers synchroniseren met Azure AD met Azure AD Connect.
- Volledige Azure AD Connect Organizational Unit (OU) synchronisatie.
- Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben voor Microsoft 365 Business Premium.

Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.

## <a name="1-verify-mdm-authority-in-intune"></a>1. MDM-autoriteit in Intune verifiëren

Ga naar portal.azure.com en zoek bovenaan de pagina naar Intune.
Selecteer op de pagina Microsoft Intune de optie **Apparaatinschrijving** en controleer op de pagina **Overzicht** of **de MDM-autoriteit** **Intune**is.

- Als **MDM-autoriteit** **geen**is, klikt u op de **MDM-autoriteit** om deze in te stellen op **Intune**.
- Als **MDM-autoriteit** **Microsoft Office 365**is, ga dan naar **Apparaten**Inschrijven  >  **en** gebruik het dialoogvenster **MDM-autoriteit toevoegen** aan het recht om **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit toevoegen** is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Controleren of Azure AD is ingeschakeld voor het samenvoegen van computers

- Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer Azure Active **Directory** (selecteer Alles weergeven als Azure Active Directory niet zichtbaar is) in de lijst **Met beheercentra.** 
- Kies **apparaten** en vervolgens **apparaatinstellingen** **in** het Azure **Active Directory-beheercentrum**.
- Controleren**of gebruikers apparaten kunnen koppelen aan Azure AD** is ingeschakeld 
    1. Als u alle gebruikers wilt inschakelen, stelt u in op **Alles**.
    2. Als u specifieke gebruikers wilt inschakelen, stelt u deze in **op Geselecteerd** om een specifieke groep gebruikers in te schakelen.
        - Voeg de gewenste domeingebruikers toe die in Azure AD zijn gesynchroniseerd aan een [beveiligingsgroep](../admin/create-groups/create-groups.md).
        - Kies **Groepen selecteren** om de mdm-gebruikersbereik voor die beveiligingsgroep in te schakelen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Controleren of Azure AD is ingeschakeld voor MDM

- Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer **Eindpunt managemen**t (selecteer **Alles weergeven** als **Eindpuntbeheer** niet zichtbaar is)
- Ga in het **Microsoft Endpoint Manager-beheercentrum**naar **Automatische**inschrijving voor  >  **Windows**  >  **Windows Windows-inschrijving**  >  **Automatic Enrollment**.
- Controleer of het gebruikersbereik van MDM is ingeschakeld.

    1. Als u alle computers wilt inschrijven, stelt u in **op Alles** om alle gebruikerscomputers die zijn aangesloten bij Azure AD en nieuwe computers automatisch in te schrijven wanneer de gebruikers een werkaccount aan Windows toevoegen.
    2. Stel in **op Sommige** om de computers van een specifieke groep gebruikers in te schrijven.
        -  Voeg de gewenste domeingebruikers toe die in Azure AD zijn gesynchroniseerd aan een [beveiligingsgroep](../admin/create-groups/create-groups.md).
        -  Kies **Groepen selecteren** om de mdm-gebruikersbereik voor die beveiligingsgroep in te schakelen.

## <a name="4-create-the-required-resources"></a>4. Maak de benodigde resources 

Het uitvoeren van de vereiste taken voor [het configureren van hybride Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet gevonden in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module. Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en groepsbeleid gemaakt en geconfigureerd.

U deze module installeren door een beroep te doen op het volgende van een exemplaar van PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Het wordt aanbevolen deze module te installeren op de Windows Server waarop Azure AD Connect wordt uitgevoerd.

Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, wordt u een beroep doen op de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) U hebt uw algemene beheerdersreferenties van Microsoft 365 Business Premium nodig bij het uitvoeren van deze taak. Wanneer u klaar bent om de resources te maken, roept u het volgende aan:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Met de eerste opdracht wordt een verbinding tot stand gebracht met de Microsoft-cloud en wanneer u wordt gevraagd, geeft u uw globale beheerdersreferenties van Microsoft 365 Business Premium op.

## <a name="5-link-the-group-policy"></a>5. Koppeling van het groepsbeleid

1. Klik in de Groepsbeleidsbeheerconsole (GPMC) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer *Een bestaande GPO koppelen...* in het contextmenu.
2. Selecteer het beleid dat in de bovenstaande stap is gemaakt en klik op **OK**.

## <a name="get-the-latest-administrative-templates"></a>De nieuwste beheersjablonen ophalen

Als u het beleid Automatische MDM-inschrijving inschakelen niet ziet **met standaard Azure AD-referenties,** kan dit zijn omdat u de ADMX niet hebt geïnstalleerd voor Windows 10, versie 1803, versie 1809 of versie 1903. Voer de volgende stappen uit (Opmerking: de nieuwste MDM.admx is backwards compatible):

1.  Download: [Beheersjablonen (.admx) voor Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Installeer het pakket op de primaire domeincontroller (PDC).
3.  Navigeren, afhankelijk van de versie naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.
4.  Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad naar **Beleidsdefinities**.
5.  Map **Beleidsdefinities** kopiëren naar **C:\Windows\SYSVOL\domain\Policies**. 
    -   Als u van plan bent een centrale beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van Beleidsdefinities toe.
6.  Start de primaire domeincontroller opnieuw om het beleid beschikbaar te maken. Deze procedure zal ook werken voor elke toekomstige versie.

Op dit punt moet u het beleid **Automatische MDM-inschrijving inschakelen** kunnen zien met standaard Azure AD-referenties beschikbaar.
