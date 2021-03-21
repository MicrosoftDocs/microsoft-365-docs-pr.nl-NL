---
title: Federatieverificatie met hoge beschikbaarheid Fase 5 Federatief verificatie configureren voor Microsoft 365
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
description: 'Overzicht: Configureer Azure AD Connect voor uw federatief hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929406"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="30016-103">Federatief hoge beschikbaarheid fase 5: Federatief verificatie configureren voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30016-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="30016-104">In deze laatste fase van het implementeren van federatieverificatie met hoge beschikbaarheid voor Microsoft 365 in Azure-infrastructuurservices, krijgt en installeert u een certificaat dat is uitgegeven door een openbare certificeringsinstantie, controleert u de configuratie en installeert en vervolgens Azure AD Connect op de adreslijstsynchronisatieserver installeert en uit.</span><span class="sxs-lookup"><span data-stu-id="30016-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="30016-105">Azure AD Connect configureert uw Microsoft 365-abonnement en uw Active Directory Federation Services (AD FS) en proxyservers voor webtoepassing voor federatief verificatie.</span><span class="sxs-lookup"><span data-stu-id="30016-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="30016-106">Zie [Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="30016-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="30016-107">Een openbaar certificaat downloaden en kopiëren naar de adreslijstsynchronisatieserver</span><span class="sxs-lookup"><span data-stu-id="30016-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="30016-108">Ontvang een digitaal certificaat van een openbare certificeringsinstantie met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="30016-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="30016-109">Een X.509-certificaat dat geschikt is voor het maken van SSL-verbindingen.</span><span class="sxs-lookup"><span data-stu-id="30016-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="30016-110">De eigenschap Subject Alternative Name (SAN) is ingesteld op uw federatieservice FQDN (bijvoorbeeld: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="30016-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="30016-111">Het certificaat moet de persoonlijke sleutel hebben en worden opgeslagen in DE PFX-indeling.</span><span class="sxs-lookup"><span data-stu-id="30016-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="30016-112">Bovendien moeten computers en apparaten van uw organisatie vertrouwen op de openbare certificeringsinstantie die het digitale certificaat uitvaardigt.</span><span class="sxs-lookup"><span data-stu-id="30016-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="30016-113">Deze vertrouwensrelatie wordt tot stand gebracht door een hoofdcertificaat van de openbare certificeringsinstantie te laten installeren in de vertrouwde hoofdcertificeringsinstanties op uw computers en apparaten.</span><span class="sxs-lookup"><span data-stu-id="30016-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="30016-114">Computers waarop Microsoft Windows wordt uitgevoerd, hebben meestal een set van deze typen certificaten geïnstalleerd van veelgebruikte certificeringsinstanties.</span><span class="sxs-lookup"><span data-stu-id="30016-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="30016-115">Als het hoofdcertificaat van uw openbare certificeringsinstantie nog niet is geïnstalleerd, moet u dit implementeren op de computers en apparaten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="30016-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="30016-116">Zie Vereisten voor federatie-installatie [en configuratie](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)voor meer informatie over certificaatvereisten voor federatieverificatie.</span><span class="sxs-lookup"><span data-stu-id="30016-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="30016-117">Wanneer u het certificaat ontvangt, kopieert u het naar een map op het station C: van de adreslijstsynchronisatieserver.</span><span class="sxs-lookup"><span data-stu-id="30016-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="30016-118">Noem bijvoorbeeld het bestand SSL.pfx en sla het op in de map C: \\ Certs op de adreslijstsynchronisatieserver.</span><span class="sxs-lookup"><span data-stu-id="30016-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="30016-119">Uw configuratie verifiëren</span><span class="sxs-lookup"><span data-stu-id="30016-119">Verify your configuration</span></span>

<span data-ttu-id="30016-120">U moet nu klaar zijn om Azure AD Connect en federatief verificatie voor Microsoft 365 te configureren.</span><span class="sxs-lookup"><span data-stu-id="30016-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="30016-121">Om ervoor te zorgen dat u dat bent, is hier een controlelijst:</span><span class="sxs-lookup"><span data-stu-id="30016-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="30016-122">Het openbare domein van uw organisatie wordt toegevoegd aan uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="30016-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="30016-123">De Microsoft 365-gebruikersaccounts van uw organisatie zijn geconfigureerd op de openbare domeinnaam van uw organisatie en kunnen zich met succes aanmelden.</span><span class="sxs-lookup"><span data-stu-id="30016-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="30016-124">U hebt een federatieservice FQDN bepaald op basis van uw openbare domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="30016-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="30016-125">Een openbare DNS A-record voor uw federatieservice FQDN wijst naar het openbare IP-adres van de op internet gerichte Azure Load Balancer voor de proxyservers van de webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="30016-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="30016-126">Een persoonlijke DNS A-record voor uw federatieservice FQDN wijst naar het persoonlijke IP-adres van de interne Azure Load Balancer voor de AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="30016-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="30016-127">Een digitaal certificaat van de openbare certificeringsinstantie dat geschikt is voor SSL-verbindingen met de SAN-set voor uw federatieservice FQDN, is een PFX-bestand dat is opgeslagen op uw adreslijstsynchronisatieserver.</span><span class="sxs-lookup"><span data-stu-id="30016-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="30016-128">Het hoofdcertificaat voor de openbare certificeringsinstantie is geïnstalleerd in de Store vertrouwde hoofdcertificeringsinstanties op uw computers en apparaten.</span><span class="sxs-lookup"><span data-stu-id="30016-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="30016-129">Hier is een voorbeeld voor de Contoso-organisatie:</span><span class="sxs-lookup"><span data-stu-id="30016-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="30016-130">**Een voorbeeldconfiguratie voor een federatief verificatie-infrastructuur met hoge beschikbaarheid in Azure**</span><span class="sxs-lookup"><span data-stu-id="30016-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Een voorbeeldconfiguratie van de hoge beschikbaarheid van Microsoft 365 federatief verificatie-infrastructuur in Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="30016-132">Azure AD Connect uitvoeren om federatief verificatie te configureren</span><span class="sxs-lookup"><span data-stu-id="30016-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="30016-133">Met het hulpprogramma Azure AD Connect worden de AD FS-servers, de proxyservers van de webtoepassing en Microsoft 365 geconfigureerd voor federatief verificatie met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="30016-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="30016-134">Maak een externe bureaubladverbinding met uw adreslijstsynchronisatieserver met een domeinaccount met lokale beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="30016-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="30016-135">Open Internet Explorer op het bureaublad van de adreslijstsynchronisatieserver en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="30016-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="30016-136">Klik op **de pagina Microsoft Azure Active Directory Connect** op **Downloaden** en klik vervolgens op **Uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="30016-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="30016-137">Klik op **de pagina Welkom bij Azure AD Connect** op **Ik** ga akkoord en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="30016-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="30016-138">Klik op **de pagina Express-instellingen** op **Aanpassen.**</span><span class="sxs-lookup"><span data-stu-id="30016-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="30016-139">Klik op **de pagina Vereiste onderdelen installeren** op **Installeren.**</span><span class="sxs-lookup"><span data-stu-id="30016-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="30016-140">Klik op de pagina **gebruikersaanmelding** op **federatie met AD FS** en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="30016-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="30016-141">Typ op **de pagina Verbinding** maken met Azure AD de naam en het wachtwoord van een globale beheerdersaccount voor uw Microsoft 365-abonnement en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30016-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="30016-142">Controleer  op de pagina Uw mappen verbinden of uw on-premises AD DS-forest (Active Directory Domain Services) is geselecteerd in **Forest,** typ de naam en het wachtwoord van een domeinbeheerderaccount, klik op **Adreslijst** toevoegen en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30016-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="30016-143">Klik op **de configuratiepagina voor** aanmelding van Azure AD op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="30016-144">Klik op **de filterpagina Domein** en OE op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="30016-145">Klik op **de pagina Unieke identificatie van uw gebruikers** op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="30016-146">Klik op **de pagina Gebruikers en apparaten filteren** op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="30016-147">Klik op **de pagina** Optionele functies op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="30016-148">Klik op **de pagina AD FS-farm** op **Een nieuwe AD FS-farm configureren.**</span><span class="sxs-lookup"><span data-stu-id="30016-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="30016-149">Klik **op Bladeren** en geef de locatie en naam van het SSL-certificaat van de openbare certificeringsinstantie op.</span><span class="sxs-lookup"><span data-stu-id="30016-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="30016-150">Wanneer u daarom wordt gevraagd, typt u het certificaatwachtwoord en klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="30016-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="30016-151">Controleer of **de naam van de** onderwerpnaam en **federatieservice** zijn ingesteld op uw federatieservice FQDN en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="30016-152">Typ op **de pagina AD FS-servers** de naam van de eerste AD FS-server (Tabel M - Item 4 - kolom virtuele machinenaam) en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="30016-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="30016-153">Typ de naam van de tweede AD FS-server (tabel M - item 5 - kolom virtuele machinenaam), klik op Toevoegen **en** klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="30016-154">Typ op **de pagina Proxyservers** voor webtoepassing de naam van de eerste webtoepassingsproxyserver (Tabel M - Item 6 - kolom virtuele computernaam) en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="30016-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="30016-155">Typ de naam van de tweede webtoepassingsproxyserver (tabel M - item 7 - kolom virtuele computernaam), klik op Toevoegen **en** klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="30016-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="30016-156">Typ op **de pagina Referenties van domeinbeheerder** de gebruikersnaam en het wachtwoord van een domeinbeheerderaccount en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30016-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="30016-157">Typ op **de pagina AD FS-serviceaccount** de gebruikersnaam en het wachtwoord van een bedrijfsbeheerderaccount en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30016-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="30016-158">Selecteer op **de pagina Azure AD Domain** in **Domain** de DNS-domeinnaam van uw organisatie en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30016-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="30016-159">Klik op de pagina **Gereed voor configureren** op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="30016-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="30016-160">Klik op de pagina **installeren voltooid** op **verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="30016-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="30016-161">U ziet twee berichten die aangeven dat zowel het intranet als de internetconfiguratie is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="30016-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="30016-162">In het intranetbericht moet het persoonlijke IP-adres van uw interne Azure-laadsaldor voor uw AD FS-servers worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="30016-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="30016-163">In het internetbericht moet het openbare IP-adres van uw Azure Internet-laadsaldor voor proxyservers voor webtoepassing worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="30016-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="30016-164">Klik op de pagina **Installatie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="30016-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="30016-165">Hier is de definitieve configuratie, met namen van tijdelijke aanduidingen voor de servers.</span><span class="sxs-lookup"><span data-stu-id="30016-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="30016-166">**Fase 5: De uiteindelijke configuratie van een federatief verificatie-infrastructuur met hoge beschikbaarheid in Azure**</span><span class="sxs-lookup"><span data-stu-id="30016-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![De uiteindelijke configuratie van de microsoft 365 federatie-infrastructuur voor federatieverificatie met hoge beschikbaarheid in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="30016-168">Uw federatief verificatie-infrastructuur met hoge beschikbaarheid voor Microsoft 365 in Azure is voltooid.</span><span class="sxs-lookup"><span data-stu-id="30016-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30016-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="30016-169">See Also</span></span>

[<span data-ttu-id="30016-170">Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="30016-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="30016-171">Federatief identiteit voor uw Microsoft 365-dev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="30016-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="30016-172">Microsoft 365-oplossings- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="30016-172">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="30016-173">Federatief identiteit voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30016-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)