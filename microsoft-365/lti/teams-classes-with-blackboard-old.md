---
title: Gebruik Microsoft Teams lessen met Blackboard
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: De Microsoft Teams in uw Learning managementsysteem integreren
ms.openlocfilehash: 3c574184c48ae064d425ed98dbc391b8f5bcf7e0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256961"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="43e55-103">Gebruik Microsoft Teams lessen met Blackboard</span><span class="sxs-lookup"><span data-stu-id="43e55-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43e55-104">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="43e55-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="43e55-105">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="43e55-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="43e55-106">Microsoft Teams lessen is een Learning app Hulpmiddelen interoperabiliteit (LTI) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun Learning Management System (LMS) en Teams.</span><span class="sxs-lookup"><span data-stu-id="43e55-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="43e55-107">Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="43e55-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="43e55-108">De app goedkeuren in de Microsoft Azure tenant</span><span class="sxs-lookup"><span data-stu-id="43e55-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="43e55-109">De volgende taken worden uitgevoerd door de Microsoft Office 365 beheerder en de Blackboard Learn Ultra-beheerder.</span><span class="sxs-lookup"><span data-stu-id="43e55-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="43e55-110">Voordat de integratie binnen Blackboard Learn Ultra wordt uitgevoerd, moet de Microsoft Office 365-beheerder de Blackboard **MSFT-Teams** voor De Ultra Azure-app voor de tenant van de instelling Microsoft Azure goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="43e55-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="43e55-111">Zoek uw Microsoft Tenant-id.</span><span class="sxs-lookup"><span data-stu-id="43e55-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="43e55-112">Zie [hoe u de tenant kunt vinden.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)</span><span class="sxs-lookup"><span data-stu-id="43e55-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="43e55-113">Omleiden van het Microsoft Identity Platform Admin Consent Endpoint volgens het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="43e55-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="43e55-114">Vervang {tenant} door de Microsoft-tenant-id van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="43e55-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="43e55-115">De integratie-apps registreren</span><span class="sxs-lookup"><span data-stu-id="43e55-115">Register the integration apps</span></span>

<span data-ttu-id="43e55-116">Als Blackboard Learn Ultra-beheerder moet u 2 LTI 1.3-integratie-apps registreren in uw testomgeving:</span><span class="sxs-lookup"><span data-stu-id="43e55-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="43e55-117">De Blackboard Learn Class-Teams ondersteuning voor de roostersynchronisatie</span><span class="sxs-lookup"><span data-stu-id="43e55-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="43e55-118">De Microsoft Teams LTI-app voor klasteam</span><span class="sxs-lookup"><span data-stu-id="43e55-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="43e55-119">Noteer de volgende LTI-client-ID's voor beide apps:</span><span class="sxs-lookup"><span data-stu-id="43e55-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="43e55-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="43e55-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="43e55-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="43e55-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="43e55-122">Ga naar het beheerderspaneel en zoek onder **Integraties** de LTI-hulpprogrammaproviders.</span><span class="sxs-lookup"><span data-stu-id="43e55-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![Dit is het dialoogvenster Provider van LTI-hulpprogramma's met een lijst met providers](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="43e55-124">Selecteer **LTI1.3/Advantage Tool registreren.**</span><span class="sxs-lookup"><span data-stu-id="43e55-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="43e55-125">Voer de eerste van de verstrekte client-1D's in (Blackboard of Microsoft) en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="43e55-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

5. <span data-ttu-id="43e55-126">Controleer de vooraf ingevulde instellingen en controleer of de status van het hulpprogramma is gemarkeerd als goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="43e55-126">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="43e55-127">Schuif naar de onderkant en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="43e55-127">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="43e55-128">Herhaal de vorige stappen om de tweede LTI-apps in uw omgeving te registreren.</span><span class="sxs-lookup"><span data-stu-id="43e55-128">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="43e55-129">De REST-toepassing en het delen van cross origin-resources instellen</span><span class="sxs-lookup"><span data-stu-id="43e55-129">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="43e55-130">De Blackboard Learn Ultra-beheerder moet ook de REST-toepassing en de configuratie voor het delen van resources voor cross origin configureren.</span><span class="sxs-lookup"><span data-stu-id="43e55-130">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="43e55-131">Vul het volgende in om de REST-toepassing in te stellen</span><span class="sxs-lookup"><span data-stu-id="43e55-131">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="43e55-132">Open de Leerbeheerhulpmiddelen en selecteer **REST API-integraties** in de **sectie Integraties.**</span><span class="sxs-lookup"><span data-stu-id="43e55-132">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="43e55-133">Selecteer **Integraties maken** en voer dezelfde toepassings-/client-id in die u hebt ingevoerd voor het LTI-hulpprogramma Teams Blackboard Learn Class.</span><span class="sxs-lookup"><span data-stu-id="43e55-133">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="43e55-134">Voer de gebruiker leren in (dit kan uw eigen gebruikersnaam voor leren beheerders zijn) of selecteer **Bladeren om** te zoeken.</span><span class="sxs-lookup"><span data-stu-id="43e55-134">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="43e55-135">Selecteer **Ja** voor **Eindgebruikerstoegang.**</span><span class="sxs-lookup"><span data-stu-id="43e55-135">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="43e55-136">Selecteer **Ja** voor **Geautoriseerd om als gebruiker op te treden**</span><span class="sxs-lookup"><span data-stu-id="43e55-136">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="43e55-137">Selecteer **Verzenden zodra** deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="43e55-137">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="43e55-138">Cross-Origin Resource Sharing instellen</span><span class="sxs-lookup"><span data-stu-id="43e55-138">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="43e55-139">Toegang tot de Leerbeheerhulpmiddelen en selecteer Delen van resources over **meerdere origins** in **de sectie Integraties.**</span><span class="sxs-lookup"><span data-stu-id="43e55-139">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="43e55-140">Selecteer **Configuratie maken.**</span><span class="sxs-lookup"><span data-stu-id="43e55-140">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="43e55-141">Voer `https://bb-ms-teams-ultra-ext.api.blackboard.com` de origin in.</span><span class="sxs-lookup"><span data-stu-id="43e55-141">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="43e55-142">Voeg het woord **Autorisatie** toe aan **de toegestane kopteksten.**</span><span class="sxs-lookup"><span data-stu-id="43e55-142">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="43e55-143">Beschikbaar **instellen** op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="43e55-143">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="43e55-144">Selecteer **Verzenden zodra** deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="43e55-144">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="43e55-145">Klas-Teams inschakelen in Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="43e55-145">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="43e55-146">Nadat u de LTI-hulpprogramma's hebt ingeschakeld, is de volgende stap het instellen van de Microsoft Class-Teams van uw eigen Microsoft Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="43e55-146">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="43e55-147">U kunt dit doen door deze stappen uit te voeren als de Blackboard Learn Ultra-beheerder.</span><span class="sxs-lookup"><span data-stu-id="43e55-147">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="43e55-148">Selecteer **in Leer**  >  **beheerhulpmiddelen en -hulpprogramma's** **Microsoft Teams Integratiebeheerder.**</span><span class="sxs-lookup"><span data-stu-id="43e55-148">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![het dialoogvenster Hulpprogramma's en hulpprogramma's met een lijst met beschikbare hulpmiddelen](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="43e55-150">Schakel het selectievakje in voor **Inschakelen Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="43e55-150">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="43e55-151">Voer uw tenant-id in zoals wordt verwezen in de sectie onder Microsoft O365-beheerder</span><span class="sxs-lookup"><span data-stu-id="43e55-151">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="43e55-152">U kunt de instellingen pas opslaan als de app is goedgekeurd door de O365-beheerder. Zie [De app goedkeuren in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span><span class="sxs-lookup"><span data-stu-id="43e55-152">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="43e55-153">Wanneer de globale O365-beheerder de blackboard-Teams heeft goedgekeurd in uw Microsoft Tenant, selecteert u **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="43e55-153">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
