---
title: App-besturingselement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170697"
---
# <a name="app-control"></a><span data-ttu-id="42855-103">App-besturingselement</span><span class="sxs-lookup"><span data-stu-id="42855-103">App control</span></span>

<span data-ttu-id="42855-104">App-besturingselement is een optionele beveiligingspraktijk in Microsoft Managed Desktop die de uitvoering van code op clientapparaten beperkt.</span><span class="sxs-lookup"><span data-stu-id="42855-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="42855-105">Deze controle vermindert het risico op malware of kwaadaardige scripts door te eisen dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="42855-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="42855-106">Er zijn veel beveiligingsvoordelen van deze controle, maar het is vooral bedoeld om gegevens en identiteit te beschermen tegen client-gebaseerde exploits.</span><span class="sxs-lookup"><span data-stu-id="42855-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="42855-107">Microsoft Managed Desktop vereenvoudigt het beheer van app-beheerbeleid door een basisbeleid te maken dat kernproductiviteitsscenario's mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="42855-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="42855-108">U het vertrouwen uitbreiden naar andere ondertekenaars die specifiek zijn voor de apps en scripts in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="42855-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="42855-109">Elke beveiligingstechnologie vereist een evenwicht tussen gebruikerservaring, beveiliging en kosten.</span><span class="sxs-lookup"><span data-stu-id="42855-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="42855-110">App-controle vermindert de dreiging van schadelijke software in uw omgeving, maar er zijn gevolgen voor de eindgebruiker en aanvullende acties voor uw IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="42855-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="42855-111">**Extra beveiliging:**</span><span class="sxs-lookup"><span data-stu-id="42855-111">**Additional security:**</span></span>

<span data-ttu-id="42855-112">Apps of scripts die niet worden vertrouwd door het app-besturingselementbeleid, worden geblokkeerd op apparaten.</span><span class="sxs-lookup"><span data-stu-id="42855-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="42855-113">**Uw bijkomende verantwoordelijkheden:**</span><span class="sxs-lookup"><span data-stu-id="42855-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="42855-114">U bent verantwoordelijk voor het testen van uw apps om te bepalen of ze zouden worden geblokkeerd door het beleid voor toepassingscontrole.</span><span class="sxs-lookup"><span data-stu-id="42855-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="42855-115">Als een app is (of zou worden) geblokkeerd, bent u verantwoordelijk voor het identificeren van de benodigde ondertekenaarsgegevens en het aanvragen van een wijziging via de admin-portal.</span><span class="sxs-lookup"><span data-stu-id="42855-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="42855-116">**Microsoft Managed Desktop-verantwoordelijkheden:**</span><span class="sxs-lookup"><span data-stu-id="42855-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="42855-117">Microsoft Managed Desktop handhaaft het basisbeleid waarmee belangrijke Microsoft-producten zoals M365 Apps, Windows, Teams, OneDrive enzovoort kunnen worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="42855-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="42855-118">Microsoft Managed Desktop voegt uw vertrouwde ondertekenaars in en implementeert het bijgewerkte beleid op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="42855-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="42855-119">Vertrouwen in toepassingen beheren</span><span class="sxs-lookup"><span data-stu-id="42855-119">Managing trust in applications</span></span>

<span data-ttu-id="42855-120">Microsoft Managed Desktop beheert een basisbeleid dat de kerncomponenten van Microsoft-technologieën vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="42855-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="42855-121">Vervolgens *voegt u* vertrouwen toe voor uw eigen toepassingen en scripts door Microsoft Managed Desktop te informeren welke van hen u al vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="42855-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="42855-122">Basisbeleid</span><span class="sxs-lookup"><span data-stu-id="42855-122">Base policy</span></span>

<span data-ttu-id="42855-123">Microsoft Managed Desktop maakt en onderhoudt in samenwerking met microsoft cybersecurity-experts een standaardbeleid waarmee de meeste apps kunnen worden geïmplementeerd via Microsoft Intune, terwijl gevaarlijke activiteiten zoals het verzamelen van code of de uitvoering van niet-vertrouwde bestanden worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="42855-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="42855-124">Het basisbeleid hanteert de volgende benadering om de uitvoering van software te beperken:</span><span class="sxs-lookup"><span data-stu-id="42855-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="42855-125">Bestanden die door beheerders worden uitgevoerd, mogen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="42855-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="42855-126">Bestanden op locaties die *zich niet* in door de gebruiker beschrijfbare mappen bevinden, mogen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="42855-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="42855-127">Bestanden worden ondertekend door een [vertrouwde ondertekenaar](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="42855-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="42855-128">De meeste bestanden die door Microsoft zijn ondertekend, worden uitgevoerd, maar sommige worden geblokkeerd om acties met een hoog risico, zoals het verzamelen van code, te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="42855-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="42855-129">Als een andere gebruiker dan een beheerder een app of script aan een apparaat had kunnen toevoegen (dat wil zeggen in een door de gebruiker geschreven map), staan we deze niet toe, tenzij dit al specifiek is toegestaan door een beheerder.</span><span class="sxs-lookup"><span data-stu-id="42855-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="42855-130">Als een gebruiker wordt misleid om malware te proberen te installeren, als een kwetsbaarheid in een app die de gebruiker uitvoert pogingen om malware te installeren of als een gebruiker opzettelijk een onbevoegde app of script probeert uit te voeren, wordt de uitvoering gestopt.</span><span class="sxs-lookup"><span data-stu-id="42855-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="42855-131">Ondertekenaarsverzoeken</span><span class="sxs-lookup"><span data-stu-id="42855-131">Signer requests</span></span>

<span data-ttu-id="42855-132">U informeert ons welke apps worden geleverd door softwareleveranciers die u vertrouwt door een *ondertekenaarverzoek in te dienen.*</span><span class="sxs-lookup"><span data-stu-id="42855-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="42855-133">Op die manier voegen we die vertrouwensinformatie toe aan het beleid voor toepassingsbeheer voor basislijn en laten we alle software die is ondertekend met het certificaat van die uitgever, op uw apparaten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="42855-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="42855-134">Controle- en afgedwongenbeleid</span><span class="sxs-lookup"><span data-stu-id="42855-134">Audit and Enforced policies</span></span>

<span data-ttu-id="42855-135">Microsoft Managed Desktop gebruikt twee Microsoft Intune-beleidsregels om app-controle te bieden:</span><span class="sxs-lookup"><span data-stu-id="42855-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="42855-136">Controlebeleid</span><span class="sxs-lookup"><span data-stu-id="42855-136">Audit policy</span></span>
<span data-ttu-id="42855-137">Met dit beleid worden logboeken gemaakt om vast te leggen of een app of script wordt geblokkeerd door het beleid afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="42855-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="42855-138">Controlebeleid dwingt geen regels voor app-beheer af en is bedoeld voor testdoeleinden om te bepalen of een toepassing een vrijstelling van uitgevers vereist.</span><span class="sxs-lookup"><span data-stu-id="42855-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="42855-139">Het registreert waarschuwingen (8003 of 8006 gebeurtenissen) in Logboeken in plaats van het blokkeren van de uitvoering of installatie van bepaalde apps of script.</span><span class="sxs-lookup"><span data-stu-id="42855-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="42855-140">Afgedwongen beleid</span><span class="sxs-lookup"><span data-stu-id="42855-140">Enforced policy</span></span>
<span data-ttu-id="42855-141">Met dit beleid worden niet-vertrouwde apps en scripts niet-vertrouwd en maakt u logboeken wanneer een app of script wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="42855-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="42855-142">Afdwingen beleid voorkomen dat standaardgebruikers apps of scripts uitvoeren die zijn opgeslagen in door gebruikers beschrijfbare mappen.</span><span class="sxs-lookup"><span data-stu-id="42855-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="42855-143">Apparaten in de groep Testen hebben een controlebeleid toegepast, zodat u ze gebruiken om te valideren of toepassingen problemen zullen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="42855-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="42855-144">Alle andere groepen (First, Fast en Broad) gebruiken een afgedwongen beleid, zodat eindgebruikers in die groepen geen niet-vertrouwde apps of scripts kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="42855-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







