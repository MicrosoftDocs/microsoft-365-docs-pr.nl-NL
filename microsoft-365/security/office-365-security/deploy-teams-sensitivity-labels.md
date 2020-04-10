---
title: Bestanden in teams beschermen met gevoeligheidslabels.
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Overzicht: gevoeligheidslabels toepassen om bestanden in een zeer vertrouwelijk team te beveiligen.'
ms.openlocfilehash: b263aeae335b83cadb45b16d70a2a45d56f1cbd3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812438"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="67ff1-103">Bestanden in teams beschermen met gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="67ff1-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="67ff1-104">Een zeer vertrouwelijk team heeft, in tegenstelling tot een gevoeligheidslabel voor sterk gereglementeerde gegevens die iedereen op een bestand kan toepassen, een eigen label of sublabel nodig, zodat toegewezen bestanden:</span><span class="sxs-lookup"><span data-stu-id="67ff1-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a highly confidential team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="67ff1-105">Afzonderlijk worden versleuteld.</span><span class="sxs-lookup"><span data-stu-id="67ff1-105">Are individually encrypted.</span></span>
- <span data-ttu-id="67ff1-106">Aangepaste machtigingen bevatten, zodat alleen leden van het team ze kunnen openen.</span><span class="sxs-lookup"><span data-stu-id="67ff1-106">Contain custom permissions so that only members of the team can open it.</span></span>

<span data-ttu-id="67ff1-107">Om dit extra beveiligingsniveau te halen voor bestanden die zijn opgeslagen op de SharePoint-site van een team, moet u een aangepast gevoeligheidslabel configureren dat een afzonderlijk label is of een sublabel van het algemene label voor sterk gereglementeerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="67ff1-107">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="67ff1-108">Alleen teamleden zien het aangepaste etiket of sublabel in hun lijst met labels.</span><span class="sxs-lookup"><span data-stu-id="67ff1-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="67ff1-109">Gebruik een gevoeligheidslabel wanneer u een klein aantal labels nodig hebt voor zowel globaal gebruik als afzonderlijke privéteams.</span><span class="sxs-lookup"><span data-stu-id="67ff1-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="67ff1-110">Gebruik een gevoeligheids-sublabel wanneer u een groot aantal labels nodig hebt of als u labels wilt organiseren voor zeer vertrouwelijke teams onder het sterk gereglementeerde label.</span><span class="sxs-lookup"><span data-stu-id="67ff1-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="67ff1-111">Gebruik [deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een afzonderlijk label of sublabel met de volgende instellingen te configureren:</span><span class="sxs-lookup"><span data-stu-id="67ff1-111">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="67ff1-112">De naam van het label bevat de naam van het team</span><span class="sxs-lookup"><span data-stu-id="67ff1-112">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="67ff1-113">Versleuteling is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="67ff1-113">Encryption is enabled</span></span>
- <span data-ttu-id="67ff1-114">De Office 365-groep voor het team heeft machtigingen voor cocreatie</span><span class="sxs-lookup"><span data-stu-id="67ff1-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="67ff1-115">Na het maken van het nieuwe label of sublabel voor uw gebruikers, die ze vervolgens lokaal kunnen toepassen op bestanden voordat ze worden geüpload naar het team of later zodra het bestand is opgeslagen in het team.</span><span class="sxs-lookup"><span data-stu-id="67ff1-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="67ff1-116">Hier vindt u de configuratie van het zeer vertrouwelijke team dat gebruikmaakt van gevoeligheidslabels voor bestandsversleuteling en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="67ff1-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Basisbeveiliging voor een openbaar team.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="67ff1-118">Zie ook</span><span class="sxs-lookup"><span data-stu-id="67ff1-118">See Also</span></span>

[<span data-ttu-id="67ff1-119">Bestanden beveiligen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67ff1-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
<span data-ttu-id="67ff1-120">[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)</span><span class="sxs-lookup"><span data-stu-id="67ff1-120">[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)</span></span>
