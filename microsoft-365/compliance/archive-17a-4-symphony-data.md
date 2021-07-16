---
title: Een Connector voor gegevensparser van Deymfonie instellen voor het archiveren van gegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 Symphony DataParser-connector voor het importeren en archiveren van gegevens van Den Microsoft 365.
ms.openlocfilehash: 0dce81b5251612bc3c3ddb467c658bd4a32d56f7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453931"
---
# <a name="set-up-a-connector-to-archive-data-from-symphony"></a><span data-ttu-id="d7514-103">Een verbindingslijn instellen voor het archiveren van gegevens uit Deymfonie</span><span class="sxs-lookup"><span data-stu-id="d7514-103">Set up a connector to archive data from Symphony</span></span>

<span data-ttu-id="d7514-104">Gebruik de [Symphony DataParser](https://www.17a-4.com/Symphony-dataparser/) van 17a-4 LLC om communicatiegegevens van Den 17a-4 te importeren en te archiveren in postvakken van gebruikers in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="d7514-104">Use the [Symphony DataParser](https://www.17a-4.com/Symphony-dataparser/) from 17a-4 LLC to import and archive Symphony communications data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d7514-105">De DataParser bevat een Connector van Deymfonie die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7514-105">The DataParser includes a Symphony connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="d7514-106">Met de Connector Gegevensparser van Symphony worden de Gegevensparser-gegevens van Deymfonie ge converteert naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in postvakken van gebruikers in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7514-106">The Symphony DataParser connector converts Symphony data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="d7514-107">Nadat De gegevens van Symphony zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="d7514-107">After Symphony data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="d7514-108">Met behulp van een Connector voor Het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="d7514-108">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="d7514-109">Overzicht van het archiveren van De gegevens van Dessymfonie</span><span class="sxs-lookup"><span data-stu-id="d7514-109">Overview of archiving Symphony data</span></span>

<span data-ttu-id="d7514-110">In het volgende overzicht wordt uitgelegd hoe het gebruik van een gegevensconnector wordt gebruikt voor het archiveren van Gegevens van Deymfonie in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7514-110">The following overview explains the process of using a data connector to archive Symphony data in Microsoft 365.</span></span>

![Archiving workflow for Symphony data from 17a-4](../media/SymphonyDataParserConnectorWorkflow.png)

1. <span data-ttu-id="d7514-112">Uw organisatie werkt samen met 17a-4 om de Gegevensparser van De symfonie in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="d7514-112">Your organization works with 17a-4 to set up and configure the Symphony DataParser.</span></span>

2. <span data-ttu-id="d7514-113">Op regelmatige basis worden De items van de symfonie verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="d7514-113">On a regular basis, Symphony items are collected by the DataParser.</span></span> <span data-ttu-id="d7514-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="d7514-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="d7514-115">De Connector Gegevensparser van Deymfonie die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="d7514-115">The Symphony DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d7514-116">Er wordt een submap gemaakt in de map Postvak IN met de naam **Symphony DataParser** in de postvakken van de gebruiker en de Items van Dessymfonie worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="d7514-116">A subfolder in the Inbox folder named **Symphony DataParser** is created in the user mailboxes, and the Symphony items are imported to that folder.</span></span> <span data-ttu-id="d7514-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="d7514-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d7514-118">Elk Item van de symfonie bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="d7514-118">Every Symphony item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="d7514-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="d7514-119">Before you set up a connector</span></span>

- <span data-ttu-id="d7514-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="d7514-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="d7514-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="d7514-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="d7514-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="d7514-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d7514-123">De gebruiker die de Connector Voor het importeren van postvak maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7514-123">The user who creates the Symphony DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d7514-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d7514-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d7514-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7514-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="d7514-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7514-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d7514-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="d7514-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d7514-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="d7514-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-symphony-dataparser-connector"></a><span data-ttu-id="d7514-129">Stap 1: Een Connector voor gegevensparser van Dessymfonie instellen</span><span class="sxs-lookup"><span data-stu-id="d7514-129">Step 1: Set up a Symphony DataParser connector</span></span>

<span data-ttu-id="d7514-130">De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor De gegevens van Deymfonie.</span><span class="sxs-lookup"><span data-stu-id="d7514-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Symphony data.</span></span>

1. <span data-ttu-id="d7514-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectors**  >  **Symphony DataParser**.</span><span class="sxs-lookup"><span data-stu-id="d7514-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Symphony DataParser**.</span></span>

2. <span data-ttu-id="d7514-132">Klik op de pagina Productbeschrijving van De beschrijving **van Deymfoniegegevensparser** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d7514-132">On the **Symphony DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d7514-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="d7514-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d7514-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="d7514-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="d7514-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard Gegevensparser-verbinding van De symfonie.</span><span class="sxs-lookup"><span data-stu-id="d7514-135">Sign in to your 17a-4 account and complete the steps in the Symphony DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-symphony-dataparser-connector"></a><span data-ttu-id="d7514-136">Stap 2: De Connector Voor gegevensparser configureren</span><span class="sxs-lookup"><span data-stu-id="d7514-136">Step 2: Configure the Symphony DataParser connector</span></span>

<span data-ttu-id="d7514-137">Werk met ondersteuning voor 17a-4 om de Connector Voor Gegevensparser van De symfonie te configureren.</span><span class="sxs-lookup"><span data-stu-id="d7514-137">Work with 17a-4 Support to configure the Symphony DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="d7514-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="d7514-138">Step 3: Map users</span></span>

<span data-ttu-id="d7514-139">Met de Connector Gegevensparser van Symphony worden gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7514-139">The Symphony DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-symphony-dataparser-connector"></a><span data-ttu-id="d7514-140">Stap 4: De Connector Voor de gegevensparser van Dessymfonie controleren</span><span class="sxs-lookup"><span data-stu-id="d7514-140">Step 4: Monitor the Symphony DataParser connector</span></span>

<span data-ttu-id="d7514-141">Nadat u een Connector Voor Gegevensparser hebt aangemaakt, kunt u de verbindingslijnstatus in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d7514-141">After you create a Symphony DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d7514-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="d7514-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d7514-143">Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de Connector Voor gegevensparser van Dessymfonie die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="d7514-143">Click the **Connectors** tab and then select the Symphony DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d7514-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="d7514-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d7514-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="d7514-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d7514-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="d7514-146">Known issues</span></span>

<span data-ttu-id="d7514-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="d7514-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d7514-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d7514-148">Support for larger items will be available at a later date.</span></span>
