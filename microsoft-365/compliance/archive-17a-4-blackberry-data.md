---
title: Een verbindingslijn instellen voor het archiveren van BlackBerry-gegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 BlackBerry DataParser-connector voor het importeren en archiveren van BlackBerry-gegevens in Microsoft 365.
ms.openlocfilehash: 1e84a2c5273a503ccb5d88381e01160ae2abf3cd
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096386"
---
# <a name="set-up-a-connector-to-archive-blackberry-data-preview"></a><span data-ttu-id="14925-103">Een verbindingslijn instellen om BlackBerry-gegevens te archiveren (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="14925-103">Set up a connector to archive BlackBerry data (preview)</span></span>

<span data-ttu-id="14925-104">Gebruik de [BlackBerry DataParser](https://www.17a-4.com/BlackBerry-dataparser/) van 17a-4 LLC om bedrijfsgegevens van BlackBerry te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="14925-104">Use the [BlackBerry DataParser](https://www.17a-4.com/BlackBerry-dataparser/) from 17a-4 LLC to import and archive BlackBerry enterprise data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="14925-105">De DataParser bevat een BlackBerry-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14925-105">The DataParser includes a BlackBerry connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="14925-106">De BlackBerry DataParser-connector converteert BlackBerry-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14925-106">The BlackBerry DataParser connector converts BlackBerry data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="14925-107">Nadat BlackBerry-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="14925-107">After BlackBerry data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="14925-108">Als u een BlackBerry-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 uw organisatie kan voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="14925-108">Using a BlackBerry connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-blackberry-data"></a><span data-ttu-id="14925-109">Overzicht van het archiveren van BlackBerry-gegevens</span><span class="sxs-lookup"><span data-stu-id="14925-109">Overview of archiving BlackBerry data</span></span>

<span data-ttu-id="14925-110">In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om BlackBerry-gegevens te archiveren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14925-110">The following overview explains the process of using a data connector to archive BlackBerry data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor BlackBerry-gegevens van 17a-4](../media/BlackBerryDataParserConnectorWorkflow.png)

1. <span data-ttu-id="14925-112">Uw organisatie werkt met 17a-4 om de BlackBerry DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="14925-112">Your organization works with 17a-4 to set up and configure the BlackBerry DataParser.</span></span>

2. <span data-ttu-id="14925-113">BlackBerry-items worden regelmatig verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="14925-113">On a regular basis, BlackBerry items are collected by the DataParser.</span></span> <span data-ttu-id="14925-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="14925-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="14925-115">De BlackBerry DataParser-connector die u in het Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="14925-115">The BlackBerry DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="14925-116">Er wordt een submap in de map Postvak IN met de naam **BlackBerry DataParser** gemaakt in de postvakken van gebruikers en de BlackBerry-items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="14925-116">A subfolder in the Inbox folder named **BlackBerry DataParser** is created in the user mailboxes, and the BlackBerry items are imported to that folder.</span></span> <span data-ttu-id="14925-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="14925-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="14925-118">Elk BlackBerry-item bevat deze eigenschap, die wordt ingevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="14925-118">Every BlackBerry item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="14925-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="14925-119">Before you set up a connector</span></span>

- <span data-ttu-id="14925-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="14925-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="14925-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="14925-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="14925-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="14925-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="14925-123">De gebruiker die de BlackBerry DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="14925-123">The user who creates the BlackBerry DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="14925-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="14925-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="14925-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="14925-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="14925-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="14925-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="14925-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="14925-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="14925-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="14925-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-blackberry-dataparser-connector"></a><span data-ttu-id="14925-129">Stap 1: Een BlackBerry DataParser-connector instellen</span><span class="sxs-lookup"><span data-stu-id="14925-129">Step 1: Set up a BlackBerry DataParser connector</span></span>

<span data-ttu-id="14925-130">De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een 17a-4-connector voor BlackBerry-gegevens te maken.</span><span class="sxs-lookup"><span data-stu-id="14925-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for BlackBerry data.</span></span>

1. <span data-ttu-id="14925-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **BlackBerry DataParser**.</span><span class="sxs-lookup"><span data-stu-id="14925-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **BlackBerry DataParser**.</span></span>

2. <span data-ttu-id="14925-132">Klik op **de pagina Productbeschrijving van BlackBerry DataParser** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="14925-132">On the **BlackBerry DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="14925-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="14925-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="14925-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="14925-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="14925-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard BlackBerry DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="14925-135">Sign in to your 17a-4 account and complete the steps in the BlackBerry DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-blackberry-dataparser-connector"></a><span data-ttu-id="14925-136">Stap 2: De BlackBerry DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="14925-136">Step 2: Configure the BlackBerry DataParser connector</span></span>

<span data-ttu-id="14925-137">Werk met 17a-4 Ondersteuning om de BlackBerry DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="14925-137">Work with 17a-4 Support to configure the BlackBerry DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="14925-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="14925-138">Step 3: Map users</span></span>

<span data-ttu-id="14925-139">De BlackBerry DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14925-139">The BlackBerry DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-blackberry-dataparser-connector"></a><span data-ttu-id="14925-140">Stap 4: De BlackBerry DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="14925-140">Step 4: Monitor the BlackBerry DataParser connector</span></span>

<span data-ttu-id="14925-141">Nadat u een BlackBerry DataParser-verbindingslijn hebt aan Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="14925-141">After you create a BlackBerry DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="14925-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="14925-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="14925-143">Klik op het tabblad **Connectors** en selecteer vervolgens de BlackBerry DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="14925-143">Click the **Connectors** tab and then select the BlackBerry DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="14925-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="14925-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="14925-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="14925-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="14925-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="14925-146">Known issues</span></span>

<span data-ttu-id="14925-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="14925-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="14925-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="14925-148">Support for larger items will be available at a later date.</span></span>