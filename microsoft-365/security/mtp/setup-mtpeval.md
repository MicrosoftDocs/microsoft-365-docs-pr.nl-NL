---
title: Uw Microsoft Threat Protection-proefomgeving instellen
description: Toegang tot Microsoft 365 Security Center en vervolgens uw Microsoft Threat Protection-proeflabomgeving instellen
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
ms.openlocfilehash: 6cba773d0c4bea259db151d5a8f1d8e03954a045
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717293"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Uw Microsoft Threat Protection-proefomgeving instellen 

**Van toepassing op:**
- Microsoft Threat Protection 


Het maken van een Microsoft Threat Protection-proeflabomgeving en het implementeren ervan is een proces in drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-evaluatielab voorbereiden" />
      <br/>Fase 1: Voorbereiden</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-evaluatielab instellen" />
      <br/>Fase 2: Setup</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-proeflabomgeving en aan boord van uw eindpunten" />
      <br/>Fase 3: & onboard configureren</a><br>
</td>


  </tr>
</table>

U bevindt zich momenteel in de opgezette fase. Neem de eerste stappen om toegang te krijgen tot Microsoft 365 Security Center en stel vervolgens uw proeflabomgeving in.

Meld u aan voor een Office 365- of Azure Active Directory-abonnement om een *.onmicrosoft.com* tenant te genereren waarmee u zich aanmelden voor uw Microsoft 365 E5-licentie. 

>[!NOTE]
>Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, u de stappen voor het maken van proef tenant voor Office 365 E5 overslaan.

In deze fase wordt u begeleid naar:
- Een proef tenant voor Office 365 E5 maken
- Microsoft 365-proefabonnement inschakelen


## <a name="create-an-office-365-e5-trial-tenant"></a>Een proef tenant voor Office 365 E5 maken
>[!NOTE]
>Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, u de stappen voor het maken van proef tenant voor Office 365 E5 overslaan.

1. Ga naar de [Office 365 E5-productportal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **Gratis proefversie**.
![Afbeelding of_Office gratis proefpagina 365 E5](../../media/mtp-eval-9.png) <br>
  
2. Voltooi de proefregistratie door uw e-mailadres (persoonlijk of zakelijk) in te voeren. Klik **op Account instellen**.
![Image of_Office 365 E5 trial registration setup pagina](../../media/mtp-eval-10.png) <br> 

3. Vul uw voornaam, achternaam, bedrijfstelefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.  
<br>![Afbeelding of_Office 365 E5-testregistratie-installatiepagina waarin wordt gevraagd om naam, telefoon en bedrijfsgegevens](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>Het land of de regio die u hier instelt, bepaalt de regio van het datacenter die uw Office 365 ontvangt.
  
4. Kies uw verificatievoorkeur: via een sms of oproep. Klik **op Verificatiecode verzenden**. 
![Image of_Office 365 E5 trial registration setup pagina vragen om verificatie voorkeur](../../media/mtp-eval-12.png) <br>

5. Stel de aangepaste domeinnaam in voor uw tenant en klik vervolgens op **Volgende**.
<br>![Afbeelding of_Office 365 E5-testregistratieregistratiepagina waar u uw aangepaste domeinnaam instellen](../../media/mtp-eval-13.png) <br>
 
6. Stel de eerste identiteit in die een globale beheerder voor de tenant zal zijn. Geef **naam** en **wachtwoord in**. Klik **op Aanmelden**.
![Afbeelding of_Office 365 E5-testregistratie-instellingspagina waar u uw bedrijfsidentiteit instellen](../../media/mtp-eval-14.png) <br>

7. Klik **op Ga naar Setup** om de inrichting van office 365 E5-proef tenanten te voltooien.
<br>![Afbeelding van de installatiepagina van office 365 E5-proefregistratie wordt gevraagd op de knop Installatie gaan te klikken](../../media/mtp-eval-15.png) <br>

8. Verbind uw bedrijfsdomein met de Office 365-tenant. [Optioneel] Kies **Een domein verbinden dat u al bezit** en typ uw domeinnaam. Klik op **Volgende**.
<br>![Afbeelding of_Office 365 E5 Setup-pagina waar u uw aanmelding en e-mail moet personaliseren](../../media/mtp-eval-16.png) <br>
 
9. U moet een TXT- of MX-record toevoegen om het domeineigendom te valideren. Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren**.
<br>![Afbeelding of_Office 365 E5-instellingspagina waar u een TXT MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png) <br>
 
10. [Optioneel] Maak meer gebruikersaccounts voor uw tenant. U deze stap overslaan door op **Volgende**te klikken.
![Afbeelding of_Office 365 E5-instellingspagina waar u meer gebruikers toevoegen](../../media/mtp-eval-18.png) <br>
 
11. [Optioneel] Office-apps downloaden. Klik **op Volgende** om deze stap over te slaan. 
<br>![Afbeelding of_Office 365 E5-pagina waar u uw Office-apps installeren](../../media/mtp-eval-19.png) <br>

12. [Optioneel] E-mailberichten migreren. Nogmaals, u deze stap overslaan.
<br>![Afbeelding of_Office 365 E5 waar u instellen of e-mailberichten moeten worden gemigreerd of niet](../../media/mtp-eval-20.png) <br>
 
13. Kies online services. Selecteer **Exchange** en klik op **Volgende**. 
<br>![Afbeelding of_Office 365 E5 waar u uw online diensten kiezen](../../media/mtp-eval-21.png) <br>

14. Voeg MX-, CNAME- en TXT-records toe aan uw domein. Selecteer **Verifiëren**wanneer u voltooid bent.
<br>![Afbeelding of_Office 365 E5 hier u uw DNS-records toevoegen](../../media/mtp-eval-22.png) <br>
 
15. Gefeliciteerd, u hebt de inrichting van uw Office 365-tenant voltooid.
<br>![Bevestigingspagina van image of_Office 365 E5 setup](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365-proefabonnement inschakelen

>[!NOTE]
>Als u zich aanmeldt voor een proefabonnement, u 25 gebruikerslicenties voor een maand gebruiken. Zie [Probeer of koop een M365-abonnement](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.

1. Klik in [microsoft 365-beheercentrum](https://admin.microsoft.com/)op **Facturering** en navigeer vervolgens naar **Services kopen**.

2. Selecteer **Microsoft 365 E5** en klik op **Gratis proefperiode starten.** 
![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten](../../media/mtp-eval-24.png) <br>

3. Kies uw verificatievoorkeur: via een sms of oproep. Zodra u hebt besloten, voert u het telefoonnummer in, selecteert u **Sms me** of **Bel mij** afhankelijk van uw selectie.
![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina vragen om contactgegevens om code te sturen om te bewijzen dat je geen robot bent](../../media/mtp-eval-25.png) <br>
 
4. Voer de verificatiecode in en klik op **Uw gratis proefperiode starten.** 
<br>![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina waar u verificatiecode invullen die het systeem heeft verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png) <br>

5. Klik **op Probeer nu** om uw Microsoft 365 E5-proefversie te bevestigen.
<br>![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten waar u de knop Nu proberen moet klokken om te beginnen](../../media/mtp-eval-27.png) <br>
 
6. Ga naar de gebruikers van **het Microsoft 365-beheercentrum**  >  **Users**  >  **Gebruikers Actieve gebruikers**. Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren**en wissel de licentie van Office 365 E5 naar **Microsoft 365 E5**. Klik op **Opslaan**.
![Afbeelding of_Microsoft pagina 365-beheercentrum waar u Microsoft 365 E5-licentie selecteren](../../media/mtp-eval-28.png) <br>
 
7. Selecteer het globale beheerdersaccount opnieuw en klik op **Gebruikersnaam beheren**.
<br>![Afbeelding of_Microsoft 365-pagina met beheercentrum waar u Account selecteren en vervolgens gebruikersnaam beheren](../../media/mtp-eval-29.png) <br>

8. [Optioneel] Wijzig het domein van *onmicrosoft.com* naar uw eigen domein, afhankelijk van wat u hebt gekozen in de vorige stappen. Klik op **Wijzigingen opslaan**.
<br>![Afbeelding of_Microsoft 365-pagina beheercentrum waar u uw domeinvoorkeur wijzigen](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Volgende stap
|||
|:-------|:-----|
|![Fase 3: & onboard configureren](../../media/config-onboard.png) <br>[Fase 3: & onboard configureren](config-mtpeval.md) | Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-evaluatielab en aan boord van uw eindpunten.
