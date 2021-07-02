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
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256972"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="d9801-103">Integratie Microsoft OneDrive LTI met Canvas</span><span class="sxs-lookup"><span data-stu-id="d9801-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="d9801-104">Het integreren Microsoft OneDrive LTI met Canvas is een proces in twee stappen.</span><span class="sxs-lookup"><span data-stu-id="d9801-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="d9801-105">Met de eerste stap kunt Microsoft OneDrive in Canvas en met de tweede stap wordt de Microsoft OneDrive LTI beschikbaar in canvascursussen.</span><span class="sxs-lookup"><span data-stu-id="d9801-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="d9801-106">Aanbevolen browserinstellingen</span><span class="sxs-lookup"><span data-stu-id="d9801-106">Recommended browser settings</span></span>

- <span data-ttu-id="d9801-107">Cookies moeten zijn ingeschakeld voor Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d9801-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="d9801-108">Pop-ups mogen niet worden geblokkeerd voor Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d9801-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="d9801-109">Cookies zijn standaard niet ingeschakeld in de incognitomodus van de Chrome-browser en moeten worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d9801-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="d9801-110">Microsoft OneDrive LTI werkt in de privémodus in Microsoft Edge browser.</span><span class="sxs-lookup"><span data-stu-id="d9801-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="d9801-111">Zorg ervoor dat u cookies niet hebt geblokkeerd (die standaard zijn ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="d9801-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="d9801-112">LTI Microsoft OneDrive in canvas inschakelen</span><span class="sxs-lookup"><span data-stu-id="d9801-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9801-113">De persoon die deze integratie uitvoert, moet een beheerder van Canvas zijn en een beheerder van de Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="d9801-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="d9801-114">Meld u aan <a href="https://onedrivelti.microsoft.com/admin" target="_blank">bij Microsoft OneDrive LTI-registratieportal</a></span><span class="sxs-lookup"><span data-stu-id="d9801-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="d9801-115">Selecteer de **knop Toestemming van** beheerder en accepteer de machtigingen.</span><span class="sxs-lookup"><span data-stu-id="d9801-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="d9801-116">Selecteer de **knop Nieuwe LTI-tenant** maken.</span><span class="sxs-lookup"><span data-stu-id="d9801-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="d9801-117">Selecteer canvas op de  pagina LTI-registratie in de vervolgkeuzekeuzepagina en voer de basis-URL van het canvas-exemplaar in.</span><span class="sxs-lookup"><span data-stu-id="d9801-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="d9801-118">Als uw canvas-exemplaar bijvoorbeeld https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) is, moet de volledige URL worden ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="d9801-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="De pagina LTI-tenantbeheer, met een vervolgkeuzeveld voor het kiezen van het LTI-consumentenplatform en een URL-tekstveld.":::

4. <span data-ttu-id="d9801-120">Kopieer de JSON door de **knop** Kopiëren te selecteren (een pictogram aan de rechterkant met twee pagina's boven op elkaar).</span><span class="sxs-lookup"><span data-stu-id="d9801-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="d9801-121">Hiermee wordt de sleutel in Canvas gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="d9801-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Een afbeelding met de kopieerknop die de weergegeven JSON-tekst kopieert en deze beschikbaar maakt voor sleutelgeneratie in Canvas.":::

5. <span data-ttu-id="d9801-123">Meld u als beheerder aan bij het canvas-exemplaar en selecteer **Ontwikkelaarstoetsen** in het menu aan de linkerkant van de pagina.</span><span class="sxs-lookup"><span data-stu-id="d9801-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="d9801-124">Maak in de vervolgkeuzepagina een ontwikkelaarssleutel door **LTI-toets** te kiezen in de vervolgkeuzepagina rechtsboven op de pagina.</span><span class="sxs-lookup"><span data-stu-id="d9801-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Een schermafbeelding met de linkernavigatiebalk waarop Ontwikkelaarstoetsen zijn geselecteerd en het item LTI-toets geselecteerd in een vervolgkeuzekeuzevenster aan de rechterkant van de pagina.":::

6. <span data-ttu-id="d9801-126">Selecteer op de pagina  Configureren in de vervolgkeuzekeuzepagina Methode **JSON** plakken als methode en plak de JSON-tekst die u hebt gekopieerd in stap 5 in het tekstveld dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d9801-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="d9801-127">Sla de sleutel op en deze wordt beschikbaar in Canvas in **de status Uit.**</span><span class="sxs-lookup"><span data-stu-id="d9801-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="d9801-128">Schakel de toets **In en** kopieer de sleutel in de **kolom Details** die u in de volgende stap wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d9801-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="De pagina Canvas met de sleutel die is ingesteld in een uitgeschakelde toestand. Deze moet zijn ingeschakeld en de sleutel moet worden gekopieerd uit de kolom details op deze pagina.":::

8. <span data-ttu-id="d9801-130">Ga terug naar de Microsoft OneDrive LTI-registratieportal en plak de sleutel in het **veld Canvas Client-id.**</span><span class="sxs-lookup"><span data-stu-id="d9801-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="d9801-131">Selecteer **Volgende** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="d9801-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="De LTI-tenantregistratiepagina, waarin de JSON-tekst en het tekstvak worden weergegeven waarin de sleutel moet worden gekopieerd.":::

9. <span data-ttu-id="d9801-133">Controleer en sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="d9801-133">Review and save your changes.</span></span> <span data-ttu-id="d9801-134">Er wordt een bericht weergegeven bij een geslaagde registratie.</span><span class="sxs-lookup"><span data-stu-id="d9801-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="d9801-135">Uw registratiegegevens kunnen ook worden gecontroleerd door de knop **LTI-tenants** weergeven op de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d9801-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="d9801-136">LTI Microsoft OneDrive in canvascursussen inschakelen</span><span class="sxs-lookup"><span data-stu-id="d9801-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="d9801-137">Een canvasbeheerder kan de Microsoft OneDrive LTI inschakelen voor alle cursussen.</span><span class="sxs-lookup"><span data-stu-id="d9801-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="d9801-138">Als Microsoft OneDrive LTI nodig is in een specifieke cursus (en niet alle cursussen), moet de docent dezelfde stappen volgen binnen de cursusinstellingen.</span><span class="sxs-lookup"><span data-stu-id="d9801-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="d9801-139">Meld u aan als beheerder en ga naar de **Instellingen** sectie.</span><span class="sxs-lookup"><span data-stu-id="d9801-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="d9801-140">Ga naar de **sectie Apps** en selecteer de **knop App-configuraties** weergeven.</span><span class="sxs-lookup"><span data-stu-id="d9801-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="d9801-141">Selecteer de **knop App** toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d9801-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="d9801-142">Kies in **de vervolgkeuzekeuzeoptie** Configuratietype de **optie Op client-id.**</span><span class="sxs-lookup"><span data-stu-id="d9801-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="d9801-143">Plak de waarde van de ontwikkelaarssleutel die eerder is gegenereerd in het **veld Client-id** en selecteer de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="d9801-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="De pagina App toevoegen, met de optie Door client-id onder de vervolgkeuzelijst Configuratietype.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="d9801-145">Samenwerking Instellingen voor Microsoft OneDrive LTI in canvascursussen</span><span class="sxs-lookup"><span data-stu-id="d9801-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="d9801-146">Als u wilt samenwerken voor docenten en leerlingen/studenten, moet u de samenwerkingsinstelling niet inschakelen.</span><span class="sxs-lookup"><span data-stu-id="d9801-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="d9801-147">Als u wilt weten of de instelling niet is ingeschakeld, volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="d9801-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="d9801-148">Meld u aan als beheerder en ga naar de **Instellingen** sectie.</span><span class="sxs-lookup"><span data-stu-id="d9801-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="d9801-149">Ga naar **de sectie Functieopties** en ga naar de **sectie** Cursus.</span><span class="sxs-lookup"><span data-stu-id="d9801-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="d9801-150">Stel de **functie Extern samenwerkingshulpmiddel** zo in dat deze niet is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d9801-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="d9801-151">Samenwerking kan worden toegewezen aan individuele leerlingen/studenten en aan groepen leerlingen/studenten.</span><span class="sxs-lookup"><span data-stu-id="d9801-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="d9801-152">Het toewijzen aan afzonderlijke leerlingen/studenten werkt standaard.</span><span class="sxs-lookup"><span data-stu-id="d9801-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="d9801-153">Als u samenwerking wilt kunnen toewijzen aan een groep leerlingen/studenten, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d9801-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="d9801-154">Meld u aan als beheerder en ga naar de **sectie Ontwikkelaarssleutels.**</span><span class="sxs-lookup"><span data-stu-id="d9801-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="d9801-155">Zoek de sleutel met waarde 17000000000710 en stel deze in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="d9801-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
