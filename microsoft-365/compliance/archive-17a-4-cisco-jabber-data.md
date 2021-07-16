---
title: Een connector instellen voor het archiveren van Cisco Jabber-gegevens in Microsoft 365
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
description: Lees hoe u een 17a-4 Cisco Jabber DataParser-connector kunt instellen en gebruiken om Cisco Jabber-gegevens te importeren en te archiveren in Microsoft 365.
ms.openlocfilehash: 45f3b59fb4a99d8084b882607b925cf449525cba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454527"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a><span data-ttu-id="706c5-103">Een connector instellen voor het archiveren van Cisco Jabber-gegevens</span><span class="sxs-lookup"><span data-stu-id="706c5-103">Set up a connector to archive Cisco Jabber data</span></span>

<span data-ttu-id="706c5-104">Gebruik cisco [Jabber DataParser](https://www.17a-4.com/jabber-dataparser/) van 17a-4 LLC om gegevens van Cisco Jabber te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="706c5-104">Use the [Cisco Jabber DataParser](https://www.17a-4.com/jabber-dataparser/) from 17a-4 LLC to import and archive data from Cisco Jabber to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="706c5-105">De DataParser bevat een Cisco Jabber-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="706c5-105">The DataParser includes a Cisco Jabber connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="706c5-106">De Cisco Jabber DataParser-connector converteert Cisco Jabber-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="706c5-106">The Cisco Jabber DataParser connector converts Cisco Jabber data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="706c5-107">Nadat Cisco Jabber-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance.</span><span class="sxs-lookup"><span data-stu-id="706c5-107">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="706c5-108">Als u een Cisco Jabber-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="706c5-108">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="706c5-109">Overzicht van het archiveren van Cisco Jabber-gegevens</span><span class="sxs-lookup"><span data-stu-id="706c5-109">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="706c5-110">In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om Cisco Jabber-gegevens te archiveren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="706c5-110">The following overview explains the process of using a data connector to archive Cisco Jabber data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor Cisco Jabber-gegevens van 17a-4](../media/CiscoJabberDataParserConnectorWorkflow.png)

1. <span data-ttu-id="706c5-112">Uw organisatie werkt met 17a-4 om de Cisco Jabber DataParser in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="706c5-112">Your organization works with 17a-4 to set up and configure the Cisco Jabber DataParser.</span></span>

2. <span data-ttu-id="706c5-113">Regelmatig worden Cisco Jabber-items verzameld door de DataParser.</span><span class="sxs-lookup"><span data-stu-id="706c5-113">On a regular basis, Cisco Jabber items are collected by the DataParser.</span></span> <span data-ttu-id="706c5-114">De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="706c5-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="706c5-115">De Cisco Jabber DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="706c5-115">The Cisco Jabber DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="706c5-116">Een submap in de map Postvak IN met de naam **Cisco Jabber DataParser** wordt gemaakt in de postvakken van de gebruiker en de Cisco Jabber-items worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="706c5-116">A subfolder in the Inbox folder named **Cisco Jabber DataParser** is created in the user mailboxes, and the Cisco Jabber items are imported to that folder.</span></span> <span data-ttu-id="706c5-117">De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="706c5-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="706c5-118">Elk Cisco Jabber-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.</span><span class="sxs-lookup"><span data-stu-id="706c5-118">Every Cisco Jabber item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="706c5-119">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="706c5-119">Before you set up a connector</span></span>

- <span data-ttu-id="706c5-120">Maak een DataParser-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="706c5-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="706c5-121">Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="706c5-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="706c5-122">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="706c5-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="706c5-123">De gebruiker die de Cisco Jabber DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="706c5-123">The user who creates the Cisco Jabber DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="706c5-124">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="706c5-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="706c5-125">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="706c5-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="706c5-126">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="706c5-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="706c5-127">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="706c5-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="706c5-128">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="706c5-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-cisco-jabber-dataparser-connector"></a><span data-ttu-id="706c5-129">Stap 1: Een Cisco Jabber DataParser-connector instellen</span><span class="sxs-lookup"><span data-stu-id="706c5-129">Step 1: Set up a Cisco Jabber DataParser connector</span></span>

<span data-ttu-id="706c5-130">De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor Cisco Jabber-gegevens.</span><span class="sxs-lookup"><span data-stu-id="706c5-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Cisco Jabber data.</span></span>

1. <span data-ttu-id="706c5-131">Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **Cisco Jabber DataParser**.</span><span class="sxs-lookup"><span data-stu-id="706c5-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Cisco Jabber DataParser**.</span></span>

2. <span data-ttu-id="706c5-132">Klik op **de pagina Cisco Jabber DataParser-productbeschrijving** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="706c5-132">On the **Cisco Jabber DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="706c5-133">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="706c5-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="706c5-134">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="706c5-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="706c5-135">Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard Cisco Jabber DataParser-verbinding.</span><span class="sxs-lookup"><span data-stu-id="706c5-135">Sign in to your 17a-4 account and complete the steps in the Cisco Jabber DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-cisco-jabber-dataparser-connector"></a><span data-ttu-id="706c5-136">Stap 2: De Cisco Jabber DataParser-connector configureren</span><span class="sxs-lookup"><span data-stu-id="706c5-136">Step 2: Configure the Cisco Jabber DataParser connector</span></span>

<span data-ttu-id="706c5-137">Werk met 17a-4 Ondersteuning om de Cisco Jabber DataParser-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="706c5-137">Work with 17a-4 Support to configure the Cisco Jabber DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="706c5-138">Stap 3: Gebruikers in kaart brengen</span><span class="sxs-lookup"><span data-stu-id="706c5-138">Step 3: Map users</span></span>

<span data-ttu-id="706c5-139">De Cisco Jabber DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="706c5-139">The Cisco Jabber DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-dataparser-connector"></a><span data-ttu-id="706c5-140">Stap 4: De Cisco Jabber DataParser-connector controleren</span><span class="sxs-lookup"><span data-stu-id="706c5-140">Step 4: Monitor the Cisco Jabber DataParser connector</span></span>

<span data-ttu-id="706c5-141">Nadat u een Cisco Jabber DataParser-connector hebt aan Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="706c5-141">After you create a Cisco Jabber DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="706c5-142">Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="706c5-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="706c5-143">Klik op **het tabblad Connectors** en selecteer vervolgens de Cisco Jabber DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.</span><span class="sxs-lookup"><span data-stu-id="706c5-143">Click the **Connectors** tab and then select the Cisco Jabber DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="706c5-144">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="706c5-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="706c5-145">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="706c5-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="706c5-146">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="706c5-146">Known issues</span></span>

<span data-ttu-id="706c5-147">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="706c5-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="706c5-148">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="706c5-148">Support for larger items will be available at a later date.</span></span>
