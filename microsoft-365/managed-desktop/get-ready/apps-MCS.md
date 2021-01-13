---
title: Werken met Microsoft Consulting Services
description: voorbereiding en stappen die u moet volgen om te werken met MCS om uw apps te pakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, apps, MCS, verpakking
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841421"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="a8e7a-104">Werken met Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="a8e7a-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="a8e7a-105">U kunt deelnemen aan Microsoft Consulting Services (MCS) om uw apps te laten inpakken voor gebruik met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a8e7a-106">Neem voor exacte informatie contact op met uw accountvertegenwoordiger om contact op te nemen met MCS en uw specifieke app-verpakkings project te bereiken.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="a8e7a-107">Rollen en verantwoordelijkheden</span><span class="sxs-lookup"><span data-stu-id="a8e7a-107">Roles and responsibilities</span></span>

<span data-ttu-id="a8e7a-108">Als u wilt werken met een pakket met de MCS-app, **moet u deze elementen geven**:</span><span class="sxs-lookup"><span data-stu-id="a8e7a-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="a8e7a-109">De bronprogramma bestanden (bijvoorbeeld setup.exe of. msi).</span><span class="sxs-lookup"><span data-stu-id="a8e7a-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="a8e7a-110">De installatie-instructies, waarop u informatie kunt opgeven over de manier waarop de definitieve installatie moet opletten.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="a8e7a-111">Moet u bijvoorbeeld een snelkoppeling op het bureaublad van de app vinden?</span><span class="sxs-lookup"><span data-stu-id="a8e7a-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="a8e7a-112">Wat moet de zichtbaarheid van de app?</span><span class="sxs-lookup"><span data-stu-id="a8e7a-112">What should the app's visibility be?</span></span> <span data-ttu-id="a8e7a-113">Moet de app verbinding maken met een server en zo ja, welke?</span><span class="sxs-lookup"><span data-stu-id="a8e7a-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="a8e7a-114">Voor meer informatie raadpleegt u de [aanvraag sjabloon toepassings verpakking](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="a8e7a-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="a8e7a-115">U moet uw eigen Acceptatietest uitvoeren om te controleren of de app werkt zoals u deze nodig hebt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="a8e7a-116">**MCS voert de volgende handelingen uit:**</span><span class="sxs-lookup"><span data-stu-id="a8e7a-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="a8e7a-117">Controleren of de app is verboden of niet wordt toegestaan in de Microsoft beheerde bureaubladomgeving.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="a8e7a-118">Tests voor installatie, opstarten en verwijdering van de app voor compatibiliteit met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="a8e7a-119">Als met MCS een compatibiliteitsprobleem wordt gedetecteerd, wordt de app in de app voor de [bureaublad-app](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) voor herstel uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="a8e7a-120">Verpakt de app met uw specificatie en test app-implementatie met Microsoft intune.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="a8e7a-121">Leveringsschema voor apps</span><span class="sxs-lookup"><span data-stu-id="a8e7a-121">App delivery schedule</span></span>

<span data-ttu-id="a8e7a-122">Start het pakket met de app-gegevens naar de Microsoft beheerde bureaublad Portal.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a8e7a-123">Het verpakkings team beoordeelt telkens elke donderdag nieuwe inzendingen.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="a8e7a-124">Na onderzoek en verpakking worden de ingepakte apps na vrijdag afgeleverd.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="a8e7a-125">Er kunnen maximaal vijf apps per week worden ingepakt en u kunt aan de slag met de service, zodat de service aan uw wensen voldoet.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![agenda met de app-instroom in een donderdag (de 21 in dit voorbeeld), media validatie de volgende dag, verpakking op de volgende maandag (de 25e) en de bezorging van de app op de volgende vrijdag (de 29)](../../media/MCS-cal.png)

<span data-ttu-id="a8e7a-127">U ontvangt een melding wanneer de app is geleverd.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="a8e7a-128">Op dit moment hebt u 21 dagen voor het uitvoeren van acceptatie testen en het goedkeuren van het werk in de Microsoft beheerde bureaublad Portal.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a8e7a-129">Als u een probleem met de app ontdekt tijdens het testen van uw acceptatie, moet u de app in de Microsoft Managed Desktop Portal afwijzen en wordt u via e-mail verbonden met een MCS-pakket om het probleem te begrijpen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="a8e7a-130">Accounts en omgevingen testen</span><span class="sxs-lookup"><span data-stu-id="a8e7a-130">Testing accounts and environment</span></span>

<span data-ttu-id="a8e7a-131">Als u wilt dat het team de migratie naar Microsoft intune uitvoert, is het raadzaam bepaalde machtigingen te verlenen:</span><span class="sxs-lookup"><span data-stu-id="a8e7a-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="a8e7a-132">Toegang tot implementatie functies voor app Microsoft intune voor de pakket functie voor het toevoegen en toewijzen van de app</span><span class="sxs-lookup"><span data-stu-id="a8e7a-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="a8e7a-133">Testgroepen, gebruikersaccounts en licenties voor de packages om de apps te kunnen testen</span><span class="sxs-lookup"><span data-stu-id="a8e7a-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="a8e7a-134">MCS maakt gebruik van deze machtigingen om de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="a8e7a-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="a8e7a-135">Ervoor zorgen dat de app werkt op de virtuele machine die is geconfigureerd voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a8e7a-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="a8e7a-136">De app uploaden naar Microsoft intune for Deployment voor uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="a8e7a-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="a8e7a-137">Zonder deze machtigingen is het mogelijk dat de MCS doorschakelt, maar de toepassingen kan niet worden geüpload naar uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="a8e7a-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


