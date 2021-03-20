---
title: Beveiligingstechnologieën in Microsoft Managed Desktop
description: Technologieën die worden gebruikt voor apparaatbeveiliging, identiteits- en toegangsbeheer, netwerkbeveiliging en informatiebeveiliging
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b1111f0867ff9a49ba670cdd8b48d10d158fd3ed
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917768"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Beveiligingstechnologieën in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop gebruikt verschillende Microsoft-technologieën om beheerde apparaten en gegevens te beveiligen. Daarnaast worden in het Microsoft Managed Desktop Security Operations Center verschillende [processen](security-operations.md) gebruikt in combinatie met deze technologieën.

Met name: 

- [Apparaatbeveiliging:](#device-security) beveiliging en beveiliging op Microsoft Managed Desktop-apparaten
- [Identiteits- en Access-beheer:](#identity-and-access-management) veilig gebruik van apparaten beheren via Azure Active Directory-identiteitsservices
- [Netwerkbeveiliging:](#network-security) VPN-informatie en aanbevolen oplossing en instellingen voor Microsoft Managed Desktop
- [Informatiebeveiliging:](#information-security) optionele beschikbare services om gevoelige informatie verder te beveiligen 

Zie ons whitepaper op [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Apparaatbeveiliging

Microsoft Managed Desktop zorgt ervoor dat alle beheerde apparaten worden beveiligd en beveiligd en dat bedreigingen zo vroeg mogelijk worden gedetecteerd met behulp van de volgende services:

Service | Beschrijving
--- | ---
Antivirus | Microsoft Defender AV is geïnstalleerd en geconfigureerd<br>Microsoft Defender AV-definities zijn up-to-date
Volledige volumeversleuteling |    Windows BitLocker is de oplossing voor volumeversleuteling voor Microsoft Managed Desktop-apparaten.<br><br>Zodra een organisatie is aan boord van de service, worden apparaten versleuteld met Windows BitLocker met ingebouwde Trust Platform Module (TPM) om te voorkomen dat onbevoegde toegang tot lokale gegevens wordt gebruikt wanneer het apparaat in de slaapstand staat of uit staat. 
Monitoring |    Microsoft Defender voor Eindpunt wordt gebruikt voor beveiligingsrisicocontrole op alle beheerde bureaubladapparaten van Microsoft. Met Defender voor Eindpunt kunnen zakelijke klanten geavanceerde bedreigingen in hun bedrijfsnetwerk detecteren, onderzoeken en beantwoorden. Zie Microsoft Defender voor Eindpunt voor [meer informatie.](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Updates voor besturingssysteem |  Microsoft Managed Desktop-apparaten zijn altijd beveiligd met de meest recente beveiligingsupdates.
Configuratie van beveiligde apparaten |   Microsoft Managed Desktop implementeert de Microsoft-beveiligingslijnlijn. Zie Windows-beveiligingslijnlijnen voor [meer informatie.](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identiteits- en toegangsbeheer

Identiteits- en toegangsbeheer beschermt bedrijfsactiva en bedrijfskritische gegevens. Microsoft Managed Desktop configureert apparaten om veilig gebruik te garanderen met beheerde identiteiten van Azure Active Directory (Azure AD). Het is de verantwoordelijkheid van de klant om nauwkeurige informatie te behouden in de Azure AD-tenant. 

Service | Beschrijving
--- | ---
Biometrische verificatie |  Met Windows Hello kunnen gebruikers zich aanmelden met hun gezicht of pincode, waardoor wachtwoorden moeilijker te vergeten of te stelen zijn. Klanten zijn verantwoordelijk voor het implementeren van de vereiste vereisten voor hun on-premises Active Directory voor gebruik van deze service in een hybride configuratie. Zie Windows Hello voor [meer informatie.](/windows-hardware/design/device-experiences/windows-hello) 
Standaardgebruiksmachtiging |  Als u het systeem wilt beveiligen en veiliger wilt maken, krijgt de gebruiker standaardgebruikersmachtigingen toegewezen. Deze machtiging wordt toegewezen als onderdeel van de kant-en-dooservaring van Windows Autopilot.



## <a name="network-security"></a>Netwerkbeveiliging

Klanten zijn verantwoordelijk voor netwerkbeveiliging. 

Service | Beschrijving
--- | ---
VPN | Klanten zijn eigenaar van hun VPN-infrastructuur, zodat beperkte bedrijfsresources buiten het intranet kunnen worden getoond.<br><br>Minimumvereiste: Voor Microsoft Managed Desktop is een compatibele en ondersteunde VPN-oplossing voor Windows 10 vereist. Als uw organisatie een VPN-oplossing nodig heeft, moet deze Windows 10 ondersteunen en worden verpakt en geïmplementeerd via Intune. Neem contact op met de uitgever van uw software voor meer informatie.<br><br>Aanbeveling:<br>- Microsoft raadt een moderne VPN-oplossing aan die eenvoudig via Intune kan worden geïmplementeerd om VPN-profielen te pushen. Deze benadering biedt een altijd-on, naadloze, betrouwbare en veilige manier om toegang te krijgen tot het bedrijfsnetwerk. Zie [[VPN-instellingen in Intune]](/intune/vpn-settings-configure)voor meer informatie.<br>- Dikke VPN-clients of oudere VPN-clients worden niet aanbevolen door Microsoft tijdens het gebruik van Microsoft Managed Desktop, omdat dit van invloed kan zijn op de gebruikersomgeving.<br>- Microsoft raadt aan dat het uitgaande webverkeer rechtstreeks naar internet gaat zonder de VPN te gebruiken om prestatieproblemen te voorkomen.<br>- In het ideale moment raadt Microsoft het gebruik van Azure Active Directory App Proxy aan in plaats van een VPN.


## <a name="information-security"></a>Informatiebeveiliging

U kunt deze optionele services configureren om bedrijfsactiva met hoge waarde te beschermen. 

Service | Beschrijving
--- | ---
Gegevensherstel  | Gegevens die zijn opgeslagen in belangrijke mappen op het apparaat, maken een back-up van OneDrive voor Bedrijven. Microsoft Managed Desktop is niet verantwoordelijk voor gegevens die niet worden gesynchroniseerd met OneDrive voor Bedrijven. 
Windows-gegevensbescherming |    Voor bedrijven die hoge niveaus van informatiebeveiliging vereisen, raden we [Windows Information Protection](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) en Azure Information Protection [aan.](https://www.microsoft.com/cloud-platform/azure-information-protection).