---
title: Uw proefversie van Microsoft Threat Protection voorbereiden
description: Voorbereiden van de handtekening van belanghebbenden, tijdlijnen, omgevingsoverwegingen en adoptievolgorde bij het instellen van uw microsoft threat protection-proeflabomgeving
keywords: MTP-proefvoorbereiding, implementeren, voorbereiden, stakeholder, tijdlijn, omgeving, eindpunt, server, beheer, adoptie
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
ms.openlocfilehash: da0fd99aaa533c6e4f65b5b279adcd9a4b648c9c
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049625"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-environment"></a>Uw proefversie van Microsoft Threat Protection voorbereiden

**Geldt voor:**
- Microsoft Threat Protection

Het maken van een Microsoft Threat Protection trial lab omgeving en het implementeren ervan is een proces in drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw proefversie van Microsoft Threat Protection voorbereiden" />
      <br/>Fase 1: Voorbereiden</a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw proefversie van Microsoft Threat Protection instellen" />
      <br/>Fase 2: Setup</a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="Elke Microsoft Threat Protection-pijler configureren en aan boord van uw eindpunten" />
      <br/>Fase 3: & configureren</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

Je zit momenteel in de voorbereidingsfase.


Voorbereiding is de sleutel tot een succesvolle implementatie. In deze sectie wordt u doorgeleid naar wat u moet overwegen bij het maken van een proeflabomgeving voor uw Microsoft Threat Protection-implementatie.

## <a name="prerequisites"></a>Vereisten
Meer informatie over de vereisten voor licenties, hardware en software en andere configuratie-instellingen voor het inrichten en gebruiken van Microsoft Threat Protection. Zie de minimumvereisten voor [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide), Microsoft Defender [ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), Azure [ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), Microsoft Cloud [App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Belanghebbenden en afmelding
Het volgende gedeelte dient om alle belanghebbenden te identificeren die betrokken zijn bij het project en die mogelijk moeten ondertekenen, beoordelen of op de hoogte blijven, zelfs voor een evaluatie of een proof of concept dry-run.

>[!NOTE]
>Niet alle organisaties hebben mogelijk de volwassenheid van de beveiligingsorganisatie om dergelijke rollen te hebben. In dat geval u overleggen met uw leiderschapsteam over beoordeling en goedkeuringsverantwoordelijkheden.

Voeg belanghebbenden toe aan de onderstaande tabel, indien van toepassing op uw organisatie.

-   SO = Aanmelden voor dit project

-   R = Dit project bekijken en input leveren

-   I = Op de hoogte van dit project

| Name                 | Rol                                                                                                                                                                                                          | Actie |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Naam en e-mail invoeren | **Chief Information Security Officer (CISO)** *Een executive vertegenwoordiger die fungeert als sponsor binnen de organisatie voor de nieuwe technologie inzet.*                                                  | Dus     |
| Naam en e-mail invoeren | **Hoofd van Cyber Defense Operations Center (CDOC)** *Een vertegenwoordiger van het CDOC-team dat bepaalt hoe deze verandering is afgestemd op de processen in het beveiligingsteam van klanten.*       | Dus     |
| Naam en e-mail invoeren | **Security Architect** *Een vertegenwoordiger van het Security team dat bepaalt hoe deze verandering is afgestemd op de kern Security architectuur in de organisatie.*                         | R      |
| Naam en e-mail invoeren | **Workplace Architect** *Een vertegenwoordiger van het IT-team dat bepaalt hoe deze verandering is afgestemd op de kernwerkplekarchitectuur in de organisatie.*                             | R      |
| Naam en e-mail invoeren | **Security Analyst** *Een vertegenwoordiger van het CDOC-team die input kan leveren over de detectiemogelijkheden, gebruikerservaring en het algehele nut van deze wijziging vanuit het oogpunt van beveiligingsactiviteiten.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Uw Azure Active Directory voorbereiden
Sla deze stap over als u synchronisatie tussen Active Directory en Azure Active Directory on-premises al hebt ingeschakeld. Bekijk bestaande best practices-documentatie vanuit Azure Active Directory. De volgende stappen zijn geoptimaliseerd om Microsoft Threat Protection te evalueren.

1. Ga naar de [Azure Active Directory-portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD Connect**. 
![Afbeelding van azure Active Directory-portalpagina](../../media/mtp-eval-1.png) <br> 

2. Klik **op Downloaden** van Microsoft Azure Active Directory **Connect** en zet deze over naar uw domeincontroller.
![Afbeelding van de downloadpagina van Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. Volg op de domeincontroller de wizard Azure Active Directory Connect. Lees de licentievoorwaarden en privacyverklaring en schakel het selectievakje in als u hiermee akkoord gaat. Klik op **Continue**.
![Afbeelding van de welkomstpagina van Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Navigeer naar **Expresinstellingen**.
![Afbeelding van de pagina Expresinstellingen](../../media/mtp-eval-4.png) <br>

5. Voer uw globale beheerdersreferenties in. Klik op **Volgende**.
![Afbeelding van de PAGINA Verbinding maken met Azure AD waar u de referenties van uw globale beheerder moet invoeren](../../media/mtp-eval-5.png) <br>

6. Voer de referenties van de bedrijfsbeheerder van Active Directory Domain Services in. Klik op **Volgende**.
![Afbeelding van de pagina Verbinding maken met AD DS waar u uw referenties moet invoeren](../../media/mtp-eval-6.png) <br>

7. Klik **op Installeren** om de configuratie te bevestigen.
![Afbeelding van de bevestigingspagina van de configuratie](../../media/mtp-eval-7.png) <br>

8. Gefeliciteerd, u hebt Azure Active Directory Connect geconfigureerd.
![Afbeelding van een met succes geconfigureerde Azure Active Directory Connect-pagina](../../media/mtp-eval-8.png) <br>

U nu [gebruikers en groepen toevoegen aan Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) en een [SAM-R-beleid configureren.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Configuratievolgorde
De onderstaande tabel geeft de volgorde aan die Microsoft aanbeveelt voor het configureren van de Microsoft Threat Protection-componenten voor de implementatie van uw proeflabomgeving.

| Component                               | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Configuratievolgorderang |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 Advanced Threat Protection| Office 365 ATP beschermt uw organisatie tegen schadelijke bedreigingen van e-mailberichten, koppelingen en samenwerkingstools. <br> [Meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1                   |
|Azure Advanced Threat Protection|Azure ATP gebruikt Active Directory-signalen om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insideracties gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. <br> [Meer informatie](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security is een Cloud Access Security Broker (CASB) die op meerdere clouds werkt. Het biedt een rijke zichtbaarheid, controle over gegevensreizen en geavanceerde analyses om cyberbedreigingen in al uw cloudservices te identificeren en te bestrijden. <br> [Meer informatie](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender Advanced Threat Protection | Microsoft Defender ATP-eindpuntdetectie- en -reactiemogelijkheden bieden geavanceerde aanvalsdetecties die bijna realtime en bruikbaar zijn. Beveiligingsanalisten kunnen waarschuwingen effectief prioriteren, inzicht krijgen in het volledige bereik van een inbreuk en reactieacties ondernemen om bedreigingen te verwerkeren. <br> [Meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Volgende stap
|||
|:-------|:-----|
|![Fase 2: Setup](../../media/setup.png) <br>[Fase 2: Setup](setup-mtpeval.md) | Uw proefversie van Microsoft Threat Protection instellen

