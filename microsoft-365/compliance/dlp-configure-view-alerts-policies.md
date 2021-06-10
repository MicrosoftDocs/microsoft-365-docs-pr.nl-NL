---
title: Waarschuwingen voor preventiebeleid voor gegevensverlies configureren en weergeven
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het definiëren en beheren van waarschuwingen voor preventiebeleid voor gegevensverlies.
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162584"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>Waarschuwingen voor preventie van gegevensverlies configureren en weergeven

DLP-agenten (Data Loss Prevention) kunnen beschermende acties uitvoeren om onbedoeld delen van gevoelige items te voorkomen. Wanneer een actie wordt ondernomen voor een gevoelig item, kunt u een melding krijgen door waarschuwingen voor DLP te configureren. In dit artikel wordt beschreven hoe u beleidsregels voor rich alert kunt definiëren die zijn gekoppeld aan uw DLP-beleid (Data Loss Prevention). U ziet hoe u het nieuwe DLP-dashboard voor waarschuwingsbeheer in het [Microsoft 365 compliancecentrum](https://compliance.microsoft.com/) kunt gebruiken om waarschuwingen, gebeurtenissen en bijbehorende metagegevens voor DLP-beleidsovertredingen weer te geven.

<!-- LEFT OFF HERE-->

## <a name="features"></a>Functies

De volgende functies maken deel uit van deze functies:

-   **DLP-waarschuwingsbeheerdashboard:** in [het Microsoft 365 compliancecentrum](https://compliance.microsoft.com/)worden op dit dashboard waarschuwingen voor DLP-beleid dat wordt afgedwongen voor de volgende werkbelastingen:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Apparaten
-   **Geavanceerde configuratieopties voor waarschuwingen:** deze opties maken deel uit van de DLP-ontwerpstroom voor beleid. Gebruik ze om uitgebreide waarschuwingsconfiguraties te maken. U kunt een waarschuwing voor één gebeurtenis of een samengevoegde waarschuwing maken op basis van het aantal gebeurtenissen of de grootte van de gelekte gegevens.

## <a name="before-you-begin"></a>Voordat u begint

Voordat u begint, moet u de benodigde vereisten hebben:

-   Licenties voor het DLP-waarschuwingenbeheerdashboard
-   Licenties voor configuratieopties voor waarschuwingen
-   Rollen

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licenties voor het DLP-waarschuwingsbeheerdashboard

Alle in aanmerking komende tenants voor Office 365 DLP hebben toegang tot het nieuwe DLP-waarschuwingsbeheerdashboard. Om aan de slag te gaan, moet u in aanmerking komen voor Office 365 DLP voor Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Zie Welke licenties bieden een gebruiker de rechten om van de service te profiteren voor meer informatie over de licentievereisten voor Office 365 DLP? voor [meer informatie](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)over de licentievereisten voor DLP.

Klanten die [Endpoint DLP](endpoint-dlp-learn-about.md) gebruiken die in aanmerking komen voor [Teams DLP,](dlp-microsoft-teams.md) zien hun waarschuwingen voor DLP-eindpuntbeleid en Teams DLP-beleidswaarschuwingen in het DLP-dashboard voor waarschuwingsbeheer.

### <a name="licensing-for-alert-configuration-options"></a>Licenties voor configuratieopties voor waarschuwingen

-   Configuratie van een waarschuwing met één gebeurtenis: organisaties met een E1-, F1- of G1-abonnement of een E3- of **G3-abonnement** kunnen alleen waarschuwingsbeleid maken wanneer een waarschuwing wordt geactiveerd telkens wanneer een activiteit plaatsvindt.
-   **Configuratie van geaggregeerde** waarschuwingen: als u statistisch waarschuwingsbeleid wilt configureren op basis van een drempelwaarde, moet u een van de volgende configuraties hebben:
    -   Een E5- of G5-abonnement
    -   Een E1-, F1- of G1-abonnement of een E3- of G3-abonnement met een van de volgende functies:
        -   Office 365 Advanced Threat Protection Plan 2
        -   Microsoft 365 E5 Compliance
        -   Microsoft 365 invoeglicentie voor eDiscovery en Audit

### <a name="roles"></a>Rollen

Als u het DLP-waarschuwingsbeheerdashboard wilt weergeven of de configuratieopties voor waarschuwingen in een DLP-beleid wilt bewerken, moet u lid zijn van een van deze rollengroepen:

-   Compliancebeheerder
-   Compliancegegevensbeheerder
-   Beveiligingsbeheerder
-   Beveiligingsoperator
-   Beveiligingslezer

Als u het DLP-dashboard voor waarschuwingsbeheer wilt openen, hebt u de rol Waarschuwingen beheren en een van de volgende rollen nodig:

-   DLP-compliancebeheer
-   View-Only DLP Compliance Management

## <a name="alert-configuration-experience"></a>Configuratie-ervaring met waarschuwingen

Als u in aanmerking komt voor [statistische](#licensing-for-alert-configuration-options)configuratieopties voor waarschuwingen, ziet u de volgende opties inline in de ontwerpervaring voor DLP-beleid.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Schermafbeelding met opties voor incidentenrapporten voor gebruikers die in aanmerking komen voor statistische configuratieopties voor waarschuwingen." border="false":::

U kunt deze waarschuwingsconfiguratieopties gebruiken om een instelling te configureren die definieert hoe vaak een DLP-regel kan overeenkomen voordat een waarschuwing wordt geactiveerd. Met deze configuratie kunt u een beleid instellen om een waarschuwing te genereren telkens wanneer een activiteit overeenkomt met de beleidsvoorwaarden of wanneer een bepaalde drempel wordt overschreden, op basis van het aantal activiteiten of op basis van het volume van geëfiltreerde gegevens.

Als u in aanmerking komt voor [configuratieopties](#licensing-for-alert-configuration-options)voor een waarschuwing voor één gebeurtenis, ziet u de volgende optie voor de configuratie van waarschuwingen in de ontwerpervaring voor DLP-beleid. Gebruik deze optie om een waarschuwing te maken die telkens wordt verhoogd wanneer een DLP-regel wordt gebruikt vanwege een gebruikersactiviteit.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Schermafbeelding met opties voor incidentrapporten voor gebruikers die in aanmerking komen voor configuratieopties voor een waarschuwing voor één gebeurtenis." border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP-dashboard voor waarschuwingsbeheer

Werken met het DLP-dashboard voor waarschuwingsbeheer:

1.  Ga in [Microsoft 365 compliancecentrum](https://www.compliance.microsoft.com)naar **Preventie van gegevensverlies.**

2.  Selecteer het **tabblad Waarschuwingen** om het dashboard met DLP-waarschuwingen weer te geven.

    -   Kies filters om de lijst met waarschuwingen te verfijnen. Kies **Kolommen aanpassen** om de eigenschappen weer te geven die u wilt zien. U kunt er ook voor kiezen om de waarschuwingen in oplopende of aflopende volgorde in een kolom te sorteren.
    -   Selecteer een waarschuwing om details te zien:

        :::image type="content" source="../media/alert-details.png" alt-text="Schermafbeelding met waarschuwingsdetails in het DLP-dashboard voor waarschuwingsbeheer." border="false":::

1.  Selecteer het **tabblad** Gebeurtenissen om alle gebeurtenissen weer te geven die aan de waarschuwing zijn gekoppeld. U kunt een bepaalde gebeurtenis kiezen om de details ervan weer te geven.
    In de volgende tabel ziet u enkele details van de gebeurtenis.
    
    | Categorie          | Eigenschapsnaam                 | Beschrijving                                                                | Toepasselijke gebeurtenistypen                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Details van de gebeurtenis*||
    |      | Id                            | Unieke id die is gekoppeld aan de gebeurtenis                                        | Alle gebeurtenissen                               |
    |                   | Locatie                      | Werkbelasting waarbij de gebeurtenis is gedetecteerd                                      | Alle gebeurtenissen                               |
    |                   | Tijd van activiteit              | Tijd van de gebruikersactiviteit die de DLP-schending heeft veroorzaakt                    | Alle gebeurtenissen                               |
    |*Beïnvloede entiteiten*||
    |  | Gebruiker                          | Gebruiker die de DLP-schending heeft veroorzaakt                                          | Alle gebeurtenissen                               |
    |                   | Hostname                      | Hostnaam van de computer waarop de DLP-schending is gedetecteerd              | Apparatengebeurtenissen                           |
    |                   | IP-adres                    | IP-adres van de computer                                                  | Apparatengebeurtenissen                           |
    |                   | Bestandspad                     | Absoluut pad van het bestand dat betrokken is bij de schending                        | SharePoint, OneDrive en apparaten gebeurtenissen |
    |                   | E-mailontvangers              | Geadresseerden van de e-mail die het DLP-beleid heeft geschonden                       | Exchange gebeurtenissen                          |
    |                   | E-mail onderwerp                 | Onderwerp van het e-mailbericht dat het DLP-beleid heeft geschonden                          | Exchange gebeurtenissen                          |
    |                   | E-mailbijlagen             | Namen van de bijlagen in de e-mail die het DLP-beleid hebben geschonden         | Exchange gebeurtenissen                          |
    |                   | Site-eigenaar                    | Naam van de site-eigenaar                                                     | SharePoint en OneDrive gebeurtenissen           |
    |                   | Site-URL                      | Volledige URL van de SharePoint of OneDrive site                                | SharePoint en OneDrive gebeurtenissen           |
    |                   | Bestand gemaakt                  | Tijd van het maken van bestanden                                                      | SharePoint en OneDrive gebeurtenissen           |
    |                   | Bestand laatst gewijzigd            | Tijd van de laatste wijziging van het bestand                                  | SharePoint en OneDrive gebeurtenissen           |
    |                   | Bestandsgrootte                     | Grootte van het bestand                                                           | SharePoint en OneDrive gebeurtenissen           |
    |                   | Bestandseigenaar                    | Eigenaar van het bestand                                                          | SharePoint en OneDrive gebeurtenissen           |
    |*Beleidsdetails*||
    |     | DLP-beleid gematched            | Naam van het DLP-beleid dat is gematcht                                    | Alle gebeurtenissen                               |
    |                   | Regel overeenkomend                  | Naam van de DLP-regel in het DLP-beleid dat is gematcht                    | Alle gebeurtenissen                               |
    |                   | Gedetecteerde typen gevoelige informatie | Gevoelige informatietypen die zijn gedetecteerd als onderdeel van het DLP-beleid | Alle gebeurtenissen                               |
    |                   | Acties die zijn ondernomen                 | Acties die zijn genomen als onderdeel van het overeenkomende DLP-beleid                          | Alle gebeurtenissen                               |
    |                   | Beleid voor gebruikers overroeden          | Of de gebruiker het beleid oversroeedt via de beleidstip                | Alle gebeurtenissen                               |
    |                   | Uitvullingstekst overschrijven   | Rechtvaardiging verstrekt om de beleidstip te overschrijven                          | Alle gebeurtenissen                               |
    
1.  Selecteer het **tabblad Gevoelige infotypen** om details weer te geven over de gevoelige informatietypen die in de inhoud zijn gedetecteerd. Details zijn betrouwbaarheid en aantal.

2.  Nadat u de waarschuwing hebt onderzocht, kiest u **Waarschuwing beheren** om de status te wijzigen (**Actief**, **Onderzoeken,** **Afgewezen** of **Opgelost**). U kunt ook opmerkingen toevoegen en de waarschuwing toewijzen aan iemand in uw organisatie.

    -   Als u de geschiedenis van werkstroombeheer wilt bekijken, kiest u **Managementlogboek.**
    -   Nadat u de vereiste actie voor de waarschuwing hebt ondernomen, stelt u de status van de waarschuwing in op **Opgelost.**