---
title: First-Run-ervaring met de pagina AutoPilot en Inschrijvingsstatus
description: De weergave van de ESP-ervaring toepassen, de gebruikte instellingen en configuratiewijzigingen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7337dd28f7940256d1753cd4c0b6309406fab2d1
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305268"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>First-Run-ervaring met de pagina AutoPilot en Inschrijvingsstatus

Op Microsoft Managed Desktop wordt de pagina met de [inschrijvings status](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) van Microsoft- [gebruiker en micro](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) Soft intune gebruikt om de beste ervaring voor uw gebruikers te bieden.

De pagina met de inschrijvings status is momenteel beschikbaar in de openbare preview-versie.

## <a name="initial-deployment"></a>Eerste implementatie

Als u de ESP-ervaring wilt bieden, moet u apparaten registreren in de Microsoft beheerde bureaublad service. Zie voor meer informatie over het registreren [nieuwe apparaten registreren](../get-started/register-devices-self.md) of [stappen voor partners om apparaten te registreren](../get-started/register-devices-partner.md).

Wanneer uw apparaten met de service zijn geregistreerd, kunt u ESP inschakelen voor uw door Microsoft beheerde bureaublad apparaten door een ondersteuningsticket in te dienen via de [Beheer Portal](https://portal.azure.com/). We implementeren de ESP-configuratie eerst naar de groep testen wanneer u het ticket. Het wordt elke 24 uur gedistribueerd naar de andere latere implementatie groepen (voor het eerst, snel en algemeen). Als u de implementatie wilt onderbreken, moet u een ander ticket vragen om te worden bewaard.

## <a name="autopilot-profile-settings"></a>Auto Pilot-profielinstellingen

Microsoft Managed Desktop gebruikt de volgende instellingen in het auto pilot-profiel dat wordt gebruikt voor de apparaten van uw gebruikers:


|Instelling  |Value  |
|---------|---------|
|Implementatie modus |  Gebruikersgerichte       |
|Deelnemen aan Azure AD als     |  Azure AD lid geworden       |
|Taal (regio)     | Standaard besturingssysteem        |
|Automatisch configureren van toetsenbord     | Nee        |
|Licentievoorwaarden voor Microsoft-software     |  Zichtbaar       |
|Privacy-instellingen     | Zichtbaar        |
|Opties voor het wijzigen van uw account verbergen     | Toon        |
|Type gebruikersaccount     |  Standard       |
|Sta White Glove OOBE toe     |  Ja       |
|De sjabloonnaam van apparaat toepassen     | Ja        |
|Voer een naam in     | MMD-% ASELECT: 11%        |

> [!NOTE]
> Hoewel het inrichten van ' White Glove ' alleen wordt ingeschakeld voor klanten met ESP, wordt het momenteel niet ondersteund in Microsoft Managed Desktop.

## <a name="enrollment-status-page-settings"></a>Instellingen van de pagina inschrijvings status

Microsoft Managed Desktop gebruikt de volgende instellingen voor de pagina met de inschrijvings status:


|Instelling  |Value  |
|---------|---------|
|Voortgang van configuratie van apps en profielen weergeven     | Ja        |
|Een foutmelding weergeven wanneer de installatie langer duurt dan het opgegeven aantal minuten     |  60       |
|Aangepaste berichten weergeven wanneer de fout voor een tijdslimiet optreedt     |  Ja       |
|Foutbericht     | Ja, het duurt iets langer om uw apparaat in te stellen dan verwacht. Klik hieronder om aan de slag te gaan en de installatie op de achtergrond wordt voltooid        |
|Gebruikers toestaan logboeken over installatiefouten te verzamelen     |  Ja       |
|Slechts pagina's weergeven op apparaten die zijn ingericht via OOBE (out-of-Box Experience)     | Ja        |
|Het gebruik van een apparaat blokkeren totdat alle apps en profielen zijn geïnstalleerd     |  Ja       |
|Gebruikers toestaan om het apparaat opnieuw in te stellen als de installatiefout optreedt     |  Ja       |
|Gebruikers toestaan om Apparaatbeheer te gebruiken als de installatiefout optreedt     |  Ja       |
|Het gebruik van een apparaat blokkeren totdat deze vereiste apps zijn geïnstalleerd als ze zijn toegewezen aan de gebruiker/het apparaat     |  Modern Workplace-time correctie       |



De pagina met de inschrijvings status vindt plaats in drie fasen. Zie [informatie over het controleren](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)van de status van pagina's voor meer informatie.

De ervaring verloopt als volgt:

1. De auto pilot-ervaring begint en de gebruiker voert zijn of haar referenties in.
2. Op het apparaat wordt de pagina met de inschrijvings status geopend en wordt de instelling van apparatuur voor het voorbereiden van apparatuur en de instelling van de De derde stap (account configuratie) wordt *momenteel overgeslagen* in de Microsoft beheerde bureaubladconfiguratie, omdat gebruikers ESP is uitgeschakeld. Het apparaat wordt opnieuw gestart.
3. Nadat de computer opnieuw is opgestart, wordt de aanmeldingspagina van Windows met **andere gebruiker**geopend.
4. De gebruikers voeren hun referenties opnieuw in en het bureaublad wordt geopend.

> [!NOTE]
> Win32-apps worden alleen geïmplementeerd in ESP als de Windows 10-versie 1903 of hoger is.

![Start pagina van het instellen van auto pilot met de fasen apparaat voorbereiden en instellen van apparatuur.](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Witte Glove inrichten

Microsoft Managed Desktop biedt op dit moment geen ondersteuning voor de functie "White Glove" van Windows auto pilot.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>De pagina-instellingen voor de instellingen voor auto pilot en inschrijvings status wijzigen

Als de installatie van de Microsoft-website die door Microsoft wordt beheerd, niet precies overeenkomt met uw behoeften, kunt u een ondersteuningsticket via de [Beheer Portal](https://portal.azure.com/)opslaan. Hier volgen enkele voorbeelden van de typen configuraties die u mogelijk nodig hebt:

### <a name="autopilot-settings-change"></a>Wijziging van auto pilot-instellingen

Mogelijk wilt u een andere sjabloon voor de naam van de apparaat aanvragen. U kunt echter de implementatie modus wijzigen, lid worden van Azure als privacy-instellingen of type gebruikers account.

### <a name="enrollment-status-page-settings-change"></a>Wijziging van de pagina instellingen voor de inschrijvings status

- Een langer aantal minuten voor de instelling ' een fout weergeven wanneer de installatie langer duurt dan een bepaald aantal minuten '.
- Het foutbericht wordt weergegeven
- Toepassingen toe te voegen of te verwijderen in het instelling gebruik van het apparaat blokkeren totdat deze vereiste apps zijn geïnstalleerd.

## <a name="required-applications"></a>Vereiste toepassingen

- U moet toepassingen in de moderne werkruimten voor de *Apparaatgroepen* testen, voornaam, Snelzoeken en algemeen. Toepassingen moeten worden geïnstalleerd in de context System. Zorg ervoor dat u het testen met ESP in de groep testen uitvoert voordat u ze aan alle groepen toewijst.
- Het apparaat moet opnieuw worden gestart wanneer het apparaat niet opnieuw is opgestart. Als u het toepassingspakket maakt, is het raadzaam dat toepassingen zijn ingesteld op ' niets doen ' wanneer u het toepassingspakket maakt.
- U kunt alleen bepaalde toepassingen beperken tot de kerntoepassingen die een gebruiker onmiddellijk nodig heeft wanneer deze zich aanmeldt bij het apparaat.
- Houd de totale grootte van alle toepassingen samen met 1 GB onder 1 GB om te voorkomen dat er timeouts optreedt tijdens de installatiefase van de toepassing.
- In het ideale geval moeten apps geen afhankelijkheden hebben. Als u apps hebt die afhankelijkheden *moeten* hebben, moet u ervoor zorgen dat u deze configureert, test en valideert als onderdeel van de ESP-evaluatie.
- Er kunnen geen toepassingen worden gebruikt die de context ' User ' (bijvoorbeeld teams) vereisen in de openbare preview van ESP.
