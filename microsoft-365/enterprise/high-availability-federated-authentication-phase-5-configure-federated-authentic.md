---
title: Federatieve authenticatiefase van hoge beschikbaarheid 5 federatieve authenticatie voor Microsoft 365 configureren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 'Overzicht: Configureer Azure AD Connect voor uw federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: f00763487261b62940ac5def38d35158db77a699
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689332"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>Federatieve authenticatiefase van hoge beschikbaarheid 5: federatieve verificatie voor Microsoft 365 configureren

In deze laatste fase van de implementatie van federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure-infrastructuurservices, installeert en installeert u een certificaat dat is uitgegeven door een openbare certificeringsinstantie, controleert u de configuratie en voert u Azure AD Connect op de adreslijstsynchronisatie server uit. Met Azure AD Connect worden uw Microsoft 365-abonnement en de proxyservers voor Active Directory Federation Services (AD FS) en webtoepassingsproxy (Active Directory Federation Services) en webtoepassingsproxy-servers geconfigureerd voor Federatie verificatie.
  
Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>Een openbaar certificaat aanvragen en kopiëren naar de adreslijstsynchronisatie server

U ontvangt een digitaal certificaat van een openbare certificeringsinstantie met de volgende eigenschappen:
  
- Een X. 509-certificaat geschikt voor het maken van SSL-verbindingen.
    
- De uitgebreide eigenschap Subject name (SAN) wordt ingesteld op de naam van uw Federation-service (voorbeeld: fs.contoso.com).
    
- Het certificaat moet de persoonlijke sleutel hebben en zijn opgeslagen in de PFX-indeling.
    
Daarnaast moeten uw computers en apparaten van uw organisatie de openbare certificeringsinstantie die het digitaal certificaat uitgeeft, vertrouwen. Deze vertrouw baarheid wordt bepaald door een basiscertificaat te gebruiken van de openbare certificeringsinstantie die in het archief met vertrouwde basiscertificeringsinstanties op uw computers en apparaten is geïnstalleerd. Voor computers waarop Microsoft Windows wordt uitgevoerd is meestal een reeks van deze typen certificaten geïnstalleerd van veelgebruikte certificeringsinstanties. Als het basiscertificaat van uw openbare certificeringsinstantie nog niet is geïnstalleerd, moet u dit implementeren op de computers en apparaten van uw organisatie.
  
Zie vereisten [voor Federatie installeren en configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)voor meer informatie over de certificaatvereisten voor federatieve verificatie.
  
Wanneer u het certificaat ontvangt, kopieert u het naar een map op C: station van de adreslijstsynchronisatie server. Geef bijvoorbeeld het bestand SSL. pfx op en sla dit op in de map C: \\ certs op de adreslijstsynchronisatie server.
  
## <a name="verify-your-configuration"></a>De configuratie verifiëren

Nu moet u Azure AD Connect en federatieve verificatie voor Microsoft 365 configureren. U kunt er ook voor zorgen dat u het volgende ziet:
  
- Het openbare domein van uw organisatie wordt toegevoegd aan uw abonnement op Microsoft 365.
    
- De Microsoft 365-gebruikersaccounts van uw organisatie zijn geconfigureerd voor de openbare domeinnaam van uw organisatie en kan zich nu aanmelden.
    
- U hebt een Federatie service-FQDN vastgesteld op basis van uw openbare domeinnaam.
    
- Een openbare DNS-record voor de FQDN van de Federation service verwijst naar het openbare IP-adres van de Azure-Load Balancer op internet voor de webtoepassingsproxy-servers.
    
- Een persoonlijke DNS-record voor de FQDN van de Federation service verwijst naar het persoonlijke IP-adres van de interne Azure Load Balancer voor de AD FS-servers.
    
- Een openbare certificeringsinstantie-digitaal certificaat voor isssued dat geschikt is voor SSL-verbindingen met de SAN-set met de Federatie service FQDN is een PFX-bestand dat is opgeslagen op de adreslijstsynchronisatie server.
    
- Het basiscertificaat voor de openbare certificeringsinstantie wordt in de lijst met vertrouwde basiscertificeringsinstanties geïnstalleerd op uw computer en apparaten.
    
Hier ziet u een voorbeeld van de contoso-organisatie:
  
**Een voorbeeld configuratie voor een federatieve verificatie-infrastructuur met hoge beschikbaarheid in azure**

![Een voorbeeld van de configuratie van de High Availability Microsoft 365 federatieve verificatie-infrastructuur in azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>Azure AD Connect uitvoeren om federatieve verificatie te configureren

Met het hulpprogramma Azure AD Connect worden de AD FS-servers, de webtoepassingsproxy en Microsoft 365 voor federatieve verificatie met de volgende stappen geconfigureerd:
  
1. Maak een verbinding met extern bureaublad met de adreslijstsynchronisatie server met een domeinaccount met lokale beheerdersbevoegdheden.
    
2. Open op de computer van de adreslijstsynchronisatie server Internet Explorer en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
3. Klik op de pagina **Microsoft Azure Active Directory Connect** op **downloaden**en klik vervolgens op **uitvoeren**.
    
4. Klik op de pagina **Welkom bij Azure AD Connect** op **Ik ga akkoord**en klik vervolgens op **Doorgaan.**
    
5. Klik op de pagina **Express Settings** op **Customize**.
    
6. Klik op de pagina **vereiste onderdelen installeren** op **installeren**.
    
7. Klik op de pagina **gebruikersaanmelding** op **federatie met AD FS**en klik vervolgens op **volgende**.
    
8. Typ op de pagina **verbinding maken met Azure AD** de naam en het wachtwoord voor het globale beheerdersaccount voor uw abonnement op microsoft 365 en klik op **volgende**.
    
9. Zorg ervoor dat op de pagina **verbinding maken met uw** telefoonnummers het domein Active Directory Domain Services (AD DS) is geselecteerd in **het forest**, typ de naam en het wachtwoord van een domeinbeheerdersaccount en **Klik op** **volgende**.
    
10. Klik op de pagina met **aanmeld configuraties van Azure AD** op **volgende**.
    
11. Klik op de pagina **domein en ou filtering** op **volgende**.
    
12. Op de pagina **unieke identificatie van uw gebruikers klikt u** op **volgende**.
    
13. Klik op de pagina **gebruikers en apparaten filteren** op **volgende**.
    
14. Klik op de pagina **optionele functies** op **volgende**.
    
15. Klik op de **AD FS-Farm** pagina op **een nieuwe AD FS-farm configureren**.
    
16. Klik op **Bladeren** en geef de locatie en de naam op van het SSL-certificaat van de openbare certificeringsinstantie.
    
17. Wanneer u hierom wordt gevraagd, typt u het certificaatwachtwoord en klikt u vervolgens op **OK**.
    
18. Controleer of de naam van het **onderwerp** en de naam van de **Federation service** zijn ingesteld op de FQDN van de Federation service en klik op **volgende**.
    
19. Op de pagina **AD FS servers** typt u de naam van de eerste AD FS-server (tabel M-item 4-kolomnaam van virtuele machine) en klikt u vervolgens op **toevoegen**.
    
20. Typ de naam van de tweede AD FS-server (tabel M-item 5-kolom met virtuele machinenaam), klik op **toevoegen**en klik op **volgende**.
    
21. Typ op de pagina **Webtoepassings proxyservers** de naam van de eerste server van de webtoepassing (tabel M-item 6-kolomnaam van virtuele machine) en klik op **toevoegen**.
    
22. Typ de naam van de tweede server van de webtoepassingsproxy (tabel M-item 7: kolomnaam van virtuele machine), klik op **toevoegen**en klik op **volgende**.
    
23. Typ op de pagina **referenties van domeinbeheerder** de gebruikersnaam en het wachtwoord van een domeinbeheerdersaccount en klik op **volgende**.
    
24. Typ op de pagina **AD FS service-account** de gebruikersnaam en het wachtwoord van een beheerder account van een beheerder en klik op **volgende**.
    
25. Selecteer op de pagina **Azure AD domain** in **Domain**de naam van de DNS-domeinnaam van uw organisatie en klik op **volgende**.
    
26. Klik op de pagina **Gereed voor configureren** op **Installeren**.
    
27. Klik op de pagina **installeren voltooid** op **verifiëren**. U ziet twee berichten om aan te geven dat zowel het intranet als de Internet configuratie zijn geverifieerd.
    
  - In het intranet bericht moet het persoonlijke IP-adres van uw Azure Internal Load Balancer voor uw AD FS-servers worden vermeld.
    
  - Het Internet bericht moet worden vermeld in het openbare IP-adres van uw Azure Internet Facing Load Balancer voor de proxyservers van uw webtoepassing.
    
28. Klik op de pagina **Installatie voltooid** op **Afsluiten**.
    
Dit is de laatste configuratie, met de namen van de tijdelijke aanduidingen voor de servers.
  
**Fase 5: de laatste configuratie van een federatieve verificatie-infrastructuur met hoge beschikbaarheid in azure**

![De laatste configuratie van de High Availability Microsoft 365 federatieve verificatie-infrastructuur in azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Uw federatieve verificatie-infrastructuur van hoge beschikbaarheid voor Microsoft 365 in Azure is voltooid.
  
## <a name="see-also"></a>Zie ook

[Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-oplossingen- en -architectuurcentrum](../solutions/solution-architecture-center.md)

[Federatieve identiteit voor Microsoft 365](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


