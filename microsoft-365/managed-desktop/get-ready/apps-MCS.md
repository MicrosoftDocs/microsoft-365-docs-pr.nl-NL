---
title: Werken met Microsoft Consulting Services
description: Voorbereidingen en stappen die u moet volgen om samen te werken met MCS om uw apps te verpakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1441ca3305a5f3e5a83ddd5e1547812f08d7d96b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445694"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="a9108-104">Werken met Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="a9108-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="a9108-105">U kunt microsoft Consulting Services (MCS) gebruiken om uw apps te laten verpakken voor gebruik met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a9108-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a9108-106">Voor meer informatie kunt u contact opnemen met uw accountvertegenwoordiger om contact op te nemen met MCS en het specifieke app-verpakkingsproject te bekijken.</span><span class="sxs-lookup"><span data-stu-id="a9108-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="a9108-107">Rollen en verantwoordelijkheden</span><span class="sxs-lookup"><span data-stu-id="a9108-107">Roles and responsibilities</span></span>

<span data-ttu-id="a9108-108">Als u wilt werken met mcs-app-verpakking, **moet u de volgende elementen leveren:**</span><span class="sxs-lookup"><span data-stu-id="a9108-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="a9108-109">De broninstallateurbestanden (bijvoorbeeld setup.exe of .msi).</span><span class="sxs-lookup"><span data-stu-id="a9108-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="a9108-110">De installatie-instructies, met informatie over hoe de uiteindelijke installatie eruit moet zien.</span><span class="sxs-lookup"><span data-stu-id="a9108-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="a9108-111">Moet er bijvoorbeeld een bureaubladsnelkoppeling naar de app zijn?</span><span class="sxs-lookup"><span data-stu-id="a9108-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="a9108-112">Wat moet de zichtbaarheid van de app zijn?</span><span class="sxs-lookup"><span data-stu-id="a9108-112">What should the app's visibility be?</span></span> <span data-ttu-id="a9108-113">Moet de app verbinding maken met een server en zo ja, welke?</span><span class="sxs-lookup"><span data-stu-id="a9108-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="a9108-114">Zie de aanvraagsjabloon [voor aanvraag voor toepassingen voor meer informatie.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="a9108-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="a9108-115">U moet uw eigen acceptatietest uitvoeren om te controleren of de app werkt zoals u dat nodig hebt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="a9108-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="a9108-116">**MCS zorgt voor de volgende acties:**</span><span class="sxs-lookup"><span data-stu-id="a9108-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="a9108-117">Controleren of de app is verboden of beperkt in de Microsoft Managed Desktop-omgeving.</span><span class="sxs-lookup"><span data-stu-id="a9108-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="a9108-118">Testen van de installatie, het starten en verwijderen van de app om de compatibiliteit met Windows 10 te waarborgen.</span><span class="sxs-lookup"><span data-stu-id="a9108-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="a9108-119">Als MCS een compatibiliteitsprobleem detecteert, wordt de app door mcs overgehandigd aan het [App Assure-programma](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) voor herstel.</span><span class="sxs-lookup"><span data-stu-id="a9108-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="a9108-120">De app inpakken op uw specificatie en vervolgens app-implementatie testen met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a9108-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="a9108-121">Planning voor app-bezorging</span><span class="sxs-lookup"><span data-stu-id="a9108-121">App delivery schedule</span></span>

<span data-ttu-id="a9108-122">Start het verpakkingsproces door de app-informatie te uploaden naar de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="a9108-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a9108-123">Het verpakkingsteam bekijkt elke donderdag nieuwe inzendingen.</span><span class="sxs-lookup"><span data-stu-id="a9108-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="a9108-124">Na controle en verpakking worden de verpakte apps de volgende vrijdag bezorgd.</span><span class="sxs-lookup"><span data-stu-id="a9108-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="a9108-125">Er kunnen maximaal vijf apps per week worden verpakt om te starten, maar de service kan worden opgeschaald naar uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="a9108-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![agenda met app-instroom op een donderdag (de 21e in dit voorbeeld), mediavalidatie de volgende dag, verpakking op de volgende maandag (de 25e) en app-bezorging op de volgende vrijdag (de 29e)](../../media/MCS-cal.png)

<span data-ttu-id="a9108-127">U krijgt een melding zodra de app is geleverd.</span><span class="sxs-lookup"><span data-stu-id="a9108-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="a9108-128">Op dat moment hebt u 21 dagen om acceptatietests uit te voeren en het werk goed te keuren in de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="a9108-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a9108-129">Als u tijdens uw acceptatietest een probleem met de app ontdekt, weigert u de app in de Microsoft Managed Desktop-portal en wordt u via e-mail verbonden met een MCS-packager om het probleem te begrijpen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="a9108-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="a9108-130">Accounts en omgeving testen</span><span class="sxs-lookup"><span data-stu-id="a9108-130">Testing accounts and environment</span></span>

<span data-ttu-id="a9108-131">Als het verpakkingsteam de migratie naar Microsoft Intune wil voltooien, raden we u aan bepaalde machtigingen in te leveren:</span><span class="sxs-lookup"><span data-stu-id="a9108-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="a9108-132">Toegang tot de app-implementatiemogelijkheden van Microsoft Intune voor de packager om de app toe te voegen en toe te wijzen</span><span class="sxs-lookup"><span data-stu-id="a9108-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="a9108-133">Testgroepen, gebruikersaccounts en licenties voor de verwerkers om de apps te kunnen testen</span><span class="sxs-lookup"><span data-stu-id="a9108-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="a9108-134">MCS gebruikt deze machtigingen om de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="a9108-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="a9108-135">Ervoor zorgen dat de app werkt op een virtuele computer die is geconfigureerd voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a9108-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="a9108-136">De app uploaden naar Microsoft Intune voor implementatie naar uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="a9108-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="a9108-137">Zonder deze machtigingen kan MCS verder gaan, maar kunnen ze de toepassingen niet uploaden naar uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="a9108-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
