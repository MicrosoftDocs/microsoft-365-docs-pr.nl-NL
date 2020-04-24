---
title: 'Stap 5: overwegingen met betrekking tot beveiliging en compliance'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over belangrijke overwegingen met betrekking tot beveiliging en compliance in Windows en Office.
ms.openlocfilehash: 003064f521f1a68c01da9d6a2c9fb19eae7d3eaf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636770"
---
# <a name="step-5-security-and-compliance-considerations"></a>Stap 5: overwegingen met betrekking tot beveiliging en compliance

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><strong>Stap 5: overwegingen met betrekking tot beveiliging en compliance</strong></p>
<p>Windows 10 en Microsoft 365-apps voor ondernemingen bieden nieuwe manieren voor het beschermen van uw gegevens, apparaten en gebruikers en het snel detecteren van en reageren op bedreigingen. U krijgt ook meer informatie over hoe u kunt omgaan met veelvoorkomende problemen op het gebied van schijfversleuteling, antimalware-apps en beleidsregels wanneer u overstapt op Windows 10.</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Beveiliging en compliance is de vijfde stap in ons aanbevolen implementatieproces, waarin overwegingen op het gebied van beveiliging en compliance in Windows 10 en Microsoft 365-apps voor ondernemingen worden behandeld. Ga naar het [Implementatiecentrum voor desktops](https://aka.ms/HowToShift) om het volledige desktop-implementatieproces te zien.
>

Het is nu tijd om te kijken naar de opties voor nieuwe mogelijkheden voor beveiliging en compliance als onderdeel van uw implementatie van Windows 10 en Microsoft 365-apps voor ondernemingen, naast de overwegingen en veelvoorkomende hindernissen bij een overstap van eerdere versies van Windows en Office. Veel van de beveiligingsfuncties in Windows 10 zijn een belangrijke drijfveer voor de overstap naar het nieuwe platform. Daarnaast zorgen de integratie met cloudservices en de identiteitsoplossingen op basis van Azure Active Directory voor een nieuwe en doorlopende bijgewerkte beveiliging van uw gegevens, apparaten en gebruikers.

## <a name="overcoming-potential-security-related-deployment-blockers"></a>Het wegnemen van mogelijke beveiligingshindernissen voor de implementatie

Voordat we uitleggen wat de nieuwe mogelijkheden zijn die u kunt gebruiken na een overstap naar Windows 10 en Microsoft 365-apps voor ondernemingen en hoe u die kunt koppelen aan de cloud, behandelen we eerst een paar veelvoorkomende situaties die het implementatieproces kunnen onderbreken.

### <a name="disk-encryption"></a>Schijfversleuteling

De eerste van de uitdagingen waarvoor u kunt komen te staan is de versleuteling van uw harde schijf. Veel oplossingen voor schijfversleuteling kunnen niet gemakkelijk worden bijgewerkt van een oudere versie van Windows naar een nieuwe versie van Windows.

Met sommige oplossingen voor schijfversleuteling kunt u in bepaalde versies van het platform de upgrades uitvoeren met de optie ‘/reflectdrivers’ in Windows Setup. Bij andere moet u mogelijk de schijf ontsleutelen voorafgaand aan de implementatie en die na de installatie van Windows 10 opnieuw versleutelen. Met sommige oplossingen is het niet mogelijk om over te stappen van een Master Boot Record (MBR) met een verouderde BIOS naar een GUID Partition Table (GPT) die vereist is voor UEFI. Dit is van belang omdat een 64-bits versie van Windows 10 is vereist voor de nieuwe beveiligingsfuncties op basis van virtualisatie, die hieronder worden uitgelegd.

Een mogelijke oplossing voor deze problemen is om Bitlocker te gebruiken, dat onderdeel uitmaakt van Windows 10 Pro en hogere edities. Met BitLocker kunt u als deel van het proces de beveiliging voor besturingssysteemupgrades en functie-updates tijdelijk uitschakelen.

[Basisimplementatie BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)

### <a name="antivirus-and-antimalware-application-compatibility"></a>Compatibiliteit van antivirus- en antimalwaretoepassingen

Ten tweede: ondanks dat ruim [99% van de Windows-toepassingen compatibel is](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) met zowel Windows 7 als Windows 10, zijn de uitzonderingen hierop vaak antivirussoftware en VPN-clients (Virtual Private Network). Deze toepassingen zijn vaak niet ontwikkeld op basis van standaardwerkwijzen en API’s en gebruiken ongedocumenteerde methoden om uw systeem te beschermen of een verbinding met netwerkbronnen op te zetten.

Als gevolg daarvan zijn deze toepassingen gevoelig voor de veranderingen die optreden bij een overstap op een nieuwe versie van Windows. Als uw antivirus- of VPN-software niet werkt in Windows 10 of na een upgrade, is de beste oplossing meestal om de app die u gebruikt te vervangen door een andere is wordt ondersteund en is getest onder Windows 10.

### <a name="security-policies"></a>Beveiligingsbeleid

De Active Directory-groepsbeleidsinstellingen die u gebruikt voor oudere versies van Windows en Office kunnen mogelijk niet rechtstreeks worden overgezet naar Windows 10 en Microsoft 365-apps voor ondernemingen, en er zijn andere dingen om rekening mee te houden als gevolg van de nieuwere mogelijkheden op het gebied van beveiliging en compliance. Het is verstandig om de Microsoft Security Compliance Toolkit te gebruiken voor een basis voor een beveiligingsbeleid in de huidige versies van Windows en Office. Ook is het een goed idee om het gebruik van de Mobile Device Management-beleidsregels van Microsoft Intune te overwegen.

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a>Nieuwe mogelijkheden op het gebied van beveiliging en compliance in Microsoft 365

Tot zover de overwegingen met betrekking tot het overzetten van uw huidige beveiligingsmaatregelen en de zaken waarmee u rekening moet houden voorafgaand aan de overstap. Laten we nu eens kijken naar de nieuwe mogelijkheden die u kunt gebruiken wanneer u overstapt op Windows 10 en Microsoft 365-apps voor ondernemingen, en de cloudopties van onder andere EMS.

### <a name="identity-and-access-management"></a>Identiteits-en toegangsbeheer

We beginnen met identiteits- en toegangsbeheer. Azure Active Directory is het identiteitsbesturingsvlak voor apps, apparaten en cloudservices en is de moderne manier om verbinding te maken met Microsoft 365 en andere cloudservices. Met voorwaardelijke toegang kunt u verschillende verificatievereisten definiëren, afhankelijk van uw aanmeldlocatie, het apparaat dat u gebruik en zaken zoals afwijkend gedrag.

Op apparaatniveau kan biometrie een uniek identificatiemiddel zijn voor eenvoudige en goed beveiligde toegang tot uw apparaten en apps. Op termijn hebt u daardoor ook minder wachtwoorden nodig. Windows Hello biedt op apparaten gebaseerde meervoudige verificatie. Het is gebaseerd op het apparaat zelf, uw pincode of een uniek biometrisch identificatiemiddel zoals uw gezicht of vingerafdruk, en het gebruik daarvan kunt u via beleidsregels afdwingen.

[Grondbeginselen van Azure-identiteitsbeheer](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-fundamentals)

[Meer informatie over Azure-identiteitsoplossingen](https://docs.microsoft.com/azure/active-directory/fundamentals/understand-azure-identity-solutions)

[Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

[Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)

### <a name="virtualization-based-security"></a>Beveiliging op basis van virtualisatie

Naast identiteitsbeheer kunt u ook doorlopende bescherming tegen zowel bekende als onbekende bedreigingen inschakelen in Windows 10. Hiervoor wordt gebruikgemaakt van beveiliging op basis van virtualisatie, die de integriteit van opstarten en codering garandeert met behulp van Beveiligd opstarten. Daarnaast wordt Credential Guard gebruikt om diefstal van referenties te voorkomen, door gebruikersgeheimen te isoleren van de Windows-omgeving. Application Guard wordt ingezet om browserbedreigingen te isoleren en beperken door de browser in een geïsoleerde container uit te voeren. Al deze technologieën maken gebruik van beveiliging op basis van virtualisatie in Windows 10, en zijn fundamentele wijzigingen die niet mogelijk zijn op en Windows 7-systeem. Houd er rekening mee dat hiervoor UEFI, 64-bits Windows en ondersteuning voor virtualisatie-extensies met SLAT op hardwareniveau zijn vereist.

[Meer informatie over beveiliging op basis van virtualisatie](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-vbs)

### <a name="security-enhancements-from-cloud-services"></a>Beveiligingsverbeteringen met cloudservices

Cloudservices bieden een extra beschermingslaag ter verbetering van de beveiliging van Windows en Office. Hiermee beschikt u over een nieuwe methode voor het vaak in real time detecteren van, weerstand bieden tegen en reageren op nieuwe aanvallen en aanvalstypen. Zeker in vergelijking met traditionele software-updates en signature-bestanden voor antivirussoftware, waarbij de reactie- en updatetijd nu eenmaal een stuk langer is.

En dankzij de Microsoft Intelligent Security Graph beschikt u ook snel over informatie over en bescherming tegen nieuwe bedreigingen. Hier volgen een paar voorbeelden van de voordelen, te beginnen met die van Office.

**[Preventie van gegevensverlies](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)** is geïntegreerd in Microsoft 365-apps voor ondernemingen. Hiermee worden gebruikers op de hoogte gebracht van het beveiligingsbeleid wanneer gevoelige informatie zoals een creditcard- of BSN-nummer wordt gevonden. Met deze beleidsregels kan informatie worden verschaft of het verzenden en delen worden geblokkeerd nadat gebruikers zijn geïnformeerd.

**[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)** is een aanvullende service die u kunt gebruiken met Office en waarmee gebruikers hun Office-bestanden eenvoudig kunnen classificeren en labelen. Ook kunnen automatische acties worden getriggerd voor gelabelde bestanden, zoals versleuteling of het blokkeren van delen ervan.

Daarnaast bieden de Office-apps nu bescherming met behulp van **[Veilige koppelingen](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)**, waarmee u beschermd bent tegen een dynamische lijst van bekende kwaadaardige websites.

**[Veilige bijlagen](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)** maakt deel uit van Outlook en Exchange Online en doet meer dan alleen filteren; bijlagen worden actief geïnspecteerd. Wanneer een risicovolle bijlage wordt gevonden, wordt de gebruiker daarvan op de hoogte gebracht en wordt de kwaadaardige bijlage uit de e-mail verwijderd.

U kunt ook **[Office 365-berichtversleuteling](https://docs.microsoft.com/office365/securitycompliance/encryption)** gebruiken om uw e-mails en bijlagen te beveiligen, door ervoor te zorgen dat ze alleen kunnen worden weergegeven door de beoogde ontvangers. Deze berichtversleuteling werkt naadloos met de verificatiemethoden voor consumentenaccounts van Google, Yahoo en Microsoft, en er wordt gebruikgemaakt van eenmalige wachtwoorden om gebruikers van andere e-mailservices berichten ook op een veilige manier te laten ontvangen.

#### <a name="additional-windows-10-protections"></a>Overige beschermingsmaatregelen van Windows 10

**[Windows Defender-toepassingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** in Windows 10 werkt op basis van een goedgekeurde lijst met toegestane en niet-toegestane toepassingen waarvan de veiligheid door Microsoft is gecontroleerd. Dit alles wordt beheerd aan de hand van de beleidsregels voor eindpuntbeveiliging van Microsoft Intune.

**[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview)** is een compleet platform voor preventieve beveiliging, detectie van inbreuken, geautomatiseerde onderzoeken en herstelmaatregelen. Hiermee worden eindpunten beschermd tegen cyberbedreigingen door het detecteren van geavanceerde aanvallen en gegevensdiefstal, het automatiseren van de afhandeling van beveiligingsincidenten en het verbeteren van de algehele beveiliging.

Met **[Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** wordt de kwetsbaarheid voor aanvallen van actieve toepassingen verminderd, door te voorkomen dat malware het Windows-systeem weet binnen te dringen en te verhinderen dat niet-vertrouwde processen toegang krijgen tot beveiligde mappen.

#### <a name="microsoft-intune"></a>Microsoft Intune

[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) fungeert als een managementservice in de cloud voor mobiele scenario’s met onder andere iOS-, Android- en Windows-apparaten. Die kunnen nu worden geconfigureerd voor co-beheer, ter aanvulling en uitbreiding van de besturingselementen voor specifieke werkbelastingen die worden beheerd door Configuration Manager. Een van de voordelen daarvan is dat apparaten die toegang nodig hebben tot beveiligde middelen moeten worden geregistreerd bij apparaatbeheer; inclusief apparaten die niet worden beheerd of geen deel uitmaken van een domein of Azure Active Directory. U kunt bovendien gebruikmaken van fijnmazige handhaving van beleidsregels voor configuratie en compliance, op besturingssysteem- en toepassingsniveau. Met Microsoft Intune worden beleidsregels en instellingen voor toepassingen centraal geconfigureerd voor Microsoft 365-apps voor ondernemingen en Store-apps in Windows 10.

## <a name="next-step"></a>Volgende stap

## <a name="step-6-os-deployment-and-feature-updates"></a>[Stap 6: implementatie van besturingssysteem en functie-updates](https://aka.ms/mdd6)

## <a name="previous-step"></a>Vorige stap 

## <a name="step-4-user-files-and-settings"></a>[Stap 4: gebruikersbestanden en -instellingen](https://aka.ms/mdd4)
