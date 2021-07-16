---
title: Gebruik Microsoft Teams met Canvas
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
description: De Microsoft Teams met Canvas integreren
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454683"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="95397-103">Gebruik Microsoft Teams met Canvas</span><span class="sxs-lookup"><span data-stu-id="95397-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="95397-104">Microsoft Teams lessen is een Learning app Hulpmiddelen interoperabiliteit (LTI) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun Learning Management System (LMS) en Teams.</span><span class="sxs-lookup"><span data-stu-id="95397-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="95397-105">Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="95397-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="95397-106">Vereisten vóór implementatie</span><span class="sxs-lookup"><span data-stu-id="95397-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="95397-107">De huidige class Teams LTI ondersteunt alleen het synchroniseren van Canvas-gebruikers met Microsoft Azure Active Directory (AAD) in een beperkt bereik.</span><span class="sxs-lookup"><span data-stu-id="95397-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="95397-108">Uw tenant moet een exacte overeenkomst hebben tussen een Canvas-veld (e-mail, gebruikers-id of SIS-id) en de UPN in Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="95397-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="95397-109">We werken eraan om de flexibiliteit voor de synchronisatiefunctionaliteit uit te breiden, maar in de tussentijd worden gebruikers in Canvas die niet zijn afgestemd op een UPN in AAD niet toegevoegd aan de Teams-klas gesynchroniseerd met Canvas.</span><span class="sxs-lookup"><span data-stu-id="95397-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="95397-110">Er kan slechts één Microsoft-tenant worden gebruikt voor het toewijzen van gebruikers tussen Canvas en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95397-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="95397-111">U moet SDS uitschakelen voordat u de klasse Teams LTI gebruikt om duplicatie van groepen te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="95397-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="95397-112">Microsoft Office 365 Beheerder</span><span class="sxs-lookup"><span data-stu-id="95397-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="95397-113">Voordat u de Microsoft Teams-integratie binnen Instructure Canvas beheert, is het belangrijk dat de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas is goedgekeurd door de Microsoft Office 365-beheerder van uw instelling in uw Microsoft Azure-tenant voordat u de canvasbeheerderconfiguratie voltooit.</span><span class="sxs-lookup"><span data-stu-id="95397-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="95397-114">Meld u aan bij Canvas.</span><span class="sxs-lookup"><span data-stu-id="95397-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="95397-115">Selecteer de **koppeling** Beheerder in de globale navigatie en selecteer vervolgens uw account.</span><span class="sxs-lookup"><span data-stu-id="95397-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="95397-116">Selecteer in de navigatie van de **beheerder de Instellingen** koppeling en vervolgens op het tabblad **Integraties.**</span><span class="sxs-lookup"><span data-stu-id="95397-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="95397-117">Schakel Microsoft Teams synchroniseren in door de schakelknop in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="95397-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="95397-119">Voer uw Microsoft-tenantnaam en aanmeldingskenmerk in.</span><span class="sxs-lookup"><span data-stu-id="95397-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="95397-120">Het aanmeldingskenmerk wordt gebruikt voor het koppelen van de Canvas-gebruiker aan een Azure Active Directory gebruiker.</span><span class="sxs-lookup"><span data-stu-id="95397-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="95397-121">Selecteer **Bijwerken Instellingen** eenmaal klaar.</span><span class="sxs-lookup"><span data-stu-id="95397-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="95397-122">Als u toegang wilt goedkeuren voor de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas, selecteert u de koppeling **Tenanttoegang verlenen.**</span><span class="sxs-lookup"><span data-stu-id="95397-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="95397-123">U wordt omgeleid naar het Microsoft Identity Platform Admin Consent Endpoint.</span><span class="sxs-lookup"><span data-stu-id="95397-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![machtigingen](media/permissions.png)

8. <span data-ttu-id="95397-125">Selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="95397-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="95397-126">Canvasbeheerder</span><span class="sxs-lookup"><span data-stu-id="95397-126">Canvas Admin</span></span>

<span data-ttu-id="95397-127">Stel de Microsoft Teams LTI 1.3-integratie in.</span><span class="sxs-lookup"><span data-stu-id="95397-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="95397-128">Als canvasbeheerder moet u de LTI-app Microsoft Teams in uw omgeving toevoegen.</span><span class="sxs-lookup"><span data-stu-id="95397-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="95397-129">Noteer de LTI-client-id voor de app.</span><span class="sxs-lookup"><span data-stu-id="95397-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="95397-130">Microsoft Teams klassen - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="95397-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="95397-131">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="95397-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="95397-132">Selecteer **+ App** om de Teams LTI-apps toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="95397-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![externe apps](media/external-apps.png)

3. <span data-ttu-id="95397-134">Selecteer **Op client-id** voor configuratietype.</span><span class="sxs-lookup"><span data-stu-id="95397-134">Select **By Client ID** for configuration type.</span></span>

   ![app toevoegen](media/add-app.png)

4. <span data-ttu-id="95397-136">Voer de opgegeven client-id in en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="95397-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="95397-137">U ziet de naam van Microsoft Teams LTI-app voor de client-id ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="95397-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="95397-138">Kies **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="95397-138">Select **Install**.</span></span>

   <span data-ttu-id="95397-139">De Microsoft Teams klassen LTI-app wordt toegevoegd aan de lijst met externe apps.</span><span class="sxs-lookup"><span data-stu-id="95397-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="95397-140">De LTI-app voor canvascursussen inschakelen</span><span class="sxs-lookup"><span data-stu-id="95397-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="95397-141">Als u de LTI-app in een cursus wilt gebruiken, moet een docent van de canvascursus integratiessynchronisatie inschakelen. Elke cursus moet door een docent zijn ingeschakeld voor het maken van een overeenkomend team. er is geen globaal mechanisme voor het maken van teams.</span><span class="sxs-lookup"><span data-stu-id="95397-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="95397-142">Dit is ontworpen als een voorzorgsmaatregel om te voorkomen dat ongewenste teams worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="95397-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="95397-143">Verwijs uw docenten naar de documentatie voor docenten [voor](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) het inschakelen van de LTI-app voor elke cursus en het voltooien van de integratie-instelling.</span><span class="sxs-lookup"><span data-stu-id="95397-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
