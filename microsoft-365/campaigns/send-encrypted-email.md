---
title: Versleutelde e-mail verzenden
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over het verzenden van versleutelde e-mail via Outlook.
ms.openlocfilehash: f5184de55ce07d5e669e98afb6e627833071c4ba
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526874"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Uw gevoelige e-mailberichten versleutelen of labelen

Uw gegevens en campagne-informatie zijn belangrijk en vaak vertrouwelijk. Help deze gevoelige informatie te beschermen door versleutelings- en gevoeligheidslabels te gebruiken, zodat u en uw e-mailontvangers de informatie behandelen met de gevoeligheid die dit vereist.


## <a name="best-practices"></a>Aanbevolen procedures

Voordat u e-mail verzendt met vertrouwelijke of gevoelige informatie, u overwegen het inschakelen van:

- **Versleuteling:** U uw e-mail versleutelen om de privacy van de informatie in de e-mail te beschermen. Wanneer u een e-mailbericht versleutelt, wordt het omgezet van leesbare platte tekst in vervormde cyphertekst. Alleen de ontvanger die de privésleutel heeft die overeenkomt met de openbare sleutel die wordt gebruikt om het bericht te versleutelen, kan het bericht ontcijferen om te lezen. Elke ontvanger zonder de bijbehorende privésleutel ziet echter onleesbare tekst. Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen, automatisch te versleutelen. Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten waarin specifieke woorden of zinnen worden vermeld. Alle versleutelingsregels worden automatisch toegepast.
- **Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u toepassen op uw bestanden en e-mail om ze te laten voldoen aan het beleid voor informatiebescherming van uw campagne. Wanneer u een label instelt, blijft het label bij uw e-mail, zelfs wanneer het wordt verzonden, bijvoorbeeld door als koptekst naar uw bericht te worden weergegeven.

![Diagram van een e-mail met bijschriften voor labels en versleuteling](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Instellen

Als u een bericht wilt versleutelen dat niet aan een vooraf gedefinieerde regel voldoet of als uw beheerder geen regels heeft ingesteld, u verschillende versleutelingsregels toepassen voordat u het bericht verzendt. Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u **Opties > Machtigingen**en selecteert u de beveiligingsoptie die u nodig hebt. U ook een versleuteld bericht verzenden door de knop **Beveiligen** in de webversie van Outlook te selecteren. Zie [Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook voor pc voor](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)meer informatie.

## <a name="admin-settings"></a>Beheerdersinstellingen

U alles te weten komen over het instellen van e-mailversleuteling bij [e-mailversleuteling in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>E-mailberichten automatisch versleutelen

Beheerders kunnen regels voor e-mailstromen maken om e-mailberichten die worden verzonden en ontvangen van uw campagne automatisch te beschermen. Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen uit versleutelde berichten die afkomstig zijn van uw organisatie of uit antwoorden op versleutelde berichten die vanuit uw organisatie worden verzonden. 

U maakt regels voor e-mailstroom om e-mailberichten te versleutelen met de nieuwe ome-mogelijkheden (Office 365 Message Encryption). Definieer regels voor e-mailstroom voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange Admin Center (EAC). 

1. Meld u in een webbrowser aan met een werk- of schoolaccount dat algemene beheerdersmachtigingen heeft gekregen. 
2. Kies de tegel Beheerder. 
3. Kies in het beheercentrum **Beheercentra > Exchange**. 

Zie [Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen voor](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)meer informatie.

### <a name="brand-your-encryption-messages"></a>Uw versleutelingsberichten brandmerken

U uw campagnebranding ook toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen. [Zie Het merk van uw organisatie toevoegen aan uw versleutelde berichten voor](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)meer informatie.

