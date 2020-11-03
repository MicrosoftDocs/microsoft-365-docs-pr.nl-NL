---
title: Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving instellen
description: Ga vervolgens naar Microsoft 365-Beveiligingscentrum en stel uw Microsoft 365 Defender-omgeving voor proef Lab in.
keywords: Instellingen voor Microsoft Threat Protection-proefabonnement, Microsoft Threat Protection voor de proefversie, Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab instellen
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844822"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Uw Microsoft 365-proef omgeving voor Lab instellen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender 


U maakt een Microsoft 365-proefabonnement voor proef omgevingen of pilot omgevingen en de implementatie ervan is een proces van drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Uw Microsoft 365 Defender-evaluatie lab of prototypeomgeving voorbereiden" />
      <br/>Fase 1: voorbereiding </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving instellen" />
      <br/>Fase 2: instellen </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Elke Microsoft 365 voor Microsoft Defender-pijler configureren voor uw proefabonnement voor Microsoft 365 Defender of een proef omgeving" />
      <br/>Fase 3: & onboard configureren </a><br>
</td>


  </tr>
</table>

U bevindt zich momenteel in de configuratiefase. Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum en vervolgens uw proefabonnement of pilot omgeving in te stellen.

Registreer u voor een Office 365-of Azure Active Directory-abonnement om een *. onmicrosoft.com* -Tenant te genereren die u kunt gebruiken om zich aan te melden voor uw microsoft 365 E5-licentie. 

>[!NOTE]
>Als u al een bestaand abonnement voor Office 365 of Azure Active Directory hebt, kunt u de stappen voor het maken van een proefversie van Office 365 E5 overslaan.

In deze fase wordt u begeleid bij het volgende:
- Een Office 365 E5-proef Tenant maken
- Microsoft 365-proefabonnement inschakelen


## <a name="create-an-office-365-e5-trial-tenant"></a>Een Office 365 E5-proef Tenant maken
>[!NOTE]
>Als u al een bestaand Office 365-of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van de proefversie van Office 365 E5 overslaan.

1. Ga naar de [Office 365 E5-product Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **gratis proefversie**.

   ![Gratis proef pagina voor afbeelding of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. Voltooi de registratie van het proefabonnement door uw e-mailadres (persoonlijk of zakelijk) in te voeren. Klik op **account instellen**.

   ![Installatiepagina voor het instellen van of_Office 365 E5 proef registratie](../../media/mtp-eval-10.png)

3. Vul uw voornaam, achternaam, zakelijk telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.  

   ![Afbeelding of_Office 365 E5-registratiepagina voor het instellen van een naam, telefoon en bedrijf vragen](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > In het land of de regio die u hebt ingesteld, wordt het datacenter regio weergegeven waarop uw Office 365 wordt gehost.
  
4. Kies uw verificatie voorkeur: via een SMS-bericht of-oproep. Klik op **verificatie code verzenden**. 

   ![Voor of_Office beeld van een pagina voor het instellen van een proefabonnement voor 365 E5 voor de verificatie](../../media/mtp-eval-12.png)

5. Stel de aangepaste domeinnaam voor de Tenant in en klik op **volgende**.

   ![Voorbeeld van een pagina voor het instellen van een proefabonnement op of_Office 365 E5 waarop u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)
 
6. U kunt de eerste identiteit instellen, wat een globale beheerder voor de Tenant wordt. Voer **naam** en **wachtwoord** in. Klik op **Aanmelden**.

   ![Voorbeeld van een pagina voor het instellen van een proefabonnement op of_Office 365 E5 waarop u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)

7. Klik op **Ga naar Setup** om de inlevering van de Office 365 E5-proefversie te voltooien.

   ![Afbeelding van het instellen van de proef instelling voor het registreren van Office 365 E5 u vragen om te klikken op de knop Ga naar instellen](../../media/mtp-eval-15.png)

8. Verbind uw bedrijfsdomein met de Office 365-Tenant. Option Kies **al uw eigen domein verbinden** en typ uw domeinnaam. Klik op **Volgende**.

   ![Installatiepagina voor afbeelding of_Office 365 E5 waarop u uw aanmeldings-en e-mailadres aan uw persoonlijke voorkeur kunt aanpassen](../../media/mtp-eval-16.png)
 
9. Een TXT-of MX-record toevoegen om de eigendom van het domein te valideren. Wanneer u de TXT-of MX-record aan uw domein hebt toegevoegd, selecteert u **verifiëren**.

   ![Installatiepagina voor afbeelding of_Office 365 E5 waarop u een TXT of MX-record moet toevoegen om uw domein te bevestigen](../../media/mtp-eval-17.png)
 
10. Option Maak meer gebruikersaccounts voor uw Tenant. U kunt deze stap overslaan door te klikken op **volgende**.

    ![Installatiepagina van of_Office 365 E5 waarop u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)
 
11. Option Download Office-apps. Klik op **volgende** om deze stap over te slaan. 

    ![Pagina of_Office 365 E5 waarop u uw Office-apps kunt installeren](../../media/mtp-eval-19.png)

12. Option E-mailberichten migreren. U kunt deze stap overslaan.

    ![Afbeelding of_Office 365 E5 waarop u kunt instellen of u e-mailberichten wilt migreren](../../media/mtp-eval-20.png)
 
13. Kies Online Services. Selecteer **Exchange** en klik op **volgende**. 

    ![Afbeelding of_Office 365 E5 waar u uw Online Services kunt kiezen](../../media/mtp-eval-21.png)

14. MX-, CNAME-en TXT-records toevoegen aan uw domein. Wanneer u klaar bent, selecteert u **verifiëren**.

    ![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)
 
15. Gefeliciteerd, u hebt het inrichten voor de Office 365-Tenant voltooid.

    ![Afbeelding of_Office 365 E5-bevestigingspagina voor de voltooiing van instellingen](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365-proefabonnement inschakelen

>[!NOTE]
>Als u zich aanmeldt voor een proefversie, geeft u 25 gebruikerslicenties voor een maand te gebruiken. Zie [een M365-abonnement uitproberen of kopen](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.

1. Klik in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/)op **facturering** en ga vervolgens naar **Services aanschaffen**.

2. Selecteer **Microsoft 365 E5** en klik op **gratis proefversie starten**. 

   ![Afbeelding of_Microsoft 365 E5 gratis proefversie starten](../../media/mtp-eval-24.png)

3. Kies uw verificatie voorkeur: via een SMS-bericht of-oproep. Als u hebt besloten, voert u het telefoonnummer in en selecteert u de **tekst mij** of **Bel mij** afhankelijk van uw selectie.

   ![Afbeelding of_Microsoft 365 E5 de gratis proef pagina voor het starten van een proefabonnement voor contactgegevens om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)
 
4. Voer de verificatiecode in en klik op **Start uw gratis proefperiode**.

   ![Afbeelding of_Microsoft 365 E5-proef pagina voor het starten van een gratis proefperiode waarop u verificatiecode kunt invullen waarbij het systeem wordt verzonden om bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)

5. Klik op **nu proberen** om uw microsoft 365 E5-proefabonnement te bevestigen.

   ![Afbeelding of_Microsoft 365 E5 start de pagina gratis proefperiode waarop u de knop nu starten moet klokken om te beginnen](../../media/mtp-eval-27.png)
 
6. Ga naar de gebruikers van het **Microsoft 365-Beheercentrum**  >  **Users**  >  **Active users**. Selecteer uw gebruikersaccount, selecteer **productlicenties beheren** en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5**. Klik op **Opslaan**.

   ![Afbeelding of_Microsoft pagina van het Beheercentrum van 365, waarop u Microsoft 365 E5-licentie kunt selecteren](../../media/mtp-eval-28.png)
 
7. Selecteer opnieuw het account van de globale beheerder en klik op **gebruikersnaam beheren**.

   ![Afbeelding of_Microsoft pagina van het Beheercentrum van 365, waarop u account kunt selecteren en vervolgens gebruikersnaam kunt beheren](../../media/mtp-eval-29.png)

8. Option Wijzig het domein in *onmicrosoft.com* in uw eigen domein, afhankelijk van de optie die u in de vorige stappen hebt gekozen. Klik op **Wijzigingen opslaan**.

   ![Afbeelding of_Microsoft pagina van het Beheercentrum van 365, waarop u de voorkeuren van uw domein kunt wijzigen](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Volgende stap
|![Fase 3: & onboard configureren](../../media/config-onboard.png) <br>[Fase 3: & onboard configureren](config-mtpeval.md) | Configureer elke Microsoft 365 Defender-pijler voor uw proefabonnement voor Microsoft 365 voor de proefversie of een proef omgeving, en haal uw eindpunten over.
|:-------|:-----|
