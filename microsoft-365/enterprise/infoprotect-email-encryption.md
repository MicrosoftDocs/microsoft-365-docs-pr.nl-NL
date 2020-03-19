---
title: 'Stap 6: E-mailversleuteling configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Begrijpen en configureren van beheer van privileged access voor Office 365.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809155"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="9a544-103">Stap 6: E-mailversleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="9a544-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="9a544-104">*Deze stap is optioneel en geldt voor zowel de E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9a544-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Informatiebescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="9a544-106">Er zijn drie soorten e-mailversleuteling in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a544-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="9a544-107">Office Message Encryption (OME)</span><span class="sxs-lookup"><span data-stu-id="9a544-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="9a544-108">Versleuteling voor Exchange Online-e-mail die buiten uw organisatie wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="9a544-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="9a544-109">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="9a544-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="9a544-110">Versleuteling en machtigingen die met de e-mail reizen.</span><span class="sxs-lookup"><span data-stu-id="9a544-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="9a544-111">Beveiligde/multifunctionele internetmailextensies (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="9a544-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="9a544-112">E-mailbeveiliging met versleuteling en digitale handtekeningen.</span><span class="sxs-lookup"><span data-stu-id="9a544-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="9a544-113">Versleuteling van Office 365-berichten</span><span class="sxs-lookup"><span data-stu-id="9a544-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="9a544-114">Met OME kan uw organisatie versleutelde e-mailberichten verzenden en ontvangen tussen mensen binnen en buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9a544-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="9a544-115">OME werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices.</span><span class="sxs-lookup"><span data-stu-id="9a544-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="9a544-116">Versleuteling van e-mailberichten zorgt ervoor dat alleen beoogde ontvangers het bericht kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="9a544-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![OME-versleuteling van e-mailberichten](../media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="9a544-118">U stelt transportregels in die de voorwaarden voor versleuteling definiëren.</span><span class="sxs-lookup"><span data-stu-id="9a544-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="9a544-119">Wanneer een gebruiker een bericht verzendt dat overeenkomt met een regel, wordt versleuteling automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="9a544-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="9a544-120">Als ontvangers versleutelde berichten willen weergeven, kunnen ze een eenmalige toegangscode krijgen, zich aanmelden met een Microsoft-account of zich aanmelden met een werk- of schoolaccount dat is gekoppeld aan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a544-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="9a544-121">Ontvangers kunnen ook versleutelde antwoorden verzenden.</span><span class="sxs-lookup"><span data-stu-id="9a544-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="9a544-122">Ze hebben hun eigen Microsoft 365-abonnement niet nodig om versleutelde berichten te bekijken of versleutelde antwoorden te verzenden.</span><span class="sxs-lookup"><span data-stu-id="9a544-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="9a544-123">Zie [Office 365-berichtversleuteling](https://docs.microsoft.com/Office365/SecurityCompliance/ome)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a544-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="9a544-124">Irm</span><span class="sxs-lookup"><span data-stu-id="9a544-124">IRM</span></span>

<span data-ttu-id="9a544-125">IRM in Microsoft 365 helpt u uw gegevens te beveiligen met extra versleuteling en door een intelligent beleid toe te passen dat aangeeft wie toegang heeft tot wat ze kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="9a544-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="9a544-126">Voor e-mailberichten u IRM gebruiken voor versleuteling en gebruiksbeperkingen toepassen.</span><span class="sxs-lookup"><span data-stu-id="9a544-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="9a544-127">U bijvoorbeeld opgeven dat sommige ontvangers alle mogelijkheden hebben om de e-mail te beheren en dat sommige niet de mogelijkheid hebben om de e-mail af te drukken of door te sturen.</span><span class="sxs-lookup"><span data-stu-id="9a544-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="9a544-128">IRM-beleid is geconfigureerd in Microsoft 365 en kan van toepassing zijn op documenten in SharePoint Online en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="9a544-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="9a544-129">Een iRM-beveiligde e-mail bevat de toegepaste beleidsinstellingen die zijn toegepast en waarmee u ermee reist.</span><span class="sxs-lookup"><span data-stu-id="9a544-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![IRM-bescherming van e-mailberichten](../media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="9a544-131">Wanneer de ontvanger de e-mail opent met het opgenomen beleid, worden de beleidsinstellingen gebruikt om het bericht te decoderen en te bepalen wat de ontvanger ermee kan doen.</span><span class="sxs-lookup"><span data-stu-id="9a544-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="9a544-132">Zie [Informatierechtenbeheer in Exchange Online voor]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a544-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="9a544-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="9a544-133">S/MIME</span></span>

<span data-ttu-id="9a544-134">S/MIME is een op digitale certificaten gebaseerde e-mailgebaseerde beveiligingsoplossing waarmee u zowel een bericht versleutelen als digitaal ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="9a544-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="9a544-135">De berichtversleuteling zorgt ervoor dat alleen de beoogde ontvanger het bericht kan openen en lezen.</span><span class="sxs-lookup"><span data-stu-id="9a544-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="9a544-136">Een digitale handtekening helpt de ontvanger de identiteit van de afzender te valideren en te bepalen dat alleen de afzender deze heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="9a544-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![S/MIME bescherming van e-mailberichten](../media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="9a544-138">S/MIME kan worden gebruikt voor e-mail naar andere postvakken in uw Microsoft 365-abonnement of naar externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9a544-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="9a544-139">Zowel berichtversleuteling als digitale handtekeningen worden mogelijk gemaakt door het gebruik van digitale certificaten die de openbare en private sleutels bevatten voor het versleutelen of decoderen van berichten en het maken en verifiëren van digitale handtekeningen.</span><span class="sxs-lookup"><span data-stu-id="9a544-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="9a544-140">Als u S/MIME wilt gebruiken, moet u de openbare sleutels voor elke ontvanger hebben.</span><span class="sxs-lookup"><span data-stu-id="9a544-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="9a544-141">Ontvangers onderhouden hun eigen privésleutels, die veilig moeten blijven.</span><span class="sxs-lookup"><span data-stu-id="9a544-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="9a544-142">Als uw privésleutel is gecompromitteerd, moet u een nieuw digitaal certificaat krijgen en openbare sleutels herverdelen naar alle potentiële afzenders.</span><span class="sxs-lookup"><span data-stu-id="9a544-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="9a544-143">Zie [S/MIME voor het ondertekenen en versleutelen](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)van berichten voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a544-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="9a544-144">Zie als tussencontrolepunt de [exitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) die overeenkomen met deze stap.</span><span class="sxs-lookup"><span data-stu-id="9a544-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="9a544-145">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9a544-145">Next step</span></span>

|||
|:-------|:-----|
|![Stap 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="9a544-147">Beheer van bevoegde toegang configureren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9a544-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
