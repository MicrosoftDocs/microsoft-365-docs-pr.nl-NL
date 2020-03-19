---
title: Werken met Microsoft Consulting Services
description: voorbereiding en stappen die moeten worden gevolgd om met MCS samen te werken om uw apps te verpakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, MCS, verpakking
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0cb4da85b5548ced757197a3af818e212b065b47
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806829"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="62c1f-104">Werken met Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="62c1f-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="62c1f-105">U contact opnemen met Microsoft Consulting Services (MCS) om uw apps te laten verpakken voor gebruik met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="62c1f-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="62c1f-106">Werk voor meer informatie samen met uw accountvertegenwoordiger contact op met MCS en bereik uw specifieke app-verpakkingsproject.</span><span class="sxs-lookup"><span data-stu-id="62c1f-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="62c1f-107">Rollen en verantwoordelijkheden</span><span class="sxs-lookup"><span data-stu-id="62c1f-107">Roles and responsibilities</span></span>

<span data-ttu-id="62c1f-108">Als u wilt werken met mcs-appverpakking, **moet u deze elementen opgeven:**</span><span class="sxs-lookup"><span data-stu-id="62c1f-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="62c1f-109">De broninstallatiebestanden (bijvoorbeeld setup.exe of .msi).</span><span class="sxs-lookup"><span data-stu-id="62c1f-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="62c1f-110">De installatie-instructies, met details over hoe de uiteindelijke installatie eruit moet zien.</span><span class="sxs-lookup"><span data-stu-id="62c1f-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="62c1f-111">Moet er bijvoorbeeld een snelkoppeling naar de app zijn?</span><span class="sxs-lookup"><span data-stu-id="62c1f-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="62c1f-112">Wat moet de zichtbaarheid van de app zijn?</span><span class="sxs-lookup"><span data-stu-id="62c1f-112">What should the app's visibility be?</span></span> <span data-ttu-id="62c1f-113">Moet de app verbinding maken met een server en zo ja, welke?</span><span class="sxs-lookup"><span data-stu-id="62c1f-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="62c1f-114">Zie voor meer informatie de sjabloon voor de [aanvraag voor de aanvraag](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)voor de verpakking van toepassingen .</span><span class="sxs-lookup"><span data-stu-id="62c1f-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="62c1f-115">U moet uw eigen acceptatietests uitvoeren om te controleren of de app werkt zoals u dat nodig hebt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="62c1f-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="62c1f-116">**MCS zal deze acties verzorgen:**</span><span class="sxs-lookup"><span data-stu-id="62c1f-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="62c1f-117">Controleren of de app verboden of beperkt is in de Microsoft Managed Desktop-omgeving.</span><span class="sxs-lookup"><span data-stu-id="62c1f-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="62c1f-118">Het testen van de installatie, het starten en verwijderen van de app om compatibiliteit met Windows 10 te garanderen.</span><span class="sxs-lookup"><span data-stu-id="62c1f-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="62c1f-119">Als MCS een compatibiliteitsprobleem ontdekt, geven ze de app af aan het [Desktop App Assure-programma](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) voor herstel.</span><span class="sxs-lookup"><span data-stu-id="62c1f-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="62c1f-120">De app in pakken volgens uw specificatie en vervolgens de implementatie van apps testen met Behulp van Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="62c1f-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="62c1f-121">App-leveringsschema</span><span class="sxs-lookup"><span data-stu-id="62c1f-121">App delivery schedule</span></span>

<span data-ttu-id="62c1f-122">Start het verpakkingsproces door de app-informatie te uploaden naar de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="62c1f-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="62c1f-123">Het verpakkingsteam bespreekt elke donderdag nieuwe inzendingen.</span><span class="sxs-lookup"><span data-stu-id="62c1f-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="62c1f-124">Na beoordeling en verpakking worden de verpakte apps de volgende vrijdag geleverd.</span><span class="sxs-lookup"><span data-stu-id="62c1f-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="62c1f-125">Maximaal vijf apps per week kunnen worden verpakt om te starten, maar de service kan worden geschaald om aan uw behoeften te voldoen.</span><span class="sxs-lookup"><span data-stu-id="62c1f-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![agenda met app-instroom op een donderdag (de 21e in dit voorbeeld), mediavalidatie de volgende dag, verpakking op de volgende maandag (de 25e) en app-levering op de daaropvolgende vrijdag (de 29e)](../../media/MCS-cal.png)

<span data-ttu-id="62c1f-127">U ontvangt een melding zodra de app is geleverd.</span><span class="sxs-lookup"><span data-stu-id="62c1f-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="62c1f-128">Op dat moment hebt u 21 dagen de tijd om acceptatietests uit te voeren en het werk af te tekenen in de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="62c1f-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="62c1f-129">Als u tijdens uw acceptatietest een probleem met de app ontdekt, weigert u de app in de Microsoft Managed Desktop-portal en wordt u via e-mail verbonden met een MCS-pakketer om het probleem te begrijpen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="62c1f-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="62c1f-130">Het testen van accounts en omgeving</span><span class="sxs-lookup"><span data-stu-id="62c1f-130">Testing accounts and environment</span></span>

<span data-ttu-id="62c1f-131">Als u de migratie naar Microsoft Intune wilt voltooien, raden we u aan bepaalde machtigingen te verstrekken:</span><span class="sxs-lookup"><span data-stu-id="62c1f-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="62c1f-132">Toegang tot de app-implementatiemogelijkheden van Microsoft Intune voor de verpakker om de app toe te voegen en toe te wijzen</span><span class="sxs-lookup"><span data-stu-id="62c1f-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="62c1f-133">Test groepen, gebruikersaccounts en licenties voor de verpakkers om de apps te kunnen testen</span><span class="sxs-lookup"><span data-stu-id="62c1f-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="62c1f-134">MCS gebruikt deze machtigingen om de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="62c1f-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="62c1f-135">Ervoor zorgen dat de app werkt op virtuele machine die is geconfigureerd voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="62c1f-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="62c1f-136">De app uploaden naar Microsoft Intune voor implementatie naar uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="62c1f-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="62c1f-137">Zonder deze machtigingen is het mogelijk voor MCS om verder te gaan, maar ze zullen niet in staat zijn om de toepassingen te uploaden naar uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="62c1f-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


