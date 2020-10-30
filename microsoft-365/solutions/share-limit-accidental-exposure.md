---
title: Onopzettelijke blootstelling beperken
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
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Meer informatie over het beperken van de onopzettelijke blootstelling van informatie bij het delen van bestanden met personen van buiten uw organisatie.
ms.openlocfilehash: 6250103e36900da76a4529a73b78f14862ab86ef
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769004"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen van buiten uw organisatie

Wanneer u bestanden en mappen deelt met personen van buiten uw organisatie, zijn er diverse opties om de kans te verkleinen dat vertrouwelijke informatie per ongeluk wordt gedeeld. U kunt de opties in dit artikel kiezen die het meest tegemoet te komen aan de behoeften van uw organisatie.

## <a name="use-best-practices-for-anyone-links"></a>Aanbevolen procedures gebruiken voor Iedereen-koppelingen

Als personen in uw organisatie moeten kunnen delen zonder verificatie, maar u zich zorgen maakt dat niet-geverifieerde personen de inhoud wijzigen, leest u [Aanbevolen procedures voor niet-geverifieerd delen](best-practices-anonymous-sharing.md) voor hulp bij het werken met niet-geverifieerde delen in uw organisatie.

## <a name="turn-off-anyone-links"></a>Iedereen-koppelingen uitschakelen

Wij raden u aan *Iedereen* -koppelingen ingeschakeld te laten voor geschikte inhoud, omdat dit de eenvoudigste manier is om te delen en om het risico te beperken dat gebruikers andere oplossingen zoeken waarop de IT-afdeling geen invloed heeft. *Iedereen* -koppelingen kunnen worden doorgestuurd naar anderen, maar bestandstoegang is alleen beschikbaar voor personen die de koppeling hebben.

Als u wilt dat personen van buiten uw organisatie zich altijd moeten verifiëren bij het openen van inhoud in SharePoint, Groepen of Teams, kunt u delen met *Iedereen* uitschakelen. Hiermee voorkomt u dat gebruikers inhoud niet-geverifieerd delen.

Als u *Iedereen* -koppelingen uitschakelt, kunnen gebruikers nog steeds eenvoudig met gasten delen met behulp van *Specifieke personen* -koppelingen. In dit geval zijn alle personen van buiten uw organisatie verplicht zich te verifiëren voordat ze toegang krijgen tot de gedeelde inhoud.

Afhankelijk van uw behoeften kunt u *Iedereen* -koppelingen voor specifieke sites of voor uw hele organisatie uitschakelen.

*Iedereen* -koppelingen voor uw organisatie uitschakelen
1. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen** .
2. Stel de instellingen voor extern delen van SharePoint in op **Nieuwe en bestaande gasten** .

   ![Schermafbeelding van de instellingen voor extern delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. Klik op **Opslaan** .

*Iedereen* -links voor een site uitschakelen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen** .
2. Selecteer de site die u wilt configureren.
3. Klik op het lint op **Delen** .
4. Zorg ervoor dat delen is ingesteld op **Nieuwe en bestaande gasten** .

   ![Schermafbeelding van de instellingen voor extern delen op siteniveau in SharePoint](../media/sharepoint-site-external-sharing-settings.png)

5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan** .

## <a name="domain-filtering"></a>Domeinfiltering

U kunt lijsten voor het toestaan of weigeren van domeinen gebruiken om te specificeren welke domeinen uw gebruikers kunnen gebruiken wanneer zij iets met personen van buiten uw organisatie delen.

Met een lijst Toestaan kunt u een lijst opgeven met domeinen waarin gebruikers in uw organisatie kunnen delen met personen van buiten uw organisatie. Delen met andere domeinen wordt geblokkeerd. Als uw organisatie alleen samenwerkt met personen uit een lijst met specifieke domeinen, kunt u deze functie gebruiken om te voorkomen dat er met andere domeinen wordt gedeeld.

Met een lijst Weigeren kunt u een lijst opgeven met domeinen waaruit gebruikers in uw organisatie niet kunnen delen met personen van buiten uw organisatie. Delen met de opgegeven domeinen wordt geblokkeerd. Dit kan handig zijn als u bijvoorbeeld concurrenten hebt, waarvan u wilt voorkomen dat zij toegang hebben tot de inhoud van uw organisatie.

De lijsten Toestaan en Weigeren zijn alleen van toepassing op delen met gasten. Gebruikers kunnen nog steeds delen met personen van verboden domeinen met *Iedereen* -koppelingen als u deze niet hebt uitgeschakeld. Voor de beste resultaten met lijsten voor het toestaan en weigeren van domeinen kunt u eventueel de *Iedereen* -koppelingen uitschakelen, zoals hierboven beschreven.

Een lijst voor het toestaan of weigeren van domeinen instellen
1. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen** .
2. Onder **Geavanceerde instellingen voor extern delen** selecteert u het selectievakje **Extern delen beperken per domein** .
3. Klik op **Domeinen toevoegen** .
4. Selecteer of u wilt dat er domeinen worden geblokkeerd, typ de domeinen en klik op **OK** .

   ![Schermafbeelding van de instelling voor extern delen per domein beperken in SharePoint](../media/sharepoint-sharing-block-domain.png)

5. Klik op **Opslaan** .

Als u het delen per domein op een hoger niveau dan SharePoint en OneDrive wilt beperken, kunt u [uitnodigingen voor B2B-gebruikers toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) in Microsoft Azure Active Directory. (Voor deze instellingen moet u de [SharePoint- en OneDrive-integratie met Microsoft Azure AD B2B (Voorbeeld)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) configureren om invloed te hebben op SharePoint en OneDrive.)

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Het delen van bestanden, mappen en sites met personen van buiten uw organisatie beperken tot gespecificeerde beveiligingsgroepen

U kunt het delen van bestanden, mappen en sites met personen van buiten uw organisatie beperken tot leden van een specifieke beveiligingsgroep. Dit is handig als u extern delen wilt inschakelen, maar wel met een goedkeuringswerkstroom of aanvraagproces. U kunt desgewenst van uw gebruikers vragen dat ze een trainingscursus voltooien voordat ze aan de beveiligingsgroep worden toegevoegd en extern kunnen delen.

Extern delen beperken tot leden van een beveiligingsgroep
1. Klik in het [SharePoint Online Beheercentrum](https://admin.microsoft.com/sharepoint) in het navigatievenster aan de linkerkant, onder **Beleid** op **Delen** .
2. Vouw onder **Extern delen** de optie **Meer instellingen voor extern delen** uit.

3. Selecteer **Alleen gebruikers in een bepaalde beveiligingsgroep toestaan om extern te delen** en selecteer vervolgens **Beveiligingsgroepen beheren** .

    ![Schermafbeelding van het deelvenster Beveiligingsgroepen beheren](https://docs.microsoft.com/sharepoint/sharepointonline/media/manage-security-groups.png)

4. Voer in het dialoogvenster **Een beveiligingsgroep toevoegen** een naam in voor een beveiligingsgroep. Het dialoogvenster Beveiligingsgroep wordt nu weergegeven.

5. Selecteer naast de naam van de beveiligingsgroep, in de vervolgkeuzelijst **Kan delen met** een van de twee opties:

    - **Alleen geverifieerde gasten** (standaard)
    - **Iedereen**

6. Kies **Opslaan** .

Merk op dat dit invloed heeft op bestanden, mappen en sites, maar niet op Microsoft 365-groepen of Teams. Wanneer leden gasten uitnodigen voor een privégroep in Microsoft 365 of een privéteam in Microsoft Teams, wordt de uitnodiging voor goedkeuring naar de teameigenaar gestuurd.

## <a name="see-also"></a>Zie ook

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Aanbevolen procedures voor het delen van bestanden en mappen met anonieme gebruikers](best-practices-anonymous-sharing.md)