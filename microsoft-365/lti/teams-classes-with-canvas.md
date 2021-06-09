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
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821880"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="21a03-103">Gebruik Microsoft Teams met Canvas</span><span class="sxs-lookup"><span data-stu-id="21a03-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21a03-104">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="21a03-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="21a03-105">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="21a03-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="21a03-106">Microsoft Teams lessen is een LTI-app (Learning Tools Interoperability) waarmee docenten en leerlingen eenvoudig kunnen navigeren tussen hun LMS (Learning Management System) en Teams.</span><span class="sxs-lookup"><span data-stu-id="21a03-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="21a03-107">Gebruikers hebben rechtstreeks vanuit hun LMS toegang tot hun klasteams die aan hun cursus zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="21a03-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="21a03-108">Microsoft Office 365 Beheerder</span><span class="sxs-lookup"><span data-stu-id="21a03-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="21a03-109">Voordat u de Microsoft Teams-integratie binnen Instructure Canvas beheert, is het belangrijk dat de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas is goedgekeurd door de Microsoft Office 365-beheerder van uw instelling in uw Microsoft Azure-tenant voordat u de canvasbeheerderconfiguratie voltooit.</span><span class="sxs-lookup"><span data-stu-id="21a03-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="21a03-110">Meld u aan bij Canvas.</span><span class="sxs-lookup"><span data-stu-id="21a03-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="21a03-111">Selecteer de **koppeling** Beheerder in de globale navigatie en selecteer vervolgens uw account.</span><span class="sxs-lookup"><span data-stu-id="21a03-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="21a03-112">Selecteer in de navigatie van de **beheerder de Instellingen** koppeling en vervolgens op het tabblad **Integraties.**</span><span class="sxs-lookup"><span data-stu-id="21a03-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="21a03-113">Voer uw Microsoft-tenantnaam en aanmeldingskenmerk in.</span><span class="sxs-lookup"><span data-stu-id="21a03-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="21a03-114">Het aanmeldingskenmerk wordt gebruikt voor het koppelen van de Canvas-gebruiker aan een Azure Active Directory gebruiker.</span><span class="sxs-lookup"><span data-stu-id="21a03-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="21a03-115">Selecteer **Bijwerken Instellingen** eenmaal klaar.</span><span class="sxs-lookup"><span data-stu-id="21a03-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="21a03-116">Als u toegang wilt goedkeuren voor de **Microsoft-Teams-Sync-for-Canvas Azure-app** van Canvas, selecteert u de koppeling **Tenanttoegang verlenen.**</span><span class="sxs-lookup"><span data-stu-id="21a03-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="21a03-117">U wordt omgeleid naar het Microsoft Identity Platform Admin Consent Endpoint.</span><span class="sxs-lookup"><span data-stu-id="21a03-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![machtigingen](media/permissions.png)

7. <span data-ttu-id="21a03-119">Selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="21a03-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="21a03-120">Schakel de Microsoft Teams synchronisatie in door de schakelknop in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="21a03-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="21a03-122">Canvasbeheerder</span><span class="sxs-lookup"><span data-stu-id="21a03-122">Canvas Admin</span></span>

<span data-ttu-id="21a03-123">Stel de Microsoft Teams LTI 1.3-integratie in.</span><span class="sxs-lookup"><span data-stu-id="21a03-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="21a03-124">Als canvasbeheerder moet u de LTI-app Microsoft Teams in uw omgeving toevoegen.</span><span class="sxs-lookup"><span data-stu-id="21a03-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="21a03-125">Noteer de LTI-client-id voor de app.</span><span class="sxs-lookup"><span data-stu-id="21a03-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="21a03-126">Microsoft Teams klassen - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="21a03-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="21a03-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="21a03-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="21a03-128">Selecteer **+ App** om de Teams LTI-apps toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="21a03-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![externe apps](media/external-apps.png)

3. <span data-ttu-id="21a03-130">Selecteer **Op client-id** voor configuratietype.</span><span class="sxs-lookup"><span data-stu-id="21a03-130">Select **By Client ID** for configuration type.</span></span>

   ![app toevoegen](media/add-app.png)

4. <span data-ttu-id="21a03-132">Voer de opgegeven client-id in en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="21a03-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="21a03-133">U ziet de naam van Microsoft Teams LTI-app voor de client-id ter bevestiging.</span><span class="sxs-lookup"><span data-stu-id="21a03-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="21a03-134">Kies **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="21a03-134">Select **Install**.</span></span>

   <span data-ttu-id="21a03-135">De Microsoft Teams klassen LTI-app wordt toegevoegd aan de lijst met externe apps.</span><span class="sxs-lookup"><span data-stu-id="21a03-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
