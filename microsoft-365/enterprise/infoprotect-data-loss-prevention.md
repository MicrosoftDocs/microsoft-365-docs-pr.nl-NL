---
title: 'Stap 5: Office 365 Preventie van gegevensverlies configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie over het gebruik van Office 365 Preventie van gegevensverlies en implementeren in Microsoft 365.
ms.openlocfilehash: 896670e9ae83324a1220d64f49a8ea48aee85169
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805276"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>Stap 5: Office 365 Preventie van gegevensverlies configureren

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 6: Gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Met een beleid voor preventie van gegevensverlies (DLP-beleid) in het Office 365-beveiligings- en nalevingscentrum kunt u gevoelige gegevens in Microsoft 365 identificeren, controleren en automatisch beschermen. Met DLP-beleid kunt u het volgende doen:

- Gevoelige informatie identificeren op meerdere locaties, zoals Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
- Voorkomen dat gevoelige gegevens per ongeluk worden gedeeld door de toegang tot een document te blokkeren of het e-mailbericht te blokkeren.
- Gevoelige informatie controleren en beveiligen in de bureaubladversies van Excel, PowerPoint en Word.
- Gebruikers leren hoe ze compatibel blijven, zonder hun werkstroom met e-mailmeldingen en beleidstips te onderbreken. 
- Bekijk DLP-rapporten met inhoud die overeenkomt met het DLP-beleid van uw organisatie.

Met een DLP-beleid wordt het volgende aangegeven:

- **Waar:** locaties, zoals Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams-chats en kanalen.
- **Wanneer:** voorwaarden dat de inhoud moet overeenstemmen met een bepaalde beleidsregel.
- **Hoe:** acties binnen die overeenkomende beleidsregel automatisch moeten worden uitgevoerd voor de overeenkomende voorwaarden.

Met andere woorden:

- Voor een document op deze locatie (waar), als de inhoud aan de voorwaarden van een regel voldoet (wanneer), worden de acties die in de regel zijn opgegeven, automatisch uitgevoerd (hoe).

Om te bepalen welke DLP-beleid u nodig hebt, moet u uw documenten analyseren en de gegevenstypen die bescherming moeten hebben tegen gegevensverlies. Als u bijvoorbeeld een financiële organisatie bent in de Verenigde Staten van Amerika, maakt u een DLP-beleid dat voorkomt dat documenten met Amerikaanse burgerservicenummers worden gedeeld buiten de organisatie of worden verzonden via e-mail naar locaties buiten de organisatie.

Vervolgens configureert en test u het beleid met testlocaties om het juiste DLP-gedrag te garanderen en om het aantal fout-positieven zo laag mogelijk te houden.

Ten slotte kunt u het uitrollen in uw organisatie door de werknemers van het nieuwe beleid en het gewenste gedrag op de hoogte te stellen en het bereik van de locaties te vergroten.

Zie [Aan de slag met aanbevelingen voor DLP-beleid](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations) voor meer informatie.

Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) voor deze stap als tussentijds controlepunt.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 6](../media/stepnumbers/Step6.png)|[E-mailversleuteling configureren](infoprotect-email-encryption.md)|


