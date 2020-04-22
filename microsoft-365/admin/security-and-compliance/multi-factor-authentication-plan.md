---
title: Plannen voor meervoudige verificatie voor Microsoft 365-implementaties
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over multi-factor authenticatie in Microsoft 365 en de stappen die u moet volgen om deze in te stellen.
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665666"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Plannen voor meervoudige verificatie voor Microsoft 365-implementaties

Meervoudige verificatie (Multi-Factor Authentication of MFA) is een verificatiemethode waarvoor meer dan één verificatiemethode is vereist en waarmee een tweede beveiligingslaag wordt toegevoegd voor gebruikersaanmeldingen en -transacties. Het werkt door een toevoegingsverificatiestap te vereisen met informatie die verder gaat dan het wachtwoord van het gebruikersaccount, zoals:
  
- Een willekeurig gegenereerde verificatiecode die naar uw smartphone wordt verzonden
    
- Een telefonische oproep
    
- Een smartcard (al dan niet virtueel) 
    
- Een biometrisch apparaat 
    
## <a name="mfa-in-microsoft-365"></a>MFA in Microsoft 365

Microsoft 365 maakt gebruik van MFA om de extra beveiliging te bieden en wordt beheerd vanuit het Microsoft 365-beheercentrum. Microsoft 365 biedt de volgende subset van [Azure Multi-Factor Authentication-mogelijkheden](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) als onderdeel van het abonnement: 
  
- De mogelijkheid om MFA in te schakelen en af te dwingen voor eindgebruikers
    
- Het gebruik van een mobiele app (online- en eenmalig wachtwoord [OTP]) als tweede verificatiefactor
    
- Het gebruik van een telefonische oproep als tweede verificatiefactor
    
- Het gebruik van een sms-bericht (Short Message Service) als tweede verificatiefactor
    
- Toepassingswachtwoorden voor clients van niet-browser (bijvoorbeeld de communicatiesoftware van Microsoft Lync 2013)
    
- Standaardbegroetingen van Microsoft tijdens telefonische verificatieoproepen
    
Zie [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927)voor de volledige lijst met toegevoegde functies. U altijd de volledige functionaliteit krijgen door [Azure Multi-Factor Authentication-licenties aan](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)te schaffen. 
  
U krijgt een andere subset van mogelijkheden, afhankelijk van of u alleen cloud-identiteit gebruikt waar de gebruikersaccounts in Microsoft 365 bestaan, of hybride ingesteld met één aanmelding en Active Directory Federation Services (AD FS). 
  
|**Waar beheert u Microsoft 365?**|**Opties voor MFA als tweede factor**|
|:-----|:-----|
|Alleen cloud  <br/> | Azure Multi-Factor Authentication (tekst of telefoongesprek)  <br/> |
|Hybride installatie, on-premises beheer  <br/> | Als u gebruikersidentiteiten on-premises beheerd, hebt u de volgende keuzes:  <br/> - Fysieke of virtuele smartcard (AD FS)  <br/> - Azure Multi-Factor Authentication (module voor AD FS)  <br/>  - Azure Multi-Factor Authenticatie  <br/> |
   
De Apparaten-apps van Office 2013 ondersteunen MFA door gebruik te maken van de [Active Directory Authentication Library (ADAL).](https://go.microsoft.com/fwlink/p/?LinkId=526684) Azure Active Directory (Azure AD) host een webpagina waar gebruikers zich kunnen aanmelden. De id-provider kan Azure AD zijn of een federatieve identiteitsprovider, bijvoorbeeld AD FS. De verificatie voor federatieve gebruikers gaat volgens deze stappen:
  
1. Azure AD leidt de gebruiker door naar de aanmeldingswebpagina die wordt gehost door de identiteitsprovider van record voor de organisatie. De id-provider wordt vastgesteld door het domein dat is opgegeven in de aanmeldingsnaam van de gebruiker.
    
2. De gebruiker meldt zich via zijn of haar apparaat aan op de aanmeldingspagina van de webpagina. 
    
3. De id-provider retourneert een token naar Azure AD nadat de gebruiker is aangemeld.
    
4. Azure AD retourneert een JSON-webtoken (JWT) naar de Office-apparaat-app en de apparaat-app wordt geverifieerd met behulp van een JWT met Microsoft 365. 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Vereisten voor Office 2013-client-apps

Als u MFA voor Office 2013-clienttoepassingen wil inschakelen, moet de volgende software zijn geïnstalleerd (de hieronder genoemde versie of een latere versie), afhankelijk van het feit of u een [Klik-en-Klaar-installaties](#click-to-run-based-installations) of een [MSI-installaties](#msi-based-installations) hebt.
  
Ga als volgt te werk om na te gaan of uw installatie van Office een Klik-en-klaar- of MSI-installatie is:
  
1. Start Outlook 2013.
    
2. Kies **Office-account**in het menu **Bestand** .
    
3. Voor Klik-en-Klaar-installaties van Outlook 2013 wordt het item **Bijwerkopties** weergegeven. Voor MSI-installaties wordt het item **Bijwerkopties** niet weergegeven. 
    
    ![Zo weet u of uw Installatie van Office 2013 op basis van klikken of MSI is gebaseerd](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Sor meer informatie, zie de [FAQ over moderne authenticatie wiki artikel](https://go.microsoft.com/fwlink/p/?LinkId=530064).
  
### <a name="click-to-run-based-installations"></a>Klik-en-Klaar-installaties

Voor op klik-en-uitvoering gebaseerde installaties moet u de volgende software hebben geïnstalleerd, met de onderstaande bestandsversie of een latere bestandsversie. Als uw bestandsversie niet gelijk is aan of hoger is dan de genoemde bestandsversie, moet u deze bijwerken aan de hand van de volgende stappen.
  
|**Bestandsnaam**|**Installatiepad op uw computer**|**Bestandsversie**|
|:-----|:-----|:-----|
|Mso. Dll  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|Csi. Dll  <br/> |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove.EXE  <br/> |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|ADAL. Dll  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |verschilt  <br/> |
   
### <a name="msi-based-installations"></a>MSI-installaties

Voor MSI-installaties moet de hieronder vermelde bestandsversie of een latere versie van de volgende software zijn geïnstalleerd. Als uw bestandsversie niet gelijk is aan of hoger is dan de genoemde bestandsversie, dient u deze bij te werken via de koppeling in de kolom KB-artikel met update.
  
|**Bestandsnaam**|**Installatiepad op uw computer**|**Waar vindt u de update**|**Versie**|
|:-----|:-----|:-----|:-----|
|Mso. Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|Csi. Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove.exe  <br/> |C:\Program Files\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|ADAL. Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |Niet van toepassing  <br/> |
   
## <a name="enable-mfa"></a>MFA inschakelen

Voer de volgende stappen uit om MFA voor uw abonnement in te schakelen:
  
1. Indien nodig: 

  - [Moderne verificatie voor Office 2013 inschakelen op Windows-apparaten](enable-modern-authentication.md).
    
  - Azure Multi-Factor Authentication instellen met directoryservices van derden.
    
    Bekijk [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor informatie over specifieke identiteitsproviders die zijn geaccepteerd voor dit programma. 
    
2. [MFA instellen voor Microsoft 365](set-up-multi-factor-authentication.md).
    
3. Vertel individuele gebruikers hoe ze zich moeten aanmelden via MFA. Zie [Aanmelden bij Microsoft 365 met MFA](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).

> [!IMPORTANT]
> Als u uw gebruikers hebt ingeschakeld voor Azure Multi-Factor Authentication en alle apparaten met Office 2013 die niet zijn ingeschakeld voor moderne verificatie, moeten ze AppPasswords op die apparaten gebruiken. Meer informatie over AppPasswords en wanneer/waar/hoe ze gebruikt moeten worden vindt u hier: [App Passwords with Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).
  
## <a name="faq"></a>Veelgestelde vragen

[FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064) (Wiki-artikel met veelgestelde vragen over moderne verificatie)
  
## <a name="known-issues"></a>Bekende problemen

[Moderne verificatie van Office 2013 en Microsoft 365 Apps voor bedrijfsmoderne verificatie: dingen die u moet weten voordat u ingaat](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Problemen met Azure Multi-Factor Authentication oplossen:**
  
Zie [Problemen met Azure Multi-Factor Authentication oplossen](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Problemen met aanmelden voor moderne verificatie met Office 2013 oplossen bij gebruik van AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Als alternatieve id's niet werken:**
  
[PowerShell gebruiken om dubbele UPN's op te lossen](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script om dubbele UPN's op te lossen](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filters voor clienttoegang:**
  
[Office 2013- en Microsoft 365 Apps for enterprise-beleid voor moderne verificatie en filterbeleid voor clienttoegang: dingen die u moet weten voordat u ingaat](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Welke apps ondersteunen MFA?**
  
|**Windows**|**Mac**|**Ios**|**Android-telefoon**|**Android-tablet**|
|:-----|:-----|:-----|:-----|:-----|
|Moderne verificatie voor Word 2013, Word 2016, Excel 2013, Excel 2016, NetworkSolutionsBP-Verify-1-3, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016 Lync 2013 en Skype voor Bedrijven wordt ondersteund in deze versie.  <br/> |Moderne verificatie voor Word 2016 voor Mac, Excel 2016 voor Mac en PowerPoint 2016 voor Mac wordt ondersteund in deze versie.  <br/> |Moderne verificatie voor Word voor iPad, Excel voor iPad en PowerPoint voor iPad wordt ondersteund in deze versie.  <br/> |Moderne verificatie voor Word voor Android, Excel voor Android en PowerPoint voor Android wordt ondersteund in deze versie.  <br/> |Moderne verificatie voor Word voor Android, Excel voor Android en PowerPoint voor Android wordt ondersteund in deze versie.  <br/> |
|Moderne verificatie voor Outlook 2013 en Outlook 2016 wordt ondersteund in deze versie.  <br/> |Moderne verificatie voor Outlook 2016 voor Mac wordt ondersteund in deze versie.  <br/> |Moderne verificatie voor Outlook voor iPad wordt ondersteund in deze versie.  <br/> |||
   

