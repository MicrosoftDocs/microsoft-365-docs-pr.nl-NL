---
title: Een connector instellen voor het archiveren van InvestEdge-gegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 InvestEdge DataParser-connector voor het importeren en archiveren van InvestEdge-gegevens in Microsoft 365.
ms.openlocfilehash: b20d9809c4bea113580a62c7a414321ed15da6ad
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454467"
---
# <a name="set-up-a-connector-to-archive-investedge-data"></a><span data-ttu-id="deaa4-103">Een connector instellen voor het archiveren van InvestEdge-gegevens</span><span class="sxs-lookup"><span data-stu-id="deaa4-103">Set up a connector to archive InvestEdge data</span></span>

<span data-ttu-id="deaa4-104">Gebruik [de InvestEdge DataParser](https://www.17a-4.com/investedge-dataparser/) van 17a-4 LLC om gegevens uit InvestEdge te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="deaa4-104">Use the [InvestEdge DataParser](https://www.17a-4.com/investedge-dataparser/) from 17a-4 LLC to import and archive data from InvestEdge to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="deaa4-105">De DataParser bevat een InvestEdge-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="deaa4-105">The DataParser includes a InvestEdge connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="deaa4-106">De InvestEdge DataParser-connector converteert InvestEdge-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in postvakken van gebruikers in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="deaa4-106">The InvestEdge DataParser connector converts InvestEdge data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="deaa4-107">Nadat InvestEdge-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="deaa4-107">After InvestEdge data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="deaa4-108">Met behulp van een InvestEdge-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="deaa4-108">Using a InvestEdge connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-investedge-data"></a><span data-ttu-id="deaa4-109">Overzicht van het archiveren van InvestEdge-gegevens</span><span class="sxs-lookup"><span data-stu-id="deaa4-109">Overview of archiving InvestEdge data</span></span>

<span data-ttu-id="deaa4-110">In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om InvestEdge-gegevens te archiveren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="deaa4-110">The following overview explains the process of using a data connector to archive InvestEdge data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor InvestEdge-gegevens van 17a-4](../media/InvestEdgeDataParserConnectorWorkflow.png)

1. <span data-ttu-id="deaa4-112">Uw organisatie werkt met 17a-4 om de InvestEdge DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="deaa4-112">Your organization works with 17a-4 to set up and configure the InvestEdge DataParser.</span></span>

2. <span data-ttu-id="deaa4-113">Op regelmatige basis worden InvestEdge-items verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="deaa4-113">On a regular basis, InvestEdge items are collected by the DataParser.</span></span> <span data-ttu-id="deaa4-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="deaa4-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="deaa4-115">De InvestEdge DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en draagt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="deaa4-115">The InvestEdge DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="deaa4-116">Een submap in de map Postvak IN met de naam **InvestEdge DataParser** wordt gemaakt in de postvakken van gebruikers en de InvestEdge-items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="deaa4-116">A subfolder in the Inbox folder named **InvestEdge DataParser** is created in the user mailboxes, and the InvestEdge items are imported to that folder.</span></span> <span data-ttu-id="deaa4-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="deaa4-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="deaa4-118">Elk InvestEdge-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="deaa4-118">Every InvestEdge item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="deaa4-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="deaa4-119">Before you set up a connector</span></span>

- <span data-ttu-id="deaa4-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="deaa4-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="deaa4-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="deaa4-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="deaa4-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="deaa4-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="deaa4-123">De gebruiker die de InvestEdge DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="deaa4-123">The user who creates the InvestEdge DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="deaa4-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="deaa4-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="deaa4-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="deaa4-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="deaa4-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="deaa4-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="deaa4-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="deaa4-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="deaa4-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="deaa4-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-investedge-dataparser-connector"></a><span data-ttu-id="deaa4-129">Stap 1: Een InvestEdge DataParser-connector instellen</span><span class="sxs-lookup"><span data-stu-id="deaa4-129">Step 1: Set up a InvestEdge DataParser connector</span></span>

<span data-ttu-id="deaa4-130">De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor InvestEdge-gegevens.</span><span class="sxs-lookup"><span data-stu-id="deaa4-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for InvestEdge data.</span></span>

1. <span data-ttu-id="deaa4-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **InvestEdge DataParser**.</span><span class="sxs-lookup"><span data-stu-id="deaa4-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **InvestEdge DataParser**.</span></span>

2. <span data-ttu-id="deaa4-132">Klik op **de pagina Productbeschrijving van InvestEdge DataParser** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="deaa4-132">On the **InvestEdge DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="deaa4-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="deaa4-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="deaa4-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="deaa4-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="deaa4-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard InvestEdge DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="deaa4-135">Sign in to your 17a-4 account and complete the steps in the InvestEdge DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-investedge-dataparser-connector"></a><span data-ttu-id="deaa4-136">Stap 2: De InvestEdge DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="deaa4-136">Step 2: Configure the InvestEdge DataParser connector</span></span>

<span data-ttu-id="deaa4-137">Werk met 17a-4 Ondersteuning om de InvestEdge DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="deaa4-137">Work with 17a-4 Support to configure the InvestEdge DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="deaa4-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="deaa4-138">Step 3: Map users</span></span>

<span data-ttu-id="deaa4-139">De InvestEdge DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="deaa4-139">The InvestEdge DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-investedge-dataparser-connector"></a><span data-ttu-id="deaa4-140">Stap 4: De InvestEdge DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="deaa4-140">Step 4: Monitor the InvestEdge DataParser connector</span></span>

<span data-ttu-id="deaa4-141">Nadat u een InvestEdge DataParser-connector hebt aan Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="deaa4-141">After you create a InvestEdge DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="deaa4-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="deaa4-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="deaa4-143">Klik op het tabblad **Connectors** en selecteer vervolgens de InvestEdge DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="deaa4-143">Click the **Connectors** tab and then select the InvestEdge DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="deaa4-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="deaa4-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="deaa4-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="deaa4-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="deaa4-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="deaa4-146">Known issues</span></span>

<span data-ttu-id="deaa4-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="deaa4-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="deaa4-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="deaa4-148">Support for larger items will be available at a later date.</span></span>
