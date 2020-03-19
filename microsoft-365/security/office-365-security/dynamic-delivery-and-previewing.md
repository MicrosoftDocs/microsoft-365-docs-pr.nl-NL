---
title: Dynamische weergave en previewing met veilige office 365-bijlagen voor ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Wanneer u uw BELEID voor veilige ATP-bijlagen instelt, kiest u Dynamische bezorging om vertragingen in berichten te voorkomen en mensen in staat te stellen bijlagen te bekijken die worden gescand.
ms.openlocfilehash: 755a5a317710946a3a03004482a6b48c8947c1a7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809515"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Dynamische weergave en previewing met veilige office 365-bijlagen voor ATP

## <a name="overview"></a>Overzicht

Dynamic Delivery is een optie die kan worden geselecteerd voor [ATP Safe Attachments.](atp-safe-attachments.md) Lees dit artikel voor meer informatie over de mogelijkheden voor dynamische weergave en preview-bijlagen in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).

Wanneer [het beleid voor veilige bijlagen van ATP is ingesteld](set-up-atp-safe-attachments-policies.md) voor uw organisatie, zijn er verschillende opties voor de manier waarop e-mailbijlagen worden verwerkt. Deze omvatten **Block**, **Replace**, en **Dynamic Delivery**. Afhankelijk van de manier waarop het beleid voor veilige bijlagen van ATP is geconfigureerd, kunnen e-mailontvangers een kleine vertraging in de e-mailbezorging ervaren terwijl hun bijlagen worden gescand. Als u berichtvertragingen wilt voorkomen, kiest u **Dynamische bezorging**.

## <a name="how-dynamic-delivery-works"></a>Hoe Dynamic Delivery werkt

Dynamic Delivery elimineert e-mailvertragingen door de hoofdtekst van een e-mailbericht door te sturen naar de ontvanger met een tijdelijke aanduiding voor elke e-mailbijlage. De tijdelijke aanduiding blijft totdat een kopie van de bijlage wordt gescand en bepaald dat deze veilig is door [ATP Safe Attachments.](atp-safe-attachments.md)

- Als elke bijlage wordt gewist, is deze beschikbaar om te openen of te downloaden.

- Als wordt vastgesteld dat een bijlage schadelijk is, wordt deze naar quarantaine verzonden, waar iemand in het beveiligingsteam van uw organisatie (zoals een globale office 365-beheerder of beveiligingsbeheerder) in quarantaine geplaatste berichten in [Office 365](manage-quarantined-messages-and-files.md)kan beheren.

De meeste PDF's en Office-documenten kunnen in de veilige modus worden bekeken terwijl het ATP-scannen aan de gang is. Als een bijlage niet compatibel is met de dynamic delivery-voorleesproef, zien e-mailontvangers een tijdelijke aanduiding voor bijlagen totdat het scannen van ATP-veilige bijlagen is voltooid.

> [!TIP]
> Als u een mobiel apparaat gebruikt en PDF's in eerste instantie niet worden weergegeven in Dynamic Delivery-previewer, probeert u zich aan te melden bij Office 365 met uw mobiele browser.

Met Dynamic Delivery kunnen mensen hun e-mailberichten meteen lezen en erop reageren, terwijl hun bijlagen worden geanalyseerd.

Het scannen van ATP-bijlagen vindt plaats in dezelfde regio waar uw Office 365-gegevens zich bevinden. Zie Waar bevinden uw gegevens zich voor meer informatie over de geografie van [datacenters?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Wat gebeurt er als iemand een e-mail doorstuurt die een bijlage bevat?

Stel dat een organisatie Dynamische bezorging gebruikt voor hun [ATP-beleid voor veilige bijlagen](set-up-atp-safe-attachments-policies.md)en dat iemand een e-mail ontvangt die een bijlage bevat. Stel nu dat die persoon het e-mailbericht doorstuurt naar iemand anders. Wat gebeurt er? Het hangt ervan af of de extra ontvangers zijn opgenomen in atp-beleid voor veilige bijlagen.

- Als een ontvanger wordt gedekt door een ATP-beleid voor veilige bijlagen met behulp van de optie Dynamische bezorging, ziet de ontvanger de tijdelijke aanduiding, met de mogelijkheid om een voorbeeld van compatibele bestanden te bekijken.

- Als een ontvanger niet onder een ATP-beleid voor veilige bijlagen valt, gaan de e-mail en bijlage door, zonder dat er tijdelijke aanduidingen voor ATP-veilige bijlagen worden gescand of tijdelijke aanduidingen voor bijlagen worden gescand.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Wat is er nodig om Dynamic Delivery te laten werken?

- Uw organisatie moet beschikken over [Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)

- Beleid moet worden gedefinieerd voor veilige ATP-bijlagen met de optie Dynamische bezorging (zie Beleid voor [veilige bijlagen voor ATP instellen in Office 365](set-up-atp-safe-attachments-policies.md))

- De e-mail van uw organisatie moet worden gehost in Office 365. Hoewel [Office 365 Advanced Threat Protection kan worden gebruikt met elke SMTP-mailoverdrachtagent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (zoals Exchange Server), vereist de optie Dynamische bezorging voor veilige bijlagen van ATP dat de e-mail van uw organisatie wordt gehost in Office 365. Als uw e-mail niet wordt gehost in Office 365, kiest u een andere [beleidsoptie voor veilige bijlagen atp,](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)zoals **Blokkeren**.

## <a name="additional-considerations"></a>Aanvullende overwegingen

Er zijn bepaalde scenario's waarin Dynamic Delivery niet wordt ondersteund. Deze omvatten de volgende gegevens:

- E-mailberichten die zich in openbare mappen bevinden

- E-mailberichten die worden doorgestuurd naar en vervolgens terug naar het postvak van de gebruiker met behulp van aangepaste regels

- E-mailberichten die (automatisch of handmatig) worden verplaatst vanuit het gehoste postvak en naar andere locaties, waaronder archiefmappen

- E-mailberichten die worden verwijderd

- De zoekmap van een gebruiker met postvak waarin een foutstatus is

- Omgevingen waarin een Exchange Online-beheerder Exclaimer heeft ingeschakeld. Zie Berichten met bijlagen worden [niet geleverd wanneer ATP Dynamic Delivery en Exclaimer worden gebruikt](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery) om dit op te lossen.

- Berichten versleuteld met [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)

- In gevallen waarin Dynamic Delivery niet wordt ondersteund, scant ATP Safe Attachments geen e-mailberichten. Het leveren van e-mailberichten met bijlagen die URL's bevatten, wordt echter gecontroleerd, afhankelijk van hoe uw [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) is geconfigureerd. In deze gevallen worden URL's in e-mailberichten en Office-bestanden gecontroleerd.
