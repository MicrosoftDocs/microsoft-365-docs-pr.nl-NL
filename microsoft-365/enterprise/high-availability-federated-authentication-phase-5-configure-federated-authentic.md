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
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="28ab0-103">Federatieve authenticatiefase van hoge beschikbaarheid 5: federatieve verificatie voor Microsoft 365 configureren</span><span class="sxs-lookup"><span data-stu-id="28ab0-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="28ab0-104">In deze laatste fase van de implementatie van federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure-infrastructuurservices, installeert en installeert u een certificaat dat is uitgegeven door een openbare certificeringsinstantie, controleert u de configuratie en voert u Azure AD Connect op de adreslijstsynchronisatie server uit.</span><span class="sxs-lookup"><span data-stu-id="28ab0-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="28ab0-105">Met Azure AD Connect worden uw Microsoft 365-abonnement en de proxyservers voor Active Directory Federation Services (AD FS) en webtoepassingsproxy (Active Directory Federation Services) en webtoepassingsproxy-servers geconfigureerd voor Federatie verificatie.</span><span class="sxs-lookup"><span data-stu-id="28ab0-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="28ab0-106">Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="28ab0-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="28ab0-107">Een openbaar certificaat aanvragen en kopiëren naar de adreslijstsynchronisatie server</span><span class="sxs-lookup"><span data-stu-id="28ab0-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="28ab0-108">U ontvangt een digitaal certificaat van een openbare certificeringsinstantie met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="28ab0-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="28ab0-109">Een X. 509-certificaat geschikt voor het maken van SSL-verbindingen.</span><span class="sxs-lookup"><span data-stu-id="28ab0-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="28ab0-110">De uitgebreide eigenschap Subject name (SAN) wordt ingesteld op de naam van uw Federation-service (voorbeeld: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="28ab0-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="28ab0-111">Het certificaat moet de persoonlijke sleutel hebben en zijn opgeslagen in de PFX-indeling.</span><span class="sxs-lookup"><span data-stu-id="28ab0-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="28ab0-112">Daarnaast moeten uw computers en apparaten van uw organisatie de openbare certificeringsinstantie die het digitaal certificaat uitgeeft, vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="28ab0-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="28ab0-113">Deze vertrouw baarheid wordt bepaald door een basiscertificaat te gebruiken van de openbare certificeringsinstantie die in het archief met vertrouwde basiscertificeringsinstanties op uw computers en apparaten is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="28ab0-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="28ab0-114">Voor computers waarop Microsoft Windows wordt uitgevoerd is meestal een reeks van deze typen certificaten geïnstalleerd van veelgebruikte certificeringsinstanties.</span><span class="sxs-lookup"><span data-stu-id="28ab0-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="28ab0-115">Als het basiscertificaat van uw openbare certificeringsinstantie nog niet is geïnstalleerd, moet u dit implementeren op de computers en apparaten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="28ab0-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="28ab0-116">Zie vereisten [voor Federatie installeren en configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)voor meer informatie over de certificaatvereisten voor federatieve verificatie.</span><span class="sxs-lookup"><span data-stu-id="28ab0-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="28ab0-117">Wanneer u het certificaat ontvangt, kopieert u het naar een map op C: station van de adreslijstsynchronisatie server.</span><span class="sxs-lookup"><span data-stu-id="28ab0-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="28ab0-118">Geef bijvoorbeeld het bestand SSL. pfx op en sla dit op in de map C: \\ certs op de adreslijstsynchronisatie server.</span><span class="sxs-lookup"><span data-stu-id="28ab0-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="28ab0-119">De configuratie verifiëren</span><span class="sxs-lookup"><span data-stu-id="28ab0-119">Verify your configuration</span></span>

<span data-ttu-id="28ab0-120">Nu moet u Azure AD Connect en federatieve verificatie voor Microsoft 365 configureren.</span><span class="sxs-lookup"><span data-stu-id="28ab0-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="28ab0-121">U kunt er ook voor zorgen dat u het volgende ziet:</span><span class="sxs-lookup"><span data-stu-id="28ab0-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="28ab0-122">Het openbare domein van uw organisatie wordt toegevoegd aan uw abonnement op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28ab0-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="28ab0-123">De Microsoft 365-gebruikersaccounts van uw organisatie zijn geconfigureerd voor de openbare domeinnaam van uw organisatie en kan zich nu aanmelden.</span><span class="sxs-lookup"><span data-stu-id="28ab0-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="28ab0-124">U hebt een Federatie service-FQDN vastgesteld op basis van uw openbare domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="28ab0-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="28ab0-125">Een openbare DNS-record voor de FQDN van de Federation service verwijst naar het openbare IP-adres van de Azure-Load Balancer op internet voor de webtoepassingsproxy-servers.</span><span class="sxs-lookup"><span data-stu-id="28ab0-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="28ab0-126">Een persoonlijke DNS-record voor de FQDN van de Federation service verwijst naar het persoonlijke IP-adres van de interne Azure Load Balancer voor de AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="28ab0-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="28ab0-127">Een openbare certificeringsinstantie-digitaal certificaat voor isssued dat geschikt is voor SSL-verbindingen met de SAN-set met de Federatie service FQDN is een PFX-bestand dat is opgeslagen op de adreslijstsynchronisatie server.</span><span class="sxs-lookup"><span data-stu-id="28ab0-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="28ab0-128">Het basiscertificaat voor de openbare certificeringsinstantie wordt in de lijst met vertrouwde basiscertificeringsinstanties geïnstalleerd op uw computer en apparaten.</span><span class="sxs-lookup"><span data-stu-id="28ab0-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="28ab0-129">Hier ziet u een voorbeeld van de contoso-organisatie:</span><span class="sxs-lookup"><span data-stu-id="28ab0-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="28ab0-130">**Een voorbeeld configuratie voor een federatieve verificatie-infrastructuur met hoge beschikbaarheid in azure**</span><span class="sxs-lookup"><span data-stu-id="28ab0-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Een voorbeeld van de configuratie van de High Availability Microsoft 365 federatieve verificatie-infrastructuur in azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="28ab0-132">Azure AD Connect uitvoeren om federatieve verificatie te configureren</span><span class="sxs-lookup"><span data-stu-id="28ab0-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="28ab0-133">Met het hulpprogramma Azure AD Connect worden de AD FS-servers, de webtoepassingsproxy en Microsoft 365 voor federatieve verificatie met de volgende stappen geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="28ab0-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="28ab0-134">Maak een verbinding met extern bureaublad met de adreslijstsynchronisatie server met een domeinaccount met lokale beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="28ab0-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="28ab0-135">Open op de computer van de adreslijstsynchronisatie server Internet Explorer en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="28ab0-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="28ab0-136">Klik op de pagina **Microsoft Azure Active Directory Connect** op **downloaden**en klik vervolgens op **uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="28ab0-137">Klik op de pagina **Welkom bij Azure AD Connect** op **Ik ga akkoord**en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="28ab0-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="28ab0-138">Klik op de pagina **Express Settings** op **Customize**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="28ab0-139">Klik op de pagina **vereiste onderdelen installeren** op **installeren**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="28ab0-140">Klik op de pagina **gebruikersaanmelding** op **federatie met AD FS**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="28ab0-141">Typ op de pagina **verbinding maken met Azure AD** de naam en het wachtwoord voor het globale beheerdersaccount voor uw abonnement op microsoft 365 en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="28ab0-142">Zorg ervoor dat op de pagina **verbinding maken met uw** telefoonnummers het domein Active Directory Domain Services (AD DS) is geselecteerd in **het forest**, typ de naam en het wachtwoord van een domeinbeheerdersaccount en **Klik op** **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="28ab0-143">Klik op de pagina met **aanmeld configuraties van Azure AD** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="28ab0-144">Klik op de pagina **domein en ou filtering** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="28ab0-145">Op de pagina **unieke identificatie van uw gebruikers klikt u** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="28ab0-146">Klik op de pagina **gebruikers en apparaten filteren** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="28ab0-147">Klik op de pagina **optionele functies** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="28ab0-148">Klik op de **AD FS-Farm** pagina op **een nieuwe AD FS-farm configureren**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="28ab0-149">Klik op **Bladeren** en geef de locatie en de naam op van het SSL-certificaat van de openbare certificeringsinstantie.</span><span class="sxs-lookup"><span data-stu-id="28ab0-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="28ab0-150">Wanneer u hierom wordt gevraagd, typt u het certificaatwachtwoord en klikt u vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="28ab0-151">Controleer of de naam van het **onderwerp** en de naam van de **Federation service** zijn ingesteld op de FQDN van de Federation service en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="28ab0-152">Op de pagina **AD FS servers** typt u de naam van de eerste AD FS-server (tabel M-item 4-kolomnaam van virtuele machine) en klikt u vervolgens op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="28ab0-153">Typ de naam van de tweede AD FS-server (tabel M-item 5-kolom met virtuele machinenaam), klik op **toevoegen**en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="28ab0-154">Typ op de pagina **Webtoepassings proxyservers** de naam van de eerste server van de webtoepassing (tabel M-item 6-kolomnaam van virtuele machine) en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="28ab0-155">Typ de naam van de tweede server van de webtoepassingsproxy (tabel M-item 7: kolomnaam van virtuele machine), klik op **toevoegen**en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="28ab0-156">Typ op de pagina **referenties van domeinbeheerder** de gebruikersnaam en het wachtwoord van een domeinbeheerdersaccount en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="28ab0-157">Typ op de pagina **AD FS service-account** de gebruikersnaam en het wachtwoord van een beheerder account van een beheerder en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="28ab0-158">Selecteer op de pagina **Azure AD domain** in **Domain**de naam van de DNS-domeinnaam van uw organisatie en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="28ab0-159">Klik op de pagina **Gereed voor configureren** op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="28ab0-160">Klik op de pagina **installeren voltooid** op **verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="28ab0-161">U ziet twee berichten om aan te geven dat zowel het intranet als de Internet configuratie zijn geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="28ab0-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="28ab0-162">In het intranet bericht moet het persoonlijke IP-adres van uw Azure Internal Load Balancer voor uw AD FS-servers worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="28ab0-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="28ab0-163">Het Internet bericht moet worden vermeld in het openbare IP-adres van uw Azure Internet Facing Load Balancer voor de proxyservers van uw webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="28ab0-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="28ab0-164">Klik op de pagina **Installatie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="28ab0-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="28ab0-165">Dit is de laatste configuratie, met de namen van de tijdelijke aanduidingen voor de servers.</span><span class="sxs-lookup"><span data-stu-id="28ab0-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="28ab0-166">**Fase 5: de laatste configuratie van een federatieve verificatie-infrastructuur met hoge beschikbaarheid in azure**</span><span class="sxs-lookup"><span data-stu-id="28ab0-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![De laatste configuratie van de High Availability Microsoft 365 federatieve verificatie-infrastructuur in azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="28ab0-168">Uw federatieve verificatie-infrastructuur van hoge beschikbaarheid voor Microsoft 365 in Azure is voltooid.</span><span class="sxs-lookup"><span data-stu-id="28ab0-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28ab0-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="28ab0-169">See Also</span></span>

[<span data-ttu-id="28ab0-170">Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure</span><span class="sxs-lookup"><span data-stu-id="28ab0-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="28ab0-171">Federatieve identiteit voor uw Microsoft 365 dev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="28ab0-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="28ab0-172">Microsoft 365-oplossingen- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="28ab0-172">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="28ab0-173">Federatieve identiteit voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28ab0-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


