---
title: 'Stap 6: E-mailversleuteling configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Begrijpen en configureren van beheer van privileged access voor Office 365.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809155"
---
# <a name="step-6-configure-email-encryption"></a>Stap 6: E-mailversleuteling configureren

*Deze stap is optioneel en geldt voor zowel de E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 6: Informatiebescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Er zijn drie soorten e-mailversleuteling in Microsoft 365.

|||
|:-------|:-----|
| Office Message Encryption (OME) | Versleuteling voor Exchange Online-e-mail die buiten uw organisatie wordt verzonden. |
| Information Rights Management (IRM) | Versleuteling en machtigingen die met de e-mail reizen. |
| Beveiligde/multifunctionele internetmailextensies (S/MIME) | E-mailbeveiliging met versleuteling en digitale handtekeningen. |
|||

## <a name="office-365-message-encryption"></a>Versleuteling van Office 365-berichten

Met OME kan uw organisatie versleutelde e-mailberichten verzenden en ontvangen tussen mensen binnen en buiten uw organisatie. OME werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. Versleuteling van e-mailberichten zorgt ervoor dat alleen beoogde ontvangers het bericht kunnen bekijken.

![OME-versleuteling van e-mailberichten](../media/infoprotect-email-encryption/ome-encryption.png)

U stelt transportregels in die de voorwaarden voor versleuteling definiëren. Wanneer een gebruiker een bericht verzendt dat overeenkomt met een regel, wordt versleuteling automatisch toegepast.

Als ontvangers versleutelde berichten willen weergeven, kunnen ze een eenmalige toegangscode krijgen, zich aanmelden met een Microsoft-account of zich aanmelden met een werk- of schoolaccount dat is gekoppeld aan Microsoft 365. Ontvangers kunnen ook versleutelde antwoorden verzenden. Ze hebben hun eigen Microsoft 365-abonnement niet nodig om versleutelde berichten te bekijken of versleutelde antwoorden te verzenden.

Zie [Office 365-berichtversleuteling](https://docs.microsoft.com/Office365/SecurityCompliance/ome)voor meer informatie.

## <a name="irm"></a>Irm

IRM in Microsoft 365 helpt u uw gegevens te beveiligen met extra versleuteling en door een intelligent beleid toe te passen dat aangeeft wie toegang heeft tot wat ze kunnen doen. Voor e-mailberichten u IRM gebruiken voor versleuteling en gebruiksbeperkingen toepassen. U bijvoorbeeld opgeven dat sommige ontvangers alle mogelijkheden hebben om de e-mail te beheren en dat sommige niet de mogelijkheid hebben om de e-mail af te drukken of door te sturen. 

IRM-beleid is geconfigureerd in Microsoft 365 en kan van toepassing zijn op documenten in SharePoint Online en e-mailberichten. Een iRM-beveiligde e-mail bevat de toegepaste beleidsinstellingen die zijn toegepast en waarmee u ermee reist. 

![IRM-bescherming van e-mailberichten](../media/infoprotect-email-encryption/irm-protection.png)

Wanneer de ontvanger de e-mail opent met het opgenomen beleid, worden de beleidsinstellingen gebruikt om het bericht te decoderen en te bepalen wat de ontvanger ermee kan doen. 

Zie [Informatierechtenbeheer in Exchange Online voor]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)meer informatie.

## <a name="smime"></a>S/MIME

S/MIME is een op digitale certificaten gebaseerde e-mailgebaseerde beveiligingsoplossing waarmee u zowel een bericht versleutelen als digitaal ondertekenen. De berichtversleuteling zorgt ervoor dat alleen de beoogde ontvanger het bericht kan openen en lezen. Een digitale handtekening helpt de ontvanger de identiteit van de afzender te valideren en te bepalen dat alleen de afzender deze heeft verzonden.

![S/MIME bescherming van e-mailberichten](../media/infoprotect-email-encryption/smime-protection.png)

S/MIME kan worden gebruikt voor e-mail naar andere postvakken in uw Microsoft 365-abonnement of naar externe gebruikers.
Zowel berichtversleuteling als digitale handtekeningen worden mogelijk gemaakt door het gebruik van digitale certificaten die de openbare en private sleutels bevatten voor het versleutelen of decoderen van berichten en het maken en verifiëren van digitale handtekeningen.
Als u S/MIME wilt gebruiken, moet u de openbare sleutels voor elke ontvanger hebben. Ontvangers onderhouden hun eigen privésleutels, die veilig moeten blijven. Als uw privésleutel is gecompromitteerd, moet u een nieuw digitaal certificaat krijgen en openbare sleutels herverdelen naar alle potentiële afzenders.

Zie [S/MIME voor het ondertekenen en versleutelen](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)van berichten voor meer informatie.


Zie als tussencontrolepunt de [exitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) die overeenkomen met deze stap.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 7](../media/stepnumbers/Step7.png)|[Beheer van bevoegde toegang configureren voor Office 365](infoprotect-configure-privileged-access-management.md)|
