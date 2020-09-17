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
description: Leer hoe u een B2B-extranetsite of-team maakt met beheerde gastgebruikers van een partnerorganisatie.
ms.openlocfilehash: 83252241833f3dfe663cc70eae28a5df1214cce0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949382"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Een B2B-extranet maken met beheerde gasten

Met [Azure Active Directory-beheer van rechten](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) kunt u een B2B-extranet maken om samen te werken met een partnerorganisatie die gebruikmaakt van Azure Active Directory. Hiermee kunnen gebruikers zichzelf registreren op de extranetsite of het team en toegang krijgen via een goedkeuringswerkstroom.

Met deze methode voor het delen van bronnen voor samenwerking kan de organisatie organisatie de gastgebruikers aan hun einde bijhouden en goedkeuren, waardoor de belasting van uw IT-afdeling wordt beperkt en de functies voor de samenwerking voor de samenwerking voor de samenwerking voor de samenwerking kunnen worden beheerd.

In dit artikel worden de stappen beschreven voor het maken van een bron pakket (in dit geval een site of team) dat u kunt delen met een partnerorganisatie via een registratie model voor selfservice toegang. 

Voordat u begint, maakt u de site of het team dat u wilt delen met de partnerorganisatie en schakelt u de site in voor het delen van gasten. Zie [samenwerken met gasten in een site](collaborate-in-site.md) of [samenwerken met gasten in een team](collaborate-as-team.md) voor meer informatie. U wordt ook aangeraden [een beveiligde omgeving voor het delen van gasten](create-secure-guest-sharing-environment.md) te bekijken voor informatie over beveiligings-en compliance-functies die u kunt gebruiken om uw beheerbeleidsregels te beschermen bij het samenwerken aan gasten.

## <a name="license-requirements"></a>Licentievereisten

Voor het gebruik van deze functie is een Azure AD Premium-licentie vereist. 

Gespecialiseerde wolken, zoals Azure Duitsland en Azure China 21Vianet, zijn momenteel niet beschikbaar.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video ziet u de procedures in dit artikel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>De partnerorganisatie verbinden

Om gasten van een partnerorganisatie uit te nodigen, moet u het domein van de partner toevoegen als een verbonden organisatie in azure Active Directory.

Een verbonden organisatie toevoegen
1. Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identity governance**.
2. Klik op **verbonden organisaties**.
4. Klik op **verbonden organisatie toevoegen**.
5. Voer een naam en beschrijving voor de organisatie in en klik op **volgende: adreslijst + domein**.
6. Klik op **adreslijst + domein toevoegen**.
7. Typ het domein voor de organisatie waarmee u verbinding wilt maken en klik op **toevoegen**.
8. Klik op **verbinden**en klik vervolgens op **volgende: sponsors**.
9. Voeg mensen uit uw organisatie of organisatie toe die u wilt gebruiken voor de toegang tot gastgebruikers.
10. Klik op **volgende: bekijken + maken**.
11. Controleer de instellingen die u hebt gekozen en klik vervolgens op **maken**.

    ![Schermafbeelding van de pagina verbonden organisaties in azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Kies de resources die u wilt delen

De eerste stap bij het selecteren van resources om te delen met een partnerorganisatie is het maken van een catalogus om deze te bevatten.

Een catalogus maken
1. Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identity governance**.
2. Klik op **catalogussen**.
3. Klik op **nieuwe catalogus**.
4. Typ een naam en beschrijving voor de catalogus en zorg ervoor dat **ingeschakeld** en **ingeschakeld voor externe gebruikers** zijn ingesteld op **Ja**.
5. Klik op **Maken**.

   ![Schermafbeelding van de pagina catalogussen in azure Active Directory Identity governance](../media/identity-governance-catalogs.png)

Nadat de catalogus is gemaakt, voegt u de SharePoint-site of het team toe dat u wilt delen met de partnerorganisatie.

Resources aan een catalogus toevoegen
1. Klik in azure AD Identity governance op **catalogi**en klik vervolgens op de catalogus waaraan u resources wilt toevoegen.
2. Klik op **resources** en klik vervolgens op **resources toevoegen**.
3. Selecteer de teams of SharePoint-sites die u wilt opnemen in uw extranet en klik op **toevoegen**.

   ![Schermafbeelding van de pagina met catalogus resources in azure Active Directory Identity governance](../media/identity-governance-catalog-resource.png)

Wanneer u de bronnen hebt gedefinieerd die u wilt delen, moet u een toegangs pakket maken, waarmee het type toegang dat partner gebruikers worden verleend en het goedkeuringsproces voor nieuwe partner gebruikers die toegang vraagt, wordt gedefinieerd.

Een toegangs pakket maken
1. Klik in azure AD Identity governance op **catalogi**en klik vervolgens op de catalogus waarop u een toegangs pakket wilt maken.
2. Klik op **toegangs pakketten**en klik vervolgens op **nieuw toegangs pakket**.
3. Typ een naam en beschrijving voor het toegangs pakket en klik vervolgens op **volgende: resource rollen**.
4. Kies de resources in de catalogus die u wilt gebruiken voor uw extranet.
5. Kies voor elke **resource de gebruikersrol** die u wilt verlenen aan de gastgebruikers die het extranet gebruiken.
6. Klik op **volgende: aanvragen**.
7. Kies onder **gebruikers die toegang kunnen aanvragen** **voor gebruikers die niet in uw adreslijst**staan.
8. Zorg ervoor dat de optie **specifieke verbonden organisaties** is geselecteerd en klik vervolgens op **mappen toevoegen**.
9. Kies de verbonden organisatie die u eerder toevoegt en klik vervolgens op **selecteren**
10. Kies onder **goedkeuring**de optie **Ja** voor **Goedkeuring vereisen**.
11. Kies onder **First beoordelaar**een van de sponsors die u eerder hebt toegevoegd of kies een specifieke gebruiker.
12. Klik op **terugval toevoegen** en selecteer een terugval beoordelaar.
13. Kies onder **inschakelen**de optie **Ja**.
14. Klik op **volgende: levenscyclus**.
15. Kies de instellingen voor het verloop en toegangscontrole die u wilt gebruiken en klik op **volgende: controleren + maken**.
16. Controleer de instellingen en klik vervolgens op **maken**.

    ![Schermafbeelding van het scherm met toegangs pakketten in azure Active Directory Identity governance](../media/identity-governance-access-packages.png)

Als u een partner maakt met een grote organisatie, wilt u mogelijk het toegangs pakket verbergen. Als het pakket verborgen is, wordt het pakket niet in de partnerorganisatie weergegeven op de portal van *Mijn toegang* . In plaats daarvan moet de persoon een directe koppeling sturen om zich voor het pakket te registreren. Als u het toegangs pakket verbergt, kan het aantal ongepaste toegangsaanvragen verminderd en worden de beschikbare toegangs pakketten in de portal van de partnerorganisatie ook bijgehouden.

Een toegangs pakket instellen op verborgen
1. Klik in azure AD Identity governance op **toegangs pakketten**en klik vervolgens op uw toegangs pakket.
2. Klik op de pagina **overzicht** op **bewerken**.
3. Kies onder **Eigenschappen**de optie **Ja** voor **verborgen**en klik vervolgens op **Opslaan**.

   ![Schermafbeelding van het scherm Eigenschappen van het Access-pakket bewerken](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Gebruikers van partners uitnodigen

Als u het toegangs pakket instelt op verborgen, moet u een rechtstreekse koppeling naar de partnerorganisatie verzenden, zodat ze toegang tot uw site of team kunnen aanvragen.

De koppeling naar een Access-Portal zoeken
1. Klik in azure AD Identity governance op **toegangs pakketten**en klik vervolgens op uw toegangs pakket.
2. Klik op de pagina **overzicht** op **naar Klembord kopiëren om** de **koppeling naar de portal voor mijn toegang**.

   ![Schermafbeelding van eigenschappen van het Access-pakket met de koppeling naar de portal van Access](../media/identity-governance-access-portal-link.png)

Wanneer u de koppeling hebt gekopieerd, kunt u deze delen met uw contactpersoon in de partnerorganisatie en ze kunnen het verzenden naar de gebruikers in het samenwerkingsteam.

## <a name="see-also"></a>Zie ook

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)
