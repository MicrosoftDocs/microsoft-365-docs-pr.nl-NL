---
title: Een B2B-extranet maken met beheerde gasten
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Meer informatie over het maken van een B2B-extranetsite of -team met beheerde gasten van een partnerorganisatie.
ms.openlocfilehash: d76951da5d8affa1dac08cbdc68a91329ca069ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538241"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Een B2B-extranet maken met beheerde gasten

U kunt Azure Active Directory [Entitlement Management gebruiken](/azure/active-directory/governance/entitlement-management-overview) om een B2B-extranet te maken om samen te werken met een partnerorganisatie die Azure Active Directory. Hierdoor kunnen gebruikers zich zelf registreren voor de extranetsite of het extranetteam en toegang krijgen via een goedkeuringswerkstroom.

Met deze methode voor het delen van resources voor samenwerking kan de partnerorganisatie helpen bij het onderhouden en goedkeuren van de gasten aan hun kant, waardoor de belasting voor uw IT-afdeling wordt verkleind en degenen die het meest vertrouwd zijn met de samenwerkingsovereenkomst, gebruikerstoegang kunnen beheren.

In dit artikel worden de stappen beschreven voor het maken van een pakket met resources (in dit geval een site of team) die u met een partnerorganisatie kunt delen via een registratiemodel voor selfservicetoegang. 

Voordat u begint, maakt u de site of het team dat u wilt delen met de partnerorganisatie en stelt u deze in voor het delen van gasten. Zie [Samenwerken met gasten op een site](collaborate-in-site.md) of Samenwerken met gasten in een [team](collaborate-as-team.md) voor meer informatie. We raden u [](create-secure-guest-sharing-environment.md) ook aan een beveiligde omgeving voor het delen van gasten te bekijken voor informatie over beveiligings- en compliancefuncties die u kunt gebruiken om uw beheerbeleid te behouden wanneer u samenwerkt met gasten.

## <a name="license-requirements"></a>Licentievereisten

Voor het gebruik van deze functie is een Azure AD-Premium P2-licentie vereist. 

Gespecialiseerde clouds, zoals Azure Germany en Azure China 21Vianet, zijn momenteel niet beschikbaar voor gebruik.

## <a name="video-demonstration"></a>Videodemonstratie

In deze video worden de procedures in dit artikel beschreven.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Verbinding maken partnerorganisatie

Als u gasten uit een partnerorganisatie wilt uitnodigen, moet u het domein van de partner toevoegen als verbonden organisatie in Azure Active Directory.

Een verbonden organisatie toevoegen
1. Klik [Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer**.
2. Klik **op Verbonden organisaties.**
4. Klik **op Verbonden organisatie toevoegen.**
5. Typ een naam en beschrijving voor de organisatie en klik vervolgens **op Volgende: Directory + domein.**
6. Klik **op Adreslijst + domein toevoegen.**
7. Typ het domein voor de organisatie die u wilt verbinden en klik vervolgens op **Toevoegen.**
8. Klik **Verbinding maken** en klik vervolgens op **Volgende: Sponsors.**
9. Voeg personen toe van uw organisatie of de organisatie die u verbindt met wie u de toegang voor gasten wilt goedkeuren.
10. Klik op **Volgendet: Controleren + Maken**.
11. Controleer de instellingen die u hebt gekozen en klik vervolgens op **Maken.**

    ![Schermafbeelding van de pagina verbonden organisaties in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>De resources kiezen die u wilt delen

De eerste stap bij het selecteren van resources die u wilt delen met een partnerorganisatie, is het maken van een catalogus om deze te bevatten.

Een catalogus maken
1. Klik [Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer**.
2. Klik **op Catalogi.**
3. Klik **op Nieuwe catalogus.**
4. Typ een naam en beschrijving voor de catalogus en zorg ervoor dat **Ingeschakeld** en Ingeschakeld voor **externe gebruikers** beide zijn ingesteld op **Ja.**
5. Klik op **Maken**.

   ![Schermafbeelding van de cataloguspagina in Azure Active Directory Identiteitsbeheer](../media/identity-governance-catalogs.png)

Wanneer de catalogus is gemaakt, voegt u de SharePoint site of team toe die u wilt delen met de partnerorganisatie.

Resources toevoegen aan een catalogus
1. Klik in Azure AD Identity Governance op **Catalogi** en klik vervolgens op de catalogus waar u resources wilt toevoegen.
2. Klik **op Resources** en klik vervolgens op Resources **toevoegen.**
3. Selecteer de teams of SharePoint sites die u wilt opnemen in uw extranet en klik vervolgens op **Toevoegen.**

   ![Schermafbeelding van de pagina catalogusbronnen in Azure Active Directory Identiteitsbeheer](../media/identity-governance-catalog-resource.png)

Nadat u de resources hebt gedefinieerd die u wilt delen, is de volgende stap het maken van een access-pakket, waarin het type toegang wordt gedefinieerd dat partnergebruikers worden verleend en het goedkeuringsproces voor nieuwe partnergebruikers die toegang aanvragen.

Een toegangspakket maken
1. Klik in Azure AD Identity Governance op **Catalogi** en klik vervolgens op de catalogus waar u een access-pakket wilt maken.
2. Klik **op Access-pakketten** en klik vervolgens op **Nieuw toegangspakket.**
3. Typ een naam en beschrijving voor het access-pakket en klik vervolgens **op Volgende: Resourcerollen.**
4. Kies de resources in de catalogus die u wilt gebruiken voor uw extranet.
5. Kies voor elke resource in **de** kolom Rol de gebruikersrol die u wilt verlenen aan de gasten die het extranet gebruiken.
6. Klik **op Volgende: Aanvragen.**
7. Kies **onder Gebruikers die toegang kunnen aanvragen** de optie Voor gebruikers die niet in uw **adreslijst staan.**
8. Controleer of de **optie Specifieke verbonden organisaties** is geselecteerd en klik vervolgens op **Directories toevoegen.**
9. Kies de verbonden organisatie die u eerder hebt toevoegen en klik vervolgens op **Selecteren**
10. Kies **onder Goedkeuring** de optie **Ja** voor **Goedkeuring vereisen.**
11. Kies **onder Eerste goedkeurder** een van de sponsors die u eerder hebt toegevoegd of kies een specifieke gebruiker.
12. Klik **op Terugval toevoegen** en selecteer een fallback-goedkeurder.
13. Kies **onder Inschakelen** de optie **Ja.**
14. Klik **op Volgende: Levenscyclus.**
15. Kies de instellingen voor verloop en toegangsbeoordeling die u wilt gebruiken en klik vervolgens op **Volgende: Controleren + Maken.**
16. Controleer de instellingen en klik vervolgens op **Maken.**

    ![Schermafbeelding van het scherm access packages in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Als u een partnerschap aan gaat met een grote organisatie, kunt u het toegangspakket verbergen. Als het pakket is verborgen, zien gebruikers in de partnerorganisatie het pakket niet in hun *My Access-portal.* In plaats daarvan moeten ze een directe koppeling ontvangen om zich aan te melden voor het pakket. Het verbergen van het toegangspakket kan het aantal ongepaste toegangsaanvragen verminderen en kan ook helpen om beschikbare toegangspakketten georganiseerd te houden in de portal van de partnerorganisatie.

Een toegangspakket instellen op verborgen
1. Klik in Azure AD Identity Governance op **Access-pakketten** en klik vervolgens op uw toegangspakket.
2. Klik op **de pagina** Overzicht op **Bewerken.**
3. Kies **onder Eigenschappen** de optie **Ja** voor **verborgen** en klik vervolgens op **Opslaan.**

   ![Schermafbeelding van een scherm met eigenschappen van een bewerkingstoegangspakket](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Partnergebruikers uitnodigen

Als u het toegangspakket hebt ingesteld op verborgen, moet u een directe koppeling naar de partnerorganisatie verzenden, zodat deze toegang tot uw site of team kan aanvragen.

De koppeling toegangsportal zoeken
1. Klik in Azure AD Identity Governance op **Access-pakketten** en klik vervolgens op uw toegangspakket.
2. Klik op **de** pagina Overzicht op **Koppeling kopiëren naar klembord** voor de koppeling **Mijn Access-portal.**

   ![Schermafbeelding van eigenschappen van access package met access portal link](../media/identity-governance-access-portal-link.png)

Nadat u de koppeling hebt gekopieerd, kunt u deze delen met uw contactpersoon bij de partnerorganisatie en deze verzenden naar de gebruikers in hun samenwerkingsteam.

## <a name="see-also"></a>Zie ook

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)