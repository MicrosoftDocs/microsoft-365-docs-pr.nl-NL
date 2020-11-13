---
title: Stappen voor partners om apparaten te registreren
description: Hoe partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft beheerde bureaubladversie
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071441"
---
# <a name="steps-for-partners-to-register-devices"></a>Stappen voor partners om apparaten te registreren


In dit onderwerp worden de stappen beschreven die partners volgen om apparaten te registreren. De procedure voor het registreren van apparaten wordt een beschrijving van de manier waarop u apparaten [registreert op de website van Microsoft Managed Desktop](register-devices-self.md).



## <a name="prepare-for-registration"></a>Registratie voorbereiden 
Voordat u de registratie voor een klant voltooit, moet u eerst een relatie tot stand brengen met ze in het [partner centrum](https://partner.microsoft.com/dashboard). Zie de [documentatie](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) bij de instemming voor meer informatie over dit proces. Elke CSP-partner kan apparaten toevoegen namens een klant, mits de klant dit kan verzenden. U kunt ook meer te weten komen over partnerrelaties en auto pilot-machtigingen op het [partner centrum](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Deze documentatie is alleen voor partners en Oem's. Het proces voor het zelf registreren van een beschrijving vindt u in [registreren van apparaten in Microsoft Managed Desktop](register-devices-self.md).


## <a name="register-devices-by-using-partner-center"></a>Apparaten registreren met behulp van partner centrum

Wanneer u de relatie met uw klanten tot stand hebt gebracht, kunt u de volgende stappen uitvoeren om apparaten toe te voegen aan auto pilot voor alle klanten met een relatie:

1. Navigeren naar [partner centrum](https://partner.microsoft.com/dashboard)
2. Selecteer **klanten** in het partner centrum menu en selecteer vervolgens de klant van wie u de apparaten wilt beheren.
3. Selecteer op de detailpagina van de klant de optie **apparaten**.
4. Selecteer **apparaten toevoegen** onder **profielen op apparaten toepassen** .
5. Voer **Microsoft365Managed_Autopilot** voor de groepsnaam in en selecteer vervolgens **Bladeren** om de lijst van de klant (in. CSV-bestandsindeling) naar het partner centrum te uploaden.


> [!IMPORTANT]
> De naam van de groep moet overeenkomen met **Microsoft365Managed_Autopilot** exact, met inbegrip van lettertypen en speciale tekens. Hiermee kunt u de onlangs geregistreerde apparaten toewijzen met het Microsoft Managed Desktop Auto Pilot-profiel.

>[!NOTE]
> U zou dit CSV-bestand moeten ontvangen bij de aankoop van uw apparaat. Als u een. CSV-bestand niet hebt ontvangen, kunt u er zelf een maken door de stappen uit [te voeren om apparaten toe te voegen aan de Windows auto pilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). Het Windows PowerShell-script wijkt af van de naam die wordt gebruikt voor de [beheerde portal voor Microsoft-bureaubladbeheer](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash). Partners moeten [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om apparaten te registreren voor Microsoft Managed Desktop devices in Partner Center.

Als er een foutbericht wordt weergegeven wanneer u het CSV-bestand probeert te uploaden, controleert u de indeling van het bestand. Zorg ervoor dat de kolomvolgorde overeenkomt met wat u hier kunt doen in de [Windows auto pilot-profielen op nieuwe apparaten om de OOBE van een klant aan te passen](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account). U kunt ook het voorbeeld van een CSV-bestand gebruiken dat wordt weergegeven op de koppeling naast **apparaten toevoegen** om een Apparaatlijst te maken. 

Zie [apparaten toevoegen aan het account van een klant](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)voor meer informatie over auto pilot in partner scenario's.


## <a name="register-devices-by-using-the-oem-api"></a>Apparaten registreren met behulp van de OEM-API

Voordat u de registratie voor een klant voltooit, moet u eerst een relatie tot stand brengen. U dient een unieke koppeling te hebben voor uw eigen klanten. Bekijk [hoe u OEM-relaties kunt instellen](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Wanneer u de relatie hebt ingesteld, kunt u beginnen met het registreren van apparaten voor klanten met de Groepsmarkering **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> De naam van de groep moet overeenkomen met **Microsoft365Managed_Autopilot** exact, met inbegrip van lettertypen en speciale tekens. Hiermee kunt u de onlangs geregistreerde apparaten toewijzen met het Microsoft Managed Desktop Auto Pilot-profiel.
