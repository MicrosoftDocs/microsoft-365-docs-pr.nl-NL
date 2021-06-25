---
title: Gebruik Microsoft Teams met Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: De Microsoft Teams met Canvas integreren
ms.openlocfilehash: 8e28cc8401dbf37d6e780b8f56dc300982abd0cc
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137677"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="eeffb-103">Gebruik Microsoft Teams met Canvas</span><span class="sxs-lookup"><span data-stu-id="eeffb-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eeffb-104">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="eeffb-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eeffb-105">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="eeffb-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="eeffb-106">Microsoft Teams lessen is een Learning app Hulpmiddelen interoperabiliteit (LTI) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun Learning Management System (LMS) en Teams.</span><span class="sxs-lookup"><span data-stu-id="eeffb-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="eeffb-107">Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="eeffb-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="eeffb-108">Microsoft Office 365 Beheerder</span><span class="sxs-lookup"><span data-stu-id="eeffb-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="eeffb-109">Voordat u de Microsoft Teams-integratie binnen Instructure Canvas beheert, is het belangrijk dat de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas is goedgekeurd door de Microsoft Office 365-beheerder van uw instelling in uw Microsoft Azure-tenant voordat u de canvasbeheerderconfiguratie voltooit.</span><span class="sxs-lookup"><span data-stu-id="eeffb-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="eeffb-110">Meld u aan bij Canvas.</span><span class="sxs-lookup"><span data-stu-id="eeffb-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="eeffb-111">Selecteer de **koppeling** Beheerder in de globale navigatie en selecteer vervolgens uw account.</span><span class="sxs-lookup"><span data-stu-id="eeffb-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="eeffb-112">Selecteer in de navigatie van de **beheerder de Instellingen** koppeling en vervolgens op het tabblad **Integraties.**</span><span class="sxs-lookup"><span data-stu-id="eeffb-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="eeffb-113">Schakel Microsoft Teams synchroniseren in door de schakelknop in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="eeffb-113">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="eeffb-115">Voer uw Microsoft-tenantnaam en aanmeldingskenmerk in.</span><span class="sxs-lookup"><span data-stu-id="eeffb-115">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="eeffb-116">Het aanmeldingskenmerk wordt gebruikt voor het koppelen van de Canvas-gebruiker aan een Azure Active Directory gebruiker.</span><span class="sxs-lookup"><span data-stu-id="eeffb-116">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

6. <span data-ttu-id="eeffb-117">Selecteer **Bijwerken Instellingen** eenmaal klaar.</span><span class="sxs-lookup"><span data-stu-id="eeffb-117">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="eeffb-118">Als u toegang wilt goedkeuren voor de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas, selecteert u de koppeling **Tenanttoegang verlenen.**</span><span class="sxs-lookup"><span data-stu-id="eeffb-118">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="eeffb-119">U wordt omgeleid naar het Microsoft Identity Platform Admin Consent Endpoint.</span><span class="sxs-lookup"><span data-stu-id="eeffb-119">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![machtigingen](media/permissions.png)

8. <span data-ttu-id="eeffb-121">Selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="eeffb-121">Select **Accept**.</span></span>
 
## <a name="canvas-admin"></a><span data-ttu-id="eeffb-122">Canvasbeheerder</span><span class="sxs-lookup"><span data-stu-id="eeffb-122">Canvas Admin</span></span>

<span data-ttu-id="eeffb-123">Stel de Microsoft Teams LTI 1.3-integratie in.</span><span class="sxs-lookup"><span data-stu-id="eeffb-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="eeffb-124">Als canvasbeheerder moet u de LTI-app Microsoft Teams in uw omgeving toevoegen.</span><span class="sxs-lookup"><span data-stu-id="eeffb-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="eeffb-125">Noteer de LTI-client-id voor de app.</span><span class="sxs-lookup"><span data-stu-id="eeffb-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="eeffb-126">Microsoft Teams klassen - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="eeffb-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="eeffb-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="eeffb-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="eeffb-128">Selecteer **+ App** om de Teams LTI-apps toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="eeffb-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![externe apps](media/external-apps.png)

3. <span data-ttu-id="eeffb-130">Selecteer **Op client-id** voor configuratietype.</span><span class="sxs-lookup"><span data-stu-id="eeffb-130">Select **By Client ID** for configuration type.</span></span>

   ![app toevoegen](media/add-app.png)

4. <span data-ttu-id="eeffb-132">Voer de opgegeven client-id in en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="eeffb-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="eeffb-133">U ziet de naam van Microsoft Teams LTI-app voor de client-id ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="eeffb-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="eeffb-134">Kies **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="eeffb-134">Select **Install**.</span></span>

   <span data-ttu-id="eeffb-135">De Microsoft Teams klassen LTI-app wordt toegevoegd aan de lijst met externe apps.</span><span class="sxs-lookup"><span data-stu-id="eeffb-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
