---
title: Een verbindingslijn instellen voor het archiveren van Gegevens van Het bericht van Bloomberg
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Beheerders kunnen een gegevensconnector instellen voor het importeren en archiveren van gegevens uit het e-mailhulpprogramma van Het bericht van Bloomberg in Microsoft 365. Op deze manier kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, Inhoud zoeken en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 7029b95e4b9ceb91859e2a4b38afb5205e3307b2
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162380"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Een verbindingslijn instellen voor het archiveren van Gegevens van Het bericht van Bloomberg

Gebruik een gegevensconnector in het Microsoft 365 compliancecentrum om e-mailgegevens van financiële services te importeren en te archiveren vanuit het samenwerkingshulpmiddel [Van Het bericht van Bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, wordt er eenmaal per dag verbinding gemaakt met de beveiligde FTP-site (SFTP) van uw organisatie en worden e-mailitems geïmporteerd in postvakken in Microsoft 365.

Nadat gegevens van Het bericht van Bloomberg zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties zoals Bewaring van rechtszaken, inhoud zoeken, Archiveren, auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op Gegevens van Het bericht van Bloomberg. U kunt bijvoorbeeld e-mailberichten van Het Bericht van Bloomberg doorzoeken met behulp van het zoekprogramma voor inhoud of het postvak met de Gegevens van Het Bericht van Bloomberg koppelen aan een bewaarder in een Advanced eDiscovery geval. Als u een Verbindingslijn voor Het Bericht van Bloomberg gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Overzicht van het archiveren van Gegevens van Het Bericht van Bloomberg

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van Gegevens van Het Bericht van Bloomberg in een Microsoft 365.

![Import- en archiefproces van Het bericht van Bloomberg](../media/BloombergMessageArchiving.png)

1. Uw organisatie werkt samen met Bloomberg om een SFTP-site voor Bloomberg in te stellen. U werkt ook samen met Bloomberg om Het Bericht van Bloomberg te configureren om e-mailberichten te kopiëren naar de SFTP-site van Bloomberg.

2. Elke 24 uur worden e-mailberichten van Het Bericht van Bloomberg gekopieerd naar de SFTP-site van Bloomberg.

3. De Verbindingslijn van Het Bericht van Bloomberg die u maakt in het Microsoft 365 compliancecentrum maakt elke dag verbinding met de SFTP-site van Bloomberg en brengt de e-mailberichten van de afgelopen 24 uur over naar een beveiligd Azure Storage-gebied in de Microsoft Cloud.

4. De connector importeert de e-mailberichtitems naar het postvak van een specifieke gebruiker. Er wordt een nieuwe map met de naam BloombergMessage gemaakt in het postvak van de specifieke gebruiker en de items worden in het postvak geïmporteerd.

   De verbindingslijn doet dit met behulp van de waarde van de eigenschap CorporateEmailAddress. Elk e-mailbericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het e-mailbericht. Naast automatische gebruikerstoewijzing met de waarde van de *eigenschap CorporateEmailAddress,* kunt u ook een aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Dit toewijzingsbestand bevat een UUID van Bloomberg en het bijbehorende Microsoft 365 voor elke gebruiker in uw organisatie. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing biedt, wordt voor elk e-mailitem eerst het bestand voor aangepaste toewijzing door de verbindingslijn verkend. Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met de UUID van Bloomberg van een gebruiker, gebruikt de connector de eigenschap *CorporateEmailAddress* van het e-mailitem. Als de verbindingslijn geen geldige Microsoft 365-gebruiker vindt in het bestand voor aangepaste toewijzing of de eigenschap *CorporateEmailAddress* van het e-mailitem, wordt het item niet geïmporteerd.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

Sommige implementatiestappen die nodig zijn voor het archiveren van Gegevens van Het bericht van Bloomberg zijn extern Microsoft 365 en moeten zijn voltooid voordat u de verbindingslijn in het compliancecentrum kunt maken.

- Als u een Verbindingslijn voor Het Bericht van Bloomberg wilt instellen, moet u toetsen en wachtwoordzinnen gebruiken voor Pretty Good Privacy (PGP) en Secure Shell (SSH). Deze sleutels worden gebruikt om de SFTP-site van Bloomberg te configureren en door de connector te gebruiken om verbinding te maken met de SFTP-site van Bloomberg om gegevens te importeren in Microsoft 365. De PGP-toets wordt gebruikt om de versleuteling te configureren van gegevens die worden overgebracht van de SFTP-site van Bloomberg naar Microsoft 365. De SSH-toets wordt gebruikt om secure shell te configureren om een veilige externe aanmelding in te stellen wanneer de verbindingslijn verbinding maakt met de SFTP-site van Bloomberg.

  Wanneer u een verbindingslijn instelt, hebt u de optie om openbare sleutels en wachtwoordzinnen van Microsoft te gebruiken of kunt u uw eigen privésleutels en wachtwoordzin gebruiken. U wordt aangeraden de openbare sleutels van Microsoft te gebruiken. Als uw organisatie echter al een SFTP-site van Bloomberg heeft geconfigureerd met privésleutels, kunt u een verbindingslijn maken met dezelfde persoonlijke sleutels.

- Abonneer u op [Bloomberg Anywhere.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Dit is vereist, zodat u zich kunt aanmelden bij Bloomberg Anywhere om toegang te krijgen tot de SFTP-site van Bloomberg die u moet instellen en configureren.

- Een SFTP-site (Secure file transfer protocol) instellen. Nadat u met Bloomberg hebt gewerkt om de SFTP-site in te stellen, worden gegevens van Het Bericht van Bloomberg elke dag geüpload naar de SFTP-site. De verbindingslijn die u in stap 2 maakt, maakt verbinding met deze SFTP-site en draagt de e-mailgegevens over naar Microsoft 365 postvakken. SFTP versleutelt ook de Gegevens van het Bericht van Bloomberg die tijdens het overdrachtsproces naar postvakken worden verzonden.

  Voor informatie over Bloomberg SFTP (ook wel *BB-SFTP genoemd):*

  - Zie het document 'SFTP Connectivity Standards' bij [Ondersteuning voor Bloomberg.](https://www.bloomberg.com/professional/support/documentation/)

  - Neem contact [op met de klantenondersteuning van Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

- Nadat u met Bloomberg hebt gewerkt om een SFTP-site in te stellen, geeft Bloomberg u enkele informatie nadat u hebt gereageerd op het e-mailbericht van de Implementatie van Bloomberg. Sla een kopie van de volgende gegevens op. U gebruikt deze verbindingslijn om een verbindingslijn in te stellen in stap 3.

  - Vaste code, een id voor uw organisatie en wordt gebruikt om u aan te melden bij de SFTP-site van Bloomberg.

  - Wachtwoord voor uw SFTP-site van Bloomberg

  - URL voor De SFTP-site van Bloomberg (bijvoorbeeld sftp.bloomberg.com). Daarnaast kan Bloomberg ook een bijbehorend IP-adres opgeven voor de SFTP-site van Bloomberg, die ook kan worden gebruikt om de connector in te stellen.

  - Poortnummer voor SFTP-site van Bloomberg

- Met de Verbindingslijn Bericht van Bloomberg kunt u in totaal 200.000 items in één dag importeren. Als er meer dan 200.000 items op de SFTP-site staan, worden geen van deze items geïmporteerd in Microsoft 365.

- De gebruiker die een Connector voor Het bericht van Bloomberg maakt in stap 3 (en die de openbare sleutels en het IP-adres downloadt in stap 1), moet de rol Postvak importeren exporteren in Exchange Online. Dit is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="set-up-a-connector-using-public-keys"></a>Een verbindingslijn instellen met openbare sleutels

In de stappen in deze sectie ziet u hoe u een Connector voor Een Bericht van Bloomberg in kunt stellen met de openbare sleutels voor Pretty Good Privacy (PGP) en Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Stap 1: Openbare PGP- en SSH-sleutels verkrijgen

De eerste stap is het verkrijgen van een kopie van de openbare PGP- en SSH-sleutels. U gebruikt deze sleutels in stap 2 om de SFTP-site van Bloomberg zo te configureren dat de verbindingslijn (die u maakt in stap 3) verbinding kan maken met de SFTP-site en de e-mailgegevens van Het Bericht van Bloomberg kan overbrengen naar Microsoft 365 postvakken. U verkrijgt ook een IP-adres in deze stap, dat u gebruikt bij het configureren van de SFTP-site van Bloomberg.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **Het bericht van Bloomberg** op **Weergeven.**

3. Klik op **de pagina Productbeschrijving** van Het bericht van Bloomberg op **Verbindingslijn toevoegen**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil openbare PGP- en SSH-sleutels van **Microsoft gebruiken.**

   ![Selecteer de optie voor het gebruik van openbare sleutels](../media/BloombergMessagePublicKeysOption.png)

6. Klik onder stap 1 op **de SSH-toets** Downloaden, **PGP-toets** downloaden en IP-adreskoppelingen downloaden om een kopie van elk bestand op uw lokale computer op te slaan. 

   ![Koppelingen om openbare sleutels en IP-adres te downloaden](../media/BloombergMessagePublicKeyDownloadLinks.png)

   Deze bestanden bevatten de volgende items die worden gebruikt om de SFTP-site van Bloomberg in stap 2 te configureren:

   - Openbare PGP-sleutel: deze sleutel wordt gebruikt om de versleuteling te configureren van gegevens die worden overgebracht van de SFTP-site van Bloomberg naar Microsoft 365.

   - Openbare SSH-sleutel: deze sleutel wordt gebruikt om beveiligde shell te configureren om een veilige externe aanmelding in te stellen wanneer de verbindingslijn verbinding maakt met de SFTP-site van Bloomberg.

   - IP-adres: De SFTP-site van Bloomberg is geconfigureerd voor het accepteren van verbindingsaanvragen vanaf dit IP-adres. Hetzelfde IP-adres wordt door de Verbindingslijn van Het Bericht van Bloomberg gebruikt om verbinding te maken met de SFTP-site en om gegevens van Het Bericht van Bloomberg over te brengen naar Microsoft 365.

7. Klik **op Annuleren** om de wizard te sluiten. U gaat terug naar deze wizard in stap 3 om de verbindingslijn te maken.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>Stap 2: De SFTP-site van Bloomberg configureren

> [!NOTE]
> Als uw organisatie eerder een SFTP-site van Bloomberg heeft ingesteld om Instant Bloomberg-gegevens te archiveren met openbare PGP- en SSH-sleutels, hoeft u geen andere site in te stellen. U kunt dezelfde SFTP-site opgeven wanneer u de verbindingslijn maakt in stap 3.

De volgende stap is het gebruik van de openbare PGP- en SSH-sleutels en het IP-adres dat u hebt verkregen in stap 1 om PGP-versleuteling en SSH-verificatie te configureren voor de SFTP-site van Bloomberg. Hierdoor kan de Verbindingslijn van Het Bericht van Bloomberg die u maakt in stap 3 verbinding maken met de SFTP-site van Bloomberg en de gegevens van het Bericht van Bloomberg overbrengen naar Microsoft 365. U moet samenwerken met de klantenondersteuning van Bloomberg om uw SFTP-site voor Bloomberg in te stellen. Neem contact [op met de klantenondersteuning](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) van Bloomberg voor hulp.

> [!IMPORTANT]
> U wordt aangeraden de drie bestanden die u in stap 1 hebt gedownload, bij te koppelen aan een e-mailbericht en deze te verzenden naar het klantenserviceteam wanneer u met hen werkt om uw SFTP-site van Bloomberg in te stellen.

### <a name="step-3-create-a-bloomberg-message-connector"></a>Stap 3: Een Verbindingslijn voor Het bericht van Bloomberg maken

De laatste stap is het maken van een Verbindingslijn voor Het Bericht van Bloomberg in het Microsoft 365 compliancecentrum. De connector gebruikt de informatie die u verstrekt om verbinding te maken met de SFTP-site van Bloomberg en e-mailberichten over te brengen naar de bijbehorende postvakken van gebruikers in Microsoft 365.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **Het bericht van Bloomberg** op **Weergeven.**

3. Klik op **de pagina Productbeschrijving** van Het bericht van Bloomberg op **Verbindingslijn toevoegen**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil openbare PGP- en SSH-sleutels van **Microsoft gebruiken.**

6. Voer onder Stap 3 de vereiste gegevens in de volgende vakken in en klik vervolgens **op Verbinding valideren**.

      - **Naam:** De naam voor de verbindingslijn. Deze moet uniek zijn in uw organisatie.

      - **Vaste code:** De id voor uw organisatie die wordt gebruikt als gebruikersnaam voor de SFTP-site van Bloomberg.

      - **Wachtwoord:** Het wachtwoord voor de SFTP-site van Uw organisatie.

      - **SFTP-URL:** De URL voor de SFTP-site van Bloomberg `sftp.bloomberg.com` (bijvoorbeeld). U kunt ook een IP-adres voor deze waarde gebruiken.

      - **SFTP-poort:** Het poortnummer voor de SFTP-site van Bloomberg. De verbindingslijn gebruikt deze poort om verbinding te maken met de SFTP-site.

7. Nadat de verbinding is gevalideerd, klikt u op **Volgende.**

8. Schakel op **de pagina Map Bloomberg Message-gebruikers Microsoft 365 automatische** gebruikerstoewijzing in en geef zo nodig aangepaste gebruikerstoewijzing aan.

   > [!NOTE]
   > De verbindingslijn importeert berichtitems naar het postvak van een specifieke gebruiker. Er wordt een nieuwe map met de naam **BloombergMessage** gemaakt in het postvak van de specifieke gebruiker en de items worden in het postvak geïmporteerd. De verbindingslijn gebruikt de waarde van de *eigenschap CorporateEmailAddress.* Elk chatbericht bevat deze eigenschap en de eigenschap wordt gevuld met het e-mailadres van elke deelnemer aan het chatbericht. Naast automatische gebruikerstoewijzing met de waarde van de *eigenschap CorporateEmailAddress,* kunt u ook aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Het toewijzingsbestand moet het UUID-adres van Bloomberg en het bijbehorende Microsoft 365 voor elke gebruiker bevatten. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing geeft, wordt voor elk berichtitem eerst naar aangepast toewijzingsbestand gekijken. Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met de UUID van Bloomberg van een gebruiker, gebruikt de verbindingslijn de eigenschap *CorporateEmailAddress* van het chatitem. Als de verbindingslijn geen geldige Microsoft 365 gebruiker vindt in het aangepaste toewijzingsbestand of de *eigenschap CorporateEmailAddress* van het berichtitem, wordt het item niet geïmporteerd.

9. Klik **op Volgende,** bekijk de instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

10. Ga naar de **pagina Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken. Klik op de verbindingslijn om de flyoutpagina weer te geven, die informatie over de verbindingslijn bevat.

## <a name="set-up-a-connector-using-private-keys"></a>Een verbindingslijn instellen met behulp van persoonlijke sleutels

In de stappen in deze sectie ziet u hoe u een Verbindingslijn voor Het Bericht van Bloomberg kunt instellen met PGP- en SSH-privésleutels. Deze optie voor het instellen van verbindingslijnen is bedoeld voor organisaties die al een SFTP-site van Bloomberg hebben geconfigureerd met behulp van privésleutels.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>Stap 1: Een IP-adres verkrijgen om de SFTP-site van Bloomberg te configureren

> [!NOTE]
> Als uw organisatie eerder een SFTP-site van Bloomberg heeft geconfigureerd om Instant Bloomberg-gegevens te archiveren met PGP- en SSH-privésleutels, hoeft u geen andere site te configureren. U kunt dezelfde SFTP-site opgeven wanneer u de verbindingslijn maakt in stap 2.

Als uw organisatie PGP- en SSH-privésleutels heeft gebruikt om een SFTP-site van Bloomberg in te stellen, moet u een IP-adres verkrijgen en dit aan de klantenondersteuning van Bloomberg verstrekken. De SFTP-site van Bloomberg moet zijn geconfigureerd om verbindingsaanvragen vanaf dit IP-adres te accepteren. Hetzelfde IP-adres wordt door de Verbindingslijn van Het Bericht van Bloomberg gebruikt om verbinding te maken met de SFTP-site en om gegevens van Het Bericht van Bloomberg over te brengen naar Microsoft 365.

Het IP-adres verkrijgen:

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **Het bericht van Bloomberg** op **Weergeven.**

3. Klik op **de pagina Productbeschrijving** van Het bericht van Bloomberg op **Verbindingslijn toevoegen**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil PGP- en **SSH-persoonlijke** sleutels gebruiken.

6. Klik onder stap 1 op **IP-adres downloaden** om een kopie van het IP-adresbestand op uw lokale computer op te slaan.

   ![Het IP-adres downloaden](../media/BloombergMessageConnectorIPAddress.png)

7. Klik **op Annuleren** om de wizard te sluiten. U gaat terug naar deze wizard in stap 2 om de verbindingslijn te maken.

U moet samenwerken met de klantenondersteuning van Bloomberg om uw SFTP-site van Bloomberg te configureren om verbindingsaanvragen te accepteren vanaf dit IP-adres. Neem contact [op met de klantenondersteuning](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) van Bloomberg voor hulp.

### <a name="step-2-create-a-bloomberg-message-connector"></a>Stap 2: Een Verbindingslijn voor Het bericht van Bloomberg maken

Nadat uw SFTP-site voor Bloomberg is geconfigureerd, is de volgende stap het maken van een Verbindingslijn voor Het Bericht van Bloomberg in het Microsoft 365 compliancecentrum. De connector gebruikt de informatie die u verstrekt om verbinding te maken met de SFTP-site van Bloomberg en e-mailberichten over te brengen naar de bijbehorende postvakken van gebruikers in Microsoft 365. Als u deze stap wilt voltooien, moet u kopieën hebben van dezelfde privésleutels en wachtwoordzinnen die u hebt gebruikt om uw SFTP-site van Bloomberg in te stellen.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **Het bericht van Bloomberg** op **Weergeven.**

3. Klik op **de pagina Productbeschrijving** van Het bericht van Bloomberg op **Verbindingslijn toevoegen**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil PGP- en **SSH-persoonlijke** sleutels gebruiken.

   ![Selecteer de optie voor het gebruik van persoonlijke sleutels](../media/BloombergMessagePrivateKeysOption.png)

6. Voer onder Stap 3 de vereiste gegevens in de volgende vakken in en klik vervolgens **op Verbinding valideren**.

      - **Naam:** De naam voor de verbindingslijn. Deze moet uniek zijn in uw organisatie.

      - **Vaste code:** De id voor uw organisatie die wordt gebruikt als gebruikersnaam voor de SFTP-site van Bloomberg.

      - **Wachtwoord:** Het wachtwoord voor de SFTP-site van Uw organisatie.

      - **SFTP-URL:** De URL voor de SFTP-site van Bloomberg `sftp.bloomberg.com` (bijvoorbeeld). U kunt ook een IP-adres voor deze waarde gebruiken.

      - **SFTP-poort:** Het poortnummer voor de SFTP-site van Bloomberg. De verbindingslijn gebruikt deze poort om verbinding te maken met de SFTP-site.

      - **PGP-privésleutel:** De PGP-privésleutel voor de SFTP-site van Bloomberg. Zorg ervoor dat u de volledige persoonlijke sleutelwaarde op moet nemen, inclusief de begin- en eindlijnen van het sleutelblok.

      - **Wachtwoordzin PGP-toets:** De wachtwoordzin voor de persoonlijke PGP-sleutel.

      - **SSH-privésleutel:** De SSH-privésleutel voor de SFTP-site van Bloomberg. Zorg ervoor dat u de volledige persoonlijke sleutelwaarde op moet nemen, inclusief de begin- en eindlijnen van het sleutelblok.

      - **SSH-toets passphrase:** De wachtwoordzin voor de SSH-privésleutel.

7. Nadat de verbinding is gevalideerd, klikt u op **Volgende.**

8. Schakel op **de pagina Map Bloomberg Message-gebruikers Microsoft 365 automatische** gebruikerstoewijzing in en geef zo nodig aangepaste gebruikerstoewijzing aan.

   > [!NOTE]
   > De verbindingslijn importeert berichtitems naar het postvak van een specifieke gebruiker. Er wordt een nieuwe map met de naam **BloombergMessage** gemaakt in het postvak van de specifieke gebruiker en de items worden in het postvak geïmporteerd. De verbindingslijn gebruikt de waarde van de *eigenschap CorporateEmailAddress.* Elk chatbericht bevat deze eigenschap en de eigenschap wordt gevuld met het e-mailadres van elke deelnemer aan het chatbericht. Naast automatische gebruikerstoewijzing met de waarde van de *eigenschap CorporateEmailAddress,* kunt u ook aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Het toewijzingsbestand moet het UUID-adres van Bloomberg en het bijbehorende Microsoft 365 voor elke gebruiker bevatten. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing geeft, wordt voor elk berichtitem eerst naar aangepast toewijzingsbestand gekijken. Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met de UUID van Bloomberg van een gebruiker, gebruikt de verbindingslijn de eigenschap *CorporateEmailAddress* van het chatitem. Als de verbindingslijn geen geldige Microsoft 365 gebruiker vindt in het aangepaste toewijzingsbestand of de *eigenschap CorporateEmailAddress* van het berichtitem, wordt het item niet geïmporteerd.

9. Klik **op Volgende,** bekijk de instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

10. Ga naar de **pagina Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken. Klik op de verbindingslijn om de flyoutpagina weer te geven, die informatie over de verbindingslijn bevat.

## <a name="known-issues"></a>Bekende problemen

- Threading van e-mail van Het bericht van Bloomberg dat Microsoft 365 wordt niet ondersteund. Afzonderlijke berichten die naar een persoon worden verzonden, worden geïmporteerd, maar worden niet weergegeven in een discussielijngesprek. Microsoft werkt aan ondersteuning voor threading in latere versies van de Gegevensconnector van Het bericht van Bloomberg.
