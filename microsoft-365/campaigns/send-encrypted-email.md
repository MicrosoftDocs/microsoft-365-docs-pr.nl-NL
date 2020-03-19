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
ms.openlocfilehash: 559998326caedaf3352741ad9083940f79b1a614
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806293"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Uw gevoelige e-mail versleutelen of labelen

Uw gegevens en campagne-informatie zijn belangrijk en vaak vertrouwelijk. Bescherm deze gevoelige informatie door gebruik te maken van versleutelings- en gevoeligheidslabels, zodat u en uw e-mailontvangers de informatie behandelen met de gevoeligheid die het vereist.


## <a name="best-practices"></a>Aanbevolen procedures

Voordat u e-mail met vertrouwelijke of gevoelige informatie verzendt, u overwegen in te schakelen:

- **Versleuteling:** U uw e-mail versleutelen om de privacy van de informatie in de e-mail te beschermen. Wanneer u een e-mailbericht versleutelt, wordt het omgezet van leesbare platte tekst naar vervormde cyphertekst. Alleen de ontvanger die de privésleutel heeft die overeenkomt met de openbare sleutel die wordt gebruikt om het bericht te versleutelen, kan het bericht ontcijferen om te lezen. Elke ontvanger zonder de bijbehorende privésleutel ziet echter onleesbare tekst. Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen automatisch te versleutelen. Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten waarin specifieke woorden of zinnen worden vermeld. Eventuele versleutelingsregels worden automatisch toegepast.
- **Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u op uw bestanden en e-mail toepassen om ze te laten voldoen aan het beleid voor informatiebescherming van uw campagne. Wanneer u een label instelt, blijft het label bij uw e-mail bestaan, zelfs wanneer deze wordt verzonden, bijvoorbeeld door te worden weergegeven als een koptekst voor uw bericht.

![Diagram van een e-mail met callouts voor labels en versleuteling](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Instellen

Als u een bericht wilt versleutelen dat niet voldoet aan een vooraf gedefinieerde regel of als uw beheerder geen regels heeft ingesteld, u verschillende versleutelingsregels toepassen voordat u het bericht verzendt. Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u **Opties > machtigingen**en selecteert u de beveiligingsoptie die u nodig hebt. U ook een versleuteld bericht verzenden door de knop Beveiligen in de webversie **van** Outlook te selecteren. Zie [Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook voor pc](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)voor meer informatie.

## <a name="admin-settings"></a>Beheerdersinstellingen

U alles te weten komen over het instellen van e-mailversleuteling bij [e-mailversleuteling in Office 365.](https://docs.microsoft.com/office365/securitycompliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>E-mailberichten automatisch versleutelen

Beheerders kunnen regels voor e-mailstroom maken om e-mailberichten die van uw campagne worden verzonden en ontvangen, automatisch te beveiligen. Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen uit versleutelde berichten die afkomstig zijn van binnen uw organisatie of van antwoorden op versleutelde berichten die vanuit uw organisatie worden verzonden. 

U maakt regels voor e-mailstroom om e-mailberichten te versleutelen met de nieuwe OME-mogelijkheden (Office 365 Message Encryption). Definieer regels voor de stroom van e-mailberichten voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange Admin Center (EAC). 

1. Meld u in een webbrowser met behulp van een werk- of schoolaccount dat wereldwijde beheerdersmachtigingen heeft gekregen, zich aan bij Office 365. 
2. Kies de tegel Beheerder. 
3. Kies in het beheercentrum **Beheerderscentra > Exchange**. 

Zie [Regels voor e-mailstroom definiëren om e-mailberichten in Office 365 te versleutelen](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)voor meer informatie.

### <a name="brand-your-encryption-messages"></a>Uw versleutelingsberichten brandmerken

U uw campagnenaamstijl ook toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen. Zie [Het merk van uw organisatie toevoegen aan uw versleutelde berichten](https://docs.microsoft.com/office365/securitycompliance/email-encryption)voor meer informatie.

