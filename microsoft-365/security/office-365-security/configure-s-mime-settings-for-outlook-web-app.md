---
title: S/MIME-instellingen configureren - Exchange Online voor de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online weer te geven en te configureren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0b98a853d81d5ce067233314dfc59c7f677656bd
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352031"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook

Als beheerder van Exchange Online u de webversie van Outlook (voorheen Outlook Web App) instellen om het verzenden en ontvangen van S/MIME-beveiligde berichten mogelijk te maken. Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie te bekijken en te beheren in Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) en [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Overwegingen voor nieuwe Microsoft Edge (op chromium gebaseerd)

Als u S/MIME wilt gebruiken in Outlook op het web in de nieuwe [Microsoft Edge-webbrowser,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het Microsoft Edge-browserbeleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat het toepassen van dit beleid domeingebonden computers vereist, dus het gebruik van S/MIME in de nieuwe Microsoft Edge-browser vereist effectief computers met domeinverbonden computers.

Zie [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)voor meer informatie over het beleid **extensionInstallForcelist.**

Deze stap is een vereiste voor het gebruik van nieuwe Microsoft Edge; het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd. Gebruikers wordt gevraagd om het S/MIME-besturingselement in Outlook op het web te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in hun Web-instellingen in Outlook voor de download om de downloadkoppeling voor het besturingselement te krijgen.

## <a name="considerations-for-chrome"></a>Overwegingen voor Chrome

Als u S/MIME wilt gebruiken in Outlook op het web in de Webbrowser Google Chrome, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in Chrome te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat het toepassen van dit beleid domein-verbonden computers vereist, dus het gebruik van S / MIME in Chrome vereist effectief domein-aangesloten computers.

Zie [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)voor meer informatie over het beleid **extensionInstallForcelist.**

Deze stap is een voorwaarde voor het gebruik van Chrome; het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd. Gebruikers wordt gevraagd om het S/MIME-besturingselement in Outlook op het web te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in hun Web-instellingen in Outlook voor de download om de downloadkoppeling voor het besturingselement te krijgen.

## <a name="for-more-information"></a>Voor meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)
