---
title: Spammeldingen voor eindgebruikers configureren in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: U spammeldingen van eindgebruikers configureren voor het standaardbeleid voor inhoudsbrede inhoudsfilter voor het hele standaardbedrijf of voor aangepast beleid voor inhoudsfilters dat op domeinen wordt toegepast.
ms.openlocfilehash: 6ac43ee3419e7b768312b6826994a5b8f5e4a231
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812430"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>Spammeldingen voor eindgebruikers configureren in EOP
  
> [!IMPORTANT]
> Dit onderwerp is voor zelfstandige klanten van Exchange Online Protection (EOP) die on-premises mailboxen beschermen. Exchange Online-klanten die door de cloud gehoste postvakken beschermen, moeten in plaats daarvan het volgende onderwerp lezen: [Spammeldingen](configure-end-user-spam-notifications-in-exchange-online.md)voor eindgebruikers configureren in Exchange Online . 
  
U spammeldingen van eindgebruikers configureren voor het standaardbeleid voor spamfilter voor het hele bedrijf of voor aangepast spamfilterbeleid. Als u spammeldingen van eindgebruikers inschakelt, kunnen uw gebruikers hun eigen spam-, bulk- en phishingberichten beheren. 
  
Spammeldingen van eindgebruikers bevatten een lijst met alle spamberichten die de eindgebruiker heeft ontvangen gedurende een periode die u configureert (u een waarde opgeven tussen 1 en 15 dagen). U ook de taal configureren waarin het meldingsbericht is geschreven.
  
Na ontvangst van een meldingsbericht kunnen eindgebruikers kiezen uit de volgende opties:

**Afzender blokkeren** als u wilt dat Office 365 de afzender toevoegt aan de lijst met geblokkeerde afzenders.

**Laat vrij** als het bericht geen spam is en u wilt dat Office 365 het bericht naar uw postvak verzendt.

**Controleer** of u naar de quarantaineportal in het Beveiligings- en Nalevingscentrum wilt navigeren als u andere acties wilt uitvoeren, zoals Voorbeeld of Release.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?
<a name="sectionSection0"> </a>

Geschatte tijd om te voltooien: 5 minuten
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie de vermelding 'Antispam' in het onderwerp [Functiemachtigingen in het eOP-onderwerp](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt. 
  
Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>De EAC gebruiken om spammeldingen van eindgebruikers te configureren

1. Navigeer in het Exchange Admin Center (EAC) naar**het spamfilter** **beveiliging** > .
    
2. Selecteer het inhoudsfilterbeleid waarvoor u spammeldingen van eindgebruikers wilt inschakelen (deze zijn standaard uitgeschakeld).
    
3. Klik in het rechterdeelvenster, waar de overzichtsgegevens over uw beleid worden weergegeven, op de koppeling **Spammeldingen voor** eindgebruikers configureren. 
    
4. In het volgende dialoogvenster u de volgende opties configureren:
    
1. **Spammeldingen** van eindgebruikers inschakelen Schakel dit selectievakje in om spammeldingen van eindgebruikers voor dit beleid in te schakelen. (Als dit beleid omgekeerd is ingeschakeld, u dit selectievakje uitschakelen om spammeldingen van eindgebruikers voor dit beleid uit te schakelen.) 
    
2. **Stuur elke (dagen) spammeldingen van eindgebruikers** Geef op hoe vaak spammeldingen van eindgebruikers moeten worden verzonden. De standaardinstelling is 3 dagen. U opgeven tussen 1 en 15 dagen. Als u bijvoorbeeld 7 dagen opgeeft, bevat de melding een lijst met alle berichten die in de afgelopen 7 dagen voor die gebruiker zijn bedoeld en die in plaats daarvan naar de spamquarantaine zijn verzonden. 
    
3. **Meldingstaal** Selecteer met de vervolgkeuzelijst de taal om spammeldingen van eindgebruikers voor dit beleid te schrijven. 
    
5. Klik **op Opslaan**. Een overzicht van de beleidsinstellingen van uw inhoudsfilter, inclusief de instellingen voor spammeldingen van uw eindgebruiker, wordt in het rechterdeelvenster weergegeven.
    
> [!NOTE]
>  Spammeldingen van eindgebruikers zijn alleen functioneel voor het beleid voor inhoudsfilter dat is ingeschakeld. > spammeldingen van eindgebruikers worden slechts één keer per dag verzonden. De levertijd van de melding kan niet worden gegarandeerd voor een specifieke klant en is niet configureerbaar. 
  
 **Tip:** Als u spammeldingen van eindgebruikers wilt testen door ze naar een beperkte groep gebruikers te sturen voordat u ze volledig implementeert, maakt u een aangepast inhoudsfilterbeleid waarmee spammeldingen van eindgebruikers kunnen worden uitgevoerd voor de domeinen waarin de gebruikers zich bevinden. Maak vervolgens in de EAC onder regels voor **de e-mailstroom \> **een e-mailstroomregel (ook wel een transportregel genoemd) om berichten te blokkeren vanaf quarantine@messaging.microsoft.com (het e-mailadres dat meldingen verzendt) met uitzonderingen voor de gebruikers die u de meldingen wilt ontvangen. De volgende afbeelding is een voorbeeld van het maken van een uitzondering voor twee gebruikers (SaraD en AlexD) van domein Contoso.com: 
  
![Transportregel om spammeldingen van eindgebruikers te testen](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Voor meer informatie

[Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)
  
