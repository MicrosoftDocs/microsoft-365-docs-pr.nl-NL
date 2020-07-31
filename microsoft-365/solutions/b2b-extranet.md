---
title: Een B2B-extranet maken met beheerde gasten
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over het maken van een B2B extranet-site of -team met beheerde gastgebruikers van een partnerorganisatie.
ms.openlocfilehash: 4f8eb33ad9b41f552975d4158a61ec4cedcfa9cc
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526980"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Een B2B-extranet maken met beheerde gasten

U [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) gebruiken om een B2B-extranet te maken om samen te werken met een partnerorganisatie die Azure Active Directory gebruikt. Hierdoor kunnen gebruikers zich zelf inschrijven voor de extranetsite of -team en toegang krijgen via een goedkeuringsworkflow.

Met deze methode voor het delen van resources voor samenwerking kan de partnerorganisatie helpen bij het onderhouden en goedkeuren van de gastgebruikers aan hun kant, waardoor de belasting voor uw IT-afdeling wordt verminderd en degenen die het meest bekend zijn met de samenwerkingsovereenkomst gebruikerstoegang kunnen beheren.

In dit artikel worden de stappen doorlopen om een pakket resources te maken (in dit geval een site of team) die u delen met een partnerorganisatie via een registratiemodel voor selfservicetoegang. 

Voordat u begint, maakt u de site of het team dat u wilt delen met de partnerorganisatie en schakel u deze in voor het delen van gasten. Zie [Samenwerken met gasten op een site](collaborate-in-site.md) of Samenwerken met gasten in een [team](collaborate-as-team.md) voor meer informatie. We raden u ook aan een veilige omgeving voor [het delen van gasten](create-secure-guest-sharing-environment.md) te controleren op informatie over beveiligings- en nalevingsfuncties die u gebruiken om uw governancebeleid te behouden wanneer u samenwerkt met gasten.

## <a name="video-demonstration"></a>Videodemonstratie

Deze video toont de procedures die in dit artikel worden behandeld.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>De partnerorganisatie verbinden

Als u gasten van een partnerorganisatie wilt uitnodigen, moet u het domein van de partner toevoegen als een verbonden organisatie in Azure Active Directory.

Een verbonden organisatie toevoegen
1. Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer**.
2. Klik **op Verbonden organisaties**.
4. Klik **op Verbonden organisatie toevoegen**.
5. Typ een naam en beschrijving voor de organisatie en klik op **Volgende: Directory + domein**.
6. Klik **op Map + domein toevoegen**.
7. Typ het domein voor de organisatie die u wilt verbinden en klik op **Toevoegen**.
8. Klik **op Verbinden**en klik vervolgens op **Volgende: Sponsors**.
9. Voeg mensen uit uw organisatie of de organisatie toe waarmee u verbinding maakt met wie u toegang wilt goedkeuren voor gastgebruikers.
10. Klik **op Volgende: Controleren + Maken**.
11. Bekijk de instellingen die u hebt gekozen en klik op **Maken**.

    ![Schermafbeelding van de pagina Verbonden organisaties in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>De resources kiezen die u wilt delen

De eerste stap bij het selecteren van resources die u wilt delen met een partnerorganisatie, is het maken van een catalogus die deze bevat.

Een catalogus maken
1. Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer**.
2. Klik **op Catalogi**.
3. Klik op **Nieuwe catalogus**.
4. Typ een naam en beschrijving voor de catalogus en zorg ervoor dat **Ingeschakeld** en **Ingeschakeld voor externe gebruikers** zijn ingesteld op **Ja.**
5. Klik op **Maken**.

   ![Schermafbeelding van de pagina catalogi in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Zodra de catalogus is gemaakt, voegt u de SharePoint-site of -team toe die u wilt delen met de partnerorganisatie.

Resources toevoegen aan een catalogus
1. Klik in Azure AD Identity Governance op **Catalogi**en klik vervolgens op de catalogus waar u resources wilt toevoegen.
2. Klik **op Resources** en klik vervolgens op Resources **toevoegen**.
3. Selecteer de teams of SharePoint-sites die u in uw extranet wilt opnemen en klik op **Toevoegen**.

   ![Schermafbeelding van de pagina catalogusresources in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Zodra u de resources hebt gedefinieerd die u wilt delen, is de volgende stap het maken van een toegangspakket, dat het type toegang definieert dat partnergebruikers krijgen en het goedkeuringsproces voor nieuwe partnergebruikers die toegang aanvragen.

Een toegangspakket maken
1. Klik in Azure AD Identity Governance op **Catalogi**en klik vervolgens op de catalogus waar u een toegangspakket wilt maken.
2. Klik op **Access-pakketten**en klik vervolgens op **Nieuw toegangspakket**.
3. Typ een naam en beschrijving voor het toegangspakket en klik op **Volgende: Resourcerollen**.
4. Kies de bronnen uit de catalogus die u voor uw extranet wilt gebruiken.
5. Kies voor elke resource in de kolom **Rol** de gebruikersrol die u wilt toekenn aan de gastgebruikers die het extranet gebruiken.
6. Klik **op Volgende: aanvragen**.
7. Kies **onder Gebruikers die toegang kunnen aanvragen**voor gebruikers die niet in uw map **staan.**
8. Controleer of de optie **Specifieke verbonden organisaties** is geselecteerd en klik vervolgens op **Mappen toevoegen**.
9. Kies de verbonden organisatie die u eerder toevoegt en klik op **Selecteren**
10. Kies onder **Goedkeuring**de optie **Ja** voor **Goedkeuring vereisen**.
11. Kies onder **Eerste goedkeurder**een van de sponsors die u eerder hebt toegevoegd of kies een specifieke gebruiker.
12. Klik **op Fallback toevoegen** en selecteer een terugvalkeurder.
13. Kies onder **Inschakelen**de optie **Ja**.
14. Klik **op Volgende: Levenscyclus**.
15. Kies de instellingen voor verlopen en toegang tot de controle die u wilt gebruiken en klik op **Volgende: Controleren + Maken**.
16. Controleer uw instellingen en klik op **Maken**.

    ![Schermafbeelding van het scherm toegangspakketten in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Als u samenwerkt met een grote organisatie, u het toegangspakket verbergen. Als het pakket is verborgen, zien gebruikers in de partnerorganisatie het pakket niet op hun *Mijn toegang-portal.* In plaats daarvan moeten ze een directe link worden verzonden om zich aan te melden voor het pakket. Het verbergen van het toegangspakket kan het aantal ongepaste toegangsaanvragen verminderen en kan ook helpen om beschikbare toegangspakketten georganiseerd te houden in het portaal van de partnerorganisatie.

Een toegangspakket instellen op verborgen
1. Klik in Azure AD Identity Governance op **Access-pakketten**en klik vervolgens op uw toegangspakket.
2. Klik op de pagina **Overzicht** op **Bewerken**.
3. Kies onder **Eigenschappen**De optie **Ja** voor **Verborgen**en klik vervolgens op **Opslaan**.

   ![Schermafbeelding van het scherm Eigenschappen van een toegangspakket bewerken](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Partnergebruikers uitnodigen

Als u het toegangspakket op verborgen stelt, moet u een directe koppeling naar de partnerorganisatie verzenden, zodat deze toegang tot uw site of team kan aanvragen.

De koppeling naar de toegangsportalen zoeken
1. Klik in Azure AD Identity Governance op **Access-pakketten**en klik vervolgens op uw toegangspakket.
2. Klik op de pagina **Overzicht** op **Kopiëren naar klembordkoppeling** voor de **koppeling Mijn toegang-portal**.

   ![Schermafbeelding van de eigenschappen van toegangspakket met koppeling toegangsportport](../media/identity-governance-access-portal-link.png)

Zodra u de koppeling hebt gekopieerd, u deze delen met uw contactpersoon bij de partnerorganisatie en deze naar de gebruikers van hun samenwerkingsteam sturen.

## <a name="see-also"></a>Zie ook

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

