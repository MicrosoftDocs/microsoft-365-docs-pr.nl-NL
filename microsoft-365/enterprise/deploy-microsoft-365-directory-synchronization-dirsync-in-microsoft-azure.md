---
title: De Microsoft 365 adreslijstsynchronisatie implementeren in Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Meer informatie over het implementeren van Azure AD-Verbinding maken op een virtuele computer in Azure om accounts te synchroniseren tussen uw on-premises adreslijst en de Azure AD-tenant.
ms.openlocfilehash: 52c1bb2eb53cc4e6753d528e0d82822b2a0eebc5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919084"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>De Microsoft 365 adreslijstsynchronisatie implementeren in Microsoft Azure

Azure Active Directory (Azure AD) Verbinding maken (voorheen bekend als het hulpprogramma Adreslijstsynchronisatie, hulpprogramma Adreslijstsynchronisatie of het hulpprogramma DirSync.exe) is een toepassing die u installeert op een domeingevoegde server om uw on-premises Ad DS-gebruikers (Active Directory Domain Services) te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement. Microsoft 365 gebruikt Azure AD voor de adreslijstservice. Uw Microsoft 365-abonnement bevat een Azure AD-tenant. Deze tenant kan ook worden gebruikt voor het beheer van de identiteiten van uw organisatie met andere cloudbelastingen, waaronder andere SaaS-toepassingen en apps in Azure.

U kunt Azure AD-Verbinding maken installeren op een on-premises server, maar u kunt het ook installeren op een virtuele computer in Azure om deze redenen:
  
- U kunt servers in de cloud sneller inrichten en configureren, zodat de services sneller beschikbaar zijn voor uw gebruikers.
- Azure biedt een betere beschikbaarheid van de site met minder moeite.
- U kunt het aantal on-premises servers in uw organisatie verminderen.

Voor deze oplossing is verbinding nodig tussen uw on-premises netwerk en uw virtuele Azure-netwerk. Zie een [on-premises Verbinding maken een on-premises netwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)Microsoft Azure virtuele netwerk voor meer informatie. 
  
> [!NOTE]
> In dit artikel wordt de synchronisatie van één domein in één forest beschreven. Met Azure AD Verbinding maken worden alle AD DS-domeinen in uw Active Directory-forest gesynchroniseerd met Microsoft 365. Als u meerdere Active Directory-forests wilt synchroniseren met Microsoft 365, zie [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity). 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Overzicht van het implementeren Microsoft 365 adreslijstsynchronisatie in Azure

In het volgende diagram ziet u Azure AD Verbinding maken die wordt uitgevoerd op een virtuele computer in Azure (de adreslijstsynchronisatieserver) die een on-premises AD DS-forest synchroniseert met een Microsoft 365-abonnement.
  
![Azure AD Verbinding maken hulpprogramma op een virtuele computer in Azure waarmee on-premises accounts worden gesynchroniseerd met de Azure AD-tenant van een Microsoft 365-abonnement met verkeersstroom](../media/CP-DirSyncOverview.png)
  
In het diagram zijn er twee netwerken verbonden via een site-naar-site VPN- of ExpressRoute-verbinding. Er is een on-premises netwerk waar AD DS-domeincontrollers zich bevinden en er is een virtueel Azure-netwerk met een adreslijstsynchronisatieserver, een virtuele machine met [Azure AD-Verbinding maken.](https://www.microsoft.com/download/details.aspx?id=47594) Er zijn twee hoofdverkeersstromen die afkomstig zijn van de adreslijstsynchronisatieserver:
  
-  Azure AD Verbinding maken een domeincontroller in het on-premises netwerk opvragen voor wijzigingen in accounts en wachtwoorden.
-  Azure AD Verbinding maken stuurt de wijzigingen naar accounts en wachtwoorden naar het Azure AD-exemplaar van uw Microsoft 365 abonnement. Omdat de adreslijstsynchronisatieserver zich in een uitgebreid deel van uw on-premises netwerk heeft, worden deze wijzigingen verzonden via de proxyserver van het on-premises netwerk.
    
> [!NOTE]
> Deze oplossing beschrijft de synchronisatie van één Active Directory-domein in één Active Directory-forest. Met Azure AD Verbinding maken worden alle Active Directory-domeinen in uw Active Directory-forest gesynchroniseerd met Microsoft 365. Als u meerdere Active Directory-forests wilt synchroniseren met Microsoft 365, zie [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity). 
  
Er zijn twee belangrijke stappen bij het implementeren van deze oplossing:
  
1. Maak een virtueel Azure-netwerk en maak een SITE-to-site VPN-verbinding met uw on-premises netwerk. Zie een [on-premises Verbinding maken een on-premises netwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)Microsoft Azure virtuele netwerk voor meer informatie.
    
2. Installeer [Azure AD Verbinding maken](https://www.microsoft.com/download/details.aspx?id=47594) op een virtuele machine die is verbonden met een domein in Azure en synchroniseer vervolgens de on-premises AD DS naar Microsoft 365. Het gaat hierbij om:
    
    Een Azure Virtual Machine maken om Azure AD-Verbinding maken.
    
    Azure [AD-Verbinding maken.](https://www.microsoft.com/download/details.aspx?id=47594)
    
    Voor het configureren van Azure AD-Verbinding maken vereist de referenties (gebruikersnaam en wachtwoord) van een Azure AD-beheerdersaccount en een AD DS-ondernemingsbeheerderaccount. Azure AD Verbinding maken wordt onmiddellijk en doorlopend uitgevoerd om het on-premises AD DS-forest te synchroniseren met Microsoft 365.
    
Voordat u deze oplossing in productie implementeert, kunt u de instructies [in](simulated-ent-base-configuration-microsoft-365-enterprise.md) de gesimuleerde ondernemingsbasisconfiguratie gebruiken om deze configuratie in te stellen als een proof of concept, voor demonstraties of voor experimenten.
  
> [!IMPORTANT]
> Wanneer Azure AD Verbinding maken is voltooid, worden de referenties van de AD DS-ondernemingsbeheerder niet opgeslagen. 
  
> [!NOTE]
> In deze oplossing wordt beschreven dat één AD DS-forest wordt gesynchroniseerd met Microsoft 365. De topologie die in dit artikel wordt besproken, vertegenwoordigt slechts één manier om deze oplossing te implementeren. De topologie van uw organisatie kan verschillen op basis van uw unieke netwerkvereisten en beveiligingsoverwegingen. 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Plannen voor het hosten van een adreslijstsynchronisatieserver voor Microsoft 365 in Azure
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>Vereisten

Controleer voordat u begint de volgende vereisten voor deze oplossing:
  
- Bekijk de gerelateerde planningsinhoud in [Het virtuele Azure-netwerk plannen.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)
    
- Zorg ervoor dat u voldoet aan [alle vereisten voor](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) het configureren van het virtuele Azure-netwerk.
    
- Heb een Microsoft 365 abonnement met de active directory-integratiefunctie. Voor informatie over Microsoft 365 abonnementen gaat u naar [de pagina Microsoft 365 abonnement.](https://products.office.com/compare-all-microsoft-office-products?tab=2)
    
- Een Azure Virtual Machine inrichten die Azure AD Verbinding maken om uw on-premises AD DS-forest te synchroniseren met Microsoft 365.
    
    U moet de referenties (namen en wachtwoorden) hebben voor een AD DS-ondernemingsbeheerderaccount en een Azure AD Administrator-account.
    
### <a name="solution-architecture-design-assumptions"></a>Ontwerp-aannames voor oplossingsarchitectuur

In de volgende lijst worden de ontwerpkeuzen beschreven die voor deze oplossing zijn gemaakt.
  
- Deze oplossing maakt gebruik van één virtueel Azure-netwerk met een SITE-naar-site VPN-verbinding. Het virtuele Azure-netwerk host één subnet met één server, de adreslijstsynchronisatieserver met Azure AD-Verbinding maken. 
    
- In het on-premises netwerk zijn een domeincontroller en DNS-servers aanwezig.
    
- Azure AD Verbinding maken voert wachtwoordhashsynchronisatie uit in plaats van één aanmelding. U hoeft geen AD FS-infrastructuur (Active Directory Federation Services) te implementeren. Zie De juiste verificatiemethode kiezen voor uw Azure Active Directory [hybride identiteitsoplossing](/azure/active-directory/hybrid/choose-ad-authn)voor meer informatie over wachtwoordhashsynchronisatie en opties voor één aanmelding.
    
Er zijn extra ontwerpopties die u kunt overwegen wanneer u deze oplossing implementeert in uw omgeving. Deze omvatten de volgende:
  
- Als er bestaande DNS-servers in een bestaand virtueel Azure-netwerk zijn, bepaalt u of u de adreslijstsynchronisatieserver wilt gebruiken voor naamresolutie in plaats van DNS-servers in het on-premises netwerk.
    
- Als er domeincontrollers in een bestaand virtueel Azure-netwerk zijn, bepaalt u of het configureren van Active Directory-sites en -services een betere optie voor u kan zijn. De adreslijstsynchronisatieserver kan de domeincontrollers in het virtuele Azure-netwerk opvragen voor wijzigingen in accounts en wachtwoorden in plaats van domeincontrollers in het on-premises netwerk.
    
## <a name="deployment-roadmap"></a>Routekaart voor implementatie

Het implementeren van Azure AD Verbinding maken op een virtuele machine in Azure bestaat uit drie fasen:
  
- Fase 1: Het virtuele Azure-netwerk maken en configureren
    
- Fase 2: de virtuele Azure-machine maken en configureren
    
- Fase 3: Azure AD-Verbinding maken
    
Na de implementatie moet u ook locaties en licenties toewijzen voor de nieuwe gebruikersaccounts in Microsoft 365.


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>Fase 1: Het virtuele Azure-netwerk maken en configureren

Als u het virtuele Azure-netwerk wilt maken en configureren, voltooit u Fase [1: Uw on-premises](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) netwerk voorbereiden en Fase [2: Het cross-premises](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) virtuele netwerk in Azure maken in de implementatie roadmap van [Verbinding maken een on-premises](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)netwerk naar een Microsoft Azure virtueel netwerk.
  
Dit is uw resulterende configuratie.
  
![Fase 1 van de adreslijstsynchronisatieserver voor Microsoft 365 gehost in Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
In deze afbeelding ziet u een on-premises netwerk dat is verbonden met een virtueel Azure-netwerk via een SITE-naar-site VPN- of ExpressRoute-verbinding.
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>Fase 2: de virtuele Azure-machine maken en configureren

Maak de virtuele machine in Azure met de instructies Maak uw eerste [Windows virtuele computer in de Azure-portal.](https://go.microsoft.com/fwlink/p/?LinkId=393098) Gebruik de volgende instellingen:
  
- Selecteer in **het** deelvenster Basisbeginselen hetzelfde abonnement, dezelfde locatie en resourcegroep als uw virtuele netwerk. Neem de gebruikersnaam en het wachtwoord op een veilige locatie op. U hebt deze later nodig om verbinding te maken met de virtuele machine.
    
- Kies in **het deelvenster** Kies een grootte de **standaardgrootte A2.**
    
- Selecteer in **Instellingen** deelvenster standaardopslag in **Storage** sectie het **standaardopslagtype.** Selecteer in **de** sectie Netwerk de naam van uw virtuele netwerk en het subnet voor het hosten van de adreslijstsynchronisatieserver (niet het GatewaySubnet). Laat alle andere instellingen op hun standaardwaarden staan.
    
Controleer of uw adreslijstsynchronisatieserver DNS correct gebruikt door uw interne DNS te controleren om te controleren of er een adresrecord (A) is toegevoegd voor de virtuele computer met het IP-adres. 
  
Gebruik de instructies in [Verbinding maken virtuele computer](/azure/virtual-machines/windows/connect-logon) en meld u aan om verbinding te maken met de adreslijstsynchronisatieserver met een extern bureaubladverbinding. Nadat u zich hebt aanmelden, voegt u zich bij de virtuele machine bij het on-premises AD DS-domein.
  
Als azure AD Verbinding maken toegang wilt krijgen tot internetbronnen, moet u de adreslijstsynchronisatieserver configureren om de proxyserver van het on-premises netwerk te gebruiken. Neem contact op met de netwerkbeheerder voor eventuele aanvullende configuratiestappen.
  
Dit is uw resulterende configuratie.
  
![Fase 2 van de adreslijstsynchronisatieserver voor Microsoft 365 gehost in Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
In deze afbeelding ziet u de virtuele computer van de adreslijstsynchronisatieserver in het cross-premises virtuele Azure-netwerk.
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>Fase 3: Azure AD-Verbinding maken

Voltooi de volgende procedure:
  
1. Verbinding maken verbinding maken met de adreslijstsynchronisatieserver met een Extern bureaublad-verbinding met een AD DS-domeinaccount met lokale beheerdersbevoegdheden. Zie [Verbinding maken naar de virtuele computer en meld u aan.](/azure/virtual-machines/windows/connect-logon)
    
2. Open op de adreslijstsynchronisatieserver het artikel Adreslijstsynchronisatie instellen voor [Microsoft 365](set-up-directory-synchronization.md) en volg de aanwijzingen voor adreslijstsynchronisatie met wachtwoordsynchronisatie.
    
> [!CAUTION]
> Met Setup wordt **AAD_xxxxxxxxxxxx** account gemaakt in de organisatie-eenheid Lokale gebruikers (OU). Verplaats of verwijder dit account niet of synchronisatie mislukt.
  
Dit is uw resulterende configuratie.
  
![Fase 3 van de adreslijstsynchronisatieserver voor Microsoft 365 gehost in Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
In deze afbeelding ziet u de adreslijstsynchronisatieserver met Azure AD Verbinding maken in het cross-premises virtuele Azure-netwerk.
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>Locaties en licenties toewijzen aan gebruikers in Microsoft 365

Azure AD Verbinding maken voegt accounts toe aan uw Microsoft 365-abonnement vanuit de on-premises AD DS, maar als gebruikers zich kunnen aanmelden bij Microsoft 365 en de services ervan kunnen gebruiken, moeten de accounts zijn geconfigureerd met een locatie en licenties. Gebruik deze stappen om de locatie toe te voegen en licenties voor de juiste gebruikersaccounts te activeren:
  
1. Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com)en klik vervolgens op **Beheerder.**
    
2. Selecteer **Gebruikers > Actieve gebruikers** op de linkernavigatiebalk.
    
3. Schakel in de lijst met gebruikersaccounts het selectievakje in naast de gebruiker die u wilt activeren.
    
4. Klik op de pagina voor de gebruiker op **Bewerken** voor **productlicenties.**
    
5. Selecteer op **de pagina Productlicenties** een locatie voor de gebruiker voor **Locatie** en schakel vervolgens de juiste licenties voor de gebruiker in.
    
6. Wanneer u klaar is, **klikt u op** Opslaan en klikt u tweemaal **op** Sluiten.
    
7. Ga terug naar stap 3 voor extra gebruikers.
    
## <a name="see-also"></a>Zie ook

[Microsoft 365-oplossings- en -architectuurcentrum](../solutions/index.yml)
  
[Verbinding maken een on-premises netwerk naar een Microsoft Azure virtueel netwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Azure AD-Verbinding maken](https://www.microsoft.com/download/details.aspx?id=47594)
  
[Adreslijstsynchronisatie instellen voor Microsoft 365](set-up-directory-synchronization.md)
