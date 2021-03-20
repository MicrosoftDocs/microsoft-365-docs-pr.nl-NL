---
title: Stappen voor partners om apparaten te registreren
description: Hoe Partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: be314b20573cecfdb020caf778e51a684a9b6df8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909068"
---
# <a name="steps-for-partners-to-register-devices"></a>Stappen voor partners om apparaten te registreren


In dit onderwerp worden de stappen beschreven die partners moeten volgen om apparaten te registreren. Het proces voor het zelf registreren van apparaten wordt gedocumenteerd in [Apparaten registreren in Microsoft Managed Desktop zelf.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Registratie voorbereiden 
Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met de klant tot standbrengen in het [Partnercentrum.](https://partner.microsoft.com/dashboard) Zie de [toestemmingsdocumentatie](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) voor meer informatie over dat proces. Elke CSP-partner kan apparaten toevoegen namens een klant, zolang de klant toestemming geeft. U kunt ook meer informatie krijgen over partnerrelaties en Autopilot-machtigingen bij [Help voor partnercentrum.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Deze documentatie is alleen voor Partners en OEM's. Het proces voor zelfregistratie wordt gedocumenteerd in [Register-apparaten in Microsoft Managed Desktop zelf.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Apparaten registreren met partnercentrum

Nadat u de relatie met uw klanten hebt vastgesteld, kunt u partnercentrum gebruiken om apparaten toe te voegen aan Autopilot voor alle klanten met wie u een relatie hebt door de volgende stappen uit te voeren:

1. Navigeren naar [Partnercentrum](https://partner.microsoft.com/dashboard)
2. Selecteer **Klanten** in het menu Partnercentrum en selecteer vervolgens de klant van wie u de apparaten wilt beheren.
3. Selecteer Apparaten op de detailpagina van **de klant.**
4. Selecteer **onder Profielen toepassen** op apparaten de optie Apparaten **toevoegen.**
5. Voer **Microsoft365Managed_Autopilot** voor de groepsnaam in en selecteer **Bladeren** om de lijst van de klant (in CSV-bestandsindeling) te uploaden naar partnercentrum.


> [!IMPORTANT]
> De groepsnaam moet exact **overeenkomen Microsoft365Managed_Autopilot,** inclusief hoofdletters en speciale tekens. Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen aan het Microsoft Managed Desktop Autopilot-profiel.

>[!NOTE]
> U had dit CSV-bestand moeten ontvangen bij de aankoop van uw apparaat. Als u geen CSV-bestand hebt ontvangen, kunt u er zelf een maken door de stappen in Apparaten toevoegen [aan Windows Autopilot te volgen.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Het Windows PowerShell-script verschilt van het script dat wordt gebruikt voor de [Microsoft Managed Desktop Admin portal.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash) Partners moeten [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om apparaten te registreren voor Microsoft Managed Desktop-apparaten in partnercentrum.

Als u een foutbericht krijgt terwijl u het CSV-bestand probeert te uploaden, controleert u de opmaak van het bestand. Zorg ervoor dat de kolomorder overeenkomt met wat wordt beschreven in Windows Autopilot-profielen gebruiken op nieuwe apparaten om de [out-of-box-ervaring](/partner-center/autopilot#add-devices-to-a-customers-account)van een klant aan te passen. U kunt ook het csv-voorbeeldbestand van de koppeling naast **Apparaten toevoegen** gebruiken om een lijst met apparaten te maken. 

Zie Apparaten toevoegen aan het account van een klant voor meer informatie over Autopilot in [partnerscenario's.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Apparaten registreren met de OEM-API

Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met de klant tot standbrengen. U moet een unieke koppeling hebben om aan uw respectieve klanten te leveren. Zie [Oem-relatie tot stand komen.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Nadat u de relatie hebt vastgesteld, kunt u apparaten voor klanten registreren met behulp van de **Microsoft365Managed_Autopilot.**

> [!IMPORTANT]
> De groepsnaam moet exact **overeenkomen Microsoft365Managed_Autopilot,** inclusief hoofdletters en speciale tekens. Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen aan het Microsoft Managed Desktop Autopilot-profiel.