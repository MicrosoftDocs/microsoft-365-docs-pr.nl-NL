---
title: Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande tenants
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel worden de wijzigingen beschreven die worden doorgevoerd in de beveiligingsfuncties in Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204424"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a><span data-ttu-id="c1529-103">Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande tenants</span><span class="sxs-lookup"><span data-stu-id="c1529-103">Protection features in Azure Information Protection rolling out to existing tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c1529-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c1529-104">**Applies to**</span></span>
- [<span data-ttu-id="c1529-105">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c1529-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c1529-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1529-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c1529-107">Als u wilt helpen bij de eerste stap bij het beveiligen van uw gegevens, zijn vanaf juli 2018 alle in aanmerking komende tenants van Azure Information Protection standaard ingeschakeld voor de beveiligingsfuncties in Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c1529-107">To help with the initial step in protecting your information, starting July 2018 all Azure Information Protection eligible tenants will have the protection features in Azure Information Protection turned on by default.</span></span> <span data-ttu-id="c1529-108">De beveiligingsfuncties in Azure Information Protection waren voorheen bekend in Office 365 rights management of Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="c1529-108">The protection features in Azure Information Protection were formerly known in Office 365 as Rights Management or Azure RMS.</span></span> <span data-ttu-id="c1529-109">Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u nu een begin met het beveiligen van informatie via Azure Information Protection wanneer we deze functies implementeren.</span><span class="sxs-lookup"><span data-stu-id="c1529-109">If your organization has an Office E3 service plan or a higher service plan you will now get a head start protecting information through Azure Information Protection when we roll out these features.</span></span>

## <a name="changes-beginning-july-1-2018"></a><span data-ttu-id="c1529-110">Wijzigingen vanaf 1 juli 2018</span><span class="sxs-lookup"><span data-stu-id="c1529-110">Changes beginning July 1, 2018</span></span>

<span data-ttu-id="c1529-111">Vanaf 1 juli 2018 zal Microsoft de beveiligingsfunctie in Azure Information Protection inschakelen voor alle organisaties met een van de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="c1529-111">Starting July 1, 2018, Microsoft will enable the protection capability in Azure Information Protection for all organizations with one of the following subscription plans:</span></span>

- <span data-ttu-id="c1529-112">Office 365-berichtversleuteling wordt aangeboden als onderdeel van Office 365 E3 en E5, Microsoft E3 en E5, Office 365 A1, A3 en A5 en Office 365 G3 en G5.</span><span class="sxs-lookup"><span data-stu-id="c1529-112">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5.</span></span> <span data-ttu-id="c1529-113">U hebt geen extra licenties nodig om de nieuwe beveiligingsmogelijkheden te ontvangen die worden ondersteund door Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c1529-113">You do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span>

- <span data-ttu-id="c1529-114">U kunt ook Azure Information Protection Plan 1 toevoegen aan de volgende abonnementen om de nieuwe Office 365-berichtversleuteling-mogelijkheden te ontvangen: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard of Office 365 Enterprise E1.</span><span class="sxs-lookup"><span data-stu-id="c1529-114">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard, or Office 365 Enterprise E1.</span></span>

- <span data-ttu-id="c1529-115">Elke gebruiker die profiteert van Office 365-berichtversleuteling moet een licentie hebben om onder de functie te vallen.</span><span class="sxs-lookup"><span data-stu-id="c1529-115">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>

- <span data-ttu-id="c1529-116">Zie voor de volledige lijst de [Exchange Online servicebeschrijvingen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) voor Office 365-berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="c1529-116">For the full list, see the [Exchange Online service descriptions](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) for Office 365 Message Encryption.</span></span>

<span data-ttu-id="c1529-117">Tenantbeheerders kunnen de beveiligingsstatus controleren in de Office 365 administratorportal.</span><span class="sxs-lookup"><span data-stu-id="c1529-117">Tenant administrators can check the protection status in the Office 365 administrator portal.</span></span>

![Schermafbeelding waarin wordt laten zien dat rechtenbeheer in Office 365 is geactiveerd.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a><span data-ttu-id="c1529-119">Waarom brengen we deze wijziging aan?</span><span class="sxs-lookup"><span data-stu-id="c1529-119">Why are we making this change?</span></span>

<span data-ttu-id="c1529-120">Office 365-berichtversleuteling maakt gebruik van de beveiligingsmogelijkheden in Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c1529-120">Office 365 Message Encryption leverages the protection capabilities in Azure Information Protection.</span></span> <span data-ttu-id="c1529-121">In het hart van de recente verbeteringen in Office 365-berichtversleuteling en onze bredere investeringen in informatiebeveiliging in Microsoft 365, maken we het organisaties gemakkelijker om onze beveiligingsmogelijkheden in te stellen en te gebruiken, aangezien versleutelingstechnologieën historisch gezien moeilijk zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="c1529-121">At the heart of the recent improvements to Office 365 Message Encryption and our broader investments to information protection in Microsoft 365, we are making it easier for organizations to turn on and use our protection capabilities, as historically, encryption technologies have been difficult to set up.</span></span> <span data-ttu-id="c1529-122">Door de beveiligingsfuncties in Azure Information Protection standaard in te schakelen, kunt u snel aan de slag om uw gevoelige gegevens te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="c1529-122">By turning on the protection features in Azure Information Protection by default, you can quickly get started to protect your sensitive data.</span></span>

## <a name="does-this-impact-me"></a><span data-ttu-id="c1529-123">Is dit van invloed op mij?</span><span class="sxs-lookup"><span data-stu-id="c1529-123">Does this impact me?</span></span>

<span data-ttu-id="c1529-124">Als uw organisatie een in aanmerking komende licentie Office 365, wordt uw tenant beïnvloed door deze wijziging.</span><span class="sxs-lookup"><span data-stu-id="c1529-124">If your organization has purchased an eligible Office 365 license, then your tenant will be impacted by this change.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1529-125">Als u Active Directory Rights Management Services (AD RMS) gebruikt in uw on-premises omgeving, moet u zich onmiddellijk van deze wijziging afkeert of migreren naar Azure Information Protection voordat we deze wijziging binnen 30 dagen implementeren.</span><span class="sxs-lookup"><span data-stu-id="c1529-125">If you're using Active Directory Rights Management Services (AD RMS) in your on-premises environment, you must either opt-out of this change immediately or migrate to Azure Information Protection before we roll out this change within the next 30 days.</span></span> <span data-ttu-id="c1529-126">Zie 'I use AD RMS, how do I opt out?' voor meer informatie over het kiezen van een opt-out.</span><span class="sxs-lookup"><span data-stu-id="c1529-126">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="c1529-127">verder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="c1529-127">later in this article.</span></span> <span data-ttu-id="c1529-128">Zie Migreren van AD RMS naar Azure Information Protection als u liever [migreert.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="c1529-128">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span>

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a><span data-ttu-id="c1529-129">Kan ik Azure Information Protection gebruiken met Active Directory Rights Management Services (AD RMS)?</span><span class="sxs-lookup"><span data-stu-id="c1529-129">Can I use Azure Information Protection with Active Directory Rights Management Services (AD RMS)?</span></span>

<span data-ttu-id="c1529-130">Nee.</span><span class="sxs-lookup"><span data-stu-id="c1529-130">No.</span></span> <span data-ttu-id="c1529-131">Dit is geen ondersteund implementatiescenario.</span><span class="sxs-lookup"><span data-stu-id="c1529-131">This is not a supported deployment scenario.</span></span> <span data-ttu-id="c1529-132">Zonder de extra opt-outstappen te nemen, kunnen sommige computers automatisch de service Azure Rights Management en ook verbinding maken met uw AD RMS-cluster.</span><span class="sxs-lookup"><span data-stu-id="c1529-132">Without taking the additional opt-out steps, some computers might automatically start using the Azure Rights Management service and also connect to your AD RMS cluster.</span></span> <span data-ttu-id="c1529-133">Dit scenario wordt niet ondersteund en heeft onbetrouwbare resultaten, dus het is belangrijk dat u zich binnen 30 dagen voordat we deze nieuwe functies uitrollen, deze wijziging niet meer wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c1529-133">This scenario isn't supported and has unreliable results, so it's important that you opt out of this change within the next 30 days before we roll out these new features.</span></span> <span data-ttu-id="c1529-134">Zie 'I use AD RMS, how do I opt out?' voor meer informatie over het kiezen van een opt-out.</span><span class="sxs-lookup"><span data-stu-id="c1529-134">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="c1529-135">verder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="c1529-135">later in this article.</span></span> <span data-ttu-id="c1529-136">Zie Migreren van AD RMS naar Azure Information Protection als u liever [migreert.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="c1529-136">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>

## <a name="how-do-i-know-if-im-using-ad-rms"></a><span data-ttu-id="c1529-137">Hoe weet ik of ik AD RMS gebruik?</span><span class="sxs-lookup"><span data-stu-id="c1529-137">How do I know if I'm using AD RMS?</span></span>

<span data-ttu-id="c1529-138">Gebruik deze instructies van Het voorbereiden van de omgeving voor Azure Rights Management wanneer u ook een Active Directory Rights Management Services [(AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) hebt om te controleren of u AD RMS hebt geïmplementeerd:</span><span class="sxs-lookup"><span data-stu-id="c1529-138">Use these instructions from [Preparing the environment for Azure Rights Management when you also have Active Directory Rights Management Services (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) to check if you have deployed AD RMS:</span></span>

1. <span data-ttu-id="c1529-139">Hoewel optioneel, publiceren de meeste AD RMS-implementaties het serviceverbindingspunt (SCP) naar Active Directory, zodat domeincomputers het AD RMS-cluster kunnen ontdekken.</span><span class="sxs-lookup"><span data-stu-id="c1529-139">Although optional, most AD RMS deployments publish the service connection point (SCP) to Active Directory so that domain computers can discover the AD RMS cluster.</span></span>

   <span data-ttu-id="c1529-140">Gebruik ADSI Edit om te zien of er een SCP is gepubliceerd in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span><span class="sxs-lookup"><span data-stu-id="c1529-140">Use ADSI Edit to see whether you have an SCP published in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span></span>

2. <span data-ttu-id="c1529-141">Als u geen SCP gebruikt, moeten Windows-computers die verbinding maken met een AD RMS-cluster, zijn geconfigureerd voor servicedetectie aan clientzijde of omleiding van licenties met behulp van het Windows-register: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .</span><span class="sxs-lookup"><span data-stu-id="c1529-141">If you are not using an SCP, Windows computers that connect to an AD RMS cluster must be configured for client-side service discovery or licensing redirection by using the Windows registry: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`.</span></span>

<span data-ttu-id="c1529-142">Zie Servicedetectie aan clientzijde inschakelen met behulp van het Windows [register](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) en Het serververkeer voor licenties omleiden voor meer informatie over deze [registerconfiguraties.](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)</span><span class="sxs-lookup"><span data-stu-id="c1529-142">For more information about these registry configurations, see [Enabling client-side service discovery by using the Windows registry](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).</span></span>

## <a name="i-use-ad-rms-how-do-i-opt-out"></a><span data-ttu-id="c1529-143">Ik gebruik AD RMS, hoe kan ik mij afkeert?</span><span class="sxs-lookup"><span data-stu-id="c1529-143">I use AD RMS, how do I opt out?</span></span>

<span data-ttu-id="c1529-144">Als u zich wilt afk zien van de aanstaande wijziging, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="c1529-144">To opt out of the upcoming change, complete these steps:</span></span>

1. <span data-ttu-id="c1529-145">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c1529-145">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c1529-146">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c1529-146">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c1529-147">Voer de Set-IRMConfiguration cmdlet uit met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="c1529-147">Run the Set-IRMConfiguration cmdlet using the following syntax:</span></span>

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a><span data-ttu-id="c1529-148">Wat kan ik verwachten nadat deze wijziging is aangebracht?</span><span class="sxs-lookup"><span data-stu-id="c1529-148">What can I expect after this change has been made?</span></span>

<span data-ttu-id="c1529-149">Zodra dit is ingeschakeld, kunt u de nieuwe versie van Office 365-berichtversleuteling gebruiken die is aangekondigd tijdens [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) en die gebruik maakt van de versleutelings- en beveiligingsmogelijkheden van Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c1529-149">Once this is enabled, provided you haven't opted out, you can start using the new version of Office 365 Message Encryption which was announced at [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) and leverages the encryption and protection capabilities of Azure Information Protection.</span></span>

![Schermafbeelding met een OME-beveiligd bericht in Outlook op internet.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

<span data-ttu-id="c1529-151">Zie voor meer informatie over de nieuwe verbeteringen [Office 365-berichtversleuteling.](../../compliance/ome.md)</span><span class="sxs-lookup"><span data-stu-id="c1529-151">For more information about the new enhancements, see [Office 365 Message Encryption](../../compliance/ome.md).</span></span>