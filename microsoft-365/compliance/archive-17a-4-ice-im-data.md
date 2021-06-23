---
title: Een connector instellen voor het archiveren van ICE-Verbinding maken Chatgegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een ICE-Verbinding maken 17a-4 Ice Verbinding maken Chat DataParser-connector voor het importeren en archiveren van ICE-Verbinding maken Chatgegevens in Microsoft 365.
ms.openlocfilehash: 2c9eb6524e4f5e131603b5998d215e0b2d8111d3
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097136"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data-preview"></a><span data-ttu-id="fd75c-103">Een connector instellen voor het archiveren van ICE-Verbinding maken Chatgegevens (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="fd75c-103">Set up a connector to archive ICE Connect Chat data (preview)</span></span>

<span data-ttu-id="fd75c-104">Gebruik ICE [DataParser](https://www.17a-4.com/ice-dataparser/) van 17a-4 LLC om gegevens uit ICE Verbinding maken Chat te importeren en te archiveren in postvakken van gebruikers in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="fd75c-104">Use the [ICE DataParser](https://www.17a-4.com/ice-dataparser/) from 17a-4 LLC to import and archive data from ICE Connect Chat to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fd75c-105">De DataParser bevat een ICE Chat-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd75c-105">The DataParser includes an ICE Chat connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="fd75c-106">De ICE DataParser-connector converteert ICE-Verbinding maken Chatgegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd75c-106">The ICE DataParser connector converts ICE Connect Chat data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fd75c-107">Nadat ICE Verbinding maken Chatgegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="fd75c-107">After ICE Connect Chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="fd75c-108">Als u een ICE DataParser-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="fd75c-108">Using an ICE DataParser connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ice-chat-data"></a><span data-ttu-id="fd75c-109">Overzicht van het archiveren van ICE Chat-gegevens</span><span class="sxs-lookup"><span data-stu-id="fd75c-109">Overview of archiving ICE Chat data</span></span>

<span data-ttu-id="fd75c-110">In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om ICE-Verbinding maken chatgegevens te archiveren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd75c-110">The following overview explains the process of using a data connector to archive ICE Connect Chat data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor ICE Verbinding maken Chatgegevens van 17a-4](../media/ICEChatDataParserConnectorWorkflow.png)

1. <span data-ttu-id="fd75c-112">Uw organisatie werkt met 17a-4 om ICE DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="fd75c-112">Your organization works with 17a-4 to set up and configure the ICE DataParser.</span></span>

2. <span data-ttu-id="fd75c-113">Ice-Verbinding maken chatitems worden regelmatig verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="fd75c-113">On a regular basis, ICE Connect Chat items are collected by the DataParser.</span></span> <span data-ttu-id="fd75c-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="fd75c-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="fd75c-115">De ICE DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="fd75c-115">The ICE DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fd75c-116">Er wordt een submap gemaakt in de map Postvak IN met de naam **ICE DataParser** in de postvakken van de gebruiker en de ICE Verbinding maken Chat-items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="fd75c-116">A subfolder in the Inbox folder named **ICE DataParser** is created in the user mailboxes, and the ICE Connect Chat items are imported to that folder.</span></span> <span data-ttu-id="fd75c-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="fd75c-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="fd75c-118">Elk ICE Verbinding maken Chatitem bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="fd75c-118">Every ICE Connect Chat item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="fd75c-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="fd75c-119">Before you set up a connector</span></span>

- <span data-ttu-id="fd75c-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="fd75c-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="fd75c-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="fd75c-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="fd75c-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="fd75c-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fd75c-123">De gebruiker die de ICE DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd75c-123">The user who creates the ICE DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fd75c-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fd75c-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fd75c-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd75c-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="fd75c-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd75c-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fd75c-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="fd75c-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fd75c-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="fd75c-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-ice-dataparser-connector"></a><span data-ttu-id="fd75c-129">Stap 1: Een ICE DataParser-connector instellen</span><span class="sxs-lookup"><span data-stu-id="fd75c-129">Step 1: Set up an ICE DataParser connector</span></span>

<span data-ttu-id="fd75c-130">De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor ICE-Verbinding maken Chatgegevens.</span><span class="sxs-lookup"><span data-stu-id="fd75c-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ICE Connect Chat data.</span></span>

1. <span data-ttu-id="fd75c-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **ICE DataParser**.</span><span class="sxs-lookup"><span data-stu-id="fd75c-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ICE DataParser**.</span></span>

2. <span data-ttu-id="fd75c-132">Klik op **de pagina ICE DataParser-productbeschrijving** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fd75c-132">On the **ICE DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fd75c-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="fd75c-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fd75c-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="fd75c-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="fd75c-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard ICE DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="fd75c-135">Sign in to your 17a-4 account and complete the steps in the ICE DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-ice-dataparser-connector"></a><span data-ttu-id="fd75c-136">Stap 2: De ICE DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="fd75c-136">Step 2: Configure the ICE DataParser connector</span></span>

<span data-ttu-id="fd75c-137">Werk met 17a-4 Ondersteuning om de ICE DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="fd75c-137">Work with 17a-4 Support to configure the ICE DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="fd75c-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="fd75c-138">Step 3: Map users</span></span>

<span data-ttu-id="fd75c-139">De ICE DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd75c-139">The ICE DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-ice-dataparser-connector"></a><span data-ttu-id="fd75c-140">Stap 4: De ICE DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="fd75c-140">Step 4: Monitor the ICE DataParser connector</span></span>

<span data-ttu-id="fd75c-141">Nadat u een ICE DataParser-verbindingslijn hebt aan Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fd75c-141">After you create an ICE DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fd75c-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="fd75c-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fd75c-143">Klik op **het tabblad Connectors** en selecteer vervolgens de ICE DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="fd75c-143">Click the **Connectors** tab and then select the ICE DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fd75c-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="fd75c-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fd75c-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="fd75c-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fd75c-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="fd75c-146">Known issues</span></span>

<span data-ttu-id="fd75c-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="fd75c-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fd75c-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="fd75c-148">Support for larger items will be available at a later date.</span></span>
