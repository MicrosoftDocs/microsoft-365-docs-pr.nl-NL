---
title: Problemen met adreslijstsynchronisatie in Microsoft 365 oplossen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Beschrijving van de meest voorkomende oorzaken van problemen met adreslijstsynchronisatie in Microsoft 365 en enkele manieren waarmee u ze kunt oplossen.
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689485"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="4e0de-103">Problemen met adreslijstsynchronisatie in Microsoft 365 oplossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-103">Fixing problems with directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="4e0de-104">Met adreslijstsynchronisatie kunt u gebruikers en groepen on-premises blijven beheren, en toevoegingen, verwijderingen en wijzigingen met de cloud synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="4e0de-104">With directory synchronization, you can continue to manage users and groups on-premises and synchronize additions, deletions, and changes to the cloud.</span></span> <span data-ttu-id="4e0de-105">De installatie is een beetje ingewikkeld en het kan soms lastig zijn om de bron van de problemen te identificeren.</span><span class="sxs-lookup"><span data-stu-id="4e0de-105">But setup is a little complicated and it can sometimes be difficult to identify the source of problems.</span></span> <span data-ttu-id="4e0de-106">We beschikken over informatiebronnen waarmee u potentiële problemen kunt opsporen en oplossen.</span><span class="sxs-lookup"><span data-stu-id="4e0de-106">We have resources to help you identify potential issues and fix them.</span></span>
  
## <a name="how-do-i-know-if-something-is-wrong"></a><span data-ttu-id="4e0de-107">Hoe weet ik of er iets mis is?</span><span class="sxs-lookup"><span data-stu-id="4e0de-107">How do I know if something is wrong?</span></span>

<span data-ttu-id="4e0de-108">De eerste aanwijzing dat er iets mis is, is wanneer de tegel DirSync-status in het Microsoft 365-beheercentrum aangeeft dat er een probleem is.</span><span class="sxs-lookup"><span data-stu-id="4e0de-108">The first indication that something is wrong is when the DirSync Status tile in the Microsoft 365 admin center indicates there is a problem.</span></span>
  
<span data-ttu-id="4e0de-109">U ontvangt ook een e-mailbericht (op het alternatieve e-mailadres en uw beheerderse-mailadres) van Microsoft 365 waarin wordt aangegeven dat er adreslijstsynchronisatiefouten zijn opgetreden in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4e0de-109">You will also receive a mail (to the alternate email and to your admin email) from Microsoft 365 that indicates your tenant has encountered directory synchronization errors.</span></span> <span data-ttu-id="4e0de-110">Zie [Fouten met adreslijstsynchronisatie herkennen in Microsoft 365](identify-directory-synchronization-errors.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4e0de-110">For details see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a><span data-ttu-id="4e0de-111">Hoe kom ik aan het hulpprogramma Azure Active Directory Connect?</span><span class="sxs-lookup"><span data-stu-id="4e0de-111">How do I get Azure Active Directory Connect tool?</span></span>

<span data-ttu-id="4e0de-112">Ga in het [Microsoft 365-beheercentrum](https://admin.microsoft.com) naar **Gebruikers** \> **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="4e0de-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Users** \> **Active users**.</span></span> <span data-ttu-id="4e0de-113">Klik op het menu **Meer** (drie puntjes) en selecteer **Adreslijstsynchronisatie**.</span><span class="sxs-lookup"><span data-stu-id="4e0de-113">Click the **More** menu (three dots) and select **Directory synchronization**.</span></span> 
  
<span data-ttu-id="4e0de-114">Volg de [instructies in de wizard](set-up-directory-synchronization.md) om Azure AD Connect te downloaden.</span><span class="sxs-lookup"><span data-stu-id="4e0de-114">Follow the [instructions in the wizard](set-up-directory-synchronization.md) to download Azure AD Connect.</span></span> 
  
<span data-ttu-id="4e0de-115">Als u nog steeds gebruikmaakt van Azure Active Directory (Azure AD) Sync (DirSync), vindt u in [Problemen oplossen met de installatie van het hulpprogramma Azure Active Directory-synchronisatie en foutberichten van de wizard Configuratie in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) informatie over de systeemvereisten voor de installatie van dirsync, de machtigingen die u nodig hebt en het oplossen van veelvoorkomende fouten.</span><span class="sxs-lookup"><span data-stu-id="4e0de-115">If you are still using Azure Active Directory (Azure AD) Sync (DirSync), take a look at [How to troubleshoot Azure Active Directory Sync Tool installation and Configuration Wizard error messages in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) for information about the system requirements to install dirsync, the permissions you need, and how to troubleshoot common errors.</span></span> 
  
<span data-ttu-id="4e0de-116">Zie [de instructies voor het uitvoeren van een upgrade](https://go.microsoft.com/fwlink/p/?LinkId=733240) als u Azure AD Sync wilt bijwerken naar Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4e0de-116">To update from Azure AD Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span>
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a><span data-ttu-id="4e0de-117">Veelvoorkomende oorzaken van problemen met adreslijstsynchronisatie in Microsoft 365 oplossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-117">Resolving common causes of problems with directory synchronization in Microsoft 365</span></span>

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a><span data-ttu-id="4e0de-118">Gesynchroniseerde objecten worden niet online weergegeven of bijgewerkt, of ik krijg van de service foutrapporten over synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="4e0de-118">Synchronized objects aren't appearing or updating online, or I'm getting synchronization error reports from the Service.</span></span>

- [<span data-ttu-id="4e0de-119">Tolerantie voor identiteitssynchronisatie en dubbele kenmerken</span><span class="sxs-lookup"><span data-stu-id="4e0de-119">Identity synchronization and duplicate attribute resiliency</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a><span data-ttu-id="4e0de-120">Ik krijg een melding in het beheercentrum of ik ontvang automatisch e-mailberichten dat er geen recente synchronisatiegebeurtenis is geweest</span><span class="sxs-lookup"><span data-stu-id="4e0de-120">I have an alert in the admin center, or am receiving automated emails that there hasn't been a recent synchronization event</span></span>
- [<span data-ttu-id="4e0de-121">Verbindingsproblemen met Azure AD Connect oplossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-121">Troubleshoot connectivity issues with Azure AD Connect</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [<span data-ttu-id="4e0de-122">Azure AD Connect-accounts en -machtigingen</span><span class="sxs-lookup"><span data-stu-id="4e0de-122">Azure AD Connect Accounts and permissions</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [<span data-ttu-id="4e0de-123">Azure AD Connect-synchronisatie: het Azure AD-serviceaccount beheren</span><span class="sxs-lookup"><span data-stu-id="4e0de-123">Azure AD Connect sync: How to manage the Azure AD service account</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [<span data-ttu-id="4e0de-124">Adreslijstsynchronisatie naar Azure Active Directory is gestopt of u krijgt de waarschuwing dat de synchronisatie al meer dan een dag niet is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="4e0de-124">Directory synchronization to Azure Active Directory stops or you're warned that sync hasn't registered in more than a day</span></span>](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a><span data-ttu-id="4e0de-125">Wachtwoordhashes worden niet gesynchroniseerd of ik zie in het beheercentrum een melding dat er geen recente wachtwoord-hashsynchronisatie is geweest</span><span class="sxs-lookup"><span data-stu-id="4e0de-125">Password hashes aren't synchronizing, or I'm seeing an alert in the admin center that there hasn't been a recent password hash synchronization</span></span>
- [<span data-ttu-id="4e0de-126">Wachtwoord-hashsynchronisatie met Azure AD Connect-synchronisatie implementeren</span><span class="sxs-lookup"><span data-stu-id="4e0de-126">Implementing password hash synchronization with Azure AD Connect sync</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a><span data-ttu-id="4e0de-127">Ik krijg een waarschuwing dat het objectquotum is overschreden</span><span class="sxs-lookup"><span data-stu-id="4e0de-127">I'm seeing an alert that Object quota exceeded</span></span>
- <span data-ttu-id="4e0de-128">We hebben een ingebouwd objectquotum ter bescherming van de service.</span><span class="sxs-lookup"><span data-stu-id="4e0de-128">We have a built-in object quota to help protect the service.</span></span> <span data-ttu-id="4e0de-129">Als er zich te veel objecten bevinden in de adreslijst die moet worden gesynchroniseerd met Microsoft 365, moet u [contact opnemen met de ondersteuning voor bedrijfsproducten](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) om het quotum verhogen.</span><span class="sxs-lookup"><span data-stu-id="4e0de-129">If you have too many objects in your directory that need to sync to Microsoft 365, you'll have to [Contact support for business products](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to increase your quota.</span></span>

### <a name="i-need-to-know-which-attributes-are-synchronized"></a><span data-ttu-id="4e0de-130">Ik moet weten welke kenmerken worden gesynchroniseerd</span><span class="sxs-lookup"><span data-stu-id="4e0de-130">I need to know which attributes are synchronized</span></span>
- <span data-ttu-id="4e0de-131">[Hier](https://go.microsoft.com/fwlink/p/?LinkId=396719) vindt u een lijst met alle kenmerken die worden gesynchroniseerd tussen on-premises en de cloud.</span><span class="sxs-lookup"><span data-stu-id="4e0de-131">You can find a list of all the attributes that are synced between on-premises and the cloud [right here](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a><span data-ttu-id="4e0de-132">Ik kan geen objecten beheren of verwijderen die zijn gesynchroniseerd met de cloud</span><span class="sxs-lookup"><span data-stu-id="4e0de-132">I can't manage or remove objects that were synchronized to the cloud</span></span>
- <span data-ttu-id="4e0de-133">Bent u er klaar voor alleen objecten in de cloud te beheren?</span><span class="sxs-lookup"><span data-stu-id="4e0de-133">Are you ready to manage objects in the cloud only?</span></span> <span data-ttu-id="4e0de-134">Of is er een object dat on-premises is verwijderd, maar dat vastzit in de cloud?</span><span class="sxs-lookup"><span data-stu-id="4e0de-134">Or is there an object that was deleted on-premises, but is stuck in the cloud?</span></span> <span data-ttu-id="4e0de-135">Raadpleeg [het oplossen van problemen met synchronisatie](https://go.microsoft.com/fwlink/p/?linkid=842044) en het [ondersteuningsartikel](https://go.microsoft.com/fwlink/p/?LinkId=396720) voor hulp bij het oplossen van deze problemen.</span><span class="sxs-lookup"><span data-stu-id="4e0de-135">Take a look at this [Troubleshooting Errors during synchronization](https://go.microsoft.com/fwlink/p/?linkid=842044) and [support article](https://go.microsoft.com/fwlink/p/?LinkId=396720) for guidance on how to resolve these issues.</span></span>

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a><span data-ttu-id="4e0de-136">Ik krijg het foutbericht dat mijn bedrijf het aantal objecten dat kan worden gesynchroniseerd, heeft overschreden.</span><span class="sxs-lookup"><span data-stu-id="4e0de-136">I got an error message that my company has exceeded the number of objects that can be synchronized</span></span>
- <span data-ttu-id="4e0de-137">U kunt [hier](https://go.microsoft.com/fwlink/p/?LinkId=396721) meer lezen over dit probleem.</span><span class="sxs-lookup"><span data-stu-id="4e0de-137">You can read more about this issue [here](https://go.microsoft.com/fwlink/p/?LinkId=396721).</span></span>
   
## <a name="other-resources"></a><span data-ttu-id="4e0de-138">Overige informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="4e0de-138">Other resources</span></span>

- [<span data-ttu-id="4e0de-139">Script om dubbele UPN's op te lossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-139">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [<span data-ttu-id="4e0de-140">Een niet-routeerbaar domein (zoals .lokaal) voorbereiden op adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="4e0de-140">How to prepare a non-routable domain (such as .local domain) for directory synchronization</span></span>](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [<span data-ttu-id="4e0de-141">Script om het totale aantal gesynchroniseerde objecten te tellen</span><span class="sxs-lookup"><span data-stu-id="4e0de-141">Script to count total synchronized objects</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [<span data-ttu-id="4e0de-142">Problemen met AD FS 2.0 oplossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-142">Troubleshoot AD FS 2.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [<span data-ttu-id="4e0de-143">PowerShell gebruiken om lege DisplayName-kenmerken voor groepen met e-mail op te lossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-143">Use PowerShell to fix empty DisplayName attributes for mail-enabled groups</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [<span data-ttu-id="4e0de-144">PowerShell gebruiken om dubbele UPN's op te lossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-144">Use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [<span data-ttu-id="4e0de-145">PowerShell gebruiken om dubbele e-mailadressen op te lossen</span><span class="sxs-lookup"><span data-stu-id="4e0de-145">Use PowerShell to fix duplicate email addresses</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
