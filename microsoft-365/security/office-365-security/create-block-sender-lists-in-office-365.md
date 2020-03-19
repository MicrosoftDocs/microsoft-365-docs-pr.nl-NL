---
title: Afzenderlijsten voor blokkeren maken in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Opties voor de lijst met afzenders blokkeren zijn Outlook-geblokkeerde afzenders, antispamlijsten/domeinbloklijsten, IP-bloklijsten en exchange-regels voor e-mailstromen (transportregels).
ms.openlocfilehash: fb5228bca7ac0c98a2aafd9d7b582e370698649a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810436"
---
# <a name="create-block-sender-lists-in-office-365"></a>Afzenderlijsten voor blokkeren maken in Office 365

Soms is het nodig om ongewenste e-mail van afzenders te blokkeren. Er zijn verschillende methoden beschikbaar om uit te kiezen. Deze opties omvatten Outlook Blocked Senders, Anti-Spam Sender/Domain Block Lists, IP Block Lists en Exchange mail flow rules (ook wel transportregels genoemd).

> [!NOTE]
> Hoewel lijsten met organisatieblokkeringen kunnen worden gebruikt om foute negatieven (gemiste spam) aan te pakken, moeten deze kandidaten ook worden ingediend bij Microsoft voor analyse. Het beheren van foutnegatieven door het gebruik van bloklijsten verhoogt uw administratieve overhead aanzienlijk. Als u hiervoor een blokkenlijst gebruikt, moet u het artikel ook bewaren voor [het indienen van spam, niet-spam en phishing-berichten voor oplichting bij Microsoft voor analyse](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), klaar.

De juiste methode om geblokkeerde afzenderlijsten te configureren, is afhankelijk van de omvang van de impact. Voor impact van één gebruiker kan de juiste oplossing zijn om Outlook Blocked Senders te gebruiken, maar als meerdere gebruikers of alle gebruikers worden beïnvloed, zou een van de andere opties geschikter zijn.

## <a name="options-from-least-to-broadest-scope"></a>Opties van de minst tot de breedste scope

Bij het maken van een bloklijst is het belangrijk om de juiste methode te kiezen op basis van de omvang van de impact (hoeveel mensen worden beïnvloed), zodat deze overeenkomt met de breedte van de blokkeringsmethode. De onderstaande opties worden gerangschikt op zowel scope als breedte. De lijst gaat van smal naar breed, maar lees de details voor volledige *aanbevelingen.*

- Outlook-geblokkeerde afzenders
- Anti-spambeleid: lijsten met afzender/domeinblok
- Regels voor de stroomstroom van exchange mail
- Antispambeleid: IP-bloklijsten

## <a name="use-outlook-blocked-senders"></a>Outlook-geblokkeerde afzenders gebruiken

Wanneer slechts een klein aantal gebruikers wordt beïnvloed, moet Outlook-geblokkeerde afzenders worden gebruikt, omdat dit alleen gevolgen heeft voor e-mail die naar hen wordt verzonden.

> [!IMPORTANT]
> Als de ongewenste berichten nieuwsbrieven zijn van een betrouwbare en herkenbare bron, is het afmelden van de e-mail een andere optie om te voorkomen dat de gebruiker de e-mails in de toekomst ontvangt.

De stappen om dit in te stellen verschillen tussen [de webversie](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) van Outlook en de [Outlook-client.](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) **Wanneer berichten zijn geblokkeerd als gevolg van geblokkeerde afzenders ziet u SFV:BLK in het X-Forefront-Antispam-Report,** wat aangeeft dat het bericht wordt geblokkeerd.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Lijsten voor afzender/domeinblokvan antispambeleid gebruiken

Wanneer meerdere gebruikers worden beïnvloed, is het bereik breder en moet u een bedrijfsbrede lijst met afzenders/domeinblokken gebruiken. De gedetailleerde stappen zijn te vinden in [Het beleid voor spamfilters configureren](configure-your-spam-filter-policies.md). Berichten die via deze methode worden geblokkeerd, volgen de spamactie zoals geconfigureerd in het beleid.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen; hoewel, zult u slechts 30 ingangen in het portaal kunnen invoeren. U moet PowerShell gebruiken om meer dan 30 vermeldingen toe te voegen.

## <a name="use-exchange-mail-flow-rules-specific-senders"></a>Specifieke afzenders van Exchange-e-mailstroomregels gebruiken

Als u wilt voorkomen dat berichten worden verzonden naar specifieke gebruikers of in de hele organisatie, u regels voor e-mailstroom gebruiken. Regels voor e-mailstromen zijn flexibeler omdat ze het e-mailadres of domein van de afzender kunnen activeren, evenals trefwoorden en andere eigenschappen in het bericht. Met deze flexibiliteit u gedeeltelijke blokken maken. Zie [Regels voor e-mailstroom gebruiken om de SCL in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie over regels voor e-mailstroom.

> [!IMPORTANT]
> Het is gemakkelijk om regels te maken die *overdreven* agressief zijn, als gevolg daarvan is het belangrijk dat de criteria die worden gebruikt zo specifiek mogelijk zijn. Zorg er ook voor dat u controle op de regel die u maakt inschakelen en testen doet om ervoor te zorgen dat alles werkt zoals verwacht.

## <a name="use-anti-spam-policy-ip-block-lists"></a>IP-bloklijsten voor antispambeleid gebruiken

Als het niet mogelijk is om een van de andere opties te gebruiken om een afzender te blokkeren, *kunt* u de IP-blokkeringslijst van antispambeleid gebruiken. Zie [Het beleid voor verbindingsfilter configureren](configure-the-connection-filter-policy.md)voor meer informatie. Het is belangrijk om het aantal geblokkeerde IP's tot een minimum te beperken, dus het blokkeren van hele IP-adresbereiken wordt *niet* aanbevolen.

U moet *vooral* voorkomen dat ip-adresbereiken worden toegevoegd die behoren tot consumentenservices of gedeelde infrastructuren, en ervoor zorgen dat u de lijst met toegestane IP-adressen bekijkt als onderdeel van regulier onderhoud. **Omdat in-items routes kunnen worden geopend voor aanvallen, moet u deze lijst nauwkeurig beheren en regelmatig de vermeldingen verwijderen die niet meer nodig zijn.** Als u het toelaat in een lijst met veilige afzenders, moet u de risico's en voorzorgsmaatregelen in *[lijsten met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)* lezen en begrijpen.
