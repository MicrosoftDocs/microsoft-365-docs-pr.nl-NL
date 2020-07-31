---
title: Onopzettelijke blootstelling beperken
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
localization_priority: Priority
f1.keywords: NOCSH
description: Meer informatie over het beperken van de onopzettelijke blootstelling van informatie bij het delen van bestanden met personen van buiten uw organisatie.
ms.openlocfilehash: 266c395b6165eac4fbb7c3f7a6ed9e77a1287ba4
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527620"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen van buiten uw organisatie

Wanneer u bestanden en mappen deelt met personen van buiten uw organisatie, zijn er diverse opties om de kans te verkleinen dat vertrouwelijke informatie per ongeluk wordt gedeeld. U kunt de opties in dit artikel kiezen die het meest tegemoet te komen aan de behoeften van uw organisatie.

## <a name="use-best-practices-for-anyone-links"></a>Aanbevolen procedures gebruiken voor Iedereen-koppelingen

Als personen in uw organisatie moeten kunnen delen zonder verificatie, maar u zich zorgen maakt dat niet-geverifieerde personen de inhoud wijzigen, leest u [Aanbevolen procedures voor niet-geverifieerd delen](best-practices-anonymous-sharing.md) voor hulp bij het werken met niet-geverifieerde delen in uw organisatie.

## <a name="turn-off-anyone-links"></a>Iedereen-koppelingen uitschakelen

Wij raden u aan *Iedereen*-koppelingen ingeschakeld te laten voor geschikte inhoud, omdat dit de eenvoudigste manier is om te delen en om het risico te beperken dat gebruikers andere oplossingen zoeken waarop de IT-afdeling geen invloed heeft. *Iedereen*-koppelingen kunnen worden doorgestuurd naar anderen, maar bestandstoegang is alleen beschikbaar voor personen die de koppeling hebben.

Als u wilt dat personen van buiten uw organisatie zich altijd moeten verifiëren bij het openen van inhoud in SharePoint, Groepen of Teams, kunt u delen met *Iedereen* uitschakelen. Hiermee voorkomt u dat gebruikers inhoud niet-geverifieerd delen.

Als u *Iedereen*-koppelingen uitschakelt, kunnen gebruikers nog steeds eenvoudig met gasten delen met behulp van *Specifieke personen*-koppelingen. In dit geval zijn alle personen van buiten uw organisatie verplicht zich te verifiëren voordat ze toegang krijgen tot de gedeelde inhoud.

Afhankelijk van uw behoeften kunt u *Iedereen*-koppelingen voor specifieke sites of voor uw hele organisatie uitschakelen.

*Iedereen*-koppelingen voor uw organisatie uitschakelen
1. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.
2. Stel de instellingen voor extern delen van SharePoint in op **Nieuwe en bestaande gasten**.</br>
   ![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-organization-external-sharing-controls-new-users.png)
3. Klik op **Opslaan**.

*Iedereen*-links voor een site uitschakelen
1. Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.
2. Selecteer de site voor het team dat u zojuist hebt gemaakt.
3. Klik op het lint op **Delen**.
4. Zorg ervoor dat delen is ingesteld op **Nieuwe en bestaande gasten**.</br>
   ![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)
5. Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.

## <a name="domain-filtering"></a>Domeinfiltering

U kunt lijsten voor het toestaan of weigeren van domeinen gebruiken om te bepalen welke domeinen uw gebruikers kunnen delen met personen van buiten uw organisatie.

Met een lijst Toestaan kunt u een lijst opgeven met domeinen waarin gebruikers in uw organisatie kunnen delen met personen van buiten uw organisatie. Delen met andere domeinen wordt geblokkeerd. Als uw organisatie alleen samenwerkt met personen uit een lijst met specifieke domeinen, kunt u deze functie gebruiken om te voorkomen dat er met andere domeinen wordt gedeeld.

Met een lijst Weigeren kunt u een lijst opgeven met domeinen waaruit gebruikers in uw organisatie niet kunnen delen met personen van buiten uw organisatie. Delen met de opgegeven domeinen wordt geblokkeerd. Dit kan handig zijn als u bijvoorbeeld concurrenten hebt, waarvan u wilt voorkomen dat zij toegang hebben tot de inhoud van uw organisatie.

De lijsten Toestaan en Weigeren zijn alleen van toepassing op delen met gasten. Gebruikers kunnen nog steeds delen met personen van verboden domeinen met *Iedereen*-koppelingen als u deze niet hebt uitgeschakeld. Voor de beste resultaten met lijsten voor het toestaan en weigeren van domeinen kunt u eventueel de *Iedereen*-koppelingen uitschakelen, zoals hierboven beschreven.

Een lijst Toestaan of Weigeren voor een domein instellen voor personen van buiten uw organisatie
1. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.
2. Onder **Geavanceerde instellingen voor extern delen** selecteert u het selectievakje **Extern delen beperken per domein**.
3. Klik op **Domeinen toevoegen**.
4. Selecteer of u wilt dat er domeinen worden geblokkeerd, typ de domeinen en klik op **OK**.</br>
   ![Schermafbeelding van de instelling voor extern delen per domein beperken van SharePoint](../media/sharepoint-sharing-block-domain.png)
5. Klik op **Opslaan**.

Als u het delen per domein op een hoger niveau dan SharePoint en OneDrive wilt beperken, kunt u [uitnodigingen voor B2B-gebruikers toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) in Microsoft Azure Active Directory. (Voor deze instellingen moet u de [SharePoint- en OneDrive-integratie met Microsoft Azure AD B2B (Voorbeeld)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) configureren om invloed te hebben op SharePoint en OneDrive.)

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Het delen van bestanden, mappen en sites met personen van buiten uw organisatie beperken tot gespecificeerde beveiligingsgroepen

U kunt het delen van bestanden, mappen en sites met personen van buiten uw organisatie beperken tot leden van een specifieke beveiligingsgroep. Dit is handig als u extern delen wilt inschakelen, maar wel met een goedkeuringswerkstroom of aanvraagproces.

Extern delen beperken tot leden van een beveiligingsgroep
1. Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.
2. Onder **Andere instellingen**. volg het koppeling naar **Extern delen beperken tot specifieke beveiligingsgroepen**.
3. Selecteer onder **Wie kan delen buiten uw organisatie** een of beide selectievakjes: a. **Alleen gebruikers in geselecteerde beveiligingsgroepen kunnen met externe gebruikers delen** om een beveiligingsgroep op te geven die met geverifieerde gebruikers kan delen b. **Alleen gebruikers in geselecteerde beveiligingsgroepen kunnen met externe gebruikers delen en met gebruik van anonieme koppelingen** om een beveiligingsgroep op te geven die met geverifieerde gebruikers kan delen met gebruik van Iedereen-koppelingen
4. Klik op **OK**.

Merk op dat dit invloed heeft op bestanden, mappen en sites, maar niet op Microsoft 365-groepen of Teams. Wanneer leden gasten uitnodigen voor een privégroep in Microsoft 365 of een privéteam in Microsoft Teams, wordt de uitnodiging voor goedkeuring naar de teameigenaar gestuurd.

## <a name="see-also"></a>Zie ook

[Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

[Aanbevolen procedures voor het delen van bestanden en mappen met anonieme gebruikers](best-practices-anonymous-sharing.md)