---
title: Spammeldingen voor eindgebruikers configureren in Exchange Online
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
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: U spammeldingen voor eindgebruikers configureren voor het standaard beleid voor spamfilters voor het hele bedrijf of voor aangepaste spamfilterbeleidsregels die worden toegepast op domeinen.
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42810223"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Spammeldingen voor eindgebruikers configureren in Exchange Online

> [!IMPORTANT]
> Dit onderwerp is voor Exchange Online-klanten die postvakken die in de cloud worden gehost, beschermen. Zelfstandige klanten van Exchange Online Protection (EOP) die on-premises postvakken beschermen, moeten in plaats daarvan het volgende onderwerp lezen: [Spammeldingen voor eindgebruikers configureren in EOP](configure-end-user-spam-notifications-in-eop.md). 
  
U spammeldingen voor eindgebruikers configureren voor het standaard beleid voor spamfilters voor het hele bedrijf of voor het aangepaste beleid voor spamfilters. Met spammeldingen van eindgebruikers kunnen uw gebruikers hun eigen in quarantaine geplaatste spam-, bulk- en phishingberichten beheren.   
  
Spammeldingen van eindgebruikers bevatten een lijst met alle spam-quarantaine berichten die de eindgebruiker heeft ontvangen gedurende een periode die u configureert (u een waarde opgeven tussen 1 en 15 dagen). U ook de taal configureren waarin het meldingsbericht is geschreven.
  
Na ontvangst van een melding kunnen eindgebruikers kiezen uit de volgende opties:

**Afzender blokkeren** als u wilt dat Office 365 de afzender toevoegt aan de lijst met geblokkeerde afzenders.

**Laat u los** als het bericht geen spam is en u wilt dat Office 365 het bericht naar uw postvak verzendt.

**Controleer of** u naar de quarantaineportal in het Beveiligingscentrum & wilt navigeren als u andere acties wilt uitvoeren, zoals Voorbeeld of Release.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd om te voltooien: 2 minuten
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het item 'Antispam' in het onderwerp [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) om te zien welke machtigingen u nodig hebt. 
  
Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>De EAC gebruiken om spammeldingen van eindgebruikers te configureren

1. Navigeer in het Exchange-beheercentrum (EAC) naar het filter **Beveiligingspam** \> **Spam filter**.
    
2. Selecteer het spamfilterbeleid waarvoor u spammeldingen van eindgebruikers wilt inschakelen (deze zijn standaard uitgeschakeld).
    
3. Klik in het rechterdeelvenster, waar de overzichtsgegevens over uw beleid worden weergegeven, op de koppeling **Spammeldingen voor eindgebruikers configureren.** 
    
4. In het volgende dialoogvenster u de volgende opties configureren:
    
   - **Spammeldingen van eindgebruikers inschakelen** Schakel dit selectievakje in om spammeldingen van eindgebruikers voor dit beleid in te schakelen. (Als dit beleid daarentegen is ingeschakeld, u dit selectievakje uitschakelen om spammeldingen van eindgebruikers voor dit beleid uit te schakelen.) 
    
   - **Elke (dag) spammeldingen van eindgebruikers verzenden** Geef op hoe vaak spammeldingen van eindgebruikers moeten worden verzonden. De standaardinstelling is 3 dagen. U tussen 1 en 15 dagen opgeven. Als u bijvoorbeeld 7 dagen opgeeft, bevat de melding een lijst met alle berichten die in de afgelopen zeven dagen voor die gebruiker zijn bedoeld en die in plaats daarvan naar de spamquarantaine zijn verzonden. 
    
   - **Meldingstaal** Selecteer met de vervolgkeuzelijst de taal waarin u spammeldingen voor eindgebruikers voor dit beleid wilt schrijven. 
    
   - Klik op **Opslaan**. In het rechterdeelvenster verschijnt een overzicht van de beleidsinstellingen voor spamfilters, inclusief de instellingen voor spammeldingen van eindgebruikers.
    
> [!NOTE]
>  Spammeldingen van eindgebruikers zijn alleen functioneel voor het beleid voor spamfilters dat is ingeschakeld. > Spammeldingen van eindgebruikers worden slechts één keer per dag verzonden. De levertijd van de melding kan niet worden gegarandeerd voor een specifieke klant en is niet configureerbaar. 
  
 **Tip:** Als u spammeldingen van eindgebruikers wilt testen door ze naar een beperkte groep gebruikers te sturen voordat u ze volledig implementeert, maakt u een aangepast spamfilterbeleid waarmee spammeldingen van eindgebruikers worden ingesteld voor de domeinen waarin de gebruikers zich bevinden. Maak vervolgens in de EAC onder **E-mailstroomregels \> **een e-mailstroomregel (ook wel een transportregel genoemd) om berichten te blokkeren van quarantine@messaging.microsoft.com (het e-mailadres dat meldingen verzendt) met uitzonderingen voor de gebruikers die u de meldingen wilt ontvangen. De volgende afbeelding is een voorbeeld van het maken van een uitzondering voor twee gebruikers (SaraD en AlexD) van domein Contoso.com: 
  
![Transportregel om spammeldingen van eindgebruikers te testen](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>De SCC gebruiken om spammeldingen van eindgebruikers te configureren

U ook het Beveiligings- en Compliancecenter (SCC) gebruiken om spammeldingen van eindgebruikers te configureren. Voer de volgende stappen uit:

1. Open het Beveiligings- en Compliancecenter, navigeer naar **Threat** \> Management https://protection.office.com/antispam **Policy** \> **Anti-spam** of gebruik de directe link.

2. Klik op de pijl-omlaag naast het spamfilterbeleid waarvoor u spammeldingen van eindgebruikers wilt inschakelen.

3. Klik op de link **Spammeldingen voor eindgebruikers configureren.**

4. In het volgende dialoogvenster u de volgende opties configureren:
    
   - **Spammeldingen van eindgebruikers inschakelen** Schakel dit selectievakje in om spammeldingen van eindgebruikers voor dit beleid in te schakelen. (Als dit beleid daarentegen is ingeschakeld, u dit selectievakje uitschakelen om spammeldingen van eindgebruikers voor dit beleid uit te schakelen.) 
    
   - **Elke (dag) spammeldingen van eindgebruikers verzenden** Geef op hoe vaak spammeldingen van eindgebruikers moeten worden verzonden. De standaardinstelling is 3 dagen. U tussen 1 en 15 dagen opgeven. Als u bijvoorbeeld 7 dagen opgeeft, bevat de melding een lijst met alle berichten die in de afgelopen zeven dagen voor die gebruiker zijn bedoeld en die in plaats daarvan naar de spamquarantaine zijn verzonden. 
    
   - **Meldingstaal** Selecteer met de vervolgkeuzelijst de taal waarin u spammeldingen voor eindgebruikers voor dit beleid wilt schrijven. 
    
   - Klik op **Opslaan**. In het deelvenster verschijnt een overzicht van de beleidsinstellingen voor spamfilters, inclusief de instellingen voor spammeldingen van eindgebruikers.

## <a name="for-more-information"></a>Voor meer informatie

[Uw beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)

[Beleid voor set-hostedcontentfilter](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
