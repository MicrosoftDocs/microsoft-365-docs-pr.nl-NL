---
title: Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: U een Exchange-e-mailstroomregel maken om te voorkomen dat uw gebruikers e-mailberichten naar Microsoft verzenden voor analyse en deze gebruiken in uw eigen beveiligingsprocessen
ms.openlocfilehash: ae8655416840dc326344e2c2aea7c67486389492
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805890"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren

Er zijn meerdere manieren waarop u fout-positieve en fout-negatieve berichten naar Microsoft verzenden voor analyse. Als beheerder u regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren als spam, niet-spam en phishing.As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. Zie [Spam, niet-spam en phishing-scamberichten verzenden voor analyse voor](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)meer informatie. Omgekeerd u een Exchange-mailstroomregel maken (ook wel een transportregel genoemd) om te voorkomen dat uw gebruikers e-mailberichten naar Microsoft verzenden voor analyse en deze gebruiken in uw eigen beveiligingsprocessen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd om te voltooien: 5 minuten

U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie de vermeldingen 'E-mailstroom' en 'Outlook op het webpostvakbeleid' in [Exchange Online-machtigingen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)om te zien welke machtigingen u nodig hebt.

Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Gebruik de EAC om een e-mailstroomregel te maken om handmatige ongewenste e-mail-, phishing- en niet-ongewenste rapporten van gebruikers weer te geven

1. Navigeer in de EAC naar **E-mailstroomregels** \> **Rules**.

2. Klik ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.

3. Geef de regel een naam en klik op **Meer opties**.

4. Selecteer **onder Deze regel toepassen als**u De **ontvanger** selecteert en vervolgens adres selecteert dat een van deze **woorden bevat**.

5. Ga in het vak **Woorden of zinnen opgeven** de volgende stappen uit:

   - Typ, `abuse@messaging.microsoft.com` **klik** ![op](../../media/ITPro-EAC-AddIcon.gif)Pictogram `junk@office365.microsoft.com` Toevoegen, typ](../../media/ITPro-EAC-AddIcon.gif)en klik vervolgens op Pictogram Toevoegen **toevoegen** ![. Deze e-mailadressen worden gebruikt om valse negatieve berichten naar Microsoft te verzenden.

   - Typ `phish@office365.microsoft.com` en klik op](../../media/ITPro-EAC-AddIcon.gif)Pictogram Toevoegen **toevoegen** ![. Dit e-mailadres wordt gebruikt om gemiste phishingberichten naar Microsoft te sturen.

   - Typ, `false_positive@messaging.microsoft.com` **klik** ![op](../../media/ITPro-EAC-AddIcon.gif)Pictogram `not_junk@office365.microsoft.com`toevoegen, typ en](../../media/ITPro-EAC-AddIcon.gif) **klik** ![vervolgens op Pictogram toevoegen toevoegen . Deze e-mailadressen worden gebruikt om fout-positieve berichten naar Microsoft te verzenden.

   - Klik op **OK**.

6. Selecteer **onder Doe het volgende**bcc het bericht **naar...** en selecteer vervolgens de postvakken waar u de berichten wilt ontvangen.

7. Als u wilt, u selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere selecties. We raden u aan de regel te testen voor een periode voordat u deze afdwingt. Zie [Procedures voor regels voor e-mailstromen](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).

8. Klik **op** de knop Opslaan om de regel op te slaan. Het staat in je lijst met regels.

Nadat u de regel hebt gemaakt en afgedwongen, worden alle berichten die vanuit uw organisatie naar opgegeven e-mailadressen worden verzonden, gekopieerd naar het opgegeven postvak.
