---
title: Dynamische levering en previewing met ATP Safe Attachments
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
description: Wanneer u uw ATP-beleid voor veilige bijlagen instelt, kiest u Dynamische bezorging om berichtvertragingen te voorkomen en personen in staat te stellen een voorbeeld van bijlagen te bekijken die worden gescand.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e2da24ebac5863ab7852fdf8f9c7af8d507698b
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430349"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a>Dynamische levering en previewing met ATP Safe Attachments

## <a name="basic-features-of-dynamic-delivery"></a>Basisfuncties van Dynamic Delivery

Dynamische bezorging is een optie die kan worden geselecteerd voor de [veilige bijlagen van ATP. Lees dit artikel om meer te weten te komen over de mogelijkheden van Dynamische bezorging en bijlagenvoorbeeld in [veilige bijlagen van ATP in Office 365](atp-safe-attachments.md).

Wanneer [ATP-beleid voor veilige bijlagen wordt ingesteld](set-up-atp-safe-attachments-policies.md) voor uw organisatie, zijn er verschillende opties voor het verwerken van e-mailbijlagen. Deze omvatten **blokkeren**, **vervangen** en **dynamische bezorging**. Afhankelijk van hoe het ATP-beleid voor veilige bijlagen is geconfigureerd, kunnen geadresseerden van e-mailberichten een kleine vertraging in de bezorging van e-mail ondervinden terwijl hun bijlagen worden gescand. Als u vertragingen bij berichten wilt voorkomen, kiest u **dynamische bezorging**.

## <a name="how-dynamic-delivery-works"></a>Hoe dynamische bezorging werkt

Dynamische bezorging elimineert e-mailvertragingen door de hoofdtekst van een e-mailbericht door te sturen naar de ontvanger met een tijdelijke aanduiding voor e-mailbijlage(n). De tijdelijke aanduiding blijft staan totdat een kopie van de bijlage is gescand en door [ATP veilige bijlagen](atp-safe-attachments.md) als veilig is beoordeeld.

- Nadat een bijlage is gescand, is deze beschikbaar om te openen of te downloaden.

- Als wordt vastgesteld dat een bijlage kwaadaardig is, wordt deze naar quarantaine verzonden, waarbij iemand in het beveiligingsteam van uw organisatie (zoals een globale beheerder of beveiligingsbeheerder) in quarantaine geplaatste berichten kan [beheren in Office 365.](manage-quarantined-messages-and-files.md)

De meeste PDF-bestanden en Office-documenten kunnen worden weergegeven in de veilige modus terwijl er met ATP wordt gescand. Als een bijlage niet compatibel is met de voorbeeldweergave voor dynamische bezorging, zien geadresseerden van e-mailberichten een tijdelijke aanduiding voor bijlagen, totdat het scannen van de veilige bijlagen is voltooid.

> [!TIP]
> Als u een mobiel apparaat gebruikt en PDF's worden in het begin niet weergegeven in de dynamic delivery-previewer, u zich aanmelden met uw mobiele browser.

Met dynamische bezorging kunnen personen hun e-mailberichten meteen lezen en beantwoorden, terwijl hun bijlagen worden geanalyseerd.

ATP Safe Attachments scannen vindt plaats in dezelfde regio waar uw Microsoft 365-gegevens zich bevinden. Voor meer informatie over de geografie in datacenters raadpleegt u [waar bevinden uw gegevens zich?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Wat gebeurt er als iemand een e-mailbericht met een bijlage doorstuurt?

Stel dat een organisatie dynamische bezorging gebruikt voor hun [ATP-beleid voor veilige bijlagen](set-up-atp-safe-attachments-policies.md) en iemand ontvangt een e-mailbericht met een bijlage. Stel nu dat die persoon het e-mailbericht doorstuurt naar iemand anders. Wat gebeurt er? Het hangt af van het feit of de extra geadresseerden worden opgenomen in het ATP-beleid voor veilige bijlagen.

- Als een ontvanger wordt gedekt door een ATP-beleid voor veilige bijlagen met behulp van de optie dynamische bezorging, ziet de geadresseerde de tijdelijke aanduiding, met de mogelijkheid om compatibele bestanden te bekijken.

- Als een ontvanger niet wordt gedekt door een ATP-beleid voor veilige bijlagen, worden de e-mailberichten en bijlagen doorgestuurd zonder dat een ATP-beleidsscan voor veilige bijlagen of tijdelijke aanduidingen voor bijlagen wordt uitgevoerd.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Wat is vereist voor een dynamische bezorging?

- Uw organisatie moet beschikken over [Office 365 Advanced Threat Protection](office-365-atp.md)

- Beleid moet worden gedefinieerd voor ATP-beleid voor veilige bijlagen met de optie voor Dynamische bezorging (Zie [ATP-beleid voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md))

- Het e-mailsysteem van uw organisatie moet worden gehost in Office 365. Hoewel [Office 365 Advanced Threat Protection kan worden gebruikt met elke SMTP-mailoverdrachtsagent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (zoals Exchange Server), vereist de optie dynamische bezorging voor ATP-beleid voor veilige bijlagen dat het e-mailsysteem van uw organisatie wordt gehost in Office 365. Als uw e-mailsysteem niet wordt gehost in Office 365, kiest u een andere [optie voor het ATP-beleid voor veilige bijlagen](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), zoals **blokkeren**.

## <a name="additional-considerations"></a>Aanvullende overwegingen

Er zijn bepaalde scenario's waarin veilige bijlagen (waaronder Dynamische levering niet wordt ondersteund). Dit zijn onder andere:

- E-mailberichten die zich in openbare mappen bevinden.

- E-mailberichten die worden doorgestuurd uit en vervolgens terug in het postvak van de gebruiker met behulp van aangepaste regels.

- E-mailberichten die (automatisch of handmatig) uit het gehoste postvak worden verplaatst naar andere locaties, waaronder archiefmappen.

- E-mailberichten die worden verwijderd.

- De zoekmap voor postvakken van een gebruiker die zich in een foutstaat bevindt.

- Omgevingen waarin een Exchange Online-beheerder Exclaimer heeft ingeschakeld. Zie [Berichten met bijlagen niet worden bezorgd wanneer ATP Dynamic Delivery en Exclaimer worden gebruikt.](https://support.microsoft.com/help/4014438)

- Berichten versleuteld met [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)).

- In gevallen waarin Dynamische levering niet wordt ondersteund, scannen Safe Attachments geen e-mailberichten. Het afleveren van e-mailberichten met bijlagen die URL's bevatten, wordt echter gecontroleerd, afhankelijk van hoe uw [ATP-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) is geconfigureerd. In dergelijke gevallen worden URL's in e-mailberichten en Office-bestanden gecontroleerd.
