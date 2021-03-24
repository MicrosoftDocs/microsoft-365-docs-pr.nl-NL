---
title: Een payload maken voor training voor de aanvalssimulatie
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
description: Beheerders kunnen leren hoe ze aangepaste payloads kunnen maken voor de trainingstraining aanvalssimulatie in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059005"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Een aangepaste nettolading maken voor aanvalssimulatietraining

Microsoft biedt een krachtige payloadcatalogus voor diverse social engineering-technieken die u kunt koppelen aan uw trainingstraining voor aanvalssimulaties. U kunt echter aangepaste payloads maken die beter werken voor uw organisatie. In dit artikel wordt beschreven hoe u een payload kunt maken in de trainingstraining Aanvalssimulatie in Microsoft Defender voor Office 365.

U kunt een payload maken door op Een payload maken **te** klikken op het speciale tabblad [ **Payloads**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de wizard voor het maken [van de simulatie.](attack-simulation-training.md#selecting-a-payload)

Bij de eerste stap in de wizard selecteert u een laadvermogenstype. **Momenteel is alleen e-mail beschikbaar.**

Selecteer vervolgens een gekoppelde techniek. Zie meer informatie over technieken bij [Het selecteren van een social engineering-techniek.](attack-simulation-training.md#selecting-a-social-engineering-technique)

In de volgende stap de naam van uw laadvermogen. Desgewenst kunt u het een beschrijving geven.

## <a name="configure-payload"></a>Laadvermogen configureren

Nu is het tijd om uw laadvermogen te bouwen. Voer de naam, het e-mailadres en het onderwerp van de e-mail in in de **sectie Afzenderdetails.** Kies een phishing-URL in de opgegeven lijst. Deze URL wordt later ingesloten in de tekst van het bericht.

> [!TIP]
> U kunt een interne e-mail kiezen voor de afzender van uw payload, waardoor de payload wordt weergegeven als afkomstig van een andere werknemer van het bedrijf. Dit vergroot de gevoeligheid voor de payload en helpt werknemers bij het informeren van het risico op interne bedreigingen.

Er is een rich text editor beschikbaar om uw payload te maken. U kunt ook een e-mailbericht importeren dat u van tevoren hebt gemaakt. Gebruik de dynamische **tags** om de e-mail aan uw doelen te personaliseren terwijl u de hoofding van de e-mail maakt. Klik **op Phishing-koppeling** om de eerder geselecteerde phishing-URL toe te voegen aan de tekst van het bericht.

![Phishingkoppeling en dynamische tags gemarkeerd in het maken van laadvermogen voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Als u tijd wilt besparen, schakelt u de optie in om alle koppelingen in het e-mailbericht te vervangen **door de phishingkoppeling.**

Wanneer u klaar bent met het opbouwen van de payload naar wens, klikt u op **Volgende.**

## <a name="adding-indicators"></a>Indicatoren toevoegen

Indicatoren helpen werknemers bij het uitvoeren van de aanvalssimulatie inzicht te krijgen in de aanwijzingen die ze kunnen zoeken in toekomstige aanvallen. Als u wilt beginnen, klikt u **op Indicator toevoegen.**

Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst. Deze lijst is samengesteld om de meest voorkomende aanwijzingen te bevatten die worden weergegeven in phishing-e-mailberichten. Nadat u deze optie hebt geselecteerd, moet u ervoor zorgen dat de indicatorpositie is ingesteld op Van de boventekst van het **e-mailbericht** en klikt u op **Tekst selecteren.** Markeer het deel van uw laadvermogen waar deze indicator wordt weergegeven en klik op **Selecteren.**

![Gemarkeerde tekst in berichttekst om toe te voegen aan een indicator in training voor aanvalssimulatie](../../media/attack-sim-preview-select-text.png)

Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik in het voorbeeldkader van de indicator om een voorbeeld van de indicator te zien. Wanneer u klaar bent, klikt u op **Toevoegen.** Herhaal deze stappen totdat u alle indicatoren in uw laadvermogen hebt behandeld.

## <a name="review-payload"></a>Laadvermogen controleren

U bent klaar met het opbouwen van uw laadvermogen. Nu is het tijd om de details te bekijken en een voorbeeld van uw laadvermogen te bekijken. Het voorbeeld bevat alle indicatoren die u hebt gemaakt. U kunt elk deel van de payload bewerken vanuit deze stap. Wanneer u tevreden bent, kunt u **uw laadvermogen** verzenden.

> [!IMPORTANT]
> Payloads die u hebt gemaakt, hebben **Tenant** als bron. Wanneer u payloads selecteert, moet u ervoor zorgen dat tenant niet wordt **uitgefilterd.**

## <a name="related-links"></a>Verwante koppelingen

[Aan de slag met aanvalssimulatietraining](attack-simulation-training-get-started.md)

[Een phishing-aanvalssimulatie maken](attack-simulation-training.md)

[Meer inzicht krijgen middels aanvalssimulatietraining](attack-simulation-training-insights.md)
