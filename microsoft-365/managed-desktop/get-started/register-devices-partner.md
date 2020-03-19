---
title: Stappen voor partners om apparaten te registreren
description: Hoe partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42806827"
---
# <a name="steps-for-partners-to-register-devices"></a>Stappen voor partners om apparaten te registreren


In dit onderwerp worden de stappen beschreven die Partners moeten volgen om apparaten te registreren. Het proces voor het zelf registreren van apparaten is gedocumenteerd in [Register-apparaten in Microsoft Managed Desktop zelf.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Bereid je voor op registratie 
Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met hen aangaan in het [Partner Center.](https://partner.microsoft.com/dashboard) Selecteer **gedelegeerde beheerbevoegdheden voor Azure Active Directory en Office 365.** Meer informatie bij [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).

Als u de registratie voor uw klant wilt voltooien, maakt u eerst een CSV-bestand.

>[!NOTE]
>Voor uw gemak u een [voorbeeld CSV-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) downloaden voor deze *Partner-versie.*

Uw bestand moet **exact dezelfde kolomkoppen** bevatten als het voorbeeld (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen. Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingstool zoals Kladblok en overweegt u alle gegevens alleen in rij 1 te laten, alleen gegevens invoeren in rijen 2 en lager. 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
>Deze indeling is alleen voor het partnerproces. Het proces voor zelfregistratie wordt zelf gedocumenteerd in [Register-apparaten in Microsoft Managed Desktop.](register-devices-self.md)

>[!IMPORTANT]
>Deze waarden moeten exact overeenkomen met de waarden van de fabrikant van SMBIOS, inclusief hoofdletters en speciale tekens. 

- Fabrikant van het apparaat (voorbeeld: SpiralOrbit) 
- Apparaatmodel (voorbeeld: ContosoABC)
- Serienummer van het apparaat

## <a name="register-devices-by-using-the-azure-portal"></a>Apparaten registreren met behulp van de Azure Portal

Registreren met behulp van de Azure Portal is hetzelfde als voor selfservice, behalve dat u de portal anders opent. Voer de volgende stappen uit:

1. Navigeren naar [partnercentrum](https://partner.microsoft.com/dashboard)
2. Selecteer **Klanten**.
3. Selecteer de klant die u wilt beheren.
4. Selecteer **Servicebeheer**.
5. Selecteer **Intune**.
6. Zoek naar 'mmd' in het bovenste zoekvak van de Azure-portal.
7. Selecteer **Apparaten**.
8. Geef in **Het uploaden**van bestanden een pad naar het CSV-bestand dat u eerder hebt gemaakt.
9. Optioneel u een **order-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden. Er zijn geen opmaakvereisten voor deze waarden.
10. Selecteer **Apparaten registreren**. Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad**, gemarkeerd als **registratie in behandeling.** Registratie duurt meestal minder dan 10 minuten, en wanneer succesvol het apparaat zal worden weergegeven als **Klaar voor de gebruiker** wat betekent dat het klaar is en wachten op een eindgebruiker om te beginnen met het gebruik.


U de voortgang van apparaatregistratie controleren op de hoofdpagina **Microsoft Managed Desktop - Devices.** Mogelijke staten die daar worden gemeld zijn:

| Status | Beschrijving |
|---------------|-------------|
| Inschrijving in behandeling | Registratie is nog niet gedaan. Kom later terug. |
| Registratie is mislukt | Registratie kon niet worden voltooid. Raadpleeg [apparaatregistratie oplossen](register-devices-self.md#troubleshooting-device-registration) voor meer informatie. |
| Klaar voor gebruiker | Registratie geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker. Microsoft Managed Desktop begeleidt hen door de eerste set-up, dus u hoeft geen verdere voorbereidingen te treffen. |
| Actief | Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant. Dit geeft ook aan dat ze het apparaat regelmatig gebruiken. |
| Inactief | Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant. Ze hebben het apparaat echter niet onlangs (in de afgelopen 7 dagen) gebruikt.  |



## <a name="troubleshooting"></a>Problemen oplossen

| Foutbericht | Details |
|---------------|-------------|
| Apparaat niet gevonden | We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de meegeleverde fabrikant, model of serienummer. Bevestig deze waarden met uw leverancier van apparaten. |
| Hardwarehash niet geldig | De hardwarehash die u voor dit apparaat hebt opgegeven, is niet correct opgemaakt. Controleer de hardwarehash dubbel en stuur deze vervolgens opnieuw in. |
| Apparaat dat al is geregistreerd | Dit apparaat is al geregistreerd bij uw organisatie. Geen verdere actie vereist. |
| Apparaat dat door een andere organisatie wordt geclaimd | Dit apparaat is al geclaimd door een andere organisatie. Neem contact op met uw leverancier van het apparaat. |
| Onverwachte fout | Uw aanvraag kan niet automatisch worden verwerkt. Neem contact<support link>op met ondersteuning ( ) en geef de aanvraag-id:<requestId> |
