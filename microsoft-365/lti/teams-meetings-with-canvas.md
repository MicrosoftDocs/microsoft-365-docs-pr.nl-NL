---
title: Vergaderingen Microsoft Teams Canvas gebruiken
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
description: Vergaderingen Microsoft Teams canvas integreren
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454671"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="adcac-103">Vergaderingen Microsoft Teams Canvas gebruiken</span><span class="sxs-lookup"><span data-stu-id="adcac-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="adcac-104">Microsoft Teams vergaderingen is een app Learning Tools Interoperability (LTI) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun Learning Management System (LMS) en Teams.</span><span class="sxs-lookup"><span data-stu-id="adcac-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="adcac-105">Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="adcac-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="adcac-106">Microsoft Office 365 Beheerder</span><span class="sxs-lookup"><span data-stu-id="adcac-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="adcac-107">Voordat u de Microsoft Teams-integratie binnen Instructure Canvas beheert, is het belangrijk dat de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas is goedgekeurd door de Microsoft Office 365-beheerder van uw instelling in uw Microsoft Azure-tenant voordat u de canvasbeheerderconfiguratie voltooit.</span><span class="sxs-lookup"><span data-stu-id="adcac-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="adcac-108">Meld u aan bij Canvas.</span><span class="sxs-lookup"><span data-stu-id="adcac-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="adcac-109">Selecteer de **koppeling** Beheerder in de globale navigatie en selecteer vervolgens uw account.</span><span class="sxs-lookup"><span data-stu-id="adcac-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="adcac-110">Selecteer in de navigatie van de **beheerder de Instellingen** koppeling en vervolgens op het tabblad **Integraties.**</span><span class="sxs-lookup"><span data-stu-id="adcac-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="adcac-111">Voer uw Microsoft-tenantnaam en aanmeldingskenmerk in.</span><span class="sxs-lookup"><span data-stu-id="adcac-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="adcac-112">Het aanmeldingskenmerk wordt gebruikt voor het koppelen van de Canvas-gebruiker aan een Azure Active Directory gebruiker.</span><span class="sxs-lookup"><span data-stu-id="adcac-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="adcac-113">Selecteer **Bijwerken Instellingen** eenmaal klaar.</span><span class="sxs-lookup"><span data-stu-id="adcac-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="adcac-114">Als u toegang wilt goedkeuren voor de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas, selecteert u de koppeling **Tenanttoegang verlenen.**</span><span class="sxs-lookup"><span data-stu-id="adcac-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="adcac-115">U wordt omgeleid naar het Microsoft Identity Platform Admin Consent Endpoint.</span><span class="sxs-lookup"><span data-stu-id="adcac-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![machtigingen](media/permissions.png)

7. <span data-ttu-id="adcac-117">Selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="adcac-117">Select **Accept**.</span></span>

8. <span data-ttu-id="adcac-118">Schakel de Microsoft Teams synchronisatie in door de schakelknop in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="adcac-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="adcac-120">Canvasbeheerder</span><span class="sxs-lookup"><span data-stu-id="adcac-120">Canvas Admin</span></span>

<span data-ttu-id="adcac-121">Stel de Microsoft Teams LTI 1.3-integratie in.</span><span class="sxs-lookup"><span data-stu-id="adcac-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="adcac-122">Als canvasbeheerder moet u de LTI-app voor vergaderingen Microsoft Teams in uw omgeving toevoegen.</span><span class="sxs-lookup"><span data-stu-id="adcac-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="adcac-123">Noteer de LTI-client-id voor de app.</span><span class="sxs-lookup"><span data-stu-id="adcac-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="adcac-124">Microsoft Teams vergaderingen - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="adcac-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="adcac-125">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="adcac-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="adcac-126">Selecteer **+ App** om de Teams LTI-apps toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="adcac-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![externe apps](media/external-apps.png)

3. <span data-ttu-id="adcac-128">Selecteer **Op client-id** voor configuratietype.</span><span class="sxs-lookup"><span data-stu-id="adcac-128">Select **By Client ID** for configuration type.</span></span>

   ![app toevoegen](media/add-app.png)

4. <span data-ttu-id="adcac-130">Voer de opgegeven client-id in en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="adcac-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="adcac-131">U ziet de naam van Microsoft Teams LTI-app voor de client-id ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="adcac-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="adcac-132">Kies **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="adcac-132">Select **Install**.</span></span>

   <span data-ttu-id="adcac-133">De Microsoft Teams LTI-app voor vergaderingen wordt toegevoegd aan de lijst met externe apps.</span><span class="sxs-lookup"><span data-stu-id="adcac-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="adcac-134">Canvascursussen inschakelen</span><span class="sxs-lookup"><span data-stu-id="adcac-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="adcac-135">Als u de LTI in een cursus wilt gebruiken, moet een docent van de canvascursus de synchronisatie van de integraties inschakelen. Elke cursus moet door een docent zijn ingeschakeld om een overeenkomstige Teams te maken; er is geen globaal mechanisme voor het Teams maken.</span><span class="sxs-lookup"><span data-stu-id="adcac-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="adcac-136">Dit is ontworpen uit voorzorg om te voorkomen dat ongewenste Teams worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="adcac-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="adcac-137">Raadpleeg uw docenten voor documentatie over [docenten](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) voor het inschakelen van de LTI voor elke cursus en het afronden van de integratie-instelling.</span><span class="sxs-lookup"><span data-stu-id="adcac-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
