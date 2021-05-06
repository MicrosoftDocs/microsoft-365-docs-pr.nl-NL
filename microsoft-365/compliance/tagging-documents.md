---
title: Documenten taggen in een controleset
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Als u documenten in een revisieset tagt, kunt u overbodige inhoud verwijderen en relevante inhoud in een Advanced eDiscovery identificeren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161526"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Documenten taggen in een revisieset in Advanced eDiscovery

Het organiseren van inhoud in een revisieset is belangrijk om verschillende werkstromen in het eDiscovery-proces te voltooien. Dit omvat:

- Overbodige inhoud verwijderen

- Relevante inhoud identificeren
 
- Inhoud identificeren die moet worden gecontroleerd door een expert of een advocaat

Wanneer experts, advocaten of andere gebruikers inhoud in een revisieset bekijken, kunnen hun adviezen met betrekking tot de inhoud worden vastgelegd met behulp van tags. Als het bijvoorbeeld de bedoeling is om overbodige inhoud te verwijderen, kan een gebruiker documenten taggen met een tag zoals 'niet-responsief'. Nadat inhoud is beoordeeld en gelabeld, kan er een zoekactie voor revisiesets worden gemaakt om inhoud die is gemarkeerd als 'niet-responsief' uit te sluiten, waardoor deze inhoud niet meer in de volgende stappen in de eDiscovery-werkstroom wordt gebruikt. Het tagvenster kan voor elk geval worden aangepast, zodat de tags de beoogde revisiewerkstroom kunnen ondersteunen.

## <a name="tag-types"></a>Tagtypen

Advanced eDiscovery bevat twee typen tags:

- **Labels voor één keuze:** gebruikers worden beperkt tot het selecteren van één tag in een groep. Dit kan handig zijn om ervoor te zorgen dat gebruikers geen conflicterende tags selecteren, zoals 'responsief' en 'niet-responsief'. Deze worden weergegeven als radioknoppen.

- **Meervoudige keuzelabels:** gebruikers toestaan meerdere tags in een groep te selecteren. Deze worden weergegeven als selectievakjes.

## <a name="tag-structure"></a>Tagstructuur

Naast de tagtypen, kan de structuur van de manier waarop tags zijn ingedeeld in het tagvenster worden gebruikt om het labelen van documenten intuïtiever te maken. Tags worden gegroepeerd op secties. Zoeken in revisieset ondersteunt de mogelijkheid om te zoeken op tag en op tagsectie. Dit betekent dat u een zoekopdracht voor revisiesets kunt maken om documenten op te halen die zijn gemarkeerd met een tag in een sectie.

![Secties taggen in het tagvenster](../media/Tagtypes.png)

Tags kunnen verder worden georganiseerd door ze in een sectie te nesten. Als het bijvoorbeeld de bedoeling is om bevoorrechte inhoud te identificeren en te taggen, kan nesting worden gebruikt om duidelijk te maken dat een gebruiker een document kan taggen als 'Privileged' en het type privilege kan selecteren door de juiste geneste tag te controleren.

![Geneste tags in een tagsectie](../media/Nestingtags.png)

## <a name="applying-tags"></a>Tags toepassen

Er zijn verschillende manieren om een tag toe te passen op inhoud.

### <a name="tagging-a-single-document"></a>Eén document labelen

Wanneer u een document bekijkt in een revisieset, kunt u de tags weergeven die door een revisie kunnen worden gebruikt door te klikken op **Het deelvenster Labelen.**

![Klik op Deelvenster Tag om het deelvenster met tags weer te geven](../media/Singledoctag.png)

Op deze manier kunt u tags toepassen op het document dat in de viewer wordt weergegeven.

### <a name="bulk-tagging"></a>Bulklabels

Bulklabels kunnen worden uitgevoerd door meerdere bestanden in het  resultatenraster te selecteren en vervolgens de tags in het deelvenster Labelen te gebruiken, vergelijkbaar met het labelen van afzonderlijke documenten. Bulk-un-tagging kan worden uitgevoerd door tags tweemaal te selecteren. met de eerste klik wordt de tag toegepast en met de tweede selectie wordt ervoor gezorgd dat de tag voor alle geselecteerde bestanden is geweken.

![Een schermafbeelding van een beschrijving van een mobiele telefoon die automatisch wordt gegenereerd](../media/Bulktag.png)

> [!NOTE]
> Wanneer het label bulksgewijs wordt gemarkeerd, wordt in het labelvenster een aantal bestanden weergegeven dat voor elke tag in het deelvenster is gemarkeerd.

### <a name="tagging-in-other-review-panels"></a>Labelen in andere revisiepanelen

Wanneer u documenten controleert, kunt u de andere revisiepanelen gebruiken om andere kenmerken van documenten in het resultatenraster te bekijken. Dit omvat het controleren van andere gerelateerde documenten, e-mailthreads, near duplicates en hash duplicaten. Wanneer u bijvoorbeeld gerelateerde documenten bekijkt (met  behulp van het revisievenster documentfamilie), kunt u de controletijd aanzienlijk verminderen door gerelateerde documenten bulksgewijs te labelen. Als een e-mailbericht bijvoorbeeld meerdere bijlagen heeft en u ervoor wilt zorgen dat het hele gezin consistent wordt gelabeld.

U kunt bijvoorbeeld als volgende het deelvenster Labelen weergeven **wanneer** u het **revisievenster Documentfamilie** gebruikt:

1. Als het revisievenster is geopend voor een geselecteerd document (bijvoorbeeld  door de lijst  met gerelateerde inhoud weer te geven in het revisievenster documentfamilie, klikt u op Documenten taggen onder het documentfamiliebeoordelingsvenster.

   Het labelvenster wordt weergegeven als een pop-upvenster.

2. Kies een of meer tags om het geselecteerde document toe te passen. 

3. Als u alle documenten wilt taggen, selecteert u alle documenten in het deelvenster **Documentfamilie,** klikt u op Documenten labelen **en** kiest u vervolgens de tags die u wilt toepassen op de hele familie documenten.

![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](../media/Relatedtag.png)
