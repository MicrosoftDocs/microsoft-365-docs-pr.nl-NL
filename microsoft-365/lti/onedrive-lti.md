---
title: Interoperabiliteit Microsoft OneDrive Learning hulpprogramma's gebruiken
ms.author: heidip
author: MicrosoftHeidi
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
description: Maak en cijfertoewijzingen, bouw en beheer cursusinhoud en werk in realtime samen aan bestanden met de nieuwe Microsoft OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322219"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="c9a3d-103">Integratie Microsoft OneDrive LTI met Canvas</span><span class="sxs-lookup"><span data-stu-id="c9a3d-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="c9a3d-104">Het integreren Microsoft OneDrive LTI met Canvas is een proces in twee stappen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="c9a3d-105">Met de eerste stap kunt Microsoft OneDrive in Canvas en met de tweede stap wordt de Microsoft OneDrive LTI beschikbaar in canvascursussen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="c9a3d-106">Aanbevolen browserinstellingen</span><span class="sxs-lookup"><span data-stu-id="c9a3d-106">Recommended browser settings</span></span>

- <span data-ttu-id="c9a3d-107">Cookies moeten zijn ingeschakeld voor Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="c9a3d-108">Pop-ups mogen niet worden geblokkeerd voor Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="c9a3d-109">Cookies zijn standaard niet ingeschakeld in de incognitomodus van de Chrome-browser en moeten worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="c9a3d-110">Microsoft OneDrive LTI werkt in de privémodus in Microsoft Edge browser.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="c9a3d-111">Zorg ervoor dat u cookies niet hebt geblokkeerd (die standaard zijn ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="c9a3d-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="c9a3d-112">LTI Microsoft OneDrive in canvas inschakelen</span><span class="sxs-lookup"><span data-stu-id="c9a3d-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9a3d-113">De persoon die deze integratie uitvoert, moet een beheerder van Canvas zijn en een beheerder van de Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="c9a3d-114">Meld u aan <a href="https://onedrivelti.microsoft.com/admin" target="_blank">bij Microsoft OneDrive LTI-registratieportal</a></span><span class="sxs-lookup"><span data-stu-id="c9a3d-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="c9a3d-115">Selecteer de **knop Toestemming van** beheerder en accepteer de machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="c9a3d-116">Als deze stap niet wordt uitgevoerd, krijgt u een foutmelding in de volgende stap en kunt u deze stap een uur lang niet uitvoeren nadat u de fout hebt gekregen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="c9a3d-117">Selecteer de **knop Nieuwe LTI-tenant** maken.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="c9a3d-118">Selecteer canvas op de  pagina LTI-registratie in de vervolgkeuzekeuzepagina en voer de basis-URL van het canvas-exemplaar in.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="c9a3d-119">Als uw canvas-exemplaar bijvoorbeeld https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) is, moet de volledige URL worden ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="De pagina LTI-tenantbeheer, met een vervolgkeuzeveld voor het kiezen van het LTI-consumentenplatform en een URL-tekstveld.":::

4. <span data-ttu-id="c9a3d-121">Kopieer de JSON door de **knop** Kopiëren te selecteren (een pictogram aan de rechterkant met twee pagina's boven op elkaar).</span><span class="sxs-lookup"><span data-stu-id="c9a3d-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="c9a3d-122">Hiermee wordt de sleutel in Canvas gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Een afbeelding met de kopieerknop die de weergegeven JSON-tekst kopieert en deze beschikbaar maakt voor sleutelgeneratie in Canvas.":::

5. <span data-ttu-id="c9a3d-124">Meld u als beheerder aan bij het canvas-exemplaar en selecteer **Ontwikkelaarstoetsen** in het menu aan de linkerkant van de pagina.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="c9a3d-125">Maak in de vervolgkeuzepagina een ontwikkelaarssleutel door **LTI-toets** te kiezen in de vervolgkeuzepagina rechtsboven op de pagina.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Een schermafbeelding met de linkernavigatiebalk waarop Ontwikkelaarstoetsen zijn geselecteerd en het item LTI-toets geselecteerd in een vervolgkeuzekeuzevenster aan de rechterkant van de pagina.":::

6. <span data-ttu-id="c9a3d-127">Selecteer op de pagina  Configureren in de vervolgkeuzekeuzepagina Methode **JSON** plakken als methode en plak de JSON-tekst die u hebt gekopieerd in stap 5 in het tekstveld dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="c9a3d-128">Sla de sleutel op en deze wordt beschikbaar in Canvas in **de status Uit.**</span><span class="sxs-lookup"><span data-stu-id="c9a3d-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="c9a3d-129">Schakel de toets **In en** kopieer de sleutel in de **kolom Details** die u in de volgende stap wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="De pagina Canvas met de sleutel die is ingesteld in een uitgeschakelde toestand. Deze moet zijn ingeschakeld en de sleutel moet worden gekopieerd uit de kolom details op deze pagina.":::

8. <span data-ttu-id="c9a3d-131">Ga terug naar de Microsoft OneDrive LTI-registratieportal en plak de sleutel in het **veld Canvas Client-id.**</span><span class="sxs-lookup"><span data-stu-id="c9a3d-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="c9a3d-132">Selecteer **Volgende** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="De LTI-tenantregistratiepagina, waarin de JSON-tekst en het tekstvak worden weergegeven waarin de sleutel moet worden gekopieerd.":::

9. <span data-ttu-id="c9a3d-134">Controleer en sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-134">Review and save your changes.</span></span> <span data-ttu-id="c9a3d-135">Er wordt een bericht weergegeven bij een geslaagde registratie.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="c9a3d-136">Uw registratiegegevens kunnen ook worden gecontroleerd door de knop **LTI-tenants** weergeven op de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="c9a3d-137">LTI Microsoft OneDrive in canvascursussen inschakelen</span><span class="sxs-lookup"><span data-stu-id="c9a3d-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="c9a3d-138">Een canvasbeheerder kan de Microsoft OneDrive LTI inschakelen voor alle cursussen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="c9a3d-139">Als Microsoft OneDrive LTI nodig is in een specifieke cursus (en niet alle cursussen), moet de docent dezelfde stappen volgen binnen de cursusinstellingen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="c9a3d-140">Meld u aan als beheerder en ga naar de **Instellingen** sectie.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="c9a3d-141">Ga naar de **sectie Apps** en selecteer de **knop App-configuraties** weergeven.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="c9a3d-142">Selecteer de **knop App** toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="c9a3d-143">Kies in **de vervolgkeuzekeuzeoptie** Configuratietype de **optie Op client-id.**</span><span class="sxs-lookup"><span data-stu-id="c9a3d-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="c9a3d-144">Plak de waarde van de ontwikkelaarssleutel die eerder is gegenereerd in het **veld Client-id** en selecteer de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="De pagina App toevoegen, met de optie Door client-id onder de vervolgkeuzelijst Configuratietype.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="c9a3d-146">Samenwerking Instellingen voor Microsoft OneDrive LTI in canvascursussen</span><span class="sxs-lookup"><span data-stu-id="c9a3d-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="c9a3d-147">Als u wilt samenwerken voor docenten en leerlingen/studenten, moet u de samenwerkingsinstelling niet inschakelen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="c9a3d-148">Als u wilt weten of de instelling niet is ingeschakeld, volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="c9a3d-149">Meld u aan als beheerder en ga naar de **Instellingen** sectie.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="c9a3d-150">Ga naar **de sectie Functieopties** en ga naar de **sectie** Cursus.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="c9a3d-151">Stel de **functie Extern samenwerkingshulpmiddel** zo in dat deze niet is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="c9a3d-152">Samenwerking kan worden toegewezen aan individuele leerlingen/studenten en aan groepen leerlingen/studenten.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="c9a3d-153">Het toewijzen aan afzonderlijke leerlingen/studenten werkt standaard.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="c9a3d-154">Als u samenwerking wilt kunnen toewijzen aan een groep leerlingen/studenten, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="c9a3d-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="c9a3d-155">Meld u aan als beheerder en ga naar de **sectie Ontwikkelaarssleutels.**</span><span class="sxs-lookup"><span data-stu-id="c9a3d-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="c9a3d-156">Zoek de sleutel met waarde 17000000000710 en stel deze in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="c9a3d-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
