---
title: Teamsites maken - Ontwikkel- en testomgeving voor politieke campagnes
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Overzicht: Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8a7002b7d482c987f77907787c5233dcb8d11e9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929382"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a>Maak teamsites in een ontwikkel- en testomgeving voor politieke campagnes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**

- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- 
 **Overzicht:** Maak openbare, privé, gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving voor uw politieke campagne. 
   
Gebruik de instructies in dit artikel om een ontwikkel-/testomgeving te maken met vier verschillende soorten SharePoint Online-teamsites voor de [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)-oplossing. Deze sites worden uitgebreid beschreven in onderwerp 10, getiteld **SharePoint en OneDrive voor Bedrijven**.

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a>Fase 1: Een ontwikkel- en testomgeving voor uw politieke campagnes maken

Volg eerst de instructies in [Groepen en gebruikers configureren voor een ontwikkel-/testomgeving voor uw politieke campagne](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) om uw abonnementen, gebruikers en groepen te maken.

## <a name="phase-2-create-labels"></a>Fase 2: Labels maken

In deze fase maakt u de labels voor de verschillende beveiligingsniveaus van documentenmappen op de SharePoint Online-teamsite.

1. Indien nodig meldt u zich aan bij het beheercentrum met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement. Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Klik op het tabblad **Microsoft Office Home** op de tegel **Beheerder**.

3. Klik op het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Beheercentra > Beveiliging en compliance**.

4. Klik op het nieuwe tabblad **Start - Beveiliging en compliance** van uw browser op **Classificaties > Labels**.

5. Klik in het deelvenster **Start > Labels** op **Label maken**.

6. Typ in het deelvenster **Uw label een naam geven** **Intern** in en klik vervolgens op **Volgende**.

7. Klik in het deelvenster **Labelinstellingen** op **Volgende**.

8. Klik in het deelvenster **Bekijk uw instellingen** op **Dit label maken** en klik vervolgens op **Afsluiten**.

9. Herhaal de stappen 5-8 voor deze extra labels:

   - Privé
   - Gevoelig
   - Zeer vertrouwelijk

10. Klik in het deelvenster **Start > Labels** op **Labels publiceren**.

11. Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.

12. Klik op het deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.

13. Klik op **Gereed**.

14. Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.

15. Klik in het deelvenster **Locaties kiezen** op **Volgende**.

16. Typ in het deelvenster **Uw beleid een naam geven** **Campagne** in bij **Naam** en klik vervolgens op **Volgende**.

17. Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Afsluiten**.

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a>Fase 3: Uw SharePoint Online-teamsites maken

In deze fase kunt u SharePoint Online-teamsites voor uw politieke campagne maken en configureren die overeenkomen met de vier typen SharePoint Online-teamsites.

### <a name="campaign-wide-team-site"></a>Teamsite voor de hele campagne

Als u een openbare SharePoint Online-teamsite wilt maken, gaat u als volgt te werk:

1. Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.

4. Klik op de pagina **Site maken** op **Teamsite**.

5. Typ bij **Sitenaam****Gehele campagne** in.

6. Typ bij **Beschrijving van de teamsite** in **SharePoint-site voor de gehele campagne**.

7. Selecteer bij **Privacy-instellingen** **Publiek: iedereen in de organisatie kan toegang krijgen tot deze site** en klik vervolgens op **Volgende**.

8. Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.

Configureer vervolgens de map met documenten van de teamsite voor de gehele campagne voor het interne label.

1. Klik in het **Gehele campagne-Start**-tabblad van uw browser op **Documenten**.

2. Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.

3. Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.

4. Selecteer bij **Instellingen-Label toepassen** de optie **Intern** en klik vervolgens op **Opslaan**.

### <a name="campaign-project-1-team-site"></a>Teamsite project 1 campagne

Ga als volgt te werk om een privé SharePoint Online-teamsite voor een basislijn van een project in de campagne te maken:

1. Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.

4. Klik op de pagina **Site maken** op **Teamsite**.

5. Typ bij **Sitenaam****Campagneproject 1** in.

6. Typ bij **Beschrijving van de teamsite** **SharePoint-site voor Campagneproject 1** in.

7. Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.

8. Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.

Configureer vervolgens de map met documenten van Campagneproject 1 voor het privélabel.

1. Klik in het **Campagneproject 1-Start**-tabblad van uw browser op **Documenten**.

2. Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.

3. Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.

4. Selecteer in **Instellingen-Label toepassen** de optie **Privé** en klik vervolgens op **Opslaan**.

### <a name="campaign-marketing-team-site"></a>Teamsite voor marketing van de campagne

Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite op gevoelig niveau wilt maken marketingresources van de campagne:

1. Gebruik een browser op je lokale computer om je aan te melden bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.

4. Klik op de pagina **Site maken** op **Teamsite**.

5. Typ bij **Naam van de team site****Marketing voor campagne** in.

6. Typ bij **Beschrijving van de teamsite** **SharePoint-site voor marketing van de campagne (gevoelig)** in.

7. Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.

8. Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.

9. Klik in het nieuwe **Marketing voor campagne**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.

10. Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.

11. Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.

12. Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit, typ **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** in bij **Alle toegangsaanvragen verzenden** en klik vervolgens op **OK**.

13. Klik op **Leden marketing voor campagne** in de lijst.

14. Klik op de pagina **Personen en groepen** op **Nieuw**.

15. Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.

16. Herhaal de stappen 14 en 15 voor de groep **Analytische medewerkers** en het **Regular1**-gebruikersaccount.

17. Klik op de terugknop in uw browser.

18. Klik op **Eigenaren marketing voor campagne** in de lijst.

19. Klik op de pagina **Personen en groepen** op **Nieuw**.

20. Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.

21. Klik op de terugknop in uw browser.

22. Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Marketing voor campagne-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.

Dit zijn de resultaten van het configureren van machtigingen:

- De SharePoint-groep **Marketing voor campagne-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1), de groep **Marketing voor campagne** (deze bevat het gebruikersaccount van de globale beheerder), de groep **Analytisch personeel** (deze bevat het DataScientist1-gebruikersaccount) en het **Regular1**-gebruikersaccount.

- De SharePoint-groep **Marketing voor campagne-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).

- De SharePoint-groep **Marketing voor campagne-Bezoekers** bevat geen groepen of gebruikersaccounts.

- Leden kunnen geen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Marketing voor campagne-Eigenaren**).

- Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende bronnen, maar kunnen wel toegang tot de site vragen, waardoor een e-mail wordt verzonden naar het postvak van het ITAdmin1-gebruikersaccount.

Configureer vervolgens de map met documenten van de teamsite van de marketing voor de campagne voor het interne label.

1. Klik in het **Marketing voor campagne-Start**-tabblad van uw browser op **Documenten**.

2. Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.

3. Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.

4. Selecteer bij **Instellingen-Label toepassen** de optie **Gevoelig** en klik vervolgens op **Opslaan**.

Configureer vervolgens een beleid voor de preventie van gegevensverlies dat gebruikers een melding stuurt wanneer ze een document van de SharePoint Online-teamsite met het label Gevoelig buiten de organisatie delen. Dit DLP-beleid wordt toegepast op resources op de site van de marketing voor de campagne.

1. Klik op het tabblad **Microsoft Office Home** van uw browser op de tegel **Beveiliging en compliance**.

2. Klik op het nieuwe tabblad **Beveiliging en compliance** in uw browser op **Preventie van gegevensverlies > Beleid**.

3. Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.

4. Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast** en klik vervolgens op **Volgende**.

5. Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint Online-teamsites** in bij **Naam** en klik vervolgens op **Volgende**.

6. Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.

7. Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.

8. Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.

9. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.

10. Klik in het deelvenster **Labels** op **+Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen** en klik vervolgens op **Gereed**.

11. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.

12. Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.

13. Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.

14. Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.

15. Typ of plak in het tekstvak de volgende tekst:

    - Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand. Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op. Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.

16. Klik op **OK**.

17. Schakel in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** het selectievakje **Delen door personen niet toestaan en toegang tot gedeelde inhoud beperken** uit en klik vervolgens op **Volgende**.

18. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.

19. Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.

### <a name="campaign-strategy-team-site"></a>Teamsite voor Campagnestrategie

Ga als volgt te werk als u een geïsoleerde SharePoint Online-teamsite wilt maken op het niveau van zeer vertrouwelijke informatie voor de resources van de campagnestrategie:

1. Gebruik indien nodig een browser op je lokale computer en meld je aan bij het beheercentrum (<https://admin.microsoft.com>) met je globale beheerdersaccount.

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe **SharePoint**-tabblad in uw browser op **+ Site maken**.

4. Klik op de pagina **Site maken** op **Teamsite**.

5. Typ bij **Naam van de teamsite****Campagnestrategie** in.

6. Typ bij **Beschrijving van de teamsite** **SharePoint-site voor campagnestrategie (zeer vertrouwelijk)** in.

7. Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.

8. Klik in het **Wie wilt u toevoegen?**-venster op **Voltooien**.

9. Klik in het nieuwe **Campagnestrategie**-tabblad in uw browser in de werkbalk op het instellingenpictogram en vervolgens op **Sitemachtigingen**.

10. Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.

11. Klik in het tabblad nieuwe **Machtigingen**-tabblad in uw browser op **Instellingen voor toegangsaanvragen**.

12. Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **Leden mogen de site en afzonderlijke bestanden en mappen delen**- en **Leden kunnen anderen uitnodigen om ledengroep van de site**-selectievakjes uit (zodat alle drie de selectievakjes leeg zijn) en klik vervolgens op **OK**.

13. Klik op **Leden campagnestrategie** in de lijst.

14. Klik op de pagina **Personen en groepen** op **Nieuw**.

15. Typ in het dialoogvenster **Delen** **Senior en strategische personeel**, selecteer het en klik vervolgens op **Delen**.

16. Klik op **Eigenaren campagnestrategie** in de lijst.

17. Klik op de pagina **Personen en groepen** op **Nieuw**.

18. Typ in het dialoogvenster **Delen** **IT-personeel**, selecteer het en klik vervolgens op **Delen**.

19. Klik op de terugknop in uw browser.

20. Sluit het tabblad **Personen en groepen** in uw browser af, klik op het tabblad **Campagnestrategie-Start** in uw browser en sluit vervolgens het deelvenster **Sitemachtigingen** af.

Dit zijn de resultaten van het configureren van machtigingen:

- De SharePoint-groep **Campagnestrategie-Leden** bevat alleen de groep **Senior en strategische personeel** (deze bevat de gebruikersaccounts voor de Kandidaat, Stafchef en Strategisch1) en de groep **Campagnestrategie** (deze bevat het alleen gebruikersaccount van de globale beheerder).

- De SharePoint-groep **Campagnestrategie-Eigenaren** bevat alleen de groep **IT-personeel** (die alleen de gebruikersaccounts ITAdmin1 en ITAdmin2 bevat).

- De SharePoint-groep **Campagnestrategie-Bezoekers** bevat geen groepen of gebruikersaccounts.

- Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden uitgevoerd door leden van de groep **Campagnestrategie-Eigenaren**).

- Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen. Aanvullende machtigingen voor de site moeten worden uitgevoerd door de globale beheerder of door een lid van de groep **Campagnestrategie-Eigenaren**.

Configureer vervolgens de documentenmap van de Campagnestrategie-teamsite voor het label Zeer vertrouwelijk.

1. Klik in het tabblad **Campagnestrategie-Start** in uw browser op **Documenten**.

2. Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.

3. Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.

4. Selecteer in **Instellingen-Label toepassen** de optie **Zeer vertrouwelijk** en klik vervolgens op **Opslaan**.

Configureer vervolgens een beleid voor de preventie van gegevensverlies dat gebruikers blokkeert wanneer ze een document van de SharePoint Online-teamsite met het label Zeer vertrouwelijk buiten de organisatie delen. Dit beleid wordt toegepast op resources op de site van de Campagnestrategie.

1. Gebruik indien nodig een browser op uw lokale computer en meld u aan bij het beheercentrum (<https://admin.microsoft.com>) met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder.

2. Klik op het tabblad **Microsoft Office Home** van uw browser op de tegel **Beveiliging en compliance**.

3. Klik op het nieuwe tabblad **Beveiliging en compliance** in uw browser op **Preventie van gegevensverlies > Beleid**.

4. Klik in het deelvenster **Preventie van gegevensverlies** op **+ Een beleid maken**.

5. Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast** en klik vervolgens op **Volgende**.

6. Typ in het deelvenster **Uw beleid een naam geven** **Label Zeer vertrouwelijk voor SharePoint-sites** in bij **Naam** en klik vervolgens op **Volgende**.

7. Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.

8. Schakel in de locatielijst de locaties van **Exchange-e-mail** en **OneDrive-accounts** uit en klik vervolgens op **Volgende**.

9. Klik in het deelvenster **Het type gevoelige inhoud dat u wilt beveiligen aanpassen** op **Bewerken**.

10. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Labels**.

11. Klik in het deelvenster **Labels** op **+ Toevoegen**, selecteer het label **Zeer Vertrouwelijk**, klik op **Toevoegen** en klik vervolgens op **Gereed**.

12. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.

13. Klik in het deelvenster **De typen gevoelige inhoud aanpassen die u wilt beveiligen** op **Volgende**.

14. Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.

15. Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.

16. Typ of plak in het tekstvak de volgende tekst:

    - Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand. Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op. Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.

17. Klik op **OK**.

18. In het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?**, selecteert u **Een zakelijke reden vereisen om te overschrijven** en klikt u vervolgens op **Volgende**.

19. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.

20. Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Afsluiten**.

Gebruik de instructies in [Azure RMS activeren met het Microsoft 365-beheercentrum](/information-protection/deploy-use/activate-office365).

Configureer vervolgens Azure Information Protection met een nieuw beleid en een sublabel voor bescherming en machtigingen met de volgende stappen:

1. Meld u aan met een account met de rol Beveiligingsbeheerder of Bedrijfsbeheerder. Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Open een afzonderlijk tabblad in je browser en ga naar de Microsoft Azure-portal (<https://portal.azure.com>).

3. Typ in het deelvenster **informatie** en klik vervolgens op **Azure Information Protection**.

4. Klik op **Labels**.

5. Klik met de rechtermuisknop op het **Zeer vertrouwelijk**-label en klik vervolgens op **Voeg een sublabel toe**.

6. Typ **CampagneStrategie** in bij **Naam** en **Label voor documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.

7. Klik bij **Machtigingen instellen voor documenten en e-mail met dit label** op **Beveiligen**.

8. Klik in de sectie **Bescherming** op **Azure (cloud key)**.

9. Klik in het **Bescherming**-tabblad onder **Beschermingsinstellingen** op **+ Machtigingen toevoegen**.

10. Klik in het **Machtigingen toevoegen**-tabblad onder **Gebruikers en groepen specificeren** op **+ Adreslijst zoeken**.

11. Selecteer in het deelvenster **AAD-gebruikers en -groepen** **Senior en strategisch personeel** en klik vervolgens op **Selecteren**.

12. Klik onder **Kies vooraf ingestelde of aangepaste machtigingen** op **Aangepast** en klik vervolgens op de selectievakjes **Weergaverechten**, **Inhoud bewerken**, **Opslaan**, **Beantwoorden** en **Allen beantwoorden**.

13. Klik tweemaal op **OK**.

14. Klik in het **Sublabel**-tabblad op **Opslaan** en klik vervolgens op **OK**.

15. Klik in het **Azure Information Protection**-tabblad op **Beleid > + Een nieuw beleid toevoegen**.

16. Typ **CampagneStrategie** in bij **Naam** en **Documenten in de teamsite van de campagnestrategie** bij **Beschrijving**.

17. Klik op **Selecteer de gebruikers of groepen aan wie u dit beleid wilt toewijzen > Gebruikers/groepen** en selecteer vervolgens **Senior en strategisch personeel**.

18. Klik vervolgens op **Selecteren \> OK**.

19. Klik op **Labels toevoegen of verwijderen**. Klik in het deelvenster **Beleid: Labels toevoegen of verwijderen** op **CampagneStrategie** en klik vervolgens op **OK**.

20. Klik op **Opslaan** en klik vervolgens op **OK**.

U bent nu klaar om te beginnen met het maken van documenten op deze vier sites en het testen van de toegang hiertoe met verschillende gebruikersaccounts.

Als u een document met Azure Information Protection en dit nieuwe label wilt beveiligen, moet u [de Azure Information Protection-client installeren](/information-protection/rms-client/install-client-app) op een testcomputer, Office installeren vanuit het beheercentrum en u vervolgens aanmelden bij Microsoft Word met een account uit de groep **Senior en strategisch personeel** van uw proefabonnement.

## <a name="see-also"></a>Zie ook

[Beveiligingsrichtlijnen van Microsoft voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[Cloud adoption Test Lab Guides (TLGs)](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Microsoft 365-oplossings- en -architectuurcentrum](../../solutions/index.yml)