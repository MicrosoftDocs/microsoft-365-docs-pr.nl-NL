---
title: Een connector instellen voor het archiveren van Gegevensparser-gegevens van ServiceNow 17a-4 in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 ServiceNow DataParser-connector voor het importeren en archiveren van ServiceNow-gegevens in Microsoft 365.
ms.openlocfilehash: a01e075b6cbf400bc3b7dc38950d87443a46f81c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454419"
---
# <a name="set-up-a-connector-to-archive-data-from-servicenow"></a><span data-ttu-id="0ccb0-103">Een verbindingslijn instellen om gegevens van ServiceNow te archiveren</span><span class="sxs-lookup"><span data-stu-id="0ccb0-103">Set up a connector to archive data from ServiceNow</span></span>

<span data-ttu-id="0ccb0-104">Gebruik [serviceNow DataParser](https://www.17a-4.com/dataparser/) van 17a-4 LLC om gegevens uit ServiceNow te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-104">Use the [ServiceNow DataParser](https://www.17a-4.com/dataparser/) from 17a-4 LLC to import and archive data from ServiceNow to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0ccb0-105">De DataParser bevat een ServiceNow-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-105">The DataParser includes a ServiceNow connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="0ccb0-106">De ServiceNow DataParser-connector converteert ServiceNow-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-106">The ServiceNow DataParser connector converts ServiceNow data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="0ccb0-107">Nadat ServiceNow-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-107">After ServiceNow data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="0ccb0-108">Als u een ServiceNow-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-108">Using a ServiceNow connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-servicenow-data"></a><span data-ttu-id="0ccb0-109">Overzicht van het archiveren van ServiceNow-gegevens</span><span class="sxs-lookup"><span data-stu-id="0ccb0-109">Overview of archiving ServiceNow data</span></span>

<span data-ttu-id="0ccb0-110">In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om ServiceNow-gegevens te archiveren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-110">The following overview explains the process of using a data connector to archive ServiceNow data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor ServiceNow-gegevens van 17a-4](../media/ServiceNowDataParserConnectorWorkflow.png)

1. <span data-ttu-id="0ccb0-112">Uw organisatie werkt met 17a-4 om de ServiceNow DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-112">Your organization works with 17a-4 to set up and configure the ServiceNow DataParser.</span></span>

2. <span data-ttu-id="0ccb0-113">Op regelmatige basis worden ServiceNow-items verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-113">On a regular basis, ServiceNow items are collected by the DataParser.</span></span> <span data-ttu-id="0ccb0-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="0ccb0-115">De ServiceNow DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en draagt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-115">The ServiceNow DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="0ccb0-116">Een submap in de map Postvak IN met de naam **ServiceNow DataParser** wordt gemaakt in de postvakken van gebruikers en de ServiceNow-items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-116">A subfolder in the Inbox folder named **ServiceNow DataParser** is created in the user mailboxes, and the ServiceNow items are imported to that folder.</span></span> <span data-ttu-id="0ccb0-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="0ccb0-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="0ccb0-118">Elk ServiceNow-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-118">Every ServiceNow item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="0ccb0-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="0ccb0-119">Before you set up a connector</span></span>

- <span data-ttu-id="0ccb0-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="0ccb0-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="0ccb0-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="0ccb0-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="0ccb0-123">De gebruiker die de ServiceNow DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-123">The user who creates the ServiceNow DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0ccb0-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0ccb0-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="0ccb0-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0ccb0-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0ccb0-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-servicenow-dataparser-connector"></a><span data-ttu-id="0ccb0-129">Stap 1: Een ServiceNow DataParser-connector instellen</span><span class="sxs-lookup"><span data-stu-id="0ccb0-129">Step 1: Set up a ServiceNow DataParser connector</span></span>

<span data-ttu-id="0ccb0-130">De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een 17a-4-connector voor ServiceNow-gegevens te maken.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ServiceNow data.</span></span>

1. <span data-ttu-id="0ccb0-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **ServiceNow DataParser**.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ServiceNow DataParser**.</span></span>

2. <span data-ttu-id="0ccb0-132">Klik op **de pagina ServiceNow DataParser** productbeschrijving op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0ccb0-132">On the **ServiceNow DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="0ccb0-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="0ccb0-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0ccb0-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="0ccb0-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="0ccb0-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard ServiceNow DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-135">Sign in to your 17a-4 account and complete the steps in the ServiceNow DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-servicenow-dataparser-connector"></a><span data-ttu-id="0ccb0-136">Stap 2: De ServiceNow DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="0ccb0-136">Step 2: Configure the ServiceNow DataParser connector</span></span>

<span data-ttu-id="0ccb0-137">Werk met 17a-4 Ondersteuning om de ServiceNow DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-137">Work with 17a-4 Support to configure the ServiceNow DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="0ccb0-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="0ccb0-138">Step 3: Map users</span></span>

<span data-ttu-id="0ccb0-139">De ServiceNow DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-139">The ServiceNow DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-servicenow-dataparser-connector"></a><span data-ttu-id="0ccb0-140">Stap 4: De ServiceNow DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="0ccb0-140">Step 4: Monitor the ServiceNow DataParser connector</span></span>

<span data-ttu-id="0ccb0-141">Nadat u een ServiceNow DataParser-verbindingslijn hebt aan Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-141">After you create a ServiceNow DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="0ccb0-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0ccb0-143">Klik op het tabblad **Verbindingslijnen** en selecteer vervolgens de ServiceNow DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-143">Click the **Connectors** tab and then select the ServiceNow DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="0ccb0-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="0ccb0-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="0ccb0-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0ccb0-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="0ccb0-146">Known issues</span></span>

<span data-ttu-id="0ccb0-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="0ccb0-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0ccb0-148">Support for larger items will be available at a later date.</span></span>
