---
title: First-Run-ervaring met de pagina AutoPilot en Inschrijvingsstatus
description: De esp-ervaring, de gebruikte instellingen en configuratiewijzigingen implementeren
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b65ad2a6ac1a9b9abe06cc108a980be21152bc86
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844956"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>First-Run-ervaring met de pagina AutoPilot en Inschrijvingsstatus

Microsoft Managed Desktop gebruikt zowel [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) als Microsoft Intune's [Enrollment Status Page (ESP)](/windows/deployment/windows-autopilot/enrollment-status) om de best mogelijke first-run ervaring te bieden aan uw gebruikers.

De pagina Inschrijvingsstatus is momenteel beschikbaar in een openbaar voorbeeld.

## <a name="initial-deployment"></a>Eerste implementatie

Als u de ESP-ervaring wilt bieden, moet u apparaten registreren in de Microsoft Managed Desktop service. Zie Nieuwe apparaten zelf registreren [of Stappen](../get-started/register-devices-self.md) voor Partners om apparaten te registreren voor meer informatie [over registratie.](../get-started/register-devices-partner.md)

Wanneer uw apparaten zijn geregistreerd bij de service, kunt u ESP voor uw Microsoft Managed Desktop inschakelen door een ondersteuningsticket op te vragen via de [beheerportal.](https://portal.azure.com/) De ESP-configuratie wordt in eerste instantie geïmplementeerd in de groep Test wanneer u het ticket indeelt. De implementatie wordt elke 24 uur geïmplementeerd in de andere volgende implementatiegroepen (First, Fast en Broad). Als u de implementatie wilt onderbreken, moet u een ander ticket indienen waarin Operations wordt gevraagd de implementatie te onderbreken.

## <a name="autopilot-profile-settings"></a>Autopilot-profielinstellingen

Microsoft Managed Desktop gebruikt deze instellingen in het Autopilot-profiel dat wordt gebruikt voor de apparaten van uw gebruikers:

<br>

****

|Instelling|Waarde|
|---|---|
|Implementatiemodus|User Driven|
|Deelnemen aan Azure AD als|Azure AD is lid geworden|
|Taal (regio)|Gebruiker selecteren|
|Toetsenbord automatisch configureren|Nee|
|Licentievoorwaarden voor Microsoft Software|Verbergen|
|Privacy-instellingen|Verbergen|
|Accountopties wijzigen verbergen|Toon|
|Gebruikersaccounttype|Standard|
|White Glove OOBE toestaan|Ja|
|Apparaatnaamsjabloon toepassen|Ja|
|Een naam invoeren|MMD-%RAND:11%|
|

## <a name="enrollment-status-page-settings"></a>Instellingen voor registratiestatuspagina

Microsoft Managed Desktop gebruikt deze instellingen voor de statuspagina voor inschrijving:

<br>

****

|Instelling|Waarde|
|---|---|
|Voortgang van de app- en profielconfiguratie tonen|Ja|
|Een fout laten zien wanneer de installatie langer duurt dan het opgegeven aantal minuten|60|
|Aangepast bericht tonen wanneer er een tijdslimietfout optreedt|Ja|
|Foutbericht|Ja, het duurt iets langer om uw apparaat in te stellen dan verwacht. Klik hieronder om aan de slag te gaan en we zijn klaar met het instellen op de achtergrond|
|Gebruikers toestaan logboeken over installatiefouten te verzamelen|Ja|
|Alleen pagina weergeven op apparaten die zijn ingericht op out-of-box-ervaring (OOBE)|Ja|
|Apparaatgebruik blokkeren totdat alle apps en profielen zijn geïnstalleerd|Ja|
|Gebruikers toestaan apparaat opnieuw in te stellen als er een installatiefout optreedt|Ja|
|Gebruikers toestaan apparaat te gebruiken als er een installatiefout optreedt|Ja|
|Apparaatgebruik blokkeren totdat deze vereiste apps zijn geïnstalleerd als ze zijn toegewezen aan de gebruiker/het apparaat|Moderne werkplek - Tijdcorrectie|
|

De registratiestatuspagina-ervaring vindt plaats in drie fasen. Zie Informatie over het bijhouden [van registratiestatuspagina's](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)voor meer informatie.

De ervaring verloopt als volgt:

1. De Autopilot-ervaring wordt gestart en de gebruiker voert zijn of haar referenties in.
2. Het apparaat opent de registratiestatuspagina en gaat verder met de fasen Apparaatvoorbereiding en Apparaatinstellingen. De derde stap (Account setup) *wordt* momenteel overgeslagen in de configuratie Microsoft Managed Desktop gebruiker is uitgeschakeld. Het apparaat wordt opnieuw gestart.
3. Na het opnieuw opstarten opent het apparaat de Windows aanmeldingspagina met **Andere gebruiker.**
4. De gebruikers voeren hun referenties opnieuw in en het bureaublad wordt geopend.

> [!NOTE]
> Win32-apps worden alleen geïmplementeerd tijdens ESP als de Windows 10 versie 1903 of hoger is.

![Startpagina van Autopilot-instelling met de fasen 'apparaatvoorbereiding' en 'apparaatinstellingen'.](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a>Autopilot voor vooraf inrichtende implementatie

> [!NOTE]
> Autopilot voor vooraf inrichtende implementatie in Microsoft Managed Desktop is momenteel in openbare preview.

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>Aanvullende vereisten voor Autopilot voor vooraf inrichtende implementatie

- De registratiestatuspagina (ESP) moet zijn ingeschakeld. Zie Eerste implementatie voor [meer informatie.](#initial-deployment)
- Apparaat moet een bekabelde netwerkverbinding hebben.
- Als u apparaten hebt die vóór augustus 2020 zijn geregistreerd met Microsoft Managed Desktop portal, moet u deze opnieuw registreren.
- Apparaten moeten een fabrieksafbeelding hebben met de cumulatieve update van november 2020 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) of [20H1 2020.11C,](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) naar behoren geïnstalleerd of moeten worden bijgewerkt met de nieuwste Microsoft Managed Desktop afbeelding.
- Fysieke apparaten moeten ondersteuning bieden voor TPM 2.0 en apparaatattests. Virtuele machines worden niet ondersteund. Bij het vooraf inrichten wordt gebruikgemaakt Windows automatische automatische implementatiemogelijkheden, dus TPM 2.0 is vereist. Het TPM-bevestigingsproces vereist ook toegang tot een set HTTPS-URL's die uniek zijn voor elke TPM-provider. Zie de vermelding voor de autopilot-modus voor zelf implementeren en de vooraf inrichten van Autopilot in Windows [autopilot-netwerkvereisten](/mem/autopilot/networking-requirements#tpm)voor meer informatie.

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>Reeks gebeurtenissen in Autopilot voor vooraf inrichtende implementatie

1. It-beheerder stelt het apparaat zo nodig opnieuw in of opnieuw in.
2. IT-beheerder start het apparaat op, bereikt de out-of-box-ervaring en drukt vijf keer op Windows-toets.
3. IT-beheerder selecteert Windows Autopilot Provisioning en selecteert vervolgens **Doorgaan.** Op het Windows Autopilot-configuratiescherm wordt informatie over het apparaat weergegeven.
4. IT-beheerder selecteert **Inrichting om** het inrichtingsproces te starten.
5. Apparaat start ESP en gaat door apparaatvoorbereidings- en installatiefasen. Tijdens de installatiefase van het apparaat wordt **app-installatie x van x** weergegeven (afhankelijk van de exacte configuratie van het ESP-profiel).
6. De stap voor het instellen van het account wordt momenteel overgeslagen in Microsoft Managed Desktop configuratie, omdat we Gebruikers-ESP uitschakelen.
7. Het apparaat wordt opnieuw gestart.

Nadat het apparaat opnieuw is gestart, wordt het groene statusscherm weergegeven, met een **knop Reseal.**

> [!IMPORTANT]
> Bekende problemen:
>
> - ESP wordt niet opnieuw uitgevoerd na de Autopilot voor de functie voor vooraf inrichten van de implementatie.
> - De naam van het apparaat wordt niet gewijzigd door Autopilot voor een vooraf inrichtende implementatie. De naam van het apparaat wordt alleen gewijzigd nadat u de ESP-gebruikersstroom hebt doorgeslagen.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Statuspagina-instellingen voor Autopilot en Inschrijving wijzigen

Als de instelling die door Microsoft Managed Desktop niet precies aan uw behoeften voldoen, kunt u een ondersteuningsticket indienen via de [beheerportal.](https://portal.azure.com/) Hier vindt u enkele voorbeelden van de typen configuratie die u mogelijk nodig hebt:

### <a name="autopilot-settings-change"></a>Instellingen voor Autopilot wijzigen

Mogelijk wilt u een ander apparaatnaamsjabloon aanvragen. U kunt echter de implementatiemodus, Deelnemen aan Azure AD As, Privacy Instellingen of Gebruikersaccounttype niet wijzigen.

### <a name="enrollment-status-page-settings-change"></a>Instellingen voor registratiestatuspagina wijzigen

- Een langer aantal minuten voor de instelling 'Een fout tonen wanneer de installatie langer duurt dan het opgegeven aantal minuten'.
- Het weergegeven foutbericht
- U kunt toepassingen toevoegen of verwijderen in de instelling 'Apparaat blokkeren totdat deze vereiste apps zijn geïnstalleerd als ze zijn toegewezen aan de gebruiker/apparaat'.

## <a name="required-applications"></a>Vereiste toepassingen

- U moet toepassingen in de apparaatgroepen Moderne *werkplek* testen, Eerst, Snel en Breed targeten. Toepassingen moeten worden geïnstalleerd in de context 'Systeem'. Zorg ervoor dat u het testen met ESP in de groep Test voltooit voordat u ze aan alle groepen toewijst.
- Voor toepassingen hoeft het apparaat niet opnieuw te worden gestart. Het is raadzaam om toepassingen in te stellen op 'Niets doen' wanneer u het toepassingspakket maakt als ze opnieuw moeten worden gestart.
- Beperk vereiste toepassingen tot alleen de kerntoepassingen die een gebruiker direct nodig heeft wanneer ze zich aanmelden bij het apparaat.
- Houd de totale grootte van alle toepassingen gezamenlijk onder 1 GB om time-outs tijdens de installatiefase van de toepassing te voorkomen.
- In het ideale geval mogen apps geen afhankelijkheden hebben. Als u apps hebt die *afhankelijkheden* moeten hebben, moet u deze configureren, testen en valideren als onderdeel van uw ESP-evaluatie.
- Er kunnen geen toepassingen worden opgenomen waarvoor de context 'gebruiker' nodig is (bijvoorbeeld Teams) in het openbare voorbeeld van ESP.
