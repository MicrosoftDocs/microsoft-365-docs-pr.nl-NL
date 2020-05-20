---
title: Beveiliging in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 791a69433653de3960af6f8d8e1e9b23067dd6c0
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322003"
---
# <a name="security-in-microsoft-managed-desktop"></a>Beveiliging in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop gebruikt verschillende Microsoft-technologieën om beheerde apparaten en gegevens te beveiligen. Specifiek: 


- [Apparaatbeveiliging](#device-security) – beveiliging en beveiliging op Microsoft Managed Desktop-apparaten
- [Identiteits- en toegangsbeheer](#identity-and-access-management) – beheer veilig gebruik van apparaten via Azure Active Directory-identiteitsservices
- [Netwerkbeveiliging](#network-security) – VPN-informatie en door Microsoft Managed Desktop aanbevolen oplossing en instellingen
- [Informatiebeveiliging](#information-security) – optionele beschikbare services om gevoelige informatie verder te beschermen 

Download onze whitepaper op [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .

Zie de video [Microsoft Managed Desktop Security Operations](https://www.microsoft.com/videoplayer/embed/RE4q6nP)voor meer informatie over het Security Operations-team van Microsoft Managed Desktop en hoe deze werken om beveiliging voor uw apparaten te bieden. 

## <a name="device-security"></a>Apparaatbeveiliging

Microsoft Managed Desktop zorgt ervoor dat alle beheerde apparaten zijn beveiligd en beveiligd en detecteert bedreigingen zo vroeg mogelijk met behulp van de volgende services:

Service | Beschrijving
--- | ---
Antivirus | Microsoft Defender AV is geïnstalleerd en geconfigureerd<br>Microsoft Defender AV-definities zijn up-to-date
Versleuteling vol volume |    Windows BitLocker is de oplossing voor volumeversleuteling voor Microsoft Managed Desktop-apparaten.<br><br>Zodra een organisatie is aangesloten op de service, worden apparaten versleuteld met Windows BitLocker met ingebouwde Trust Platform Module (TPM) om onbevoegde toegang tot lokale gegevens te voorkomen wanneer het apparaat in de slaapstand staat of uit staat. 
Monitoring |    Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) wordt gebruikt voor bewaking van beveiligingsbedreigingen op alle Microsoft Managed Desktop-apparaten. Microsoft Defender ATP stelt zakelijke klanten in staat geavanceerde bedreigingen in hun bedrijfsnetwerk te detecteren, te onderzoeken en erop te reageren. Zie Microsoft Defender Advanced Threat Protection voor meer [informatie.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Updates van het besturingssysteem |  Microsoft Managed Desktop-apparaten worden altijd beveiligd met de nieuwste beveiligingsupdates.
Configuratie van beveiligde apparaten |   Microsoft Managed Desktop implementeert de Microsoft Security Baseline. Zie [Windows-beveiligingsbasislijnen](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) voor meer informatie.



## <a name="identity-and-access-management"></a>Identiteits- en toegangsbeheer

Identiteits- en toegangsbeheer beschermt bedrijfsmiddelen en bedrijfskritieke gegevens. Microsoft Managed Desktop configureert apparaten om veilig gebruik te garanderen met azure active directory (Azure AD) beheerde identiteiten. Het is de verantwoordelijkheid van de klant om nauwkeurige informatie in zijn Azure AD-tenant te bewaren. 

Service | Beschrijving
--- | ---
Biometrische verificatie |  Met Windows Hello kunnen gebruikers zich aanmelden met hun gezicht of pincode, waardoor wachtwoorden moeilijker te vergeten of te stelen zijn. Klanten zijn verantwoordelijk voor de implementatie van de noodzakelijke vereisten voor hun on-premises Active Directory voor het gebruik van deze service in een hybride configuratie. Zie Windows Hello voor meer [informatie.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Standaardtoestemming voor gebruikers |  Om het systeem te beschermen en veiliger te maken, krijgt de gebruiker standaardgebruikersmachtigingen toegewezen. Dit is toegewezen als onderdeel van de Windows Autopilot out-of-box ervaring.



## <a name="network-security"></a>Netwerkbeveiliging

Klanten zijn verantwoordelijk voor de netwerkbeveiliging. 

Service | Beschrijving
--- | ---
Vpn | Klanten zijn eigenaar van hun VPN-infrastructuur, om ervoor te zorgen dat beperkte bedrijfsmiddelen buiten het intranet kunnen worden blootgesteld.<br><br>Minimale vereiste: Microsoft Managed Desktop vereist een Windows 10-compatibele en ondersteunde VPN-oplossing. Als uw organisatie een VPN-oplossing nodig heeft, moet deze Windows 10 ondersteunen en worden verpakt en geïmplementeerd via Intune. Neem contact op met uw software-uitgever voor meer informatie.<br><br>Aanbeveling:<br>- Microsoft raadt een moderne VPN-oplossing aan die eenvoudig kan worden geïmplementeerd via Intune om VPN-profielen te pushen. Dit biedt een always-on, naadloze, betrouwbare en veilige manier om toegang te krijgen tot het bedrijfsnetwerk. Zie [[VPN-instellingen in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure)voor meer informatie.<br>- Dikke VPN-clients, of oudere VPN-clients, worden niet aanbevolen door Microsoft tijdens het gebruik van Microsoft Managed Desktop, omdat dit van invloed kan zijn op de omgeving van de eindgebruiker.<br>- Microsoft raadt aan dat het uitgaande webverkeer rechtstreeks naar internet gaat zonder via de VPN te gaan om prestatieproblemen te voorkomen.<br>- Idealiter raadt Microsoft het gebruik van Azure Active Directory App Proxy aan in plaats van een VPN.


## <a name="information-security"></a>Informatiebeveiliging

U deze optionele services configureren om bedrijfswaardevolle activa te beschermen. 

Service | Beschrijving
--- | ---
Gegevensherstel  | Er wordt een back-up gemaakt van informatie die is opgeslagen in belangrijke mappen op het apparaat en wordt geback-upt van OneDrive voor Bedrijven. Microsoft Managed Desktop is niet verantwoordelijk voor gegevens die niet zijn gesynchroniseerd met OneDrive voor Bedrijven. 
Windows-gegevensbescherming |    Voor bedrijven die een hoog niveau van informatiebeveiliging nodig hebben, raden we [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) en Azure Information Protection [aan.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

