---
title: Uw testlaboratorium Microsoft 365 Defender testomgeving instellen
description: Access Microsoft 365 Beveiligingscentrum en stel vervolgens uw Microsoft 365 Defender proeflaboratorium in
keywords: Microsoft 365 Defender proeffase instellen, Microsoft 365 Defender proefinstallatie, Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium instellen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454731"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>Uw proefversie Microsoft 365 Defender in een labomgeving instellen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender 

In dit onderwerp wordt u begeleid bij het instellen van een speciale labomgeving. Zie de nieuwe handleiding Evalueren en Microsoft 365 Defender voor informatie over het instellen van [een proefversie in productie.](eval-overview.md) 

## <a name="create-an-office-365-e5-trial-tenant"></a>Een proef tenant Office 365 E5 maken
>[!NOTE]
>Als u al een bestaand abonnement Office 365 of Azure Active Directory hebt, kunt u de stappen voor het maken Office 365 E5 proefversie van tenants overslaan.

1. Ga naar de [Office 365 E5 productportal en](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) selecteer **Gratis proefabonnement.**

   ![Gratis of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. Voltooi de proefregistratie door uw e-mailadres (persoonlijk of zakelijk) in te vullen. Klik **op Account instellen.**

   ![Installatiepagina of_Office 365 E5-proefregistratie](../../media/mtp-eval-10.png)

3. Vul uw voornaam, achternaam, zakelijke telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.  

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waarin wordt gevraagd om naam, telefoon en bedrijfsgegevens](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Het land of de regio die u hier hebt ingesteld, bepaalt de datacenterregio waar Office 365 wordt gehost.
  
4. Kies uw verificatievoorkeur: via een sms-bericht of oproep. Klik **op Verificatiecode verzenden.** 

   ![Installatiepagina of_Office 365 E5-proefregistratie waarin wordt gevraagd om verificatievoorkeur](../../media/mtp-eval-12.png)

5. Stel de aangepaste domeinnaam in voor uw tenant en klik vervolgens op **Volgende.**

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waar u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)
 
6. Stel de eerste identiteit in, die een globale beheerder voor de tenant is. Vul Naam **en** **wachtwoord in.** Klik op **Registeren**.

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waar u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)

7. Klik **op Ga naar Setup om** de proefversie van Office 365 E5 te voltooien.

   ![Afbeelding van Office 365 E5 registratiepagina voor proefversies met de vraag of u op de knop Instellen gaan wilt klikken](../../media/mtp-eval-15.png)

8. Verbinding maken uw bedrijfsdomein aan de Office 365 tenant. [Optioneel] Kies **Verbinding maken domein dat u al hebt en** typ uw domeinnaam. Klik op **Volgende**.

   ![Afbeelding of_Office 365 E5 Setup-pagina waar u uw aanmelding en e-mail moet personaliseren](../../media/mtp-eval-16.png)
 
9. Voeg een TXT- of MX-record toe om het domeineigenschap te valideren. Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren.**

   ![Afbeelding of_Office 365 E5-installatiepagina waar u een TXT of MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png)
 
10. [Optioneel] Maak meer gebruikersaccounts voor uw tenant. U kunt deze stap overslaan door op Volgende te **klikken.**

    ![Afbeelding of_Office 365 E5-installatiepagina waar u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)
 
11. [Optioneel] Download Office apps. Klik **op Volgende** om deze stap over te slaan. 

    ![Afbeelding of_Office 365 E5-pagina waar u uw apps Office installeren](../../media/mtp-eval-19.png)

12. [Optioneel] E-mailberichten migreren. Nogmaals, u kunt deze stap overslaan.

    ![Afbeelding of_Office 365 E5 waar u kunt instellen of u e-mailberichten wilt migreren of niet](../../media/mtp-eval-20.png)
 
13. Kies onlineservices. Selecteer **Exchange** en klik op **Volgende.** 

    ![Afbeelding of_Office 365 E5 waar u uw onlineservices kunt kiezen](../../media/mtp-eval-21.png)

14. Voeg MX-, CNAME- en TXT-records toe aan uw domein. Wanneer u klaar is, selecteert u **Verifiëren.**

    ![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)
 
15. Gefeliciteerd, u hebt de inrichting van uw Office 365 voltooid.

    ![Bevestigingspagina of_Office installatie van 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Proefabonnement Microsoft 365 inschakelen

>[!NOTE]
>Als u zich aanmeldt voor een proefabonnement, krijgt u 25 gebruikerslicenties voor een maand. Zie [Een M365-abonnement](../../commerce/try-or-buy-microsoft-365.md) proberen of kopen voor meer informatie.

1. Klik [Microsoft 365-beheer in Microsoft 365-beheer](https://admin.microsoft.com/) **op Facturering** en ga naar Services **aanschaffen.**

2. Selecteer **Microsoft 365 E5** en klik op **Gratis proefabonnement starten.** 

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten](../../media/mtp-eval-24.png)

3. Kies uw verificatievoorkeur: via een sms-bericht of oproep. Nadat u hebt besloten, voert u het telefoonnummer in, selecteert u **Mij sms'en** of **Mij bellen,** afhankelijk van uw selectie.

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten met vragen om contactgegevens om code te verzenden om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)
 
4. Voer de verificatiecode in en klik **op Uw gratis proefabonnement starten.**

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversiepagina waar u verificatiecode kunt invullen die het systeem heeft verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)

5. Klik **op Nu proberen** om uw proefabonnement Microsoft 365 E5 bevestigen.

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversiepagina waar u de knop Nu proberen moet kloken om te beginnen](../../media/mtp-eval-27.png)
 
6. Ga naar het **Microsoft 365-beheer Center**  >  **Users Active**  >  **Users**. Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren** en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5.** Klik op **Opslaan**.

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u een licentie Microsoft 365 E5 selecteren](../../media/mtp-eval-28.png)
 
7. Selecteer nogmaals het globale beheerdersaccount en klik **op Gebruikersnaam beheren.**

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u Account kunt selecteren en vervolgens Gebruikersnaam beheren](../../media/mtp-eval-29.png)

8. [Optioneel] Wijzig het domein van *onmicrosoft.com* in uw eigen domein, afhankelijk van wat u hebt gekozen in de vorige stappen. Klik op **Wijzigingen opslaan**.

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u uw domeinvoorkeur kunt wijzigen](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Volgende stap
|[Fase 3: Configureren & Onboard](config-m365d-eval.md) | Configureer elke Microsoft 365 Defender voor uw Microsoft 365 Defender proeflaboratorium of testomgeving en aan boord van uw eindpunten.
|:-------|:-----|
