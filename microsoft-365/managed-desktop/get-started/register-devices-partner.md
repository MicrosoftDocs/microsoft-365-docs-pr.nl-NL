---
title: Stappen voor partners om apparaten te registreren
description: Hoe partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327044"
---
# <a name="steps-for-partners-to-register-devices"></a>Stappen voor partners om apparaten te registreren


In dit onderwerp worden de stappen beschreven die partners moeten volgen om apparaten te registreren. Het proces voor het zelf registreren van apparaten is gedocumenteerd in [Apparaten registreren in Microsoft Managed Desktop zelf.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Voorbereiden op registratie 
Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met hen aangaan in het [Partnercenter.](https://partner.microsoft.com/dashboard) Zie de [toestemmingsdocumentatie](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) voor meer informatie over dat proces. Elke CSP-partner kan apparaten toevoegen namens elke klant, zolang de klant hiermee instemt. U ook meer te weten komen over partnerrelaties en Autopilot-machtigingen bij [Help voor het Partnercentrum.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Deze documentatie is alleen voor partners en OEM's. Het proces voor zelfregistratie wordt gedocumenteerd in [Apparaten registreren in Microsoft Managed Desktop zelf.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Apparaten registreren met behulp van Partnercenter

Zodra u de relatie met uw klanten hebt vastgesteld, u Partner Center gebruiken om apparaten toe te voegen aan Autopilot voor een van de klanten waarmee u een relatie hebt door de volgende stappen te volgen:

1. Navigeren naar [partnercentrum](https://partner.microsoft.com/dashboard)
2. Selecteer **klanten** in het menu Partnercentrum en selecteer vervolgens de klant van wie u de apparaten wilt beheren.
3. Selecteer **Apparaten**op de detailpagina van de klant .
4. Selecteer apparaten **toevoegen**onder **Profielen toepassen op** apparaten .
5. Voer **Microsoft365Managed_Autopilot** in voor de groepsnaam en selecteer **Bladeren** om de lijst van de klant (in CSV-bestandsindeling) naar partnercentrum te uploaden.


> [!IMPORTANT]
> De groepsnaam moet precies overeenkomen **met Microsoft365Managed_Autopilot,** inclusief hoofdletters en speciale tekens. Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen met het Microsoft Managed Desktop Autopilot-profiel.

>[!NOTE]
> U had dit CSV-bestand bij aankoop van uw apparaat moeten ontvangen. Als u geen CSV-bestand hebt ontvangen, u er zelf een maken door de stappen te volgen in [Apparaten toevoegen aan Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Het Windows PowerShell-script is anders dan het script dat wordt gebruikt voor de [Microsoft Managed Desktop Admin-portal.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash) Partners moeten [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om apparaten te registreren voor Microsoft Managed Desktop-apparaten in het Partnercentrum.

Als u een foutbericht ontvangt terwijl u het CSV-bestand probeert te uploaden, controleert u de indeling van het bestand. U alleen de hardwarehash of de OEM-naam, het serienummer en het model (in die kolomvolgorde) of de Windows-product-id gebruiken. U het csv-voorbeeldbestand van de koppeling naast **Apparaten toevoegen** ook gebruiken om een apparaatlijst te maken. 

Zie Apparaten toevoegen aan het account van een klant voor meer informatie over Autopilot in [partnerscenario's.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Apparaten registreren met behulp van de OEM-API

Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met hen aangaan. U moet een unieke link te bieden aan uw respectieve klanten. Zie [Hoe maak je OEM-relatie vast](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Zodra u de relatie hebt vastgesteld, u apparaten registreren voor klanten met behulp van de groepstag **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> De groepsnaam moet exact overeenkomen met **Microsoft365Managed_Autopilot,** inclusief hoofdletters en speciale tekens. Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen met het Microsoft Managed Desktop Autopilot-profiel.
