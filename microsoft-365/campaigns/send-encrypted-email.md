---
title: Versleutelde e-mail verzenden
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Meer informatie over het verzenden van versleutelde e-mail met Outlook.
ms.openlocfilehash: 209734bd52d1d97278d5632f035723758fe2e016
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576971"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Uw gevoelige e-mailberichten versleutelen of labelen

Uw gegevens en campagnegegevens zijn belangrijk en vaak vertrouwelijk. Bescherm deze gevoelige informatie met behulp van versleutelings- en gevoeligheidslabels, zodat u en uw e-mailontvangers de informatie met de gevoeligheid behandelen die hiervoor nodig is.

## <a name="best-practices"></a>Aanbevolen procedures

Voordat u e-mail verzendt met vertrouwelijke of gevoelige informatie, kunt u het volgende doen:

- **Versleuteling:** U kunt uw e-mail versleutelen om de privacy van de gegevens in de e-mail te beschermen. Wanneer u een e-mailbericht versleutelt, wordt het geconverteerd van leesbare tekst zonder tekst naar vervormde cyphertekst. Alleen de geadresseerde met de persoonlijke sleutel die overeenkomt met de openbare sleutel die wordt gebruikt om het bericht te versleutelen, kan het bericht ontcijferen om te lezen. Elke geadresseerde zonder de bijbehorende persoonlijke sleutel ziet echter niet-versleutelbare tekst. Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen, automatisch te versleutelen. Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten met specifieke woorden of woordgroepen. Versleutelingsregels worden automatisch toegepast.
- **Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u op uw bestanden en e-mail kunt toepassen, zodat ze voldoen aan het beleid voor informatiebeveiliging van uw campagne. Wanneer u een label in stelt, blijft het label bij uw e-mail, zelfs wanneer het wordt verzonden, bijvoorbeeld door als koptekst naar uw bericht te worden weergegeven.

![Diagram van een e-mailbericht met bijroepen voor etiketten en versleuteling](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Instellen

Als u een bericht wilt versleutelen dat niet voldoet aan een vooraf gedefinieerde regel of als uw beheerder geen regels heeft ingesteld, kunt u verschillende versleutelingsregels toepassen voordat u het bericht verzendt. Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u **Opties > Machtigingen** en selecteert u vervolgens de gewenste beveiligingsoptie. U kunt ook een versleuteld bericht verzenden door de **knop** Beveiligen te selecteren in de webversie van Outlook. Zie Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook voor pc voor [meer informatie.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>Beheerinstellingen

U vindt alles over het instellen van e-mailversleuteling bij [E-mailversleuteling in Microsoft 365.](../compliance/email-encryption.md)

### <a name="automatically-encrypt-email-messages"></a>E-mailberichten automatisch versleutelen

Beheerders kunnen regels voor e-mailstroom maken om e-mailberichten die vanuit uw campagne worden verzonden en ontvangen, automatisch te beveiligen. Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen uit versleutelde berichten die afkomstig zijn van uw organisatie of van antwoorden naar versleutelde berichten die vanuit uw organisatie worden verzonden.

U maakt regels voor de e-mailstroom om e-mailberichten te versleutelen met de nieuwe mogelijkheden van Office 365 Message Encryption (OME). Definieer e-mailstroomregels voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange Admin Center (EAC). 

1. Meld u aan in een webbrowser met een werk- of schoolaccount dat globale beheerdersmachtigingen heeft gekregen.
2. Kies de tegel Beheerder.
3. Kies beheercentra in het beheercentrum **> Exchange.**

Zie Regels voor e-mailstroom definiëren [om e-mailberichten te versleutelen voor meer informatie.](../compliance/define-mail-flow-rules-to-encrypt-email.md)

### <a name="brand-your-encryption-messages"></a>Uw versleutelingsberichten brand

U kunt ook uw campagnestijl toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen. Zie Het merk van uw organisatie toevoegen aan uw versleutelde berichten voor [meer informatie.](../compliance/email-encryption.md)