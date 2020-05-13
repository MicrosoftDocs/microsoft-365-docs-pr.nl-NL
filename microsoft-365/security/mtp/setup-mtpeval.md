---
title: Uw proefversie van Microsoft Threat Protection instellen
description: Toegang tot Microsoft 365 Security Center en stel vervolgens uw proefversie van Microsoft Threat Protection in
keywords: Microsoft Threat Protection trial setup, probeer Microsoft Threat Protection, Microsoft Threat Protection evaluatie lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 117681bd4722615e870594e46d6896e9128d0d0c
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209221"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Uw proefversie van Microsoft Threat Protection instellen 

**Geldt voor:**
- Microsoft Threat Protection 


Het maken van een Microsoft Threat Protection trial lab omgeving en het implementeren ervan is een proces in drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw Evaluatielab voor Microsoft Threat Protection voorbereiden" />
      <br/>Fase 1: Voorbereiden</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw Evaluatielab voor Microsoft Threat Protection instellen" />
      <br/>Fase 2: Setup</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-proeflabomgeving en aan boord van uw eindpunten" />
      <br/>Fase 3: & configureren</a><br>
</td>


  </tr>
</table>

U bevindt zich momenteel in de fase van de set-up. Voer de eerste stappen uit om toegang te krijgen tot Microsoft 365 Security Center en stel vervolgens uw proeflabomgeving in.

Meld u aan voor een Office 365- of Azure Active Directory-abonnement om een *.onmicrosoft.com* tenant te genereren waarmee u zich aanmelden voor uw Microsoft 365 E5-licentie. 

>[!NOTE]
>Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, u de stappen voor het maken van de proefversie van Office 365 E5 overslaan.

In deze fase wordt u begeleid naar:
- Een proefversietenant van Office 365 E5 maken
- Microsoft 365-proefabonnement inschakelen


## <a name="create-an-office-365-e5-trial-tenant"></a>Een proefversietenant van Office 365 E5 maken
>[!NOTE]
>Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, u de stappen voor het maken van de proefversie van Office 365 E5 overslaan.

1. Ga naar de [Productportal van Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **Gratis proefversie**.
![Afbeelding of_Office 365 E5 gratis proefpagina](../../media/mtp-eval-9.png) <br>
  
2. Voltooi de proefregistratie door uw e-mailadres (persoonlijk of zakelijk) in te voeren. Klik **op Account instellen**.
![Afbeelding of_Office 365 E5-installatiepagina voor proefregistratie](../../media/mtp-eval-10.png) <br> 

3. Vul uw voornaam, achternaam, zakelijk telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.  
<br>![Afbeelding of_Office 365 E5-installatiepagina voor proefregistratie met naam, telefoon en bedrijfsgegevens](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>Het land of de regio die u hier instelt, bepaalt de datacenterregio die uw Office 365 ontvangt.
  
4. Kies uw verificatievoorkeur: via een sms of oproep. Klik **op Verificatiecode verzenden**. 
![Afbeelding of_Office 365 E5-installatiepagina voor het instellen van proefaanvragen waarin om verificatievoorkeur wordt gevraagd](../../media/mtp-eval-12.png) <br>

5. Stel de aangepaste domeinnaam voor uw tenant in en klik op **Volgende**.
<br>![Afbeelding of_Office 365 E5-installatiepagina voor proefregistratie waar u uw aangepaste domeinnaam instellen](../../media/mtp-eval-13.png) <br>
 
6. Stel de eerste identiteit in die een globale beheerder voor de tenant zal zijn. **Naam** en **wachtwoord**invullen . Klik **op Aanmelden**.
![Pagina of_Office 365 E5-proefregistratie pagina waar u uw bedrijfsidentiteit instellen](../../media/mtp-eval-14.png) <br>

7. Klik **op Ga naar Setup** om de installatie van de Office 365 E5-proeftenant te voltooien.
<br>![Afbeelding van de installatiepagina voor het instellen van proefabonnementen in Office 365 E5 met de vraag om op de knop Setup gaan te klikken](../../media/mtp-eval-15.png) <br>

8. Verbind uw bedrijfsdomein met de Office 365-tenant. [Optioneel] Kies **Een domein verbinden dat u al bezit** en typ uw domeinnaam. Klik op **Volgende**.
<br>![Afbeelding of_Office 365 E5 Setup-pagina waar u uw aanmelding en e-mail moet personaliseren](../../media/mtp-eval-16.png) <br>
 
9. U moet een TXT- of MX-record toevoegen om het domeineigendom te valideren. Zodra u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren**.
<br>![Afbeelding of_Office 365 E5-installatiepagina waar u een TXT-mx-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png) <br>
 
10. [Optioneel] Maak meer gebruikersaccounts voor uw tenant. U deze stap overslaan door op **Volgende te**klikken.
![Image of_Office 365 E5 setup pagina waar u meer gebruikers toevoegen](../../media/mtp-eval-18.png) <br>
 
11. [Optioneel] Office-apps downloaden. Klik **op Volgende** om deze stap over te slaan. 
<br>![Afbeelding of_Office 365 E5-pagina waar u uw Office-apps installeren](../../media/mtp-eval-19.png) <br>

12. [Optioneel] E-mailberichten migreren. Nogmaals, u deze stap overslaan.
<br>![Afbeelding of_Office 365 E5, waar u instellen of u e-mailberichten wilt migreren of niet](../../media/mtp-eval-20.png) <br>
 
13. Kies online services. Selecteer **Exchange** en klik op **Volgende**. 
<br>![Afbeelding of_Office 365 E5 waar u uw online services kiezen, zoals Exchangem Skype voor Bedrijven of Mibile Device Management voor Office 365](../../media/mtp-eval-21.png) <br>

14. Voeg MX-, CNAME- en TXT-records toe aan uw domein. Wanneer u klaar bent, selecteert u **Verifiëren**.
<br>![Afbeelding of_Office 365 E5 hier u uw DNS-records toevoegen](../../media/mtp-eval-22.png) <br>
 
15. Gefeliciteerd, u hebt de inrichting van uw Office 365-tenant voltooid.
<br>![Afbeelding of_Office 365 E5-bevestigingspagina voor het voltooien van de installatie](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365-proefabonnement inschakelen

>[!NOTE]
>Als u zich aanmeldt voor een proefversie, u een maand lang 25 gebruikerslicenties gebruiken. Zie [Een M365-abonnement uitproberen of kopen](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.

1. Klik in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/)op **Facturering** en navigeer vervolgens naar **Services kopen**.

2. Selecteer **Microsoft 365 E5** en klik op **Gratis proefversie starten**. 
![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina](../../media/mtp-eval-24.png) <br>

3. Kies uw verificatievoorkeur: via een sms of oproep. Zodra u hebt besloten, voert u het telefoonnummer in, selecteert **u Tekst mij** of Bel **me** afhankelijk van uw selectie.
![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina vragen om contactgegevens om code te sturen om te bewijzen dat je geen robot bent](../../media/mtp-eval-25.png) <br>
 
4. Voer de verificatiecode in en klik op **Uw gratis proefversie starten**. 
<br>![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina waar u verificatiecode invullen die het systeem heeft verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png) <br>

5. Klik **op Nu proberen** om uw Proefversie van Microsoft 365 E5 te bevestigen.
<br>![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina waar je de knop Nu proberen moet klokken om te beginnen](../../media/mtp-eval-27.png) <br>
 
6. Ga naar de gebruikers van het **Microsoft 365-beheercentrum**  >  **Users**  >  **Actieve gebruikers**. Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren**en wissel de licentie vervolgens om van Office 365 E5 naar **Microsoft 365 E5**. Klik op **Opslaan**.
![Pagina Of_Microsoft 365-beheercentrum waar u Microsoft 365 E5-licentie selecteren](../../media/mtp-eval-28.png) <br>
 
7. Selecteer het globale beheerdersaccount opnieuw en klik op **Gebruikersnaam beheren**.
<br>![Pagina of_Microsoft 365-beheercentrum waar u Account selecteren en vervolgens gebruikersnaam beheren](../../media/mtp-eval-29.png) <br>

8. [Optioneel] Wijzig het domein van *onmicrosoft.com* naar uw eigen domein, afhankelijk van wat u in de vorige stappen hebt gekozen. Klik op **Wijzigingen opslaan**.
<br>![Pagina of_Microsoft 365-beheercentrum waar u de domeinvoorkeur wijzigen](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Volgende stap
||| |:-------|:-----|config-onboard.png) <br>[Fase 3: & aan boord configureren](config-mtpeval.md) | Configureer elke microsoft threat protection-pijler voor uw Microsoft Threat Protection-proeflabomgeving en aan boord van uw eindpunten.
