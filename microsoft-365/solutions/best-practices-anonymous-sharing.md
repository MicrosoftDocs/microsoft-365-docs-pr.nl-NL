---
title: Aanbevolen procedures voor niet-geverifieerd delen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: In dit artikel vindt u informatie over de aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers.
ms.openlocfilehash: 72da93a457b91ec7a25e88a0ac2aa8e64b6fe385
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526932"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a>Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers

Niet-geverifieerd delen (*iedereen*-koppelingen) kunnen handig zijn en bruikbaar in verschillende scenario's. *Iedereen*-koppelingen zijn de gemakkelijkste manier om te delen: personen kunnen de koppeling zonder verificatie openen en deze aan anderen doorsturen.

Meestal is niet alle inhoud van een organisatie geschikt voor niet-geverifieerd delen. Dit artikel behandelt de beschikbare opties om u te helpen een omgeving te creëren waarin uw gebruikers niet-geverifieerd delen van bestanden en mappen kunnen gebruiken, maar waar er waarborgen zijn om de inhoud van uw organisatie te helpen beschermen.

> [!NOTE]
> Om niet-geverifieerd delen te laten werken, moet u dit inschakelen voor uw organisatie en voor de individuele site of het team dat u gaat gebruiken. Zie [samenwerken met personen buiten uw organisatie](collaborate-with-people-outside-your-organization.md) voor het scenario dat u wilt inschakelen.

## <a name="set-an-expiration-date-for-anyone-links"></a>Een vervaldatum instellen voor koppelingen voor iedereen

Bestanden worden vaak gedurende lange perioden opgeslagen in sites, groepen en teams. Af en toe zijn er beleidsregels voor het bewaren van gegevens die vereisen dat bestanden jaren worden bewaard. Als dergelijke bestanden worden gedeeld met niet-geverifieerde personen, kan dit leiden tot onverwachte toegang en wijzigingen in bestanden in de toekomst. Om deze mogelijkheid te beperken, kunt u een vervaltijd configureren voor *iedereen*-koppelingen.

Wanneer een *iedereen*-koppeling verloopt, kan deze niet meer worden gebruikt voor toegang tot inhoud.

Een vervaldatum instellen voor iedereen-koppelingen
1. Open het SharePoint Online-beheercentrum.
2. Klik in het navigatievenster aan de linkerkant op **delen**.
3. Schakel onder **Opties voor verloop en machtigingen kiezen voor 'Iedereen'-koppelingen** het selectievakje **Deze koppelingen moeten binnen zoveel dagen verlopen** in.</br>
   ![Schermafbeelding van de verloopinstellingen van de Iedereen-koppelingen op organisatieniveau in SharePoint](../media/sharepoint-organization-anyone-link-expiration.png)
4. Typ het aantal dagen in het vak en klik vervolgens op **opslaan**.

Wanneer een *iedereen*-koppeling verloopt, kan het bestand of de map opnieuw worden gedeeld met een nieuw *iedereen*-koppeling.

## <a name="set-link-permissions"></a>Koppelingsmachtigingen instellen

Met *Iedereen*-koppelingen naar een bestand kunnen mensen het bestand bewerken en met *Iedereen*-koppelingen naar een map kunnen mensen bestanden bewerken en bekijken en nieuwe bestanden naar de map uploaden. U kunt deze machtigingen voor bestanden en mappen afzonderlijk wijzigen in alleen-weergeven.

Als u niet-geverifieerd delen wilt inschakelen, maar zich zorgen maakt over niet-geverifieerde personen die de inhoud van uw organisatie wijzigen, kunt u overwegen om de bestands- en mapmachtigingen in te stellen op **weergave**.

Machtigingen instellen voor koppelingen voor iedereen
1. Open het SharePoint Online-beheercentrum.
2. Klik in het navigatievenster aan de linkerkant op **delen**.
3. Selecteer onder **Geavanceerde instellingen voor iedereen-koppelingen** de bestands- en mapmachtigingen die u wilt gebruiken.</br>
   ![Schermafbeelding van de instellingen van de koppelingsmachtigingen op organisatieniveau in SharePoint](../media/sharepoint-organization-anyone-link-permissions.png)

Met *iedereen*-koppelingen die zijn ingesteld op **weergeven**, kunnen gebruikers nog steeds bestanden en mappen met gasten delen en hen machtigingen geven door koppelingen voor *specifieke personen* te gebruiken. Deze koppelingen vereisen dat mensen buiten uw organisatie zich als gasten verifiëren, en u kunt gastactiviteiten volgen en controleren voor bestanden en mappen die met deze links worden gedeeld.

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a>Standaardkoppelingstype instellen op alleen-werk voor personen in uw organisatie

Als *Iedereen* delen is ingeschakeld voor uw organisatie, is de standaardkoppeling voor delen normaal ingesteld op **Iedereen**. Hoewel dit handig kan zijn voor gebruikers, kan het risico op onbedoeld niet-geverifieerd delen toenemen. Als een gebruiker het type koppeling vergeet te wijzigen terwijl een beperkt document wordt gedeeld, kan het zijn dat ze per ongeluk een koppeling voor delen maken waarvoor geen verificatie is vereist.

U kunt dit risico beperken door de standaardinstelling voor koppelingen te wijzigen in een koppeling die alleen geschikt is voor personen in uw organisatie. Gebruikers die willen delen met niet-geverifieerde personen, moeten deze optie specifiek selecteren.

De standaardkoppeling voor het delen van bestanden en mappen instellen
1. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.
2. Selecteer onder **koppelingen voor bestanden en mappen****alleen personen in uw organisatie**.</br>
   ![Schermafbeelding van instelling voor standaardkoppelingstype in SharePoint](../media/sharepoint-default-sharing-link-company-link.png)
3. Klik op **Opslaan**.

## <a name="protect-against-malicious-files"></a>Beveiligen tegen schadelijke bestanden

Wanneer u anonieme gebruikers toestaat bestanden te uploaden, loopt u een groter risico dat iemand een schadelijk bestand uploadt. In Microsoft 365 kunt u de functie voor *veilige bijlagen* in de geavanceerde bedreigingsbeveiliging gebruiken om automatisch geüploade bestanden te scannen en bestanden in quarantaine te plaatsen die als onveilig worden beschouwd.

Veilige bijlagen inschakelen
1. Open het [Microsoft 365-beheercentrum](https://security.microsoft.com) voor beveiliging.
2. Klik in het navigatievenster aan de linkerkant op **beleid**.
3. Klik onder **Bescherming tegen bedreigingen** op **ATP-veilige bijlagen (Office 365)**.
4. Schakel het selectievakje **ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen** in en klik vervolgens op **opslaan**.</br>
   ![Schermafbeelding van de instelling veilige bijlagen in het beveiligings- en compliancecentrum](../media/safe-attachments-setting.png)

## <a name="add-copyright-information-to-your-files"></a>Copyrightgegevens toevoegen aan uw bestanden

Als u gevoeligheid-labels gebruikt in het Microsoft 365 -beheercentrum voor compliance, kunt u de labels zo configureren dat er automatisch een watermerk of kop- of voettekst wordt toegevoegd aan de Office-documenten van uw organisatie. Op deze manier kunt u ervoor zorgen dat gedeelde bestanden copyrightgegevens of andere eigendomsgegevens bevatten.

Een voettekst toevoegen aan een gelabeld bestand
1. Open het [Microsoft 365-beheercentrum](https://compliance.microsoft.com) voor compliance.
2. Klik in het navigatiedeelvenster aan de linkerkant onder **classificatie**op **gevoeligheidslabels**.
3. Klik op het label waaraan u een voettekst wilt toevoegen en klik vervolgens op **label bewerken**.
4. Klik op het tabblad **inhoudsmarkering** en schakel vervolgens inhoudsmarkering **in**.
5. Schakel het selectievakje in voor het type tekst dat u wilt toevoegen en klik vervolgens op **tekst aanpassen**.
6. Typ de tekst die u wilt toevoegen aan uw documenten, selecteer de gewenste tekstopties en klik vervolgens op **opslaan**.</br>
   ![Schermafbeelding van de instellingen voor het markeren van inhoud voor een gevoeligheidslabel](../media/content-marking-for-anonymous-sharing.png)
7. Klik op **Opslaan** en vervolgens op **Sluiten**.

Als inhoudsmarkering voor het label is ingeschakeld, wordt de tekst die u hebt opgegeven toegevoegd aan Office-documenten wanneer een gebruiker dat label toepast.

## <a name="see-also"></a>Zie ook


[Overzicht van gevoeligheidslabels](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

[Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten](share-limit-accidental-exposure.md)

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)