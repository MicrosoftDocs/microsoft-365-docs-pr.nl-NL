---
title: Een nettolading maken voor de training voor de aanvals-training
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe ze aangepaste nettoladingen kunnen maken voor training voor de aanvalstraining voor de aanval in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929188"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Een aangepaste nettolading maken voor aanvalssimulatietraining

Microsoft biedt een krachtige nettoladingscatalogus voor diverse social-engineering-technieken om te koppelen aan uw training voor de aanvalssinulatie. Mogelijk wilt u echter aangepaste nettolading maken die beter werkt voor uw organisatie. In dit artikel wordt beschreven hoe u een nettolading kunt maken in de training voor de attack-training in Microsoft Defender voor Office 365.

U kunt een nettolading maken door op Nettolading maken te klikken **op** het speciale tabblad [ **Nettolading**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de wizard voor het maken van [de activering.](attack-simulation-training.md#selecting-a-payload)

Bij de eerste stap in de wizard selecteert u een nettoladingstype. **Momenteel is alleen e-mail beschikbaar.**

Selecteer vervolgens een gekoppelde techniek. Meer informatie over technieken bij [Het selecteren van een techniek voor sociaal netwerken.](attack-simulation-training.md#selecting-a-social-engineering-technique)

In de volgende stap noemt u uw nettolading. Desgewenst kunt u er een beschrijving aan geven.

## <a name="configure-payload"></a>Nettolading configureren

Nu is het tijd om uw nettolading te bouwen. Voer de naam, het e-mailadres en het onderwerp van het e-mailbericht in de **sectie Sender details** in. Kies een phishing-URL uit de opgegeven lijst. Deze URL wordt later in de bericht zelf ingesloten.

> [!TIP]
> U kunt een interne e-mail voor de afzender van uw nettolading kiezen, zodat de nettolading lijkt afkomstig te zijn van een andere werknemer van het bedrijf. Hierdoor wordt de nettolading groter en kunnen werknemers beter informeren over het risico op interne bedreigingen.

Er is een rich text-editor beschikbaar om uw nettolading te maken. U kunt ook een e-mailbericht importeren dat u van tevoren hebt gemaakt. Wanneer u de hoofd-inhoud van de e-mail maakt, kunt u de dynamische tags gebruiken **om** het e-mailbericht aan uw doelen aan te persoonlijke voorkeur aan te maken. Klik **op Phishing-koppeling** om de eerder geselecteerde phishing-URL toe te voegen aan de tekst van het bericht.

![Phishing-koppeling en dynamische tags gemarkeerd bij het maken van nettolading voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Om tijd te besparen, schakelt u de optie in om alle koppelingen in het e-mailbericht te vervangen **door de phishing-koppeling.**

Als u klaar bent met het bouwen van de nettolading naar wens, klikt u op **Volgende.**

## <a name="adding-indicators"></a>Indicatoren toevoegen

Indicatoren helpen werknemers om de aanvalsinding te bekijken, en begrijpen de aanwijzingen die ze kunnen vinden in toekomstige aanvallen. Klik op Indicator toevoegen om **te beginnen.**

Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst. Deze lijst bevat de meest voorkomende aanwijzingen die voorkomen in phishing-e-mailberichten. Wanneer deze optie is geselecteerd, zorgt u ervoor dat de positie van de indicator is ingesteld op **Vanaf** de tekst van het e-mailbericht en klikt u op **Tekst selecteren.** Markeer het gedeelte van uw nettolading waar deze indicator wordt weergegeven en klik op **Selecteren.**

![Gemarkeerde tekst in berichttekst om toe te voegen aan een indicator in de training voor de aanvalstraining](../../media/attack-sim-preview-select-text.png)

Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik binnen het frame van het indicatorvoorbeeld om een voorbeeld van de indicator te zien. Als u klaar bent, klikt u **op Toevoegen.** Herhaal deze stappen totdat u alle indicatoren in uw nettolading hebt gedekt.

## <a name="review-payload"></a>Nettolading controleren

U hebt uw nettolading gebouwd. Nu is het tijd om de details te bekijken en een voorbeeld van uw nettolading te bekijken. Het voorbeeld bevat alle indicatoren die u hebt gemaakt. U kunt in deze stap elk deel van de nettolading bewerken. Zodra u tevreden bent, kunt u **uw nettolading** indienen.

> [!IMPORTANT]
> Nettoladingen die u hebt gemaakt, hebben **tenant** als bron. Als u nettolading selecteert, moet u ervoor zorgen dat u Tenant niet **uitfiltert.**

## <a name="related-links"></a>Verwante koppelingen

[Aan de slag met aanvalssimulatietraining](attack-simulation-training-get-started.md)

[Een phishing-aanval maken](attack-simulation-training.md)

[Meer inzicht krijgen middels aanvalssimulatietraining](attack-simulation-training-insights.md)
