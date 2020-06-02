---
title: Beveiliging in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 8bfd71c4a143dee54ae006c8c54d711a8785480f
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470487"
---
# <a name="security-in-microsoft-managed-desktop"></a>Beveiliging in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop gebruikt verschillende Microsoft-technologieën om beheerde apparaten en gegevens te beveiligen. Specifiek: 


- [Apparaatbeveiliging](#device-security) – beveiliging en beveiliging op Microsoft Managed Desktop-apparaten
- [Identity and Access Management](#identity-and-access-management) – veilig gebruik van apparaten beheren via Azure Active Directory-identiteitsservices
- [Netwerkbeveiliging](#network-security) – VPN-informatie en microsoft Managed Desktop aanbevolen oplossing en instellingen
- [Informatiebeveiliging](#information-security) – optionele beschikbare diensten om gevoelige informatie verder te beschermen 

Download onze whitepaper [https://aka.ms/mmd-data](https://aka.ms/mmd-data) op .


## <a name="device-security"></a>Apparaatbeveiliging

Microsoft Managed Desktop zorgt ervoor dat alle beheerde apparaten beveiligd en beveiligd zijn en detecteert bedreigingen zo vroeg mogelijk met behulp van de volgende services:

Service | Beschrijving
--- | ---
Antivirus | Microsoft Defender AV is geïnstalleerd en geconfigureerd<br>Microsoft Defender AV-definities zijn up-to-date
Volledige volumeversleuteling |    Windows BitLocker is de oplossing voor volumeversleuteling voor Microsoft Managed Desktop-apparaten.<br><br>Zodra een organisatie is ingeschakeld in de service, worden apparaten versleuteld met Windows BitLocker met ingebouwde Trust Platform Module (TPM) om ongeautoriseerde toegang tot lokale gegevens te voorkomen wanneer het apparaat in de slaapstand staat of uit staat. 
Monitoring |    Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) wordt gebruikt voor beveiligingsbedreigingenbewaking op alle Microsoft Managed Desktop-apparaten. Met Microsoft Defender ATP kunnen zakelijke klanten geavanceerde bedreigingen in hun bedrijfsnetwerk detecteren, onderzoeken en erop reageren. Zie Microsoft Defender Advanced Threat Protection voor meer [informatie.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Updates van het besturingssysteem |  Microsoft Managed Desktop-apparaten worden altijd beveiligd met de nieuwste beveiligingsupdates.
Veilige apparaatconfiguratie |   Microsoft Managed Desktop implementeert de Microsoft Security Baseline. Zie [De beveiligingsbasislijnen van Windows voor](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) meer informatie.



## <a name="identity-and-access-management"></a>Identiteits- en toegangsbeheer

Identiteits- en toegangsbeheer beschermt bedrijfsactiva en bedrijfskritieke gegevens. Microsoft Managed Desktop configureert apparaten om veilig gebruik te garanderen met azure active directory (Azure AD) beheerde identiteiten. Het is de verantwoordelijkheid van de klant om nauwkeurige informatie in zijn Azure AD-tenant bij te houden. 

Service | Beschrijving
--- | ---
Biometrische verificatie |  Met Windows Hello kunnen gebruikers zich aanmelden met hun gezicht of pincode, waardoor wachtwoorden moeilijker te vergeten of te stelen zijn. Klanten zijn verantwoordelijk voor het implementeren van de benodigde vereisten voor hun on-premises Active Directory voor het gebruik van deze service in een hybride configuratie. Zie Windows Hello voor meer [informatie.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Standaardtoestemming voor gebruikers |  Om het systeem te beschermen en veiliger te maken, krijgt de gebruiker standaardgebruikersmachtigingen toegewezen. Dit wordt toegewezen als onderdeel van de kant-en-klare ervaring van Windows Autopilot.



## <a name="network-security"></a>Netwerkbeveiliging

Klanten zijn verantwoordelijk voor de netwerkbeveiliging. 

Service | Beschrijving
--- | ---
Vpn | Klanten bezitten hun VPN-infrastructuur, om ervoor te zorgen dat beperkte bedrijfsbronnen buiten het intranet kunnen worden blootgesteld.<br><br>Minimumvereiste: Microsoft Managed Desktop vereist een Windows 10-compatibele en ondersteunde VPN-oplossing. Als uw organisatie een VPN-oplossing nodig heeft, moet deze Windows 10 ondersteunen en worden verpakt en geïmplementeerd via Intune. Neem contact op met uw softwareuitgever voor meer informatie.<br><br>Aanbeveling:<br>- Microsoft raadt een moderne VPN-oplossing aan die eenvoudig via Intune kan worden geïmplementeerd om VPN-profielen te pushen. Dit biedt een always-on, naadloze, betrouwbare en veilige manier om toegang te krijgen tot het bedrijfsnetwerk. Zie [[VPN-instellingen in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure)voor meer informatie.<br>- Dikke VPN-clients, of oudere VPN-clients, worden niet aanbevolen door Microsoft tijdens het gebruik van Microsoft Managed Desktop, omdat dit van invloed kan zijn op de omgeving van de eindgebruiker.<br>- Microsoft raadt aan dat het uitgaande webverkeer rechtstreeks naar internet gaat zonder via de VPN te gaan om prestatieproblemen te voorkomen.<br>- Idealiter raadt Microsoft het gebruik van Azure Active Directory App Proxy aan in plaats van een VPN.


## <a name="information-security"></a>Informatiebeveiliging

U deze optionele services configureren om bedrijfsactiva met een hoge waarde te beschermen. 

Service | Beschrijving
--- | ---
Gegevensherstel  | Er wordt een back-up van OneDrive voor Bedrijven van de gegevens die zijn opgeslagen in sleutelmappen op het apparaat. Microsoft Managed Desktop is niet verantwoordelijk voor gegevens die niet zijn gesynchroniseerd met OneDrive voor Bedrijven. 
Windows-gegevensbescherming |    Voor bedrijven die een hoog niveau van informatiebeveiliging vereisen, raden we [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) en Azure Information Protection [aan.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

