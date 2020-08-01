---
title: Werken met Microsoft Consulting Services
description: voorbereiding en stappen om te volgen om met MCS te werken om uw apps te verpakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, MCS, verpakking
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d2a6c09e1bcb84885e607d133c14e26e08e3c621
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530161"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="0b8bd-104">Werken met Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="0b8bd-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="0b8bd-105">U contact opnemen met Microsoft Consulting Services (MCS) om uw apps te laten verpakken voor gebruik met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="0b8bd-106">Voor exacte details u contact opnemen met uw accountvertegenwoordiger om contact op te nemen met MCS en uw specifieke app-verpakkingsproject te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="0b8bd-107">Rollen en verantwoordelijkheden</span><span class="sxs-lookup"><span data-stu-id="0b8bd-107">Roles and responsibilities</span></span>

<span data-ttu-id="0b8bd-108">Om te werken met MCS app verpakking, **moet u deze elementen:**</span><span class="sxs-lookup"><span data-stu-id="0b8bd-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="0b8bd-109">De broninstallateurbestanden (bijvoorbeeld setup.exe of .msi).</span><span class="sxs-lookup"><span data-stu-id="0b8bd-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="0b8bd-110">De installatie-instructies, met vermelding van details over hoe de uiteindelijke installatie eruit moet zien.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="0b8bd-111">Moet er bijvoorbeeld een snelkoppeling op het bureaublad naar de app zijn?</span><span class="sxs-lookup"><span data-stu-id="0b8bd-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="0b8bd-112">Wat moet de zichtbaarheid van de app zijn?</span><span class="sxs-lookup"><span data-stu-id="0b8bd-112">What should the app's visibility be?</span></span> <span data-ttu-id="0b8bd-113">Moet de app verbinding maken met een server en zo ja, welke?</span><span class="sxs-lookup"><span data-stu-id="0b8bd-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="0b8bd-114">Zie de [sjabloon aanvraagaanvraag voor toepassingen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="0b8bd-115">U moet uw eigen acceptatietests uitvoeren om te controleren of de app werkt zoals u deze nodig hebt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="0b8bd-116">**MCS zal deze acties azen:**</span><span class="sxs-lookup"><span data-stu-id="0b8bd-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="0b8bd-117">Controleren of de app verboden of beperkt is in de Microsoft Managed Desktop-omgeving.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="0b8bd-118">Het testen van de installatie, het starten en verwijderen van de app om compatibiliteit met Windows 10 te garanderen.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="0b8bd-119">Als MCS een compatibiliteitsprobleem ontdekt, geven ze de app af aan het [Desktop App Assure-programma](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) voor herstel.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="0b8bd-120">De app naar uw specificaties verpakken en vervolgens de implementatie van de app testen met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="0b8bd-121">App-leveringsschema</span><span class="sxs-lookup"><span data-stu-id="0b8bd-121">App delivery schedule</span></span>

<span data-ttu-id="0b8bd-122">Start het verpakkingsproces door de app-informatie te uploaden naar de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="0b8bd-123">Het verpakkingsteam beoordeelt elke donderdag nieuwe inzendingen.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="0b8bd-124">Na beoordeling en verpakking worden de verpakte apps de volgende vrijdag geleverd.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="0b8bd-125">Maximaal vijf apps per week kunnen worden verpakt om te starten, maar de service kan worden geschaald om aan uw behoeften te voldoen.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![kalender met app-instroom op een donderdag (de 21e in dit voorbeeld), mediavalidatie de volgende dag, verpakking op de volgende maandag (de 25e) en app-levering op de daaropvolgende vrijdag (de 29e)](../../media/MCS-cal.png)

<span data-ttu-id="0b8bd-127">U ontvangt een melding zodra de app is geleverd.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="0b8bd-128">Op dat moment hebt u 21 dagen om acceptatietests uit te voeren en u af te melden voor het werk in de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="0b8bd-129">Als u tijdens uw acceptatietests een probleem met de app ontdekt, weigert u de app in de Microsoft Managed Desktop-portal en wordt u via e-mail verbonden met een MCS-verpakker om het probleem te begrijpen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="0b8bd-130">Accounts en omgeving testen</span><span class="sxs-lookup"><span data-stu-id="0b8bd-130">Testing accounts and environment</span></span>

<span data-ttu-id="0b8bd-131">Als het verpakkingsteam de migratie naar Microsoft Intune wilt voltooien, raden we u aan bepaalde machtigingen op te geven:</span><span class="sxs-lookup"><span data-stu-id="0b8bd-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="0b8bd-132">Toegang tot de app-implementatiemogelijkheden van Microsoft Intune voor de verpakker om de app toe te voegen en toe te wijzen</span><span class="sxs-lookup"><span data-stu-id="0b8bd-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="0b8bd-133">Testgroepen, gebruikersaccounts en licenties voor de verpakkers om de apps te kunnen testen</span><span class="sxs-lookup"><span data-stu-id="0b8bd-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="0b8bd-134">MCS gebruikt deze machtigingen om de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="0b8bd-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="0b8bd-135">Ervoor zorgen dat de app werkt op virtuele machine die is geconfigureerd voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0b8bd-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="0b8bd-136">De app uploaden naar Microsoft Intune voor implementatie naar uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="0b8bd-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="0b8bd-137">Zonder deze machtigingen is het mogelijk voor MCS om verder te gaan, maar ze kunnen de toepassingen niet uploaden naar uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="0b8bd-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


