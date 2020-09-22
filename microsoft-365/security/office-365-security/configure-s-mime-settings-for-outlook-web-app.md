---
title: S/MIME-instellingen configureren-Exchange Online voor Outlook op het web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders nodig hebben om de S/MIME-instellingen in de webversie van Outlook in Exchange Online weer te geven en te configureren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe561c3a66cf2e7bdb76aabe10ffc875d85f2d77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203333"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als beheerder van Exchange Online kunt u de webversie van Outlook (voorheen Outlook Web app) instellen voor het verzenden en ontvangen van e-mailberichten die/of MIME-beveiliging zijn. Met de cmdlet **Get-SmimeConfig** en **set-SmimeConfig** kunt u deze functie weergeven en beheren in Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) en [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Aandachtspunten voor nieuwe Microsoft Edge (op basis van chroom)

Als u S/MIME in de webversie van Outlook wilt gebruiken in de nieuwe webbrowser van [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , moet u (of een andere beheerder) het browser beleid Microsoft Edge met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie te installeren in de nieuwe Microsoft Edge. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat het toepassen van dit beleid vereist domein aanmerkt of Azure AD-bijgevoegde apparaten, dus als u S/MIME in de nieuwe Microsoft Edge-browser wilt gebruiken, moet u domeinnaam of Azure AD-gekoppelde apparaten gebruiken.

Zie [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)voor meer informatie over het **ExtensionInstallForcelist** -beleid.

Deze stap is een vereiste voor het gebruik van nieuwe Microsoft Edge. het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd. Gebruikers wordt gevraagd om de S/MIME-besturing te downloaden en te installeren in de webversie van Outlook, wanneer ze het eerst gebruiken met S/MIME. Gebruikers kunnen ook proactief naar **S/MIME** in de webversie van Outlook gaan om de downloadkoppeling voor het besturingselement te downloaden.

## <a name="considerations-for-chrome"></a>Aandachtspunten voor Chrome

Als u S/MIME in de webversie van Outlook wilt gebruiken in de webversie van Google Chrome, moet u (of een andere beheerder) het Chrome-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie te installeren in Chrome. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat bij het toepassen van dit beleid toegevoegde domein-computers zijn vereist, zodat de domeinnamen voor domeinnamen in Chrome naar behoren worden gebruikt.

Zie [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)voor meer informatie over het **ExtensionInstallForcelist** -beleid.

Deze stap is een vereiste voor het gebruik van Chrome. het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd. Gebruikers wordt gevraagd om de S/MIME-besturing te downloaden en te installeren in de webversie van Outlook, wanneer ze het eerst gebruiken met S/MIME. Gebruikers kunnen ook proactief naar **S/MIME** in de webversie van Outlook gaan om de downloadkoppeling voor het besturingselement te downloaden.

## <a name="for-more-information"></a>Voor meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)
