---
title: Uw Test lab of pilotomgeving met Microsoft 365 Defender instellen
description: Access Microsoft 365 Security Center then set up your Microsoft 365 Defender trial lab environment
keywords: Microsoft Threat Protection trial setup, Microsoft Threat Protection pilot setup, try Microsoft Threat Protection, Microsoft Threat Protection evaluation lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932980"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Uw Test labomgeving met Microsoft 365 Defender instellen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender 


Het maken van een testtest of pilotomgeving van Microsoft 365 Defender en deze implementeren bestaat uit drie fasen:

|[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: Voorbereiden](prepare-mtpeval.md) |![Fase 2: Instellen](../../media/phase-diagrams/setup.png)<br/>Fase 2: Instellen |[![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: Onboard](config-mtpeval.md) | [![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Terug naar pilot playbook](mtp-pilot.md) |
|--|--|--|--|
||*U bent hier!*  | | |


U bent momenteel in de fase van de in te stellen fase. Ga als eerste te werk om het Microsoft 365-beveiligingscentrum te openen en stel vervolgens uw testtestomgeving of pilotomgeving in.

Meld u aan voor een Office 365- of Azure Active Directory-abonnement om een *.onmicrosoft.com-tenant* te genereren die u kunt gebruiken om u te registreren voor uw Microsoft 365 E5-licentie. 

>[!NOTE]
>Als u al een Office 365- of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van de proefversie van Office 365 E5 of de tenant als pilot overslaan.

In deze fase kunt u het volgende doen:
- Een proefversie-tenant van Office 365 E5 maken
- Proefabonnement op Microsoft 365 inschakelen


## <a name="create-an-office-365-e5-trial-tenant"></a>Een proefversie-tenant van Office 365 E5 maken
>[!NOTE]
>Als u al een Office 365- of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van de office 365 E5-proef tenant overslaan.

1. Ga naar de [Office 365 E5-productportal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **een gratis proefversie.**

   ![Afbeelding of_Office gratis proefversie van 365 E5](../../media/mtp-eval-9.png)
  
2. Voltooi de registratie van het proefabonnement door uw e-mailadres (persoonlijk of zakelijk) in te vullen. Klik **op Account instellen.**

   ![Afbeelding of_Office registratiepagina voor de proefversie van 365 E5](../../media/mtp-eval-10.png)

3. Vul uw voornaam, achternaam, zakelijk telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.  

   ![Afbeelding of_Office registratiepagina voor de proefversie van 365 E5 waarin om naam, telefoon en bedrijfsgegevens wordt gevraagd](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Het land of de regio die u hier hebt ingesteld, bepaalt de regio van het datacenter waar Uw Office 365 wordt gehost.
  
4. Kies uw verificatievoorkeur: via een sms-bericht of gesprek. Klik **op Verificatiecode verzenden.** 

   ![Afbeelding of_Office registratiepagina voor de proefversie van 365 E5 waarin om verificatievoorkeur wordt gevraagd](../../media/mtp-eval-12.png)

5. Stel de aangepaste domeinnaam voor uw tenant in en klik op **Volgende.**

   ![Afbeelding of_Office de registratiepagina voor proefversies van 365 E5 waar u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)
 
6. Stel de eerste identiteit in, die een globale beheerder voor de tenant wordt. Vul Naam **en** **wachtwoord in.** Klik **op Registreren.**

   ![Afbeelding of_Office registratiepagina voor proefversie 365 E5 waar u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)

7. Klik **op Ga naar Setup om** de inrichting van de proef tenant van Office 365 E5 te voltooien.

   ![Afbeelding van de registratiepagina voor proefversie van Office 365 E5 met de vraag of u wilt klikken op de knop Instellen](../../media/mtp-eval-15.png)

8. Verbind uw bedrijfsdomein met de Office 365-tenant. [Optioneel] Kies **Verbinding maken met een domein waar u al eigenaar van bent** en typ uw domeinnaam. Klik op **Volgende**.

   ![Afbeelding of_Office 365 E5-installatiepagina waar u uw aanmelding en e-mail aan uw persoonlijke voorkeur moet personaliseren](../../media/mtp-eval-16.png)
 
9. Voeg een TXT- of MX-record toe om het eigendom van het domein te valideren. Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren.**

   ![Afbeelding of_Office 365 E5-installatiepagina waar u een TXT of MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png)
 
10. [Optioneel] Maak meer gebruikersaccounts voor uw tenant. U kunt deze stap overslaan door op Volgende te **klikken.**

    ![Afbeelding of_Office 365 E5-installatiepagina waar u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)
 
11. [Optioneel] Download Office-apps. Klik **op Volgende** om deze stap over te slaan. 

    ![Afbeelding of_Office 365 E5-pagina waarop u uw Office-apps kunt installeren](../../media/mtp-eval-19.png)

12. [Optioneel] E-mailberichten migreren. Nogmaals, u kunt deze stap overslaan.

    ![Afbeelding of_Office 365 E5, waar u kunt instellen of u wel of niet e-mailberichten wilt migreren](../../media/mtp-eval-20.png)
 
13. Kies onlineservices. Selecteer **Exchange en** klik op **Volgende.** 

    ![Afbeelding of_Office 365 E5, waar u uw onlineservices kunt kiezen](../../media/mtp-eval-21.png)

14. Voeg MX-, CNAME- en TXT-records toe aan uw domein. Als u klaar is, selecteert u **Verifiëren.**

    ![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)
 
15. Gefeliciteerd, u hebt de inrichting van uw Office 365-tenant voltooid.

    ![Bevestigingspagina of_Office 365 E5 instellen](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Proefabonnement op Microsoft 365 inschakelen

>[!NOTE]
>Als u zich aanmeldt voor een proefabonnement, krijgt u 25 gebruikerslicenties die u per maand kunt gebruiken. Zie [Een M365-abonnement proberen of kopen](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.

1. Klik [in het Microsoft 365-beheercentrum](https://admin.microsoft.com/)op **Facturering** en ga naar **Services aanschaffen.**

2. Selecteer **Microsoft 365 E5 en** klik op Gratis **proefversie starten.** 

   ![Afbeelding of_Microsoft gratis proefversie van 365 E5 starten](../../media/mtp-eval-24.png)

3. Kies uw verificatievoorkeur: via een sms-bericht of gesprek. Zodra u hebt besloten, voert u het telefoonnummer in, selecteert u Sms **me** of **Bel me,** afhankelijk van uw selectie.

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversie met vragen om contactgegevens om code te verzenden om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)
 
4. Voer de verificatiecode in en klik **op Uw gratis proefabonnement starten.**

   ![Afbeelding of_Microsoft 365 E5 Start een gratis proefversiepagina waar u verificatiecode kunt invullen die door het systeem is verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)

5. Klik **op Nu proberen** om uw proefabonnement op Microsoft 365 E5 te bevestigen.

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten, waar u met de knop Nu proberen moet kloken om te beginnen](../../media/mtp-eval-27.png)
 
6. Ga naar het **Microsoft 365-beheercentrum**  >  **gebruikers die** actief  >  **zijn.** Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren** en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5.** Klik op **Opslaan**.

   ![Afbeelding of_Microsoft 365-beheercentrumpagina waar u een Microsoft 365 E5-licentie kunt selecteren](../../media/mtp-eval-28.png)
 
7. Selecteer nogmaals het globale beheerdersaccount en klik op **Gebruikersnaam beheren.**

   ![Afbeelding of_Microsoft de pagina 365-beheercentrum waar u Account kunt selecteren en vervolgens gebruikersnaam beheren](../../media/mtp-eval-29.png)

8. [Optioneel] Wijzig het domein van *onmicrosoft.com* in uw eigen domein, afhankelijk van wat u in de vorige stappen hebt gekozen. Klik op **Wijzigingen opslaan**.

   ![Afbeelding of_Microsoft 365-beheercentrumpagina waar u uw domeinvoorkeur kunt wijzigen](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Volgende stap
|[Fase 3: & onboard](config-mtpeval.md) | Configureer elke Microsoft 365 Defender-testomgeving voor uw Test lab of pilotomgeving van Microsoft 365 Defender en onboard uw eindpunten.
|:-------|:-----|
