---
title: Schakel de evaluatieomgeving voor Microsoft Defender in voor Office 365 in uw productieomgeving, activeer uw evaluatie, activering
description: Stappen voor het activeren van Microsoft Defender voor Office365-evaluatie, met proeflicenties, MX-recordafhandeling, & controle van geaccepteerde domeinen en binnenkomende verbindingen.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457919"
---
# <a name="enable-the-evaluation-environment"></a>De evaluatieomgeving inschakelen

**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 2 van 3](eval-defender-office-365-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor Office 365. Zie het [overzichtsartikel](eval-defender-office-365-overview.md)voor meer informatie over dit proces.

Gebruik de volgende stappen om de evaluatie voor Microsoft Defender in te Office 365.


![Stappen voor het inschakelen van Microsoft Defender Office 365 in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [Stap 1: Proeflicenties activeren](#step-1-activate-trial-licenses)
- [Stap 2: de openbare MX-record controleren en controleren](#step-2-audit-and-verify-the-public-mx-record)
- [Stap 3: Geaccepteerde domeinen controleren](#step-3-audit-accepted-domains)
- [Stap 4: Binnenkomende connectors controleren](#step-4-audit-inbound-connectors)
- [Stap 5: De evaluatie activeren](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>Stap 1: Proeflicenties activeren

Meld u aan bij uw bestaande Microsoft Defender voor Office 365 of tenantbeheerportal.

1. Ga naar de beheerportal.
2. Selecteer Services aanschaffen in de werkbalk Snel starten.

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Klik op Services aanschaffen in het navigatiedeelvenster van Office 365.":::

3.  Schuif omlaag naar de Add-On sectie (of zoek naar 'Defender') om de Microsoft Defender te zoeken voor Office 365 abonnementen.
4.  Klik op Details naast het plan dat u wilt evalueren.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Klik vervolgens op de knop Details.":::

5. Klik op *de koppeling Gratis proefabonnement* starten.

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Klik op de gratis proefversie van start *hyperlink* in dit deelvenster.":::

6. Bevestig uw aanvraag en klik op *de knop Nu* proberen.

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Klik nu op de knop Nu proberen *.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>Stap 2: de openbare MX-record controleren en controleren

Als u Microsoft Defender effectief wilt evalueren voor Office 365, is het belangrijk dat binnenkomende externe e-mail wordt doorgegeven via het EOP-exemplaar (Exchange Online Protection) dat is gekoppeld aan uw tenant.

1. Meld u aan bij de M365-beheerportal, vouw Instellingen uit en selecteer Domeinen.
2. Selecteer uw geverifieerde e-maildomein en klik op DNS beheren.
3. Noteer de MX-record die is gegenereerd en toegewezen aan uw EOP-tenant.
4. Open uw externe (openbare) DNS-zone en controleer de primaire MX-record die is gekoppeld aan uw e-maildomein.
    - Als uw openbare MX-record momenteel overeenkomt met het toegewezen EOP-adres (bijvoorbeeld tenant-com.mail.protection.outlook.com), moeten er geen verdere *routeringswijzigingen nodig zijn.*
    - Als uw openbare MX-record momenteel wordt overgeslagen naar een externe of on-premises SMTP-gateway, zijn mogelijk aanvullende routeringsconfiguraties vereist.
    - Als uw openbare MX-record momenteel wordt overgeslagen naar on-premises Exchange, is het mogelijk dat u nog steeds in een hybride model zit waarin sommige postvakken van geadresseerden nog niet zijn gemigreerd naar EXO.

## <a name="step-3-audit-accepted-domains"></a>Stap 3: Geaccepteerde domeinen controleren

1. Meld u aan Exchange Online beheerportal, selecteer E-mail Flow en klik vervolgens op Geaccepteerde domeinen.
2. Noteer het domeintype voor uw primaire e-maildomein in de  lijst met geaccepteerde domeinen die zijn toegevoegd en geverifieerd in uw tenant.
    - Als het domeintype  is ingesteld op Gezaghebbend, wordt ervan uitgegaan dat alle postvakken voor geadresseerden voor uw organisatie zich momenteel in Exchange Online.
    - Als het domeintype is ingesteld op ***Interne*** relay, bevindt u zich mogelijk nog steeds in een hybride model waarin sommige postvakken van geadresseerden zich nog steeds on-premises bevinden.

## <a name="step-4-audit-inbound-connectors"></a>Stap 4: Binnenkomende connectors controleren

1. Meld u aan bij Exchange Online-beheerportal, selecteer E-mail Flow en klik vervolgens op Verbindingslijnen.
2. Noteer in de lijst met geconfigureerde connectors alle vermeldingen die afkomstig zijn van **Partnerorganisatie** en die kunnen correleren met een SMTP-gateway van derden.
3. Noteer in de lijst met geconfigureerde connectors  alle vermeldingen met het label Van de e-mailserver van uw organisatie, wat kan aangeven dat u nog steeds in een hybride scenario zit.

## <a name="step-5-activate-the-evaluation"></a>Stap 5: De evaluatie activeren

Gebruik de instructies hier om uw Microsoft Defender te activeren voor Office 365 evaluatie vanuit de Microsoft 365 Defender portal.

1. Meld u aan bij uw tenant met een account dat toegang heeft tot de Microsoft 365 Defender portal.
2. Kies of u van de portal Microsoft 365 Defender **de** standaardinterface voor Microsoft Defender wilt maken voor Office 365 beheer (aanbevolen).

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Klik op de knop Instellingen in-/uitschakelen om de gecentraliseerde en verbeterde Microsoft 365 Defender voor beheer te gebruiken.":::

3. Selecteer in het navigatiemenu **Beleidsregels & onder** *E-mail & Samenwerking.*

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Hier ziet u een menuafbeelding & e-mail en samenwerking die verwijst naar Beleidsregels & regels. Klik erop!":::

4. Klik op *het & beleidsregels* op **Bedreigingsbeleid.**

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Afbeelding van het dashboard Beleid & regels en een pijl die naar bedreigingsbeleid wijst. Klik op dat volgende!":::

5. Schuif omlaag naar *Extra beleid* en selecteer de tegel Defender evalueren **Office 365** tegel.

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="De tegel Eval Defender voor Office 365 zegt dat het een proefversie van 30 dagen is via e-mail & samenwerkingsvectoren. Klik door.":::

6. Kies nu of externe e-mailroutes rechtstreeks Exchange Online of naar een gateway of service van derden en klik op Volgende.

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 evalueert het verzenden van e-mail naar uw Exchange Online postvakken. Geef de details van de manier waarop uw e-mail nu wordt gerouteerd, inclusief de naam van de uitgaande verbindingslijn die uw e-mail omsingeed. Als u alleen Exchange Online Protection (EOP) gebruikt, hebt u geen verbindingslijn. Kies een van de 3rd-party of on-premises provider, of ik gebruik alleen EOP.":::

7. Als u een gateway van derden gebruikt, selecteert u de naam van de leverancier in de vervolgkeuzelijn samen met de inkomende connector die aan die oplossing is gekoppeld. Wanneer u uw antwoorden hebt vermeld, klikt u op Volgende.

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="In dit dialoogvenster kiest u de leverancierservice van derden die uw organisatie gebruikt of selecteert u *Overige*. Selecteer in het volgende dialoogvenster omlaag de inkomende verbindingslijn. Klik vervolgens op Volgende.":::

8. Controleer uw instellingen en klik op **de knop Evaluatie** maken.

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Dit deelvenster heeft een vervolgkeuzemenu om uw instellingen te bekijken. Er is ook een klikbare koppeling naar Het routeringstype bewerken als dat nodig is. Wanneer u klaar bent, klikt u op de grote blauwe knop Evaluatie maken.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="En nu is de set-up voltooid. Op de blauwe knop op deze pagina staat 'Ga naar evaluatie'.":::      |

## <a name="next-steps"></a>Volgende stappen

Stap 3 van 3: De pilot voor Microsoft Defender instellen voor Office 365

Ga terug naar het overzicht voor [Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)