---
title: Overzicht van Microsoft 365 Enterprise-beveiliging voor de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: De manier waarop Contoso de beveiligingsfuncties in Microsoft 365 Enterprise gebruikt.
ms.openlocfilehash: c0f3497eb49a0490fccf6c0ec5174d932a21005e
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268396"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Overzicht van Microsoft 365 Enterprise-beveiliging voor de Contoso Corporation

Er is een grondige beveiligingsevaluatie uitgevoerd om akkoord te krijgen voor de implementatie van Microsoft 365 Enterprise door de IT-afdeling. Dit zijn de beveiligingsvereisten van Contoso voor de cloud:

- De sterkste verificatiemethoden worden gebruikt voor toegang van werknemers tot cloudresources
- Er wordt voor gezorgd dat pc's en mobiele apparaten op veilige wijze verbinding maken met toepassingen
- Pc's en e-mail worden beschermd tegen malware
- Machtigingen voor digitale cloudactiva bepalen wie wat kan openen en wat die persoon kan doen, en zijn ontworpen voor toegang op basis van minimale bevoegdheden
- Gevoelige en sterk gereglementeerde digitale activa worden gelabeld, versleuteld en opgeslagen op veilige locaties
- Sterk gereglementeerde digitale activa worden beschermd met extra versleuteling en machtigingen
- IT-beveiligingsmedewerkers kunnen de huidige beveiligingspostuur bewaken via centrale dashboards en ontvangen meldingen over beveiligingsgebeurtenissen voor snelle reacties en risicobeperking

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>De weg van Contoso naar Microsoft 365-beveiligingsgereedheid

Contoso heeft de volgende stappen gebruikt om hun beveiliging gereed te maken voor de implementatie van Microsoft 365 Enterprise:

1. Het aantal beheerdersaccounts voor de cloud is beperkt

   Contoso heeft een uitgebreide evaluatie gedaan van de bestaande beheerdersaccounts van Active Directory Domain Services (AD DS) en een aantal specifieke cloudbeheerdersaccounts en -groepen ingesteld.

2. Contoso heeft op drie niveaus analyse van gegevensclassificatie uitgevoerd

   Contoso heeft de drie niveaus zorgvuldig beoordeeld en vastgesteld. Die werden gebruikt om de Microsoft 365 Enterprise-functies vast te stellen om de meest waardevolle gegevens van Contoso te beveiligen.

3. Beleid voor toegang, retentie en gegevensbescherming voor gegevensniveaus bepaald

   Op basis van de gegevensniveaus heeft Contoso gedetailleerde vereisten vastgesteld, die worden gebruikt om toekomstige IT-werkbelastingen te kwalificeren die naar de cloud worden verplaatst.

Conform de aanbevolen procedures voor beveiliging en Microsoft 365 Enterprise-implementatievereisten hebben de beveiligingsbeheerders en IT-afdeling van Contoso veel beveiligingsfuncties en -mogelijkheden geïmplementeerd, zoals beschreven in de volgende secties.

## <a name="identity--access-management"></a>Identiteits- en toegangsbeheer 

- Specifieke hoofdbeheerdersaccounts met MFA en PIM

  In plaats van de hoofdbeheerdersrol toe te wijzen aan standaardgebruikersaccounts heeft Contoso drie specifieke hoofdbeheerdersaccounts gemaakt met sterke wachtwoorden en ze beschermd met Azure MFA (Multi-Factor Authentication) en Azure AD (Active Directory) PIM (Privileged Identity Management). PIM is alleen beschikbaar met Microsoft 365 E5.

  Aanmelden met een hoofdbeheerdersaccount wordt alleen gedaan voor specifieke administratieve taken, de wachtwoorden zijn alleen bekend bij aangewezen medewerkers en kunnen alleen worden gebruikt binnen de tijd die met Azure AD PIM is geconfigureerd. 

  De beveiligingsbeheerders van Contoso hebben lagere beheerdersrollen toegewezen aan accounts die geschikt zijn voor de functie en verantwoordelijkheden van die IT-medewerker.

  Zie [Informatie over beheerdersrollen in Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.

- MFA voor alle gebruikersaccounts

  MFA voegt een extra beveiligingslaag toe aan het aanmeldingsproces. Het komt erop neer dat gebruikers een telefoongesprek, sms-bericht of app-melding op hun smartphone moeten bevestigen nadat ze hun wachtwoord hebben ingevoerd. Met MFA zijn Azure AD-accounts beschermd tegen niet-geautoriseerde aanmelding, zelfs als een wachtwoord niet meer veilig is.

   - Ter bescherming tegen inbreuken op het Microsoft 365-abonnement vereist Contoso MFA voor alle hoofdbeheerdersaccounts.
   - Ter bescherming tegen phishingaanvallen, waar een kwaadwillende gebruiker de referenties van een vertrouwde persoon binnen de organisatie misbruikt en schadelijke e-mails verzendt, heeft Contoso MFA ingeschakeld voor alle gebruikersaccounts, inclusief managers en leidinggevenden. 

- Veiligere apparaat- en toepassingstoegang met beleid voor voorwaardelijke toegang

  Contoso gebruikt [beleid voor voorwaardelijke toegang](microsoft-365-policies-configurations.md) voor identiteiten, apparaten, Exchange Online en SharePoint. Het beleid voor voorwaardelijke toegang voor identiteiten houdt onder meer in dat gebruikers met een hoog risico hun wachtwoord moeten wijzigen. Daarnaast kunnen klanten geen gebruikmaken van apps die moderne verificatie niet ondersteunen. Apparaatbeleid omvat onder meer de definitie van goedgekeurde apps en het eisen van conforme pc's en mobiele apparaten. Exchange Online-beleid voor voorwaardelijke toegang omvat onder meer het blokkeren van ActiveSync-clients en de installatie van Office 365-berichtversleuteling. SharePoint-beleid voor voorwaardelijke toegang omvat onder meer extra beveiliging voor gevoelige en sterk gereglementeerde sites.

- Windows Hello voor Bedrijven

  Contoso heeft [Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) geïmplementeerd en vereist dit om uiteindelijk de noodzaak van wachtwoorden met sterke tweeledige verificatie te elimineren op pc's en mobiele apparaten met Windows 10 Enterprise.

- Windows Defender Credential Guard

  Om doelgerichte aanvallen en malware die wordt uitgevoerd in het besturingssysteem met beheerdersbevoegdheden te blokkeren, heeft Contoso [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) ingeschakeld door AD DS-groepsbeleid.

## <a name="threat-protection"></a>Bedreigingsbeveiliging

- Bescherming tegen malware met Windows Defender Antivirus

  Contoso gebruikt [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) voor bescherming tegen malware en antimalwarebeheer voor pc's en apparaten met Windows 10 Enterprise.

- Een veilige e-mailstroom en controlelogboekregistratie voor postvakken met Office 365 Advanced Threat Protection 

  Contoso gebruikt Exchange Online Protection en [Office 365 ATP (Advanced Threat Protection)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) om zich te beschermen tegen onbekende malware, virussen en schadelijke URL's die worden verstuurd via e-mailberichten. 

  Contoso heeft ook controlelogboekregistratie ingeschakeld voor postvakken om vast te stellen wie zich heeft aangemeld bij gebruikerspostvakken, berichten heeft verzonden en andere activiteiten die zijn uitgevoerd door de postvakeigenaar, een gedelegeerde gebruiker of een beheerder.

- Controle op en voorkoming van aanvallen met dreigingsonderzoek en -reacties in Office 365

  Contoso gebruikt [dreigingsonderzoek en -reacties in Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) om gebruikers te beschermen door het eenvoudiger te maken aanvallen te identificeren en erop te reageren en toekomstige aanvallen te voorkomen.

- Bescherming tegen geavanceerde aanvallen met Advanced Threat Analytics

  Contoso gebruikt [ATA (Advanced Threat Analytics)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) om zichzelf te beschermen tegen geavanceerde doelgerichte aanvallen.  ATA analyseert, leert en identificeert automatisch normaal en abnormaal gedrag van entiteiten (gebruikers, apparaten en resources). 

## <a name="information-protection"></a>Gegevensbescherming

- Gevoelige en sterk gereglementeerde digitale activa beschermen met Azure Information Protection-labels

  Contoso heeft drie niveaus van gegevensbescherming ingesteld en [Microsoft 365-vertrouwelijkheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) geïmplementeerd die gebruikers kunnen toepassen op digitale activa. Voor handelsgeheimen en ander intellectueel eigendom gebruikt Contoso gevoeligheidssublabels voor sterk gereglementeerde gegevens die inhoud versleutelen en toegang tot specifieke gebruikersaccounts en -groepen beperkt.

- Gegevensverlies op intranet voorkomen met preventie van gegevensverlies

  Contoso heeft beleid voor [preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) geconfigureerd voor Exchange Online, SharePoint en OneDrive voor Bedrijven om te voorkomen dat gebruikers gevoelige gegevens per ongeluk of opzettelijk delen.

- Gegevenslekken op apparaten voorkomen met Windows-gegevensbescherming

  Contoso gebruikt [Windows-gegevensbescherming (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) om zichzelf te beschermen tegen gegevenslekken via internet-apps en -services en bedrijfs-apps en -gegevens op zakelijke apparaten en persoonlijke apparaten die medewerkers meebrengen.

- Cloudbewaking met Microsoft Cloud App Security

  Contoso gebruikt [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) om haar cloudomgeving in kaart te brengen, het gebruik te bewaken en beveiligingsgebeurtenissen en -incidenten te detecteren. Microsoft Cloud App Security is allen beschikbaar bij Microsoft 365 E5.

- Apparaatbeheer met Microsoft Intune

  Contoso gebruikt [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) om mobiele apparaten en de apps die daarop worden uitgevoerd, te registreren, te beheren en te configureren. Beleid voor voorwaardelijke toegang voor apparaten vereist ook goedgekeurde apps en conforme pc's en mobiele apparaten.

## <a name="security-management"></a>Beveiligingsbeheer

- Centraal beveiligingsdashboard voor IT met Azure Security Center

  Contoso gebruikt het [Azure Security Center](https://azure.microsoft.com/services/security-center/) voor een uniform overzicht van beveiliging en bedreigingsbescherming om beveiligingsbeleid in de werkbelastingen te beheren en te reageren op cyberaanvallen.

- Centraal beveiligingsdashboard voor gebruikers met Windows Defender-beveiligingscentrum

  Contoso heeft de [app Windows-beveiliging](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) geïmplementeerd op haar pc's en apparaten met Windows 10 Enterprise, zodat gebruikers in één oogopslag hun beveiligingspostuur kunnen zien en actie kunnen ondernemen.

