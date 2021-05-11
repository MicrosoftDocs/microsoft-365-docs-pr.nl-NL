---
title: Een verbindingslijn instellen voor het archiveren van gegevens van de TeleMessage Enterprise Number Archiver
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van Sms en MMS-gegevens uit TeleMessage Enterprise Number Archiver. Op deze manier kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162069"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a><span data-ttu-id="fb929-104">Een verbindingslijn instellen voor het archiveren van enterprisenummergegevens</span><span class="sxs-lookup"><span data-stu-id="fb929-104">Set up a connector to archive Enterprise Number data</span></span>

<span data-ttu-id="fb929-105">Gebruik een TeleMessage-verbindingslijn in het Microsoft 365 compliancecentrum om berichten, chatberichten, spraakopnamen en voicemaillogboeken Sms te importeren en te archiveren vanuit de Enterprise Number Archiver.</span><span class="sxs-lookup"><span data-stu-id="fb929-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) messages, chat messages, voice call recordings, and voice call logs from the Enterprise Number Archiver.</span></span> <span data-ttu-id="fb929-106">Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, wordt er eenmaal per dag verbinding gemaakt met het TeleMessage-account van uw organisatie en worden de mobiele communicatiegegevens van werknemers die de TeleMessage Enterprise Number Archiver gebruiken, geïmporteerd in postvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb929-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day and imports the mobile communication data of employees using the TeleMessage Enterprise Number Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fb929-107">Nadat de gegevens van de TeleMessage Enterprise Number Archiver-connector zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties zoals Litigation Hold, Content Search, In-Place Archiving, Auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op Enterprise Number Archiver-gegevens.</span><span class="sxs-lookup"><span data-stu-id="fb929-107">After the TeleMessage Enterprise Number Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to Enterprise Number Archiver data.</span></span> <span data-ttu-id="fb929-108">U kunt bijvoorbeeld zoeken in de TeleMessage Enterprise Number Archiver Sms, MMS en Voice Call met Inhoud zoeken of het postvak met de connectorgegevens van de Enterprise Number Archiver koppelen aan een bewaarder in een Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="fb929-108">For example, you can search the TeleMessage Enterprise Number Archiver SMS, MMS, and Voice Call using Content Search or associate the mailbox that contains the Enterprise Number Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="fb929-109">Als u een enterprise number archiver-connector gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="fb929-109">Using an Enterprise Number Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-enterprise-number-data"></a><span data-ttu-id="fb929-110">Overzicht van het archiveren van enterprisenummergegevens</span><span class="sxs-lookup"><span data-stu-id="fb929-110">Overview of archiving Enterprise Number data</span></span>

<span data-ttu-id="fb929-111">In het volgende overzicht wordt uitgelegd hoe het gebruik van een connector voor het archiveren van Enterprise Network-gegevens in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb929-111">The following overview explains the process of using a connector to archive Enterprise Network data in Microsoft 365.</span></span>

![Archiveringswerkstroom ondernemingsnummer](../media/EnterpriseNumberConnectorWorkflow.png)

1. <span data-ttu-id="fb929-113">Uw organisatie werkt met TeleMessage om een connector voor het archiveren van ondernemingsnummer in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fb929-113">Your organization works with TeleMessage to set up an Enterprise Number Archiver connector.</span></span> <span data-ttu-id="fb929-114">Zie hier voor meer [informatie.](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)</span><span class="sxs-lookup"><span data-stu-id="fb929-114">For more details refer to [here](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).</span></span>

2. <span data-ttu-id="fb929-115">De connector Enterprise Number Archiver die u maakt in het Microsoft 365 compliancecentrum maakt elke dag verbinding met de TeleMessage-site en draagt de e-mailberichten van de afgelopen 24 uur over naar een beveiligd Azure Storage-gebied in de Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="fb929-115">The Enterprise Number Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

3. <span data-ttu-id="fb929-116">De verbindingslijn importeert de mobiele communicatie-items naar het postvak van een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fb929-116">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="fb929-117">Er wordt een nieuwe map met de naam Enterprise Number Archiver gemaakt in het postvak van de specifieke gebruiker en de items worden er in geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="fb929-117">A new folder named Enterprise Number Archiver is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="fb929-118">De verbindingslijn wordt toegewezen met behulp van de waarde van de eigenschap *E-mailadres van de* gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fb929-118">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="fb929-119">Elk e-mailbericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="fb929-119">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="fb929-120">Naast automatische gebruikerstoewijzing met  de waarde van de eigenschap E-mailadres van de gebruiker, kunt u ook een aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden.</span><span class="sxs-lookup"><span data-stu-id="fb929-120">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="fb929-121">Dit toewijzingsbestand moet het mobiele nummer van de gebruiker en het bijbehorende Microsoft 365 postvak voor elke gebruiker bevatten.</span><span class="sxs-lookup"><span data-stu-id="fb929-121">This mapping file should contain User’s mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="fb929-122">Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing biedt, wordt voor elk e-mailitem eerst naar aangepast toewijzingsbestand gekijken.</span><span class="sxs-lookup"><span data-stu-id="fb929-122">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="fb929-123">Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met het mobiele nummer van een gebruiker, gebruikt de verbindingslijn de eigenschap E-mailadres van de gebruiker van het e-mailitem.</span><span class="sxs-lookup"><span data-stu-id="fb929-123">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="fb929-124">Als de verbindingslijn geen geldige Microsoft 365-gebruiker vindt in het  aangepaste toewijzingsbestand of de eigenschap van het e-mailadres van het e-mailitem, wordt het item niet geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="fb929-124">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user’s email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fb929-125">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="fb929-125">Before you begin</span></span>

<span data-ttu-id="fb929-126">Enkele van de implementatiestappen die nodig zijn voor het archiveren van enterprise number archiver-gegevens zijn extern Microsoft 365 en moeten zijn voltooid voordat u de verbindingslijn in het compliancecentrum kunt maken.</span><span class="sxs-lookup"><span data-stu-id="fb929-126">Some of the implementation steps required to archive Enterprise Number Archiver data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="fb929-127">Bestel de [Enterprise Number Archiver-service bij TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) en ontvang een geldig beheeraccount voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fb929-127">Order the [Enterprise Number Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="fb929-128">U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fb929-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="fb929-129">Registreer alle gebruikers die enterprise number Sms/MMS Network archiveren in het TeleMessage-account.</span><span class="sxs-lookup"><span data-stu-id="fb929-129">Register all users that require Enterprise Number SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="fb929-130">Wanneer u gebruikers registreert, moet u hetzelfde e-mailadres gebruiken dat wordt gebruikt voor hun Microsoft 365 account.</span><span class="sxs-lookup"><span data-stu-id="fb929-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="fb929-131">Installeer en activeer de app TeleMessage Enterprise Number Archiver op de mobiele telefoons van uw werknemers.</span><span class="sxs-lookup"><span data-stu-id="fb929-131">Install and activate the TeleMessage Enterprise Number Archiver app on the mobile phones of your employees.</span></span>

- <span data-ttu-id="fb929-132">De gebruiker die een connector voor het archiveren van ondernemingsnummer maakt, moet de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb929-132">The user who creates a Enterprise Number Archiver connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fb929-133">Dit is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fb929-133">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb929-134">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb929-134">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fb929-135">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb929-135">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fb929-136">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="fb929-136">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fb929-137">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="fb929-137">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-an-enterprise-number-archiver-connector"></a><span data-ttu-id="fb929-138">Een connector voor het archiveren van ondernemingsnummer maken</span><span class="sxs-lookup"><span data-stu-id="fb929-138">Create an Enterprise Number Archiver connector</span></span>

<span data-ttu-id="fb929-139">Nadat u de vereisten hebt voltooid die in de vorige sectie zijn beschreven, kunt u een connector voor het archiveren van ondernemingsnummer maken in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fb929-139">After you've completed the prerequisites described in the previous section, you can create an Enterprise Number Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb929-140">De verbindingslijn gebruikt de gegevens die u verstrekt om verbinding te maken met de TeleMessage-site en om Sms, MMS en voicemailberichten over te brengen naar de bijbehorende postvakken van gebruikerspostvakken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb929-140">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS, MMS, and voice call messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="fb929-141">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren** \> **Enterprise Number Archiver**.</span><span class="sxs-lookup"><span data-stu-id="fb929-141">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **Enterprise Number Archiver**.</span></span>

2. <span data-ttu-id="fb929-142">Klik op **de pagina Productbeschrijving ondernemingsnummerarchief** op **Verbindingslijn toevoegen**</span><span class="sxs-lookup"><span data-stu-id="fb929-142">On the **Enterprise Number Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="fb929-143">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="fb929-143">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fb929-144">Voer op de pagina Aanmelden bij **TeleMessage** onder Stap 3 de vereiste informatie in de volgende vakken in en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fb929-144">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="fb929-145">**Gebruikersnaam:** Uw TeleMessage-gebruikersnaam.</span><span class="sxs-lookup"><span data-stu-id="fb929-145">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="fb929-146">**Wachtwoord:** Uw TeleMessage-wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="fb929-146">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="fb929-147">Nadat de verbindingslijn is gemaakt, kunt u het pop-upvenster sluiten en naar de volgende pagina gaan.</span><span class="sxs-lookup"><span data-stu-id="fb929-147">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="fb929-148">Schakel op **de pagina Gebruikerstoewijzing** automatische gebruikerstoewijzing in.</span><span class="sxs-lookup"><span data-stu-id="fb929-148">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="fb929-149">Als u aangepaste toewijzing wilt inschakelen, uploadt u een CSV-bestand dat de gebruikerstoewijzingsgegevens bevat en klikt u vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="fb929-149">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="fb929-150">Controleer de instellingen en klik vervolgens op **Voltooien om** de verbindingslijn te maken.</span><span class="sxs-lookup"><span data-stu-id="fb929-150">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="fb929-151">Ga naar het tabblad Connectors op de pagina **Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken.</span><span class="sxs-lookup"><span data-stu-id="fb929-151">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fb929-152">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="fb929-152">Known issues</span></span>

- <span data-ttu-id="fb929-153">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="fb929-153">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fb929-154">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="fb929-154">Support for larger items will be available at a later date.</span></span>