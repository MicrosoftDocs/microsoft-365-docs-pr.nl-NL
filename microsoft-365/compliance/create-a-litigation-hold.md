---
title: Een bewaring vanwege juridische procedure maken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Meer informatie over het plaatsen van een postvak in De wacht houden van rechtszaken, met behoud van alle postvakinhoud tijdens een onderzoek.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162586"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="5b6b1-103">Een bewaring vanwege juridische procedure maken</span><span class="sxs-lookup"><span data-stu-id="5b6b1-103">Create a Litigation Hold</span></span>

<span data-ttu-id="5b6b1-104">U kunt een postvak in de wacht houden om alle postvakinhoud te behouden, inclusief verwijderde items en de oorspronkelijke versies van gewijzigde items.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="5b6b1-105">Wanneer u een postvak van een gebruiker in De juridische procedure in de wacht houdt, blijft inhoud in het archiefpostvak van de gebruiker (als dit is ingeschakeld) ook behouden.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="5b6b1-106">Wanneer u een wachtperiode maakt, kunt u een duur opgeven (ook wel een tijdsinstelling *genoemd)* zodat verwijderde en gewijzigde items gedurende een bepaalde periode worden bewaard en vervolgens definitief uit het postvak worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="5b6b1-107">Of u kunt inhoud voor onbepaalde tijd behouden (een oneindige *greep* genoemd) of totdat de Procesvoeringsophoudt wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="5b6b1-108">Als u een duur van de wachtperiode opgeeft, wordt dit berekend vanaf de datum waarop een bericht wordt ontvangen of een postvakitem wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="5b6b1-109">Dit gebeurt er als u een proces in de wacht houdt.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="5b6b1-110">Items die permanent door de gebruiker worden verwijderd, blijven bewaard in de map Herstelbare items in het postvak van de gebruiker gedurende de duur van de wacht.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>

- <span data-ttu-id="5b6b1-111">Items die door de gebruiker uit de map Herstelbare items worden verwijderd, blijven bewaard gedurende de duur van de wacht.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>

- <span data-ttu-id="5b6b1-112">Het opslagquotum voor de map Herstelbare items wordt verhoogd van 30 GB naar 110 GB.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>

- <span data-ttu-id="5b6b1-113">Items in het primaire postvak van de gebruiker en de archiefpostvakken blijven behouden</span><span class="sxs-lookup"><span data-stu-id="5b6b1-113">Items in the user's primary and the archive mailboxes are retained</span></span>

## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="5b6b1-114">Een abonnementslicentie Exchange Online abonnement 2 toewijzen</span><span class="sxs-lookup"><span data-stu-id="5b6b1-114">Assign an Exchange Online Plan 2 license</span></span>

<span data-ttu-id="5b6b1-115">Als u een postvak Exchange Online bij Procesvoeringsberechting, moet er een licentie Exchange Online abonnement 2 worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="5b6b1-116">Als aan een postvak een licentie Exchange Online abonnement 1 is toegewezen, moet u het een afzonderlijke Exchange Online Archiving toewijzen om het in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="5b6b1-117">Voor Office 365 Education organisaties wordt Litigation Hold ondersteund in Office 365 A1 abonnementen, waaronder een licentie Exchange Online Abonnement 1 met aanvullende functies.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-117">For Office 365 Education organizations, Litigation Hold is supported in Office 365 A1 subscriptions, which include an Exchange Online Plan 1 license with supplemental features.</span></span> <span data-ttu-id="5b6b1-118">Zie de sectie 'Exchange Online functies' in de [Office 365 Education servicebeschrijving voor meer informatie.](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features)</span><span class="sxs-lookup"><span data-stu-id="5b6b1-118">For more information, see the "Exchange Online features" section in the [Office 365 Education service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).</span></span>

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="5b6b1-119">Een postvak in de wacht houden voor rechtszaken plaatsen</span><span class="sxs-lookup"><span data-stu-id="5b6b1-119">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="5b6b1-120">Hier volgen de stappen om een postvak in de wacht te zetten via het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-120">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="5b6b1-121">Ga naar [https://outlook.office.com/ecp](https://outlook.office.com/ecp) en meld u aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-121">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="5b6b1-122">Klik **op Geadresseerden > postvakken** in het linkernavigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-122">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="5b6b1-123">Selecteer het postvak dat u wilt plaatsen in De procesvoering en klik vervolgens op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="5b6b1-123">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="5b6b1-124">Klik op de pagina Postvakeigenschappen op **Postvakfuncties.**</span><span class="sxs-lookup"><span data-stu-id="5b6b1-124">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="5b6b1-125">Klik **onder Procesberechting: Uitgeschakeld** op **Inschakelen** om het postvak in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-125">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="5b6b1-126">Voer op **de pagina Procesvoering** de volgende optionele informatie in:</span><span class="sxs-lookup"><span data-stu-id="5b6b1-126">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="5b6b1-127">**Duur van de procesduur (dagen)** - Gebruik dit vak om een op tijd gebaseerde wachttijd te maken en op te geven hoe lang postvakitems worden gehouden wanneer het postvak in de wacht wordt geplaatst.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-127">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="5b6b1-128">De duur wordt berekend vanaf de datum waarop een postvakitem wordt ontvangen of gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-128">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="5b6b1-129">Wanneer de duur van de bewaartermijn voor een bepaald item verloopt, wordt dat item niet meer bewaard.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-129">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="5b6b1-130">Als u dit vak leeg laat, blijven items voor onbepaalde tijd behouden of totdat de wacht wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-130">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="5b6b1-131">Gebruik dagen om de duur op te geven.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-131">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="5b6b1-132">**Opmerking-** Gebruik dit vak om de gebruiker te informeren dat het postvak van de gebruiker in de wacht staat.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-132">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="5b6b1-133">De notitie wordt weergegeven op de pagina Accountgegevens in het postvak van de gebruiker als deze Outlook 2010 of hoger.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-133">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="5b6b1-134">Als u deze pagina wilt openen, kunnen gebruikers klikken **op Bestand** in Outlook.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-134">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="5b6b1-135">**URL-** Gebruik dit vak om de gebruiker naar een website te leiden voor meer informatie over procesvoering.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-135">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="5b6b1-136">Deze URL wordt weergegeven op de pagina Accountgegevens in het postvak van de gebruiker als deze Outlook 2010 of hoger.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-136">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="5b6b1-137">Als u deze pagina wilt openen, kunnen gebruikers klikken **op Bestand** in Outlook..</span><span class="sxs-lookup"><span data-stu-id="5b6b1-137">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="5b6b1-138">Klik **op Opslaan** op de pagina Litigation **Hold** en klik vervolgens **op Opslaan** op de pagina postvakeigenschappen.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-138">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="5b6b1-139">Een geschil in de wacht zetten met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b6b1-139">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="5b6b1-140">U kunt ook een procesopvolging maken door de volgende opdracht uit te voeren in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="5b6b1-140">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="5b6b1-141">Met de vorige opdracht blijven items voor onbepaalde tijd behouden omdat de duur van de bewaartijd niet is opgegeven.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-141">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="5b6b1-142">Gebruik de volgende opdracht om een tijdsgebaseerde wachttijd te maken:</span><span class="sxs-lookup"><span data-stu-id="5b6b1-142">To create a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="5b6b1-143">Zie [Set-Mailbox](/powershell/module/exchange/set-mailbox) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-143">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="5b6b1-144">Hoe werkt Litigation Hold?</span><span class="sxs-lookup"><span data-stu-id="5b6b1-144">How does Litigation Hold work?</span></span>

<span data-ttu-id="5b6b1-145">In de normale werkstroom van verwijderde items wordt een postvakitem verplaatst naar de submap Verwijderingen in de map Herstelbare items wanneer een gebruiker het item permanent verwijdert (Shift + Delete) of verwijdert uit de map Verwijderde items.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-145">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="5b6b1-146">Een verwijderingsbeleid (een bewaarlabel dat is geconfigureerd met een bewaaractie Verwijderen) verplaatst items ook naar de submap Verwijderingen wanneer de bewaarperiode verloopt.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-146">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="5b6b1-147">Wanneer een gebruiker een item in de map Herstelbare items opslossert of wanneer de bewaarperiode van het verwijderde item voor een item verloopt, wordt het verplaatst naar de submap Purges in de map Herstelbare items en gemarkeerd voor permanente verwijdering.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-147">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="5b6b1-148">Het wordt verwijderd uit Exchange de volgende keer dat het postvak wordt verwerkt door de MFA (Managed Folder Assistant).</span><span class="sxs-lookup"><span data-stu-id="5b6b1-148">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="5b6b1-149">Wanneer een postvak in de bewaartijd voor rechtszaken wordt geplaatst, blijven items in de submap Purges behouden voor de duur van de bewaartijd die is opgegeven in de bewaartijd voor rechtszaken.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-149">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold.</span></span> <span data-ttu-id="5b6b1-150">De duur van de wacht wordt berekend op basis van de oorspronkelijke datum waarop een item is ontvangen of gemaakt en definieert hoe lang items in de submap Purges worden gehouden.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-150">The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held.</span></span> <span data-ttu-id="5b6b1-151">Wanneer de duur van de wachttijd verloopt voor een item in de submap Purges, wordt het item gemarkeerd voor permanente verwijdering en wordt het verwijderd uit Exchange de volgende keer dat het postvak door de MFA wordt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-151">When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA.</span></span> <span data-ttu-id="5b6b1-152">Als een postvak voor onbepaalde tijd in de wacht wordt geplaatst, worden items nooit verwijderd uit de submap Purges.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-152">If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="5b6b1-153">In de volgende afbeelding ziet u de submappen in de mappen Herstelbare items en het werkstroomproces in de wacht houden.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-153">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![Rechtszaken Houd de levenscyclus vast](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="5b6b1-155">Als een bewaargreep die is gekoppeld aan een eDiscovery-zaak in een postvak wordt geplaatst, worden verwijderde items verplaatst van de submap Verwijderingen naar de discoveryHolds-submap en blijven ze behouden totdat het postvak wordt vrijgegeven uit de eDiscovery-bewaarplaats.</span><span class="sxs-lookup"><span data-stu-id="5b6b1-155">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
