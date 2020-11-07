---
title: Een nettolading maken voor de training voor simulatie aanval
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Meer informatie over het maken van een aangepaste nettolading voor simulatie van aanvals simulaties in Microsoft Defender voor Office 365.
ms.openlocfilehash: ffb5397d9b39a35b4cb8bd0fdb3301cd156896e1
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944521"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Een aangepaste nettolading maken voor de simulatie van aanvals oefeningen

Microsoft biedt een krachtige versie van de nettolading voor diverse social engineering-technieken voor het koppelen van uw aanvals training. U kunt echter wel aangepaste ladingen maken die beter voor uw organisatie kunnen worden gebruikt. Hieronder wordt beschreven hoe u een nettolading maakt voor simulatie van aanvals simulatie via Microsoft Defender voor Office 365.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

U kunt een nettolading maken door te klikken op **een nettolading maken** op het [tabblad specifieke **nettoladingen**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de [wizard simulatie maken](attack-simulation-training.md#selecting-a-payload).

In de eerste stap van de wizard selecteert u een type nettolading. **Momenteel is alleen e-mail beschikbaar**.

Selecteer vervolgens een gekoppelde methode. Zie voor meer informatie over technieken bij [het selecteren van een maatschappelijke techniek](attack-simulation-training.md#selecting-a-social-engineering-technique).

Geef in de volgende stap de naam uw nettolading. U kunt ook een beschrijving opgeven.

## <a name="configure-payload"></a>Nettolading configureren

Nu is het tijd om uw nettolading aan te maken. Voer de naam van de afzender, het e-mailadres en het onderwerp van de e-mail in het gedeelte **Details van afzender** in. Selecteer een phishingwebsite in de lijst met opgegeven URL'S. Deze URL wordt later ingesloten in de hoofdtekst van het bericht.

> [!TIP]
> U kunt een interne e-mail voor de afzender van uw nettolading kiezen, zodat de nettolading wordt weergegeven als de naam van een andere werknemer van het bedrijf. Hierdoor wordt de kans groter voor de nettolading en kunnen werknemers aan het risico van interne bedreigingen zorgen.

De RTF-editor is beschikbaar voor het maken van uw nettolading. U kunt ook een e-mailbericht importeren dat u vooraf hebt gemaakt. Wanneer u de hoofdtekst van het e-mailbericht structureert, profiteert u van de **dynamische Tags** om de e-mail aan te passen aan uw doelen. Klik op **phishing** om de eerder geselecteerde phishingwebsite in de hoofdtekst van het e-mailbericht toe te voegen.

![Phishing en dynamische Tags gemarkeerd in het maken van nettolading voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Als u uw tijd wilt besparen, schakelt u de optie voor het **vervangen van alle koppelingen in het e-mailbericht met de phishing-koppeling uit**.

Wanneer u klaar bent met het maken van de nettolading, klikt u op **volgende**.

## <a name="adding-indicators"></a>Indicatoren toevoegen

Indicatoren stellen medewerkers in staat inzicht te krijgen in de simulatie van een aanval in toekomstige aanvallen. Als u wilt beginnen, klikt u op **indicator toevoegen**.

Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst. Deze lijst is bedoeld voor de meest voorkomende aanwijzingen die worden weergegeven in malafide e-mailberichten. Als dit is geselecteerd, controleert u of de positie van de indicator is ingesteld op **in de hoofdtekst van het e-mailbericht** en klikt u op **tekst selecteren**. Markeer het gedeelte van uw nettolading waarbij deze indicator wordt weergegeven en klik op **selecteren**.

![Gemarkeerde tekst in de berichttekst die moet worden toegevoegd aan een indicator voor simulatie van aanvals training](../../media/attack-sim-preview-select-text.png)

Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik in het frame met het voorbeeld van de indicator om een voorbeeld van de indicator te zien. Als u klaar bent, klikt u op **toevoegen**. Herhaal deze stappen totdat alle indicatoren in uw nettolading zijn besproken.

## <a name="review-payload"></a>Nettolading controleren

U bent klaar met het maken van uw nettolading. Nu is het tijd om de details te bekijken en een voorbeeld van uw nettolading te bekijken. Het voorbeeld bevat alle indicatoren die u hebt gemaakt. U kunt in deze stap elk deel van de nettolading bewerken. Als dit is voldaan, **verzendt** u uw nettolading. 

> [!IMPORTANT]
> Nettoladingen die u hebt gemaakt, hebben een **Tenant** ingesteld als de bron. Wanneer u nettoladingen selecteert, controleert u of de **Tenant** niet is gefilterd.