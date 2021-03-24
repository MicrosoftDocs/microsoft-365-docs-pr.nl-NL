---
title: Uw proeflaboratorium of testomgeving voor Microsoft 365 Defender instellen
description: Access Microsoft 365-beveiligingscentrum en stel vervolgens uw proeflabomgeving van Microsoft 365 Defender in
keywords: Microsoft Threat Protection trial setup, Microsoft Threat Protection pilot setup, try Microsoft Threat Protection, Microsoft Threat Protection evaluation lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 976f6a1ec010348e8a281c251064acdd7a26748b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059630"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Uw proeflabomgeving voor Microsoft 365 Defender instellen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender 


Het maken van een proeflaboratorium of testomgeving van Microsoft 365 Defender en de implementatie ervan is een proces in drie fasen:

|[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fase 1: Voorbereiden](prepare-m365d-eval.md) |![Fase 2: Instellen](../../media/phase-diagrams/setup.png)<br/>Fase 2: Instellen |[![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fase 3: Onboard](config-m365d-eval.md) | [![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Terug naar pilot playbook](m365d-pilot.md) |
|--|--|--|--|
||*U bent er!*  | | |


U bent momenteel in de set-upfase. Neem de eerste stappen om toegang te krijgen tot het Microsoft 365-beveiligingscentrum en stel vervolgens uw proeflaboratorium of testomgeving in.

Meld u aan voor een Office 365- of Azure Active *Directory-abonnement* om een .onmicrosoft.com-tenant te genereren die u kunt gebruiken om u aan te melden voor uw Microsoft 365 E5-licentie. 

>[!NOTE]
>Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, kunt u de proefversie of proefversie van Office 365 E5 overslaan.

In deze fase wordt u begeleid naar:
- Een proefversie van Office 365 E5 maken
- Proefabonnement op Microsoft 365 inschakelen


## <a name="create-an-office-365-e5-trial-tenant"></a>Een proefversie van Office 365 E5 maken
>[!NOTE]
>Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van proefversies van Office 365 E5 overslaan.

1. Ga naar de [Office 365 E5-productportal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **Gratis proefabonnement.**

   ![Gratis of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. Voltooi de proefregistratie door uw e-mailadres (persoonlijk of zakelijk) in te vullen. Klik **op Account instellen.**

   ![Installatiepagina of_Office 365 E5-proefregistratie](../../media/mtp-eval-10.png)

3. Vul uw voornaam, achternaam, zakelijke telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.  

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waarin wordt gevraagd om naam, telefoon en bedrijfsgegevens](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Het land of de regio die u hier hebt ingesteld, bepaalt de datacenterregio waar uw Office 365 wordt gehost.
  
4. Kies uw verificatievoorkeur: via een sms-bericht of oproep. Klik **op Verificatiecode verzenden.** 

   ![Installatiepagina of_Office 365 E5-proefregistratie waarin wordt gevraagd om verificatievoorkeur](../../media/mtp-eval-12.png)

5. Stel de aangepaste domeinnaam in voor uw tenant en klik vervolgens op **Volgende.**

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waar u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)
 
6. Stel de eerste identiteit in, die een globale beheerder voor de tenant is. Vul Naam **en** **wachtwoord in.** Klik **op Registreren**.

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waar u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)

7. Klik **op Ga naar Setup om** de inrichting van de proefversie van Office 365 E5 te voltooien.

   ![Afbeelding van de installatiepagina voor proefregistratie van Office 365 E5 met de vraag of u op de knop Installatie starten wilt klikken](../../media/mtp-eval-15.png)

8. Verbind uw bedrijfsdomein met de Office 365-tenant. [Optioneel] Kies **Verbinding maken met een domein dat u al hebt** en typ uw domeinnaam. Klik op **Volgende**.

   ![Afbeelding of_Office 365 E5 Setup-pagina waar u uw aanmelding en e-mail moet personaliseren](../../media/mtp-eval-16.png)
 
9. Voeg een TXT- of MX-record toe om het domeineigenschap te valideren. Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren.**

   ![Afbeelding of_Office 365 E5-installatiepagina waar u een TXT of MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png)
 
10. [Optioneel] Maak meer gebruikersaccounts voor uw tenant. U kunt deze stap overslaan door op Volgende te **klikken.**

    ![Afbeelding of_Office 365 E5-installatiepagina waar u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)
 
11. [Optioneel] Office-apps downloaden. Klik **op Volgende** om deze stap over te slaan. 

    ![Afbeelding of_Office 365 E5-pagina waar u uw Office-apps kunt installeren](../../media/mtp-eval-19.png)

12. [Optioneel] E-mailberichten migreren. Nogmaals, u kunt deze stap overslaan.

    ![Afbeelding of_Office 365 E5 waar u kunt instellen of u e-mailberichten wilt migreren of niet](../../media/mtp-eval-20.png)
 
13. Kies onlineservices. Selecteer **Exchange** en klik op **Volgende.** 

    ![Afbeelding of_Office 365 E5 waar u uw onlineservices kunt kiezen](../../media/mtp-eval-21.png)

14. Voeg MX-, CNAME- en TXT-records toe aan uw domein. Wanneer u klaar is, selecteert u **Verifiëren.**

    ![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)
 
15. Gefeliciteerd, u hebt de inrichting van uw Office 365-tenant voltooid.

    ![Bevestigingspagina of_Office installatie van 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Proefabonnement op Microsoft 365 inschakelen

>[!NOTE]
>Als u zich aanmeldt voor een proefabonnement, krijgt u 25 gebruikerslicenties voor een maand. Zie [Een M365-abonnement](../../commerce/try-or-buy-microsoft-365.md) proberen of kopen voor meer informatie.

1. Klik [in het Microsoft 365-beheercentrum](https://admin.microsoft.com/)op **Facturering** en ga naar **Services aanschaffen.**

2. Selecteer **Microsoft 365 E5 en** klik op Gratis **proefabonnement starten.** 

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten](../../media/mtp-eval-24.png)

3. Kies uw verificatievoorkeur: via een sms-bericht of oproep. Nadat u hebt besloten, voert u het telefoonnummer in, selecteert u **Mij sms'en** of **Mij bellen,** afhankelijk van uw selectie.

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten met vragen om contactgegevens om code te verzenden om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)
 
4. Voer de verificatiecode in en klik **op Uw gratis proefabonnement starten.**

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversiepagina waar u verificatiecode kunt invullen die het systeem heeft verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)

5. Klik **op Nu proberen** om uw proefversie van Microsoft 365 E5 te bevestigen.

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversiepagina waar u de knop Nu proberen moet kloken om te beginnen](../../media/mtp-eval-27.png)
 
6. Ga naar het **Microsoft 365-beheercentrum**  >  **Gebruikers Actieve**  >  **gebruikers**. Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren** en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5.** Klik op **Opslaan**.

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u Microsoft 365 E5-licentie kunt selecteren](../../media/mtp-eval-28.png)
 
7. Selecteer nogmaals het globale beheerdersaccount en klik **op Gebruikersnaam beheren.**

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u Account kunt selecteren en vervolgens Gebruikersnaam beheren](../../media/mtp-eval-29.png)

8. [Optioneel] Wijzig het domein van *onmicrosoft.com* in uw eigen domein, afhankelijk van wat u hebt gekozen in de vorige stappen. Klik op **Wijzigingen opslaan**.

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u uw domeinvoorkeur kunt wijzigen](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Volgende stap
|[Fase 3: Configureren & Onboard](config-m365d-eval.md) | Configureer elke Microsoft 365 Defender-pijler voor uw proeflaboratorium of testomgeving van Microsoft 365 Defender en gebruik uw eindpunten.
|:-------|:-----|
