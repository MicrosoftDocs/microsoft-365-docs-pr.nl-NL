---
title: Een connector instellen voor het archiveren van SQL gegevens in Microsoft 365
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
ROBOTS: noindex,nofollow
description: Meer informatie over het instellen en gebruiken van een 17a-4 SQL DataParser-connector om gegevens in SQL te Microsoft 365.
ms.openlocfilehash: 17e7da9e064e6d149ebdca0436f9180c8d17ca41
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096983"
---
# <a name="set-up-a-connector-to-archive-sql-data-preview"></a><span data-ttu-id="0de2f-103">Een verbindingslijn instellen om gegevens SQL archiveren (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="0de2f-103">Set up a connector to archive SQL data (preview)</span></span>

<span data-ttu-id="0de2f-104">Gebruik de [SQL DataParser](https://www.17a-4.com/sql-dataparser/) van 17a-4 LLC om gegevens uit een SQL-database te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="0de2f-104">Use the [SQL DataParser](https://www.17a-4.com/sql-dataparser/) from 17a-4 LLC to import and archive data from a SQL database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0de2f-105">De DataParser bevat een SQL connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0de2f-105">The DataParser includes a SQL connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="0de2f-106">De SQL DataParser-connector converteert SQL gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0de2f-106">The SQL DataParser connector converts SQL data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="0de2f-107">Nadat SQL gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="0de2f-107">After SQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="0de2f-108">Met een SQL verbindingslijn voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="0de2f-108">Using a SQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-sql-data"></a><span data-ttu-id="0de2f-109">Overzicht van het archiveren SQL gegevens</span><span class="sxs-lookup"><span data-stu-id="0de2f-109">Overview of archiving SQL data</span></span>

<span data-ttu-id="0de2f-110">In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om gegevens in SQL te Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0de2f-110">The following overview explains the process of using a data connector to archive SQL data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor SQL gegevens van 17a-4](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. <span data-ttu-id="0de2f-112">Uw organisatie werkt met 17a-4 om de SQL DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="0de2f-112">Your organization works with 17a-4 to set up and configure the SQL DataParser.</span></span>

2. <span data-ttu-id="0de2f-113">Op regelmatige basis worden SQL items verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="0de2f-113">On a regular basis, SQL items are collected by the DataParser.</span></span> <span data-ttu-id="0de2f-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="0de2f-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="0de2f-115">De SQL DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en draagt de berichten over naar een veilige locatie Azure Storage in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="0de2f-115">The SQL DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="0de2f-116">Er wordt een submap in de **map Postvak SQL DataParser** gemaakt in de postvakken van de gebruiker en de SQL items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="0de2f-116">A subfolder in the Inbox folder named **SQL DataParser** is created in the user mailboxes, and the SQL items are imported to that folder.</span></span> <span data-ttu-id="0de2f-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="0de2f-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="0de2f-118">Elk SQL item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="0de2f-118">Every SQL item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="0de2f-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="0de2f-119">Before you set up a connector</span></span>

- <span data-ttu-id="0de2f-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="0de2f-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="0de2f-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="0de2f-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="0de2f-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="0de2f-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="0de2f-123">De gebruiker die de SQL DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0de2f-123">The user who creates the SQL DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0de2f-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0de2f-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0de2f-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0de2f-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="0de2f-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0de2f-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0de2f-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="0de2f-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0de2f-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="0de2f-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-sql-dataparser-connector"></a><span data-ttu-id="0de2f-129">Stap 1: Een SQL DataParser-connector instellen</span><span class="sxs-lookup"><span data-stu-id="0de2f-129">Step 1: Set up a SQL DataParser connector</span></span>

<span data-ttu-id="0de2f-130">De eerste stap is toegang tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector maken voor SQL gegevens.</span><span class="sxs-lookup"><span data-stu-id="0de2f-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for SQL data.</span></span>

1. <span data-ttu-id="0de2f-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren SQL**  >  **DataParser**.</span><span class="sxs-lookup"><span data-stu-id="0de2f-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **SQL DataParser**.</span></span>

2. <span data-ttu-id="0de2f-132">Klik op **SQL pagina Productbeschrijving van DataParser** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0de2f-132">On the **SQL DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="0de2f-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="0de2f-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0de2f-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="0de2f-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="0de2f-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard SQL DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="0de2f-135">Sign in to your 17a-4 account and complete the steps in the SQL DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-sql-dataparser-connector"></a><span data-ttu-id="0de2f-136">Stap 2: De SQL DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="0de2f-136">Step 2: Configure the SQL DataParser connector</span></span>

<span data-ttu-id="0de2f-137">Werk met 17a-4 Ondersteuning om de SQL DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="0de2f-137">Work with 17a-4 Support to configure the SQL DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="0de2f-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="0de2f-138">Step 3: Map users</span></span>

<span data-ttu-id="0de2f-139">De SQL DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0de2f-139">The SQL DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-sql-dataparser-connector"></a><span data-ttu-id="0de2f-140">Stap 4: De SQL DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="0de2f-140">Step 4: Monitor the SQL DataParser connector</span></span>

<span data-ttu-id="0de2f-141">Nadat u een SQL DataParser-verbindingslijn hebt Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0de2f-141">After you create a SQL DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="0de2f-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="0de2f-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0de2f-143">Klik op het tabblad **Verbindingslijnen** en selecteer vervolgens de SQL DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="0de2f-143">Click the **Connectors** tab and then select the SQL DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="0de2f-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="0de2f-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="0de2f-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="0de2f-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0de2f-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="0de2f-146">Known issues</span></span>

<span data-ttu-id="0de2f-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="0de2f-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="0de2f-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0de2f-148">Support for larger items will be available at a later date.</span></span>
