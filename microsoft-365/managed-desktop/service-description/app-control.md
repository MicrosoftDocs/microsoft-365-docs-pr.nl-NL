---
title: App-bediening
description: Het besturingselement voor apps en vertrouwen met toepassingen gebruiken
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
# <a name="app-control"></a><span data-ttu-id="2b459-104">App-bediening</span><span class="sxs-lookup"><span data-stu-id="2b459-104">App control</span></span>

<span data-ttu-id="2b459-105">App-besturingselement is een optionele beveiligingsprocedure in Microsoft Managed Desktop waarmee de uitvoering van code op clientapparaten wordt beperkt.</span><span class="sxs-lookup"><span data-stu-id="2b459-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="2b459-106">Dit besturingselement verkleint het risico van malware of kwaadaardige scripts door aan te geven dat alleen code die is ondertekend door een door de klant goedgekeurde lijst met uitgevers, kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2b459-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="2b459-107">Dit besturingselement biedt veel beveiligingsvoordelen, maar dit is vooral bedoeld om gegevens en identiteit te beschermen tegen exploits op basis van client.</span><span class="sxs-lookup"><span data-stu-id="2b459-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="2b459-108">Microsoft Managed Desktop vergemakkelijkt het beheer van app-beheerbeleidsregels door een basisbeleid te maken dat scenario's voor kern productiviteit mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="2b459-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="2b459-109">U kunt een vertrouwensrelatie uitbreiden naar andere ondertekeners die specifiek zijn voor de apps en scripts in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="2b459-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="2b459-110">Voor elke beveiligingstechnologie is een evenwicht tussen de gebruikerservaring, beveiliging en kosten vereist.</span><span class="sxs-lookup"><span data-stu-id="2b459-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="2b459-111">Met app-beheer wordt de bedreiging van schadelijke software in uw omgeving beperkt, maar er zijn gevolgen voor de gebruiker en verdere acties voor uw IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="2b459-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="2b459-112">**Extra beveiliging:**</span><span class="sxs-lookup"><span data-stu-id="2b459-112">**Additional security:**</span></span>

<span data-ttu-id="2b459-113">Apps of scripts die niet worden vertrouwd door het app-besturings beleid, worden geblokkeerd voor de uitvoering van apparaten.</span><span class="sxs-lookup"><span data-stu-id="2b459-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="2b459-114">**Uw nieuwe verantwoordelijkheden:**</span><span class="sxs-lookup"><span data-stu-id="2b459-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="2b459-115">U bent verantwoordelijk voor het testen van uw apps om te bepalen of deze worden geblokkeerd door het Toepassingsbeheerbeleid.</span><span class="sxs-lookup"><span data-stu-id="2b459-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="2b459-116">Als een app (of zou zijn) wordt geblokkeerd, moet u verantwoordelijk zijn voor het identificeren van de benodigde details van de ondertekenaar en het aanvragen van een wijziging via de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="2b459-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="2b459-117">**Microsoft beheerde bureaublad verantwoordelijkheden:**</span><span class="sxs-lookup"><span data-stu-id="2b459-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="2b459-118">Microsoft Managed Desktop onderhoudt het basisbeleid voor het inschakelen van belangrijkste Microsoft-producten zoals M365-apps, Windows, teams, OneDrive enzovoort.</span><span class="sxs-lookup"><span data-stu-id="2b459-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="2b459-119">Microsoft Managed Desktop voegt uw vertrouwde ondertekeners in en implementeert het bijgewerkte beleid op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="2b459-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="2b459-120">Vertrouwen in toepassingen beheren</span><span class="sxs-lookup"><span data-stu-id="2b459-120">Managing trust in applications</span></span>

<span data-ttu-id="2b459-121">Microsoft Managed Desktop met een Basisbeleid dat de kernonderdelen van Microsoft-technologieën vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="2b459-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="2b459-122">U voegt vervolgens een vertrouwensrelatie *toe* aan uw eigen toepassingen en scripts door Microsoft Managed Desktop aan te vormen van de persoon die u al vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="2b459-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="2b459-123">Basisbeleid</span><span class="sxs-lookup"><span data-stu-id="2b459-123">Base policy</span></span>

<span data-ttu-id="2b459-124">Microsoft Managed Desktop, samen met Microsoft Cyber Security experts, maakt en onderhoudt een standaardbeleid waarmee de meeste apps die worden geïmplementeerd via Microsoft intune, worden ingeschakeld tijdens het blokkeren van gevaarlijke activiteiten, zoals het maken van schadelijke activiteiten of het uitvoeren van niet-vertrouwde bestanden.</span><span class="sxs-lookup"><span data-stu-id="2b459-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="2b459-125">Het Basisbeleid heeft de volgende aanpak voor het beperken van software-uitvoering:</span><span class="sxs-lookup"><span data-stu-id="2b459-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="2b459-126">Bestanden die door beheerders worden uitgevoerd, kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2b459-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="2b459-127">Bestanden op locaties die zich *niet* in de door de gebruiker beschrijfbare directory's bevinden, kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2b459-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="2b459-128">Bestanden zijn ondertekend door een [vertrouwde ondertekenaar](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="2b459-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="2b459-129">De meeste bestanden die zijn ondertekend door Microsoft worden uitgevoerd, maar sommige worden geblokkeerd om taken met een hoge risico te voorkomen, zoals code compilatie.</span><span class="sxs-lookup"><span data-stu-id="2b459-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="2b459-130">Als een andere gebruiker dan een beheerder een app of een script kon toevoegen aan een apparaat (dat wil zeggen dat het zich in een door de gebruiker geschrijf bare map) bevindt, kan het programma niet worden uitgevoerd, tenzij het al specifiek is toegestaan door een beheerder.</span><span class="sxs-lookup"><span data-stu-id="2b459-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="2b459-131">Als een gebruiker het probleem wil doen met het installeren van malware en een aanvaller in een app die de gebruiker probeert malware te installeren of als een gebruiker voornemens is een niet-geautoriseerde app of script uit te voeren, wordt het programma beëindigd.</span><span class="sxs-lookup"><span data-stu-id="2b459-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="2b459-132">Verzender aanvragen</span><span class="sxs-lookup"><span data-stu-id="2b459-132">Signer requests</span></span>

<span data-ttu-id="2b459-133">U verwittigt welke apps door software-uitgevers worden geleverd door een *Onderteken aanvraag* te archiveren.</span><span class="sxs-lookup"><span data-stu-id="2b459-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="2b459-134">Door dit te doen, voegen we die vertrouwensgegevens toe aan het beleid voor basislijn toepassingen en toestaan dat alle software die met het certificaat van de uitgever is ondertekend, wordt uitgevoerd op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="2b459-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="2b459-135">Beleidsregels controleren en afdwingen</span><span class="sxs-lookup"><span data-stu-id="2b459-135">Audit and Enforced policies</span></span>

<span data-ttu-id="2b459-136">Microsoft Managed Desktop gebruikt twee Microsoft intune-beleidsregels voor het instellen van app-beheer:</span><span class="sxs-lookup"><span data-stu-id="2b459-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="2b459-137">Controlebeleid</span><span class="sxs-lookup"><span data-stu-id="2b459-137">Audit policy</span></span>
<span data-ttu-id="2b459-138">Met dit beleid maakt u Logboeken om te bepalen of een app of script wordt geblokkeerd door het beleid dat wordt afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="2b459-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="2b459-139">Controlebeleid beoordeelt geen app-besturings regels en is bedoeld om te testen of een toepassing een Publisher-uitzondering vereist.</span><span class="sxs-lookup"><span data-stu-id="2b459-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="2b459-140">Het logboek maakt waarschuwingen (8003 of 8006 Events) in Logboeken in plaats van de uitvoering of installatie van bepaalde apps of scripts te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="2b459-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="2b459-141">Beleid voor geforceerde beperking</span><span class="sxs-lookup"><span data-stu-id="2b459-141">Enforced policy</span></span>
<span data-ttu-id="2b459-142">Met dit beleid blokkeert u niet-vertrouwde apps en scripts van uitvoering en maakt u Logboeken wanneer u een app of script blokkeert.</span><span class="sxs-lookup"><span data-stu-id="2b459-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="2b459-143">Beleidsregels met uitgaand beleid voorkomen dat standaardgebruikers van apps of scripts worden uitgevoerd die in de door de gebruiker geschrijf bare directory's zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2b459-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="2b459-144">Voor apparaten in de test groep is een controlebeleid toegepast, zodat u deze kunt gebruiken om te controleren of toepassingen problemen kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="2b459-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="2b459-145">Alle overige groepen (voor het eerst, snel en algemeen) gebruik een afgedwongen beleid, zodat gebruikers in die groepen niet-vertrouwde apps of scripts kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2b459-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







