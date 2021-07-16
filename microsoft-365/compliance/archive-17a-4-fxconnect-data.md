---
title: Een 17a-4 DataParser-connector instellen om FX-Verbinding maken in een Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 FX Verbinding maken DataParser-connector voor het importeren en archiveren van FX-Verbinding maken in Microsoft 365.
ms.openlocfilehash: 667f36d111a877a7e2e04aa54653f61556d337d9
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454491"
---
# <a name="set-up-a-connector-to-archive-data-from-fx-connect"></a><span data-ttu-id="b27f8-103">Een connector instellen om gegevens van FX-Verbinding maken</span><span class="sxs-lookup"><span data-stu-id="b27f8-103">Set up a connector to archive data from FX Connect</span></span>

<span data-ttu-id="b27f8-104">Gebruik de [FX Verbinding maken DataParser](https://www.17a-4.com/dataparser-roadmap/) van 17a-4 LLC om gegevens uit FX-Verbinding maken te importeren en te archiveren in postvakken van gebruikers in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="b27f8-104">Use the [FX Connect DataParser](https://www.17a-4.com/dataparser-roadmap/) from 17a-4 LLC to import and archive data from FX Connect to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b27f8-105">De DataParser bevat een FX-Verbinding maken-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b27f8-105">The DataParser includes a FX Connect connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="b27f8-106">De FX Verbinding maken DataParser-connector converteert FX-Verbinding maken-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b27f8-106">The FX Connect DataParser connector converts FX Connect data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="b27f8-107">Nadat FX-Verbinding maken gegevens zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="b27f8-107">After FX Connect data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b27f8-108">Als u een FX-Verbinding maken gebruikt om gegevens in Microsoft 365 te importeren en te archiveren, kan uw organisatie voldoen aan het overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="b27f8-108">Using a FX Connect connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fx-connect-data"></a><span data-ttu-id="b27f8-109">Overzicht van het archiveren van FX-Verbinding maken gegevens</span><span class="sxs-lookup"><span data-stu-id="b27f8-109">Overview of archiving FX Connect data</span></span>

<span data-ttu-id="b27f8-110">In het volgende overzicht wordt uitgelegd hoe het gebruik van een gegevensconnector voor het archiveren van FX-Verbinding maken gegevens in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b27f8-110">The following overview explains the process of using a data connector to archive FX Connect data in Microsoft 365.</span></span>

![Archiving workflow for FX Verbinding maken data from 17a-4](../media/FXConnectDataParserConnectorWorkflow.png)

1. <span data-ttu-id="b27f8-112">Uw organisatie werkt met 17a-4 om de FX-Verbinding maken DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="b27f8-112">Your organization works with 17a-4 to set up and configure the FX Connect DataParser.</span></span>

2. <span data-ttu-id="b27f8-113">Op regelmatige basis worden FX-Verbinding maken door de DataParser verzameld.</span><span class="sxs-lookup"><span data-stu-id="b27f8-113">On a regular basis, FX Connect items are collected by the DataParser.</span></span> <span data-ttu-id="b27f8-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="b27f8-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="b27f8-115">De FX Verbinding maken DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="b27f8-115">The FX Connect DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b27f8-116">Een submap in de map Postvak IN met de naam **FX Verbinding maken DataParser** wordt gemaakt in de postvakken van de gebruiker en de FX-Verbinding maken-items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="b27f8-116">A subfolder in the Inbox folder named **FX Connect DataParser** is created in the user mailboxes, and the FX Connect items are imported to that folder.</span></span> <span data-ttu-id="b27f8-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="b27f8-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="b27f8-118">Elk FX-Verbinding maken bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="b27f8-118">Every FX Connect item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="b27f8-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="b27f8-119">Before you set up a connector</span></span>

- <span data-ttu-id="b27f8-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="b27f8-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="b27f8-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="b27f8-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="b27f8-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="b27f8-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b27f8-123">De gebruiker die de FX Verbinding maken DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b27f8-123">The user who creates the FX Connect DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b27f8-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b27f8-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b27f8-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b27f8-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b27f8-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b27f8-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b27f8-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="b27f8-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b27f8-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="b27f8-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-fx-connect-dataparser-connector"></a><span data-ttu-id="b27f8-129">Stap 1: Een FX-verbindingslijn Verbinding maken DataParser instellen</span><span class="sxs-lookup"><span data-stu-id="b27f8-129">Step 1: Set up a FX Connect DataParser connector</span></span>

<span data-ttu-id="b27f8-130">De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een 17a-4-connector voor FX-Verbinding maken maken.</span><span class="sxs-lookup"><span data-stu-id="b27f8-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for FX Connect data.</span></span>

1. <span data-ttu-id="b27f8-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op Data **connectors**  >  **FX Verbinding maken DataParser**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **FX Connect DataParser**.</span></span>

2. <span data-ttu-id="b27f8-132">Klik op **de pagina FX Verbinding maken DataParser-productbeschrijving** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="b27f8-132">On the **FX Connect DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b27f8-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="b27f8-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b27f8-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b27f8-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="b27f8-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard VERBINDING MAKEN DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="b27f8-135">Sign in to your 17a-4 account and complete the steps in the FX Connect DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-fx-connect-dataparser-connector"></a><span data-ttu-id="b27f8-136">Stap 2: De FX-Verbinding maken DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="b27f8-136">Step 2: Configure the FX Connect DataParser connector</span></span>

<span data-ttu-id="b27f8-137">Werk met 17a-4 Ondersteuning om de FX-Verbinding maken DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="b27f8-137">Work with 17a-4 Support to configure the FX Connect DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="b27f8-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="b27f8-138">Step 3: Map users</span></span>

<span data-ttu-id="b27f8-139">Met de FX Verbinding maken DataParser-connector worden gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b27f8-139">The FX Connect DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-fx-connect-dataparser-connector"></a><span data-ttu-id="b27f8-140">Stap 4: De FX-Verbinding maken DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="b27f8-140">Step 4: Monitor the FX Connect DataParser connector</span></span>

<span data-ttu-id="b27f8-141">Nadat u een FX-Verbinding maken DataParser-connector hebt Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b27f8-141">After you create a FX Connect DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b27f8-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="b27f8-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b27f8-143">Klik op het tabblad **Connectors** en selecteer vervolgens de FX Verbinding maken DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="b27f8-143">Click the **Connectors** tab and then select the FX Connect DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b27f8-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="b27f8-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b27f8-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="b27f8-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b27f8-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="b27f8-146">Known issues</span></span>

<span data-ttu-id="b27f8-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="b27f8-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b27f8-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b27f8-148">Support for larger items will be available at a later date.</span></span>
