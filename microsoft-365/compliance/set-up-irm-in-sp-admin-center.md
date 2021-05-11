---
title: Set up Information Rights Management (IRM) in SharePoint admin center
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Meer informatie over het gebruik SharePoint Online IRM via Microsoft Azure Active Directory Rights Management Services (RMS) om SharePoint lijsten en documentbibliotheken te beveiligen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161967"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="aadd4-103">Set up Information Rights Management (IRM) in SharePoint admin center</span><span class="sxs-lookup"><span data-stu-id="aadd4-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="aadd4-104">Binnen SharePoint Online wordt IRM-beveiliging toegepast op bestanden op lijst- en bibliotheekniveau.</span><span class="sxs-lookup"><span data-stu-id="aadd4-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="aadd4-105">Voordat uw organisatie IRM-beveiliging kan gebruiken, moet u eerst Rights Management instellen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="aadd4-106">IRM is afhankelijk van de Azure Rights Management Azure Information Protection om gebruiksbeperkingen te versleutelen en toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="aadd4-107">Sommige Microsoft 365 zijn Azure Rights Management, maar niet alle.</span><span class="sxs-lookup"><span data-stu-id="aadd4-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="aadd4-108">Voor meer informatie leest u Hoe Office toepassingen en services ondersteuning bieden [Azure Rights Management.](/azure/information-protection/understand-explore/office-apps-services-support)</span><span class="sxs-lookup"><span data-stu-id="aadd4-108">To learn more, read [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="aadd4-109">IRM-service in SharePoint beheercentrum</span><span class="sxs-lookup"><span data-stu-id="aadd4-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="aadd4-110">Voordat uw organisatie IRM-beveiligen SharePoint lijsten en bibliotheken, moet u eerst de Rights Management-service voor uw organisatie activeren.</span><span class="sxs-lookup"><span data-stu-id="aadd4-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="aadd4-111">Voor meer informatie over het [activeren van Azure Rights Management.](/information-protection/deploy-use/activate-service)</span><span class="sxs-lookup"><span data-stu-id="aadd4-111">To learn how see [Activating Azure Rights Management](/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="aadd4-112">U moet een werk- of schoolaccount met globale beheerdersbevoegdheden gebruiken om de Rights Management-service in te stellen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="aadd4-113">Anders kunt u IRM-functies niet gebruiken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aadd4-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="aadd4-114">Nadat u de Rights Management-service heeft geactiveerd, meld u zich aan bij het SharePoint beheercentrum om IRM in te stellen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="aadd4-115">Meld u aan als globale beheerder of SharePoint beheerder.</span><span class="sxs-lookup"><span data-stu-id="aadd4-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="aadd4-116">Selecteer het pictogram voor het startpictogram voor apps Het pictogram voor het startpictogram voor apps in Office 365 in de linkerbovenhoek en kies Beheerder om het Microsoft 365 ![ ](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) openen. </span><span class="sxs-lookup"><span data-stu-id="aadd4-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="aadd4-117">(Als u de tegel Beheerder niet ziet, hebt u geen beheerdersmachtigingen in uw organisatie.)</span><span class="sxs-lookup"><span data-stu-id="aadd4-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="aadd4-118">Kies in het linkerdeelvenster **beheercentra** \> **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="aadd4-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="aadd4-119">Kies in het linkerdeelvenster **instellingen** en kies vervolgens **de pagina Klassieke instellingen.**</span><span class="sxs-lookup"><span data-stu-id="aadd4-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="aadd4-120">Kies in **de sectie Information Rights Management (IRM)** de optie Gebruik de **IRM-service** die is opgegeven in uw configuratie en kies vervolgens IRM vernieuwen **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="aadd4-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="aadd4-121">Nadat u de IRM-instellingen hebt vernieuwd, kunnen personen in uw organisatie IRM gaan gebruiken in hun SharePoint lijsten en documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="aadd4-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="aadd4-122">De opties om dit te doen, kunnen echter maximaal een uur duren voordat ze worden weergegeven in Instellingen en Lijst Instellingen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="aadd4-123">IRM-enable SharePoint documentbibliotheken en lijsten</span><span class="sxs-lookup"><span data-stu-id="aadd4-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="aadd4-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="aadd4-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="aadd4-125">Nadat de IRM-instellingen zijn vernieuwd, kunnen site-eigenaren hun SharePoint en documentbibliotheken IRM-beveiligen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="aadd4-126">Zie Information Rights Management toepassen op een lijst [of bibliotheek voor meer informatie.](apply-irm-to-a-list-or-library.md)</span><span class="sxs-lookup"><span data-stu-id="aadd4-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="aadd4-127">Wanneer site-eigenaren IRM inschakelen voor een lijst of bibliotheek, kunnen ze alle ondersteunde bestandstypen in die lijst of bibliotheek beveiligen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="aadd4-128">Wanneer IRM is ingeschakeld voor een bibliotheek, is rechtenbeheer van toepassing op alle bestanden in die bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aadd4-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="aadd4-129">Wanneer u IRM inschakelen voor een lijst, is rechtenbeheer alleen van toepassing op bestanden die zijn gekoppeld aan lijstitems, niet de werkelijke lijstitems.</span><span class="sxs-lookup"><span data-stu-id="aadd4-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="aadd4-130">Wanneer personen bestanden downloaden in een lijst of bibliotheek met IRM-functie, worden de bestanden versleuteld, zodat alleen geautoriseerde personen ze kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="aadd4-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="aadd4-131">Elk door rechten beheerd bestand bevat ook een uitgiftelicentie die beperkingen oplegt aan de personen die het bestand bekijken.</span><span class="sxs-lookup"><span data-stu-id="aadd4-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="aadd4-132">Typische beperkingen zijn het maken van een bestand alleen-lezen, het uitschakelen van het kopiëren van tekst, het voorkomen dat personen een lokale kopie opslaan en voorkomen dat personen het bestand afdrukken.</span><span class="sxs-lookup"><span data-stu-id="aadd4-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="aadd4-133">Clientprogramma's die door IRM ondersteunde bestandstypen kunnen lezen, gebruiken de uitgiftelicentie in het door rechten beheerde bestand om deze beperkingen af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="aadd4-134">Op deze manier behoudt een door rechten beheerd bestand de beveiliging ervan, zelfs nadat het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="aadd4-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="aadd4-135">Zie Information Rights Management toepassen op een lijst of bibliotheek als u IRM wilt inschakelen voor een lijst [of bibliotheek.](apply-irm-to-a-list-or-library.md)</span><span class="sxs-lookup"><span data-stu-id="aadd4-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="aadd4-136">U kunt geen documenten maken of bewerken in een IRM-bibliotheek met Office in een browser.</span><span class="sxs-lookup"><span data-stu-id="aadd4-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="aadd4-137">In plaats daarvan kan één persoon tegelijk bestanden met IRM-versleutelde bestanden downloaden en bewerken.</span><span class="sxs-lookup"><span data-stu-id="aadd4-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="aadd4-138">Gebruik in- en uitchecken om  *coauteuring*  te beheren of te schrijven voor meerdere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="aadd4-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="aadd4-139">Wanneer u een PDF-bestand downloadt vanuit een met IRM beveiligde bibliotheek, Microsoft 365 u een beveiligd PDF-bestand.</span><span class="sxs-lookup"><span data-stu-id="aadd4-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="aadd4-140">De extensie van het bestand wordt niet gewijzigd, maar het bestand is wel beveiligd.</span><span class="sxs-lookup"><span data-stu-id="aadd4-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="aadd4-141">Als u dit bestand wilt weergeven, hebt u de Azure Information Protection Viewer, de volledige Azure Information Protection-client of een andere toepassing nodig die het weergeven van beveiligde PDF-bestanden ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="aadd4-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="aadd4-142">SharePoint Online ondersteunt versleuteling van de volgende bestandstypen:</span><span class="sxs-lookup"><span data-stu-id="aadd4-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="aadd4-143">PDF</span><span class="sxs-lookup"><span data-stu-id="aadd4-143">PDF</span></span>
    
- <span data-ttu-id="aadd4-144">De bestandsindelingen 97-2003 voor de volgende Microsoft Office: Word, Excel en PowerPoint</span><span class="sxs-lookup"><span data-stu-id="aadd4-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="aadd4-145">De Office XML-indelingen openen voor de volgende Microsoft Office programma's: Word, Excel en PowerPoint</span><span class="sxs-lookup"><span data-stu-id="aadd4-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="aadd4-146">De XPS-indeling (XML Paper Specification)</span><span class="sxs-lookup"><span data-stu-id="aadd4-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="aadd4-147">IRM-beveiliging kan niet worden toegepast op beveiligde documenten (zoals digitaal ondertekende PDF-bestanden) omdat SharePoint het document bij uploaden moet openen.</span><span class="sxs-lookup"><span data-stu-id="aadd4-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="aadd4-148">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="aadd4-148">Next steps</span></span>
<span data-ttu-id="aadd4-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="aadd4-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="aadd4-150">Nadat u IRM voor SharePoint Online hebt ingeschakeld, kunt u beginnen met het toepassen van rechtenbeheer op lijsten en bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="aadd4-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="aadd4-151">Zie Information Rights Management toepassen op een lijst of bibliotheek voor [meer informatie.](apply-irm-to-a-list-or-library.md)</span><span class="sxs-lookup"><span data-stu-id="aadd4-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="aadd4-152">De nieuwe OneDrive-synchronisatieclient voor Windows ondersteunt nu het synchroniseren van met IRM beveiligde SharePoint-documentbibliotheken en OneDrive-locaties (zolang de IRM-instelling voor de bibliotheek niet is ingesteld op het verlopen van toegangsrechten voor documenten).</span><span class="sxs-lookup"><span data-stu-id="aadd4-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="aadd4-153">Zie De nieuwe synchronisatieclient voor OneDrive implementeren voor meer informatie of om aan de slag te gaan met het implementeren van de nieuwe synchronisatieclient voor [Windows.](/onedrive/deploy-on-windows)</span><span class="sxs-lookup"><span data-stu-id="aadd4-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="aadd4-154">Top of page</span><span class="sxs-lookup"><span data-stu-id="aadd4-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)