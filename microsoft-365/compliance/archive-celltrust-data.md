---
title: Een connector instellen voor het archiveren van CellTrust-gegevens in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van CellTrust-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 855d48303c7c35c32951105799aa117675820420
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162359"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a><span data-ttu-id="d4342-105">Een verbindingslijn instellen voor het archiveren van CellTrust-gegevens</span><span class="sxs-lookup"><span data-stu-id="d4342-105">Set up a connector to archive CellTrust data</span></span>

<span data-ttu-id="d4342-106">Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van het CellTrust-platform te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="d4342-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the CellTrust platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d4342-107">Veritas biedt een [CellTrust-connector](https://globanet.com/celltrust/) die items uit de gegevensbron van derden vast legt en deze items importeert naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4342-107">Veritas provides a [CellTrust](https://globanet.com/celltrust/) connector that captures items from the third-party data source and imports those items to Microsoft 365.</span></span> <span data-ttu-id="d4342-108">De connector converteert de inhoud van Sms berichten van CellTrust-accounts naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4342-108">The connector converts the content of SMS messages from CellTrust accounts to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d4342-109">Nadat CellTrust-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="d4342-109">After CellTrust data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="d4342-110">Als u een CellTrust-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="d4342-110">Using a CellTrust connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-celltrust-data"></a><span data-ttu-id="d4342-111">Overzicht van het archiveren van CellTrust-gegevens</span><span class="sxs-lookup"><span data-stu-id="d4342-111">Overview of archiving CellTrust data</span></span>

<span data-ttu-id="d4342-112">In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van CellTrust-gegevens in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4342-112">The following overview explains the process of using a connector to archive CellTrust data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor CellTrust-gegevens](../media/CellTrustConnectorWorkflow.png)

1. <span data-ttu-id="d4342-114">Uw organisatie werkt samen met CellTrust om een CellTrust-site in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="d4342-114">Your organization works with CellTrust to set up and configure a CellTrust site.</span></span>

2. <span data-ttu-id="d4342-115">Elke 24 uur worden CellTrust-items gekopieerd naar de Veritas Merge1-site.</span><span class="sxs-lookup"><span data-stu-id="d4342-115">Once every 24 hours, CellTrust items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="d4342-116">De verbindingslijn converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="d4342-116">The connector also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="d4342-117">De CellTrust-connector die u in het Microsoft 365-compliancecentrum maakt, maakt elke dag verbinding met de Veritas Merge1-site en brengt de berichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="d4342-117">The CellTrust connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d4342-118">De automatische gebruikerstoewijzing als verbindingslijn importeert items naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="d4342-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="d4342-119">Er wordt een submap in de map Postvak IN met de naam **CellTrust** gemaakt in de postvakken van de gebruiker en de berichtitems worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="d4342-119">A subfolder in the Inbox folder named **CellTrust** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="d4342-120">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="d4342-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d4342-121">Elk CellTrust-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="d4342-121">Every CellTrust item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d4342-122">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="d4342-122">Before you begin</span></span>

- <span data-ttu-id="d4342-123">Maak een Merge1-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="d4342-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d4342-124">Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken.</span><span class="sxs-lookup"><span data-stu-id="d4342-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="d4342-125">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="d4342-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d4342-126">De gebruiker die de CellTrust-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d4342-126">The user who creates the CellTrust connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d4342-127">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d4342-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d4342-128">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d4342-128">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d4342-129">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d4342-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d4342-130">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="d4342-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d4342-131">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="d4342-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-celltrust-connector"></a><span data-ttu-id="d4342-132">Stap 1: De CellTrust-connector instellen</span><span class="sxs-lookup"><span data-stu-id="d4342-132">Step 1: Set up the CellTrust connector</span></span>

<span data-ttu-id="d4342-133">De eerste stap is toegang tot de gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor CellTrust-gegevens.</span><span class="sxs-lookup"><span data-stu-id="d4342-133">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for CellTrust data.</span></span>

1. <span data-ttu-id="d4342-134">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren** \> **CellTrust.**</span><span class="sxs-lookup"><span data-stu-id="d4342-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **CellTrust**.</span></span>

2. <span data-ttu-id="d4342-135">Klik op **de pagina Productbeschrijving van CellTrust** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d4342-135">On the **CellTrust** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d4342-136">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="d4342-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d4342-137">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="d4342-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="d4342-138">Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.</span><span class="sxs-lookup"><span data-stu-id="d4342-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="d4342-139">Stap 2: De CellTrust-connector configureren op de Veritas Merge1-site</span><span class="sxs-lookup"><span data-stu-id="d4342-139">Step 2: Configure the CellTrust connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="d4342-140">De tweede stap is het configureren van de CellTrust-connector op de Veritas Merge1-site.</span><span class="sxs-lookup"><span data-stu-id="d4342-140">The second step is to configure the CellTrust connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="d4342-141">Zie Gebruikershandleiding voor [connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de CellTrust-connector.</span><span class="sxs-lookup"><span data-stu-id="d4342-141">For information about how to configure the CellTrust connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d4342-142">Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d4342-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d4342-143">Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien</span><span class="sxs-lookup"><span data-stu-id="d4342-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d4342-144">Als u gebruikers wilt in kaart brengen en de connector wilt voltooien die is ingesteld in het Microsoft 365 compliancecentrum, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d4342-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="d4342-145">Schakel op **de pagina CellTrust-gebruikers toewijzen Microsoft 365 gebruikers automatisch** toewijzen in.</span><span class="sxs-lookup"><span data-stu-id="d4342-145">On the **Map CellTrust users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d4342-146">De CellTrust-items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d4342-146">The CellTrust items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d4342-147">Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d4342-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d4342-148">Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d4342-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-celltrust-connector"></a><span data-ttu-id="d4342-149">Stap 4: De CellTrust-verbindingslijn controleren</span><span class="sxs-lookup"><span data-stu-id="d4342-149">Step 4: Monitor the CellTrust connector</span></span>

<span data-ttu-id="d4342-150">Nadat u de CellTrust-verbindingslijn hebt maken, kunt u de status van de verbindingslijn weergeven in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d4342-150">After you create the CellTrust connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d4342-151">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="d4342-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d4342-152">Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **CellTrust-verbindingslijn** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="d4342-152">Click the **Connectors** tab and then select the **CellTrust** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d4342-153">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="d4342-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d4342-154">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="d4342-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d4342-155">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="d4342-155">Known issues</span></span>

- <span data-ttu-id="d4342-156">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="d4342-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d4342-157">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d4342-157">Support for larger items will be available at a later date.</span></span>