---
title: Geavanceerde audit instellen in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u Advanced Audit in kunt stellen, zodat u gerechtelijke onderzoeken kunt uitvoeren wanneer gebruikersaccounts worden gehackt of om andere beveiligingsgerelateerde incidenten te onderzoeken.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314301"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="ff312-103">Geavanceerde audit instellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff312-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="ff312-104">Als uw organisatie een abonnements- en eindgebruikerslicentie heeft die Geavanceerde controle ondersteunt, voert u de volgende stappen uit om de extra mogelijkheden in Advanced Audit in te stellen en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ff312-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Werkstroom voor het instellen van geavanceerde controle](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="ff312-106">Stap1: Geavanceerde controle instellen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="ff312-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="ff312-107">Geavanceerde auditfuncties, zoals de mogelijkheid om belangrijke gebeurtenissen, zoals MailItemsAccessed en Verzenden, bij te houden, vereisen een geschikte E5-licentie die aan gebruikers is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="ff312-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="ff312-108">Daarnaast moet het advanced auditing app/service plan zijn ingeschakeld voor deze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ff312-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="ff312-109">Als u wilt controleren of de app Geavanceerd controleren is toegewezen aan gebruikers, voert u de volgende stappen voor elke gebruiker uit:</span><span class="sxs-lookup"><span data-stu-id="ff312-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="ff312-110">Ga in [Microsoft 365 beheercentrum](https://admin.microsoft.com/Adminportal)naar **Gebruikers**  >  **actieve gebruikers** en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ff312-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="ff312-111">Klik op de flyoutpagina met gebruikerseigenschappen op **Licenties en apps.**</span><span class="sxs-lookup"><span data-stu-id="ff312-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="ff312-112">Controleer in **de sectie** Licenties of aan de gebruiker een E5-licentie is toegewezen of dat aan de gebruiker een geschikte invoeglicentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="ff312-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="ff312-113">Zie Licentievereisten voor geavanceerde audit voor een lijst met licenties die Geavanceerde controle [ondersteunen.](auditing-solutions-overview.md#advanced-audit-1)</span><span class="sxs-lookup"><span data-stu-id="ff312-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="ff312-114">Vouw de **sectie Apps** uit en controleer of Microsoft 365 **selectievakje** Geavanceerd controleren is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ff312-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="ff312-115">Als het selectievakje niet is geselecteerd, selecteert u het selectievakje en klikt u op **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ff312-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="ff312-116">De logboekregistratie van auditrecords voor MailItemsAccessed en Verzenden begint binnen 24 uur.</span><span class="sxs-lookup"><span data-stu-id="ff312-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="ff312-117">U moet stap 3 uitvoeren om te beginnen met het registreren van twee andere belangrijke gebeurtenissen voor geavanceerde audit: SearchQueryInitiatedExchange en SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff312-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="ff312-118">Voor organisaties die licenties toewijzen aan groepen gebruikers met behulp van groepslicenties, moet u de licentietoewijzing voor Microsoft 365 Advanced Auditing voor de groep uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ff312-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="ff312-119">Nadat u de wijzigingen hebt op slaan, controleert u of Microsoft 365 Geavanceerd controleren is uitgeschakeld voor de groep.</span><span class="sxs-lookup"><span data-stu-id="ff312-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="ff312-120">Schakel vervolgens de licentietoewijzing voor de groep weer in.</span><span class="sxs-lookup"><span data-stu-id="ff312-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="ff312-121">Zie Licenties toewijzen aan gebruikers op basis van [groepslidmaatschap in](/azure/active-directory/users-groups-roles/licensing-groups-assign)Azure Active Directory voor instructies over groepslicenties.</span><span class="sxs-lookup"><span data-stu-id="ff312-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="ff312-122">Als u de postvakacties hebt aangepast die zijn aangemeld bij gebruikerspostvakken of gedeelde postvakken, worden nieuwe belangrijke gebeurtenissen die door Microsoft zijn uitgebracht, niet automatisch gecontroleerd op die postvakken.</span><span class="sxs-lookup"><span data-stu-id="ff312-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="ff312-123">Zie de sectie 'Standaard aangemelde postvakacties wijzigen of herstellen' in Postvakcontrole beheren voor informatie over het wijzigen van de postvakacties die worden gecontroleerd voor elk [aanmeldingstype.](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)</span><span class="sxs-lookup"><span data-stu-id="ff312-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="ff312-124">Stap 2: Cruciale gebeurtenissen inschakelen</span><span class="sxs-lookup"><span data-stu-id="ff312-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="ff312-125">U moet twee belangrijke gebeurtenissen (SearchQueryInitiatedExchange en SearchQueryInitiatedSharePoint) inschakelen om te worden geregistreerd wanneer gebruikers zoekopdrachten uitvoeren in Exchange Online en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ff312-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="ff312-126">Als u wilt dat deze twee gebeurtenissen worden gecontroleerd voor gebruikers, moet u de volgende opdracht (voor elke gebruiker) uitvoeren in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ff312-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="ff312-127">In een multi-geoomgeving moet u  de vorige opdracht Postvak instellen uitvoeren in het bos waar het postvak van de gebruiker zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="ff312-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="ff312-128">Voer de volgende opdracht uit om de postvaklocatie van de gebruiker te identificeren:</span><span class="sxs-lookup"><span data-stu-id="ff312-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="ff312-129">Als de opdracht voor het inschakelen van het controleren van zoekquery's eerder is uitgevoerd in een forest dat anders is dan het postvak van de gebruiker, moet u de waarde SearchQueryInitiated verwijderen uit het postvak van de gebruiker door deze uit te voeren en vervolgens toe te voegen aan het postvak van de gebruiker in het forest waar het postvak van de gebruiker `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="ff312-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="ff312-130">Stap 3: Beleid voor controlebewaring instellen</span><span class="sxs-lookup"><span data-stu-id="ff312-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="ff312-131">Naast het standaardbeleid dat Exchange-, SharePoint- en Azure AD-auditrecords één jaar behoudt, kunt u aanvullende bewaarbeleidsregels voor auditlogboek maken om te voldoen aan de vereisten van de beveiligingsbewerkingen, IT- en complianceteams van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ff312-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="ff312-132">Zie voor meer informatie [Bewaarbeleid voor auditlogboeken beheren](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ff312-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="ff312-133">Stap 4: Zoeken naar belangrijke gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="ff312-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="ff312-134">Nu u geavanceerde controle hebt ingesteld voor uw organisatie, kunt u zoeken naar belangrijke gebeurtenissen en andere activiteiten bij het uitvoeren van gerechtelijke onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="ff312-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="ff312-135">Nadat u stap 1 en stap 2 hebt uitgevoerd, kunt u in het auditlogboek zoeken naar belangrijke gebeurtenissen en andere activiteiten tijdens het gerechtelijk onderzoek naar gecompromitteerde accounts en andere soorten beveiligings- of complianceonderzoeken.</span><span class="sxs-lookup"><span data-stu-id="ff312-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="ff312-136">Zie Geavanceerde controle gebruiken om gecompromitteerde accounts te onderzoeken voor meer informatie over het uitvoeren van een onderzoek naar gecompromitteerde [gebruikersaccounts](mailitemsaccessed-forensics-investigations.md)met behulp van de cruciale gebeurtenis MailItemsAccessed.</span><span class="sxs-lookup"><span data-stu-id="ff312-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
