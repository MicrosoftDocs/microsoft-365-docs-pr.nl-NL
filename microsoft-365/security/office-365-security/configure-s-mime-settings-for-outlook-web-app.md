---
title: S/MIME-instellingen configureren - Exchange Online voor de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online weer te geven en te configureren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906478"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>S/MIME-instellingen configureren in de webversie van Exchange Online voor Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Als beheerder van Exchange Online kunt u de webversie van Outlook (voorheen Bekend als Outlook Web App) zo instellen dat u met S/MIME beveiligde berichten kunt verzenden en ontvangen. Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie weer te geven en te beheren in Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

Zie [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) en [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Aandachtspunten voor nieuwe Microsoft Edge (op Chromium gebaseerde)

Als u S/MIME wilt gebruiken in de webversie van Outlook in de nieuwe [Microsoft Edge-webbrowser,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het Microsoft Edge-browserbeleid **extensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat voor het toepassen van dit beleid domeingevoegde of Azure AD-apparaten zijn vereist, dus voor het gebruik van S/MIME in de nieuwe Microsoft Edge-browser zijn apparaten met domein- of Azure AD-apparaten effectief vereist.

Zie [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)voor meer informatie over het **beleid van ExtensionInstallForcelist.**

Deze stap is een vereiste voor het gebruik van nieuwe Microsoft Edge. het S/MIME-besturingselement dat door gebruikers is geïnstalleerd, wordt niet vervangen. Gebruikers worden gevraagd het besturingselement S/MIME te downloaden en te installeren in de webversie van Outlook tijdens het eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in de webinstellingen van Outlook om de downloadkoppeling voor het besturingselement te downloaden.

## <a name="considerations-for-chrome"></a>Aandachtspunten voor Chrome

Als u S/MIME wilt gebruiken in de webversie van Outlook in de webbrowser van Google Chrome, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in Chrome te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat voor het toepassen van dit beleid domeincomputers zijn vereist, dus voor het gebruik van S/MIME in Chrome zijn computers met domeinen effectief vereist.

Zie [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)voor meer informatie over het **beleid van ExtensionInstallForcelist.**

Deze stap is een vereiste voor het gebruik van Chrome. het S/MIME-besturingselement dat door gebruikers is geïnstalleerd, wordt niet vervangen. Gebruikers worden gevraagd het besturingselement S/MIME te downloaden en te installeren in de webversie van Outlook tijdens het eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in de webinstellingen van Outlook om de downloadkoppeling voor het besturingselement te downloaden.

## <a name="for-more-information"></a>Voor meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)