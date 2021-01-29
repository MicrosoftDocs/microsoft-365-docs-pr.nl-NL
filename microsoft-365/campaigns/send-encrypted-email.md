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
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044214"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Uw gevoelige e-mailberichten versleutelen of labelen

Uw gegevens en campagnegegevens zijn belangrijk en vaak vertrouwelijk. Bebeveiligen deze gevoelige informatie met behulp van versleuteling en gevoeligheidslabels, zodat u en uw e-mailontvangers de informatie met de gevoeligheid behandelen die hiervoor is vereist.

## <a name="best-practices"></a>Aanbevolen procedures

Voordat u een e-mailbericht met vertrouwelijke of gevoelige informatie verzendt, kunt u het volgende in- of uitschakelen:

- **Versleuteling:** U kunt uw e-mail versleutelen om de privacy van de gegevens in de e-mail te beschermen. Wanneer u een e-mailbericht versleutelt, wordt dit geconverteerd van leesbare tekst zonder tekst naar gecodeerde cypherische tekst. Alleen de ontvanger met de persoonlijke sleutel die overeenkomt met de openbare sleutel waarmee het bericht is versleuteld, kan het bericht ontcijferen om te lezen. Iedere ontvanger zonder de bijbehorende persoonlijke sleutel ziet echter ondeci bolvormige tekst. Uw beheerder kan regels definiëren om berichten die aan bepaalde criteria voldoen, automatisch te versleutelen. Uw beheerder kan bijvoorbeeld een regel maken die alle berichten versleutelt die buiten uw organisatie worden verzonden of alle berichten die specifieke woorden of woordgroepen bevatten. Versleutelingsregels worden automatisch toegepast.
- **Gevoeligheidslabels:** Uw campagne kan ook gevoeligheidslabels instellen die u op uw bestanden en e-mailberichten kunt toepassen om ervoor te zorgen dat ze voldoen aan het beleid voor informatiebeveiliging van uw campagne. Wanneer u een label in stelt, blijft het label bij uw e-mailbericht staan, zelfs wanneer het wordt verzonden, bijvoorbeeld door deze als een koptekst voor uw bericht weer te geven.

![Diagram van een e-mailbericht met bijroepen voor labels en versleuteling](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Instellen

Als u een bericht wilt versleutelen dat niet voldoet aan een vooraf gedefinieerde regel of als uw beheerder geen regels heeft ingesteld, kunt u verschillende versleutelingsregels toepassen voordat u het bericht verzendt. Als u een versleuteld bericht wilt verzenden vanuit Outlook 2013 of 2016 of Outlook 2016 voor Mac, selecteert u Opties **>-machtigingen** en selecteert u vervolgens de gewenste beveiligingsoptie. U kunt ook een versleuteld bericht verzenden door de knop Beveiligen te **selecteren** in de webversie van Outlook. Zie Versleutelde berichten verzenden, weergeven en [beantwoorden in Outlook voor pc voor meer informatie.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>Beheerinstellingen

Meer informatie over het instellen van e-mailversleuteling bij [E-mailversleuteling in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>E-mailberichten automatisch versleutelen

Beheerders kunnen regels voor de e-mailstroom maken om e-mailberichten die vanuit uw campagne worden verzonden en ontvangen, automatisch te beveiligen. Stel regels in om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen van versleutelde berichten die afkomstig zijn van binnen uw organisatie of van antwoorden op versleutelde berichten die van uw organisatie worden verzonden.

U maakt regels voor de e-mailstroom om e-mailberichten te versleutelen met de nieuwe mogelijkheden van Office 365-berichtversleuteling (OME). Definieer regels voor de e-mailstroom voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van het Exchange-beheercentrum (EAC). 

1. Meld u in een webbrowser aan met een werk- of schoolaccount dat globale beheerdersmachtigingen heeft gekregen.
2. Kies de tegel Beheerder.
3. Kies in het beheercentrum **beheercentra > Exchange.**

Zie Regels voor de [e-mailstroom definiëren om e-mailberichten te versleutelen](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)voor meer informatie.

### <a name="brand-your-encryption-messages"></a>Uw versleutelingsberichten van een huismerk voorzien

U kunt ook de huisstijl van uw campagne toepassen om het uiterlijk en de tekst in de e-mailberichten aan te passen. Zie Het merk van uw organisatie toevoegen aan [versleutelde berichten voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)
