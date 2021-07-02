---
title: Interoperabiliteit Microsoft OneDrive Learning hulpprogramma's gebruiken
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Maak en cijfertoewijzingen, bouw en beheer cursusinhoud en werk in realtime samen aan bestanden met de nieuwe Microsoft OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256972"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integratie Microsoft OneDrive LTI met Canvas

Het integreren Microsoft OneDrive LTI met Canvas is een proces in twee stappen. Met de eerste stap kunt Microsoft OneDrive in Canvas en met de tweede stap wordt de Microsoft OneDrive LTI beschikbaar in canvascursussen.

## <a name="recommended-browser-settings"></a>Aanbevolen browserinstellingen

- Cookies moeten zijn ingeschakeld voor Microsoft OneDrive.
- Pop-ups mogen niet worden geblokkeerd voor Microsoft OneDrive.

> [!NOTE]
> - Cookies zijn standaard niet ingeschakeld in de incognitomodus van de Chrome-browser en moeten worden ingeschakeld.
> - Microsoft OneDrive LTI werkt in de privémodus in Microsoft Edge browser. Zorg ervoor dat u cookies niet hebt geblokkeerd (die standaard zijn ingeschakeld).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>LTI Microsoft OneDrive in canvas inschakelen

> [!IMPORTANT]
> De persoon die deze integratie uitvoert, moet een beheerder van Canvas zijn en een beheerder van de Microsoft 365 tenant.

1. Meld u aan <a href="https://onedrivelti.microsoft.com/admin" target="_blank">bij Microsoft OneDrive LTI-registratieportal</a>
1. Selecteer de **knop Toestemming van** beheerder en accepteer de machtigingen.
1. Selecteer de **knop Nieuwe LTI-tenant** maken. Selecteer canvas op de  pagina LTI-registratie in de vervolgkeuzekeuzepagina en voer de basis-URL van het canvas-exemplaar in.

> [!NOTE]
> Als uw canvas-exemplaar bijvoorbeeld https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) is, moet de volledige URL worden ingevoerd.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="De pagina LTI-tenantbeheer, met een vervolgkeuzeveld voor het kiezen van het LTI-consumentenplatform en een URL-tekstveld.":::

4. Kopieer de JSON door de **knop** Kopiëren te selecteren (een pictogram aan de rechterkant met twee pagina's boven op elkaar). Hiermee wordt de sleutel in Canvas gegenereerd.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Een afbeelding met de kopieerknop die de weergegeven JSON-tekst kopieert en deze beschikbaar maakt voor sleutelgeneratie in Canvas.":::

5. Meld u als beheerder aan bij het canvas-exemplaar en selecteer **Ontwikkelaarstoetsen** in het menu aan de linkerkant van de pagina. Maak in de vervolgkeuzepagina een ontwikkelaarssleutel door **LTI-toets** te kiezen in de vervolgkeuzepagina rechtsboven op de pagina.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Een schermafbeelding met de linkernavigatiebalk waarop Ontwikkelaarstoetsen zijn geselecteerd en het item LTI-toets geselecteerd in een vervolgkeuzekeuzevenster aan de rechterkant van de pagina.":::

6. Selecteer op de pagina  Configureren in de vervolgkeuzekeuzepagina Methode **JSON** plakken als methode en plak de JSON-tekst die u hebt gekopieerd in stap 5 in het tekstveld dat wordt weergegeven.
7. Sla de sleutel op en deze wordt beschikbaar in Canvas in **de status Uit.** Schakel de toets **In en** kopieer de sleutel in de **kolom Details** die u in de volgende stap wilt gebruiken.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="De pagina Canvas met de sleutel die is ingesteld in een uitgeschakelde toestand. Deze moet zijn ingeschakeld en de sleutel moet worden gekopieerd uit de kolom details op deze pagina.":::

8. Ga terug naar de Microsoft OneDrive LTI-registratieportal en plak de sleutel in het **veld Canvas Client-id.** Selecteer **Volgende** wanneer u klaar bent.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="De LTI-tenantregistratiepagina, waarin de JSON-tekst en het tekstvak worden weergegeven waarin de sleutel moet worden gekopieerd.":::

9. Controleer en sla uw wijzigingen op. Er wordt een bericht weergegeven bij een geslaagde registratie.
10. Uw registratiegegevens kunnen ook worden gecontroleerd door de knop **LTI-tenants** weergeven op de startpagina te selecteren.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>LTI Microsoft OneDrive in canvascursussen inschakelen

Een canvasbeheerder kan de Microsoft OneDrive LTI inschakelen voor alle cursussen. Als Microsoft OneDrive LTI nodig is in een specifieke cursus (en niet alle cursussen), moet de docent dezelfde stappen volgen binnen de cursusinstellingen.

1. Meld u aan als beheerder en ga naar de **Instellingen** sectie.
2. Ga naar de **sectie Apps** en selecteer de **knop App-configuraties** weergeven.
3. Selecteer de **knop App** toevoegen.
4. Kies in **de vervolgkeuzekeuzeoptie** Configuratietype de **optie Op client-id.**
5. Plak de waarde van de ontwikkelaarssleutel die eerder is gegenereerd in het **veld Client-id** en selecteer de **knop** Verzenden.

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="De pagina App toevoegen, met de optie Door client-id onder de vervolgkeuzelijst Configuratietype.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Samenwerking Instellingen voor Microsoft OneDrive LTI in canvascursussen

> [!NOTE]
> Als u wilt samenwerken voor docenten en leerlingen/studenten, moet u de samenwerkingsinstelling niet inschakelen. Als u wilt weten of de instelling niet is ingeschakeld, volgt u de onderstaande stappen.

1. Meld u aan als beheerder en ga naar de **Instellingen** sectie.
1. Ga naar **de sectie Functieopties** en ga naar de **sectie** Cursus.
1. Stel de **functie Extern samenwerkingshulpmiddel** zo in dat deze niet is ingeschakeld.

> [!NOTE]
> Samenwerking kan worden toegewezen aan individuele leerlingen/studenten en aan groepen leerlingen/studenten. Het toewijzen aan afzonderlijke leerlingen/studenten werkt standaard. Als u samenwerking wilt kunnen toewijzen aan een groep leerlingen/studenten, volgt u de volgende stappen:

1. Meld u aan als beheerder en ga naar de **sectie Ontwikkelaarssleutels.**
1. Zoek de sleutel met waarde 17000000000710 en stel deze in op **Aan**.
