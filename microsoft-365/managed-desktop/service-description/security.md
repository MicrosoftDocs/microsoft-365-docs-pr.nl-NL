---
title: Beveiligingstechnologieën in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e69656e13cd9a300cd56bdd5db7703f2387d23d4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846202"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Beveiligingstechnologieën in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop gebruikt diverse Microsoft-technologieën om beheerde apparaten en gegevens te helpen beveiligen. Daarnaast gebruikt het Microsoft beheerde bureaublad beveiliging diverse [processen](security-operations.md) die samen met deze technologieën kunnen worden gebruikt.

Precies 

- [Beveiliging van apparaten](#device-security) – beveiliging en bescherming op Microsoft beheerde bureaublad apparaten
- [Identiteit en toegangsbeheer](#identity-and-access-management) : beheer veilig gebruik van apparaten via Azure Active Directory Identity Services
- [Netwerkbeveiliging](#network-security) – VPN-informatie en door Microsoft beheerde bureaublad aanbevolen oplossing en instellingen
- [Gegevensbeveiliging](#information-security) -optionele beschikbare services om gevoelige informatie verder te beschermen 

Zie voor meer informatie over het opslaan, gebruiken en beveiligingsprocedures voor gegevens die worden gebruikt door Microsoft Managed Desktop ons White Paper op [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Beveiliging van apparaten

Microsoft Managed Desktop zorgt ervoor dat alle beheerde apparaten veilig en beschermd zijn en detecteert zo vroeg mogelijk bedreigingen met behulp van de volgende services:

Service | Beschrijving
--- | ---
Antivirussoftware | Microsoft Defender AV is geïnstalleerd en geconfigureerd<br>Definities voor Microsoft Defender AV up-to-date
Volledige volume versleuteling |    Windows BitLocker is de volume versleutelings oplossing voor Microsoft Managed Desktop devices.<br><br>Wanneer een organisatie is binnengebracht in de service, worden de apparaten versleuteld met behulp van Windows BitLocker met ingebouwde Trust platform module (TPM) om onbevoegde toegang tot lokale gegevens te voorkomen wanneer het apparaat in de slaapstand staat. 
Uitoefenen |    Microsoft Defender voor eindpunt wordt gebruikt voor beveiliging van beveiligingsbedreigingen op alle door Microsoft beheerde bureaublad apparaten. Met eindpunten voor eindpunten kunnen Enterprise-klanten geavanceerde bedreigingen op hun bedrijfsnetwerk detecteren, onderzoeken en beantwoorden. Zie [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) voor meer informatie. 
Updates voor besturingssystemen |  Door Microsoft beheerde bureaublad apparaten worden altijd de meest recente beveiligingsupdates beveiligd.
Configuratie van beveiligde apparaten |   Microsoft Managed Desktop implementeert de Microsoft-beveiligings basis. Zie [Windows-beveiligings lijnen](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) voor meer informatie.



## <a name="identity-and-access-management"></a>Identiteits- en toegangsbeheer

Identiteits-en toegangsbeheer beschermt bedrijfsmiddelen en bedrijfskritieke gegevens. Microsoft Managed Desktop configureert apparaten om te zorgen voor veilig gebruik met beheerde identiteiten van Azure Active Directory (Azure AD). Het is de verantwoordelijkheid van de klant om de juiste informatie in de Azure AD-Tenant te behouden. 

Service | Beschrijving
--- | ---
Biometrische verificatie |  Windows hello biedt gebruikers de mogelijkheid zich aan te melden met behulp van een gezicht of een pincode, zodat wachtwoorden moeilijker te onthouden of te stelen zijn. Klanten zijn verantwoordelijk voor de implementatie van de vereiste vereisten voor hun on-premises Active Directory voor gebruik van deze service in een hybride configuratie. Zie [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) voor meer informatie. 
Standaardgebruikersmachtigingen |  Om het systeem te beschermen en de beveiliging te verbeteren, worden aan de gebruiker standaardgebruikersmachtigingen toegewezen. Dit wordt toegewezen als onderdeel van de out-of-Box-ervaring van Windows auto pilot.



## <a name="network-security"></a>Netwerkbeveiliging

Klanten zijn verantwoordelijk voor netwerkbeveiliging. 

Service | Beschrijving
--- | ---
NETWERK | Klanten hebben hun eigen VPN-infrastructuur, om ervoor te zorgen dat ze niet meer kunnen worden weergegeven op het intranet.<br><br>Minimum vereiste: door Microsoft beheerde bureaubladtoepassing is een met Windows 10 compatibele en ondersteunde VPN-oplossing vereist. Als binnen uw organisatie een VPN-oplossing nodig is, moet deze Windows 10 ondersteunen en worden verpakt en geïmplementeerd via intune. Neem contact op met uw software uitgever voor meer informatie.<br><br>Raden<br>-Microsoft raadt een moderne VPN-oplossing aan die gemakkelijk kan worden geïmplementeerd via intune voor push VPN-profielen. Dit biedt een altijd, naadloos, betrouwbaar en veiligere manier om toegang te krijgen tot het bedrijfsnetwerk. Zie [[VPN-instellingen in intune]](https://docs.microsoft.com/intune/vpn-settings-configure)voor meer informatie.<br>-Dikke VPN-clients of oudere VPN-clients worden niet aanbevolen door Microsoft wanneer ze door Microsoft worden beheerd op de gebruikersomgeving.<br>-Microsoft raadt aan dat het uitgaande webverkeer rechtstreeks naar Internet gaat zonder het VPN te passeren om prestatieproblemen te voorkomen.<br>In het ideale geval raden Microsoft aan het gebruik van de app Azure Active Directory te gebruiken in plaats van een VPN.


## <a name="information-security"></a>Gegevensbeveiliging

U kunt deze optionele services configureren om bedrijfsmiddelen met een hoge waarde te beschermen. 

Service | Beschrijving
--- | ---
Gegevens herstellen  | Gegevens die zijn opgeslagen in de belangrijkste mappen op het apparaat, worden met een back-up gemaakt van OneDrive voor bedrijven. Microsoft Managed Desktop is niet verantwoordelijk voor gegevens die niet zijn gesynchroniseerd met OneDrive voor bedrijven. 
Windows-gegevensbescherming |    Voor bedrijven die een hoog niveau van gegevensbeveiliging vereisen, wordt u aangeraden [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) en [Azure Information Protection](https://www.microsoft.com/cloud-platform/azure-information-protection)te adviseren. 

