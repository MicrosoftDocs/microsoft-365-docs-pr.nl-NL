---
title: App-bediening
description: App-beheer en vertrouwen gebruiken met toepassingen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841301"
---
# <a name="app-control"></a><span data-ttu-id="0cc45-104">App-bediening</span><span class="sxs-lookup"><span data-stu-id="0cc45-104">App control</span></span>

<span data-ttu-id="0cc45-105">App-besturingselement is een optionele beveiligingspraktijk in Microsoft Managed Desktop waarmee de uitvoering van code op clientapparaten wordt beperkt.</span><span class="sxs-lookup"><span data-stu-id="0cc45-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="0cc45-106">Dit besturingselement beperkt het risico op malware of schadelijke scripts door te vereisen dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers, kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0cc45-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="0cc45-107">Er zijn veel beveiligingsvoordelen van dit besturingselement, maar het is voornamelijk bedoeld om gegevens en identiteit te beschermen tegen op de client gebaseerde exploits.</span><span class="sxs-lookup"><span data-stu-id="0cc45-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="0cc45-108">Microsoft Managed Desktop het beheer van beleidsregels voor app-beheer vereenvoudigt door een basisbeleid te maken dat basisscenario's voor productiviteit mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="0cc45-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="0cc45-109">U kunt het vertrouwen uitbreiden naar andere ondertekenaars die specifiek zijn voor de apps en scripts in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="0cc45-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="0cc45-110">Elke beveiligingstechnologie vereist een evenwicht tussen gebruikerservaring, beveiliging en kosten.</span><span class="sxs-lookup"><span data-stu-id="0cc45-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="0cc45-111">App-beheer vermindert de bedreiging van schadelijke software in uw omgeving, maar er zijn gevolgen voor de gebruiker en verdere acties voor uw IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="0cc45-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="0cc45-112">**Extra beveiliging:**</span><span class="sxs-lookup"><span data-stu-id="0cc45-112">**Additional security:**</span></span>

<span data-ttu-id="0cc45-113">Apps of scripts die niet worden vertrouwd door het beleid voor app-beheer, worden geblokkeerd voor gebruik op apparaten.</span><span class="sxs-lookup"><span data-stu-id="0cc45-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="0cc45-114">**Uw extra verantwoordelijkheden:**</span><span class="sxs-lookup"><span data-stu-id="0cc45-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="0cc45-115">U bent verantwoordelijk voor het testen van uw apps om te bepalen of deze worden geblokkeerd door het beleid voor toepassingsbeheer.</span><span class="sxs-lookup"><span data-stu-id="0cc45-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="0cc45-116">Als een app is (of wordt) geblokkeerd, bent u verantwoordelijk voor het identificeren van de benodigde ondertekenaarsgegevens en het aanvragen van een wijziging via de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="0cc45-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="0cc45-117">**Microsoft Managed Desktop verantwoordelijkheden:**</span><span class="sxs-lookup"><span data-stu-id="0cc45-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="0cc45-118">Microsoft Managed Desktop het basisbeleid dat basisproducten van Microsoft in staat stelt, zoals M365-apps, Windows, Teams, OneDrive, en ga zo maar door.</span><span class="sxs-lookup"><span data-stu-id="0cc45-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="0cc45-119">Microsoft Managed Desktop uw vertrouwde ondertekenaars in en implementeert het bijgewerkte beleid op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="0cc45-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="0cc45-120">Vertrouwen in toepassingen beheren</span><span class="sxs-lookup"><span data-stu-id="0cc45-120">Managing trust in applications</span></span>

<span data-ttu-id="0cc45-121">Microsoft Managed Desktop een basisbeleid dat de basisonderdelen van Microsoft-technologieën vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="0cc45-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="0cc45-122">Vervolgens voegt *u* vertrouwen toe voor uw eigen toepassingen en scripts door u te informeren Microsoft Managed Desktop welke van de toepassingen u al vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="0cc45-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="0cc45-123">Basisbeleid</span><span class="sxs-lookup"><span data-stu-id="0cc45-123">Base policy</span></span>

<span data-ttu-id="0cc45-124">Microsoft Managed Desktop maakt en onderhoudt in samenwerking met microsoft-experts op het gebied van cyberbeveiliging een standaardbeleid waarmee de meeste apps via Microsoft Intune kunnen worden geïmplementeerd en gevaarlijke activiteiten, zoals het opstellen of uitvoeren van niet-vertrouwde bestanden, worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="0cc45-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="0cc45-125">Het basisbeleid gaat als volgt te werk om de uitvoering van software te beperken:</span><span class="sxs-lookup"><span data-stu-id="0cc45-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="0cc45-126">Bestanden die worden uitgevoerd door beheerders, kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0cc45-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="0cc45-127">Bestanden op locaties die *niet* in door de gebruiker geschreven mappen staan, kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0cc45-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="0cc45-128">Bestanden worden ondertekend door een [vertrouwde ondertekenaar.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="0cc45-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="0cc45-129">De meeste bestanden die door Microsoft zijn ondertekend, worden uitgevoerd, maar sommige zijn geblokkeerd om acties met een hoog risico, zoals codecompilatie, te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="0cc45-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="0cc45-130">Als een andere gebruiker dan een beheerder een app of script kan hebben toegevoegd aan een apparaat (dat wil zeggen dat deze zich in een door de gebruiker kan schrijven adreslijst) heeft, is het niet toegestaan om deze uit te voeren, tenzij dit al specifiek is toegestaan door een beheerder.</span><span class="sxs-lookup"><span data-stu-id="0cc45-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="0cc45-131">Als een gebruiker wordt misleid om malware te installeren, als een beveiligingsprobleem in een app wordt uitgevoerd, probeert de gebruiker malware te installeren of als een gebruiker opzettelijk een niet-geautoriseerde app of script probeert uit te voeren, wordt de uitvoering van ons beleid gestopt.</span><span class="sxs-lookup"><span data-stu-id="0cc45-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="0cc45-132">Aanmeldingsaanvragen</span><span class="sxs-lookup"><span data-stu-id="0cc45-132">Signer requests</span></span>

<span data-ttu-id="0cc45-133">U informeert ons welke apps worden geleverd door software-uitgevers die u vertrouwt door een *aanvraag voor een ondertekenaar in te dienen.*</span><span class="sxs-lookup"><span data-stu-id="0cc45-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="0cc45-134">Op deze manier voegen we die vertrouwensgegevens toe aan het beleid voor basislijntoepassingsbeheer en staan we toe dat software die is ondertekend met het certificaat van die uitgever op uw apparaten kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0cc45-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="0cc45-135">Controle- en afgedwongen beleidsregels</span><span class="sxs-lookup"><span data-stu-id="0cc45-135">Audit and Enforced policies</span></span>

<span data-ttu-id="0cc45-136">Microsoft Managed Desktop gebruikt twee Microsoft Intune beleidsregels voor app-beheer:</span><span class="sxs-lookup"><span data-stu-id="0cc45-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="0cc45-137">Controlebeleid</span><span class="sxs-lookup"><span data-stu-id="0cc45-137">Audit policy</span></span>
<span data-ttu-id="0cc45-138">Met dit beleid worden logboeken gemaakt om vast te stellen of een app of script wordt geblokkeerd door het afgedwongen beleid.</span><span class="sxs-lookup"><span data-stu-id="0cc45-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="0cc45-139">Controlebeleid dwingt geen regels voor app-beheer af en is bedoeld voor testdoeleinden om te bepalen of voor een toepassing een uitgevervrijstelling vereist is.</span><span class="sxs-lookup"><span data-stu-id="0cc45-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="0cc45-140">Hiermee worden waarschuwingen (8003 of 8006 gebeurtenissen) in Gebeurtenisviewer vastgelegd in plaats van de uitvoering of installatie van opgegeven apps of scripts te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0cc45-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="0cc45-141">Afgedwongen beleid</span><span class="sxs-lookup"><span data-stu-id="0cc45-141">Enforced policy</span></span>
<span data-ttu-id="0cc45-142">Met dit beleid worden niet-vertrouwde apps en scripts niet uitgevoerd en worden logboeken gemaakt wanneer een app of script wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="0cc45-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="0cc45-143">Afgedwongen beleid voorkomt dat standaardgebruikers apps of scripts uitvoeren die zijn opgeslagen in door gebruikers geschreven directories.</span><span class="sxs-lookup"><span data-stu-id="0cc45-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="0cc45-144">Apparaten in de groep Test hebben een auditbeleid toegepast, zodat u ze kunt gebruiken om te valideren of toepassingen problemen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="0cc45-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="0cc45-145">Alle andere groepen (First, Fast en Broad) gebruiken een afgedwongen beleid, zodat gebruikers in die groepen geen niet-vertrouwde apps of scripts kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0cc45-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







