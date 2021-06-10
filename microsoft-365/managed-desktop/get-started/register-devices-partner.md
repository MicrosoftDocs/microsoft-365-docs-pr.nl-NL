---
title: Stappen voor partners om apparaten te registreren
description: Hoe Partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689231"
---
# <a name="steps-for-partners-to-register-devices"></a>Stappen voor partners om apparaten te registreren


In dit artikel worden de stappen beschreven die partners moeten volgen om apparaten te registreren. Het proces voor het zelf registreren van apparaten wordt gedocumenteerd in [Apparaten registreren in Microsoft Managed Desktop zelf.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Registratie voorbereiden 
Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met de klant tot standbrengen in het [Partnercentrum.](https://partner.microsoft.com/dashboard) Zie de [toestemmingsdocumentatie](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) voor meer informatie over dat proces. Elke CSP-partner kan apparaten toevoegen namens een klant, zolang de klant toestemming geeft. U kunt ook meer informatie krijgen over partnerrelaties en Autopilot-machtigingen bij [Help voor partnercentrum.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Deze documentatie is alleen voor Partners en OEM's. Het proces voor zelfregistratie wordt gedocumenteerd in [Apparaten registreren in Microsoft Managed Desktop zelf.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Apparaten registreren met partnercentrum

Nadat u de relatie met uw klanten hebt vastgesteld, kunt u partnercentrum gebruiken om apparaten toe te voegen aan Autopilot voor alle klanten met wie u een relatie hebt door de volgende stappen uit te voeren:

1. Navigeren naar [Partnercentrum](https://partner.microsoft.com/dashboard)
2. Selecteer **Klanten** in het menu Partnercentrum en selecteer vervolgens de klant van wie u de apparaten wilt beheren.
3. Selecteer Apparaten op de detailpagina van **de klant.**
4. Selecteer **onder Profielen toepassen** op apparaten de optie Apparaten **toevoegen.**
5. Voer de juiste groepstag in voor het apparaatprofiel dat u hebt  geselecteerd (zoals wordt weergegeven in de volgende tabel) en selecteer Bladeren om de lijst van de klant te uploaden (in .csv bestandsindeling) naar Partnercentrum.

|[Apparaatprofiel](../service-description/profiles.md)  |Groepstag  |
|---------|---------|
|Gevoelige gegevens     |**Microsoft365Managed \_ SensitiveData**    |
|Power-gebruiker     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> De groepsnaam moet exact overeenkomen met die in de tabel, inclusief hoofdletters en speciale tekens. Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen aan het Microsoft Managed Desktop Autopilot-profiel.

>[!NOTE]
> U had dit bestand .csv ontvangen bij de aankoop van uw apparaat. Als u geen .csv hebt ontvangen, kunt u er zelf een maken door de stappen in Apparaten toevoegen aan Windows [Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Het Windows PowerShell script verschilt van het script dat wordt gebruikt voor de [Microsoft Managed Desktop Admin portal.](./register-devices-self.md#obtain-the-hardware-hash) Partners moeten [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om apparaten te registreren Microsoft Managed Desktop apparaten in partnercentrum.

Als u een foutbericht krijgt tijdens het uploaden van het .csv bestand, controleert u de opmaak van het bestand. Zorg ervoor dat de kolomorder overeenkomt met wat wordt beschreven in Gebruik Windows Autopilot-profielen op nieuwe apparaten om de [out-of-box-ervaring](/partner-center/autopilot#add-devices-to-a-customers-account)van een klant aan te passen. U kunt ook het voorbeeldbestand .csv de koppeling naast **Apparaten toevoegen** gebruiken om een lijst met apparaten te maken. 

Zie Apparaten toevoegen aan het account van een klant voor meer informatie over Autopilot in [partnerscenario's.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Apparaten registreren met de OEM-API

Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met de klant tot standbrengen. U moet een unieke koppeling hebben om aan uw respectieve klanten te leveren. Zie [Oem-relatie tot stand komen.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Nadat u de relatie hebt vastgesteld, kunt u beginnen met het registreren van apparaten voor klanten met de juiste groepstag voor elk apparaatprofiel dat ze hebben geselecteerd:


|Apparaatprofiel  |Groepstag  |
|---------|---------|
|Gevoelige gegevens     | **Microsoft365Managed \_ SensitiveData**     |
|Power-gebruiker     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> De groepslabels moeten exact overeenkomen met die in de tabel, inclusief hoofdletters en speciale tekens. Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen aan het Microsoft Managed Desktop Autopilot-profiel.