---
title: Een connector instellen voor het archiveren van ICE Chat-gegevens
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
description: Beheerders kunnen een verbindingslijn instellen voor het importeren en archiveren van gegevens uit het ice-chatprogramma in Microsoft 365. Op deze manier kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 958a6dde0a4f23933ef6328719fbf43265420c7c
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2021
ms.locfileid: "52162779"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Een connector instellen voor het archiveren van ICE Chat-gegevens

Gebruik een native connector in het Microsoft 365 compliancecentrum om chatgegevens van financiële services te importeren en te archiveren vanuit het samenwerkingshulpmiddel ICE Chat. Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, maakt deze eenmaal per dag verbinding met de SFTP-site (ICE Chat secure FTP) van uw organisatie, converteert u de inhoud van chatberichten naar een e-mailberichtindeling en importeert u deze items vervolgens in postvakken in Microsoft 365.

Nadat ICE-chatgegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties zoals bewaring van rechtszaken, eDiscovery, archiveren, auditing, communicatie compliance en Microsoft 365 bewaarbeleid toepassen op ICE Chat-gegevens. U kunt bijvoorbeeld zoeken in ICE Chat-berichten met inhoud zoeken of het postvak met de ICE Chat-gegevens koppelen aan een bewaarder in een Advanced eDiscovery geval. Als u een ICE Chat-connector gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-ice-chat-data"></a>Overzicht van het archiveren van ICE Chat-gegevens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om ICE-chatgegevens te archiveren in Microsoft 365.

![Ice Chat-archiveringswerkstroom](../media/ICEChatConnectorWorkflow.png)

1. Uw organisatie werkt samen met ICE Chat om een ICE Chat SFTP-site in te stellen. U werkt ook met ICE Chat om ICE Chat te configureren om chatberichten te kopiëren naar uw ICE Chat SFTP-site.

2. Elke 24 uur worden chatberichten van ICE Chat gekopieerd naar uw ICE Chat SFTP-site.

3. De ICE Chat-connector die u maakt in het Microsoft 365 compliancecentrum maakt elke dag verbinding met de ICE Chat SFTP-site en brengt de chatberichten van de afgelopen 24 uur over naar een veilige Azure Storage-locatie in de Microsoft-cloud. De connector converteert ook de inhoud van een chat masseerfunctie naar een e-mailberichtindeling.

4. De connector importeert chatberichten naar de postvakken van specifieke gebruikers. Er wordt een nieuwe map met de naam **ICE Chat** gemaakt in de postvakken van de gebruiker en de chatberichten worden geïmporteerd in die map. De verbindingslijn gebruikt de waarde van de eigenschappen *SenderEmail* *en RecipientEmail.* Elk chatbericht bevat deze eigenschappen, die worden ingevuld met het e-mailadres van de afzender en elke geadresseerde/deelnemer van het chatbericht.

   Naast automatische gebruikerstoewijzing waarbij de waarden van de eigenschap *SenderEmail* en *RecipientEmail* worden gebruikt (wat betekent dat de connector een chatbericht importeert naar het postvak van de afzender en de postvakken van elke geadresseerde), kunt u ook aangepaste gebruikerstoewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Dit toewijzingsbestand bevat de ICE Chat *ImId* en het bijbehorende Microsoft 365 postvak voor elke gebruiker in uw organisatie. Als u automatische gebruikerstoewijzing inschakelen en een bestand voor aangepaste toewijzing op te geven, wordt voor elk chatitem eerst het bestand voor aangepaste toewijzing door de verbindingslijn verkend. Als er geen geldig Microsoft 365-gebruikersaccount wordt gevonden dat overeenkomt met de ICE Chat ImId van een gebruiker, gebruikt de verbindingslijn de eigenschappen *SenderEmail* en *RecipientEmail* van het chatitem om het item te importeren in de postvakken van de chatdeelnemers. Als de connector geen geldige Microsoft 365 in het bestand voor aangepaste toewijzing of de eigenschappen *SenderEmail* en *RecipientEmail* vindt, wordt het item niet geïmporteerd.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

Sommige implementatiestappen die nodig zijn om ICE Chat-gegevens te archiveren, zijn extern Microsoft 365 en moeten zijn voltooid voordat u de verbindingslijn in het compliancecentrum kunt maken.

- ICE Chat brengt hun klanten kosten in rekening voor externe naleving. Uw organisatie moet contact opnemen met de ICE Chat-verkoopgroep om te bespreken en de ICE Chat-gegevensservicesovereenkomst te ondertekenen, die u kunt verkrijgen op [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Deze overeenkomst is tussen ICE Chat en uw organisatie en heeft geen betrekking op Microsoft. Nadat u een ICE Chat SFTP-site hebt ingesteld in stap 2, biedt ICE Chat de FTP-referenties rechtstreeks aan uw organisatie. Vervolgens moet u die referenties aan Microsoft opgeven bij het instellen van de connector in stap 3.

- U moet een ICE Chat SFTP-site instellen voordat u de verbindingslijn maakt in stap 3. Nadat u met ICE Chat hebt gewerkt om de SFTP-site in te stellen, worden gegevens van ICE Chat elke dag geüpload naar de SFTP-site. De verbindingslijn die u in stap 3 maakt, maakt verbinding met deze SFTP-site en verplaatst de chatgegevens naar Microsoft 365 postvakken. SFTP versleutelt ook de ICE Chat-gegevens die tijdens het overdrachtsproces naar postvakken worden verzonden.

- Als u een ICE Chat-connector wilt instellen, moet u toetsen en wachtwoordzinnen gebruiken voor Pretty Good Privacy (PGP) en Secure Shell (SSH). Deze sleutels worden gebruikt om de ICE Chat SFTP-site te configureren en worden door de connector gebruikt om verbinding te maken met de ICE Chat SFTP-site om gegevens te importeren in Microsoft 365. De PGP-toets wordt gebruikt om de versleuteling te configureren van gegevens die worden overgebracht van de ICE Chat SFTP-site naar Microsoft 365. De SSH-toets wordt gebruikt om beveiligde shell te configureren om een veilige externe aanmelding in te stellen wanneer de verbindingslijn verbinding maakt met de ICE Chat SFTP-site.

  Wanneer u een verbindingslijn instelt, hebt u de optie om openbare sleutels en wachtwoordzinnen van Microsoft te gebruiken of kunt u uw eigen privésleutels en wachtwoordzin gebruiken. U wordt aangeraden de openbare sleutels van Microsoft te gebruiken. Als uw organisatie echter al een ICE Chat SFTP-site heeft geconfigureerd met privésleutels, kunt u een verbindingslijn maken met dezelfde persoonlijke sleutels.

- De ICE Chat-connector kan in totaal 200.000 items in één dag importeren. Als er meer dan 200.000 items op de SFTP-site staan, worden geen van deze items geïmporteerd in Microsoft 365.

- De beheerder die de ICE Chat-connector maakt in stap 3 (en die de openbare sleutels en het IP-adres downloadt in stap 1), moet de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="set-up-a-connector-using-public-keys"></a>Een verbindingslijn instellen met openbare sleutels

In de stappen in deze sectie ziet u hoe u een ICE Chat-connector kunt instellen met de openbare sleutels voor Pretty Good Privacy (PGP) en Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Stap 1: Openbare PGP- en SSH-sleutels verkrijgen

De eerste stap is het verkrijgen van een kopie van de openbare sleutels voor Pretty Good Privacy (PGP) en Secure Shell (SSH). U gebruikt deze toetsen in stap 2 om de ICE Chat SFTP-site zo te configureren dat de connector (die u maakt in stap 3) verbinding kan maken met de SFTP-site en de ICE Chat-gegevens kan overbrengen naar Microsoft 365 postvakken. U krijgt ook een IP-adres in deze stap, dat u gebruikt bij het configureren van de ICE Chat SFTP-site.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **ICE Chat** op **Weergeven.**

3. Klik op **de pagina ICE-chat** op **Verbindingslijn toevoegen.**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil openbare PGP- en SSH-sleutels van **Microsoft gebruiken.**

   ![Selecteer de optie voor het gebruik van openbare sleutels](../media/ICEChatPublicKeysOption.png)

6. Klik onder stap 1 op **de SSH-toets** Downloaden, **PGP-toets** downloaden en IP-adreskoppelingen downloaden om een kopie van elk bestand op uw lokale computer op te slaan. 

   ![Koppelingen om openbare sleutels en IP-adres te downloaden](../media/ICEChatPublicKeyDownloadLinks.png)

   Deze bestanden bevatten de volgende items die worden gebruikt voor het configureren van de ICE Chat SFTP-site in stap 2:

   - Openbare PGP-sleutel: deze sleutel wordt gebruikt om de versleuteling te configureren van gegevens die worden overgebracht van de ICE Chat SFTP-site naar Microsoft 365.

   - Openbare SSH-sleutel: deze sleutel wordt gebruikt om Secure SSH te configureren om een veilige externe aanmelding in te stellen wanneer de verbindingslijn verbinding maakt met de ICE Chat SFTP-site.

   - IP-adres: De ICE Chat SFTP-site is geconfigureerd om alleen een verbindingsaanvraag te accepteren vanaf dit IP-adres, dat wordt gebruikt door de ICE Chat-connector die u maakt in stap 3.

7. Klik **op Annuleren** om de wizard te sluiten. U gaat terug naar deze wizard in stap 3 om de verbindingslijn te maken.

### <a name="step-2-configure-the-ice-chat-sftp-site"></a>Stap 2: De ICE Chat SFTP-site configureren

De volgende stap is het gebruik van de openbare PGP- en SSH-sleutels en het IP-adres dat u hebt verkregen in stap 1 om PGP-versleuteling en SSH-verificatie te configureren voor de ICE Chat SFTP-site. Hierdoor kan de ICE Chat-connector die u maakt in stap 3 verbinding maken met de ICE Chat SFTP-site en ICE Chat-gegevens overbrengen naar Microsoft 365. U moet samenwerken met de klantenondersteuning van ICE Chat om uw ICE Chat SFTP-site in te stellen.

### <a name="step-3-create-an-ice-chat-connector"></a>Stap 3: Een ICE-chatconnector maken

De laatste stap is het maken van een ICE Chat-connector in het Microsoft 365 compliancecentrum. De connector gebruikt de informatie die u verstrekt om verbinding te maken met de ICE Chat SFTP-site en chatberichten over te brengen naar de bijbehorende postvakken van gebruikers in Microsoft 365.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **ICE Chat** op **Weergeven.**

3. Klik op **de pagina ICE-chat** op **Verbindingslijn toevoegen.**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil openbare PGP- en **SSH-sleutels gebruiken.**

6. Voer onder Stap 3 de vereiste gegevens in de volgende vakken in en klik vervolgens **op Verbinding valideren**.

   - **Vaste code:** De id voor uw organisatie, die wordt gebruikt als gebruikersnaam voor de ICE Chat SFTP-site.

   - **Wachtwoord:** Het wachtwoord voor uw ICE Chat SFTP-site.

   - **SFTP-URL:** De URL voor de ICE Chat SFTP-site `sftp.theice.com` (bijvoorbeeld). U kunt ook een IP-adres voor deze waarde gebruiken.

   - **SFTP-poort:** Het poortnummer voor de ICE Chat SFTP-site. De verbindingslijn gebruikt deze poort om verbinding te maken met de SFTP-site.

7. Nadat de verbinding is gevalideerd, klikt u op **Volgende.**

8. Schakel op **de pagina Externe gebruikers toewijzen Microsoft 365 gebruikers in,** schakel automatische gebruikerstoewijzing in en geef zo nodig aangepaste gebruikerstoewijzing. U kunt een kopie van het CSV-bestand voor gebruikerstoewijzing downloaden op deze pagina. U kunt de gebruikerstoewijzingen aan het bestand toevoegen en vervolgens uploaden.

   > [!NOTE]
   > Zoals eerder uitgelegd, bevat het CSV-bestand met aangepaste toewijzingsbestand de ICE Chat imid en het bijbehorende postvakadres Microsoft 365 elke gebruiker. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing biedt, wordt in de verbindingslijn voor elk chatitem eerst naar aangepast toewijzingsbestand gekijken. Als er geen geldige Microsoft 365-gebruiker wordt gevonden die overeenkomt met de ICE Chat-imid van een gebruiker, importeert de connector het item in de postvakken voor de gebruikers die zijn opgegeven in de eigenschappen *SenderEmail* en *RecipientEmail* van het chatitem. Als de connector geen geldige gebruiker Microsoft 365 door automatische of aangepaste gebruikerstoewijzing, wordt het item niet geïmporteerd.

9. Klik **op Volgende,** bekijk de instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

10. Ga naar de **pagina Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken.

## <a name="set-up-a-connector-using-private-keys"></a>Een verbindingslijn instellen met behulp van persoonlijke sleutels

In de stappen in deze sectie ziet u hoe u een ICE Chat-connector kunt instellen met PGP- en SSH-privétoetsen. Deze optie voor het instellen van verbindingslijnen is bedoeld voor organisaties die al een ICE Chat SFTP-site hebben geconfigureerd met behulp van persoonlijke sleutels.

### <a name="step-1-obtain-an-ip-address-to-configure-the-ice-chat-sftp-site"></a>Stap 1: Een IP-adres verkrijgen om de ICE Chat SFTP-site te configureren

Als uw organisatie PGP- en SSH-privésleutels heeft gebruikt om een ICE Chat SFTP-site in te stellen, moet u een IP-adres verkrijgen en dit opgeven bij de klantenondersteuning van ICE Chat. De ICE Chat SFTP-site moet zijn geconfigureerd voor het accepteren van verbindingsaanvragen vanaf dit IP-adres. Hetzelfde IP-adres wordt gebruikt door de ICE Chat-connector om verbinding te maken met de SFTP-site en ICE Chat-gegevens over te brengen naar Microsoft 365.

Het IP-adres verkrijgen:

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **ICE Chat** op **Weergeven.**

3. Klik op **de pagina ICE Chat-productbeschrijving** op **Verbindingslijn toevoegen**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil PGP- en **SSH-persoonlijke** sleutels gebruiken.

   ![Selecteer de optie voor het gebruik van persoonlijke sleutels](../media/ICEChatPrivateKeysOption.png)

6. Klik onder stap 1 op **IP-adres downloaden** om een kopie van het IP-adresbestand op uw lokale computer op te slaan.

   ![Het IP-adres downloaden](../media/ICEChatConnectorIPAddress.png)

7. Klik **op Annuleren** om de wizard te sluiten. U gaat terug naar deze wizard in stap 2 om de verbindingslijn te maken.

U moet werken met de klantenondersteuning van ICE Chat om uw ICE Chat SFTP-site te configureren om verbindingsaanvragen te accepteren vanaf dit IP-adres.

### <a name="step-2-create-an-ice-chat-connector"></a>Stap 2: Een ICE Chat-connector maken

Nadat uw ICE Chat SFTP-site is geconfigureerd, is de volgende stap het maken van een ICE Chat-connector in het Microsoft 365 compliancecentrum. De connector gebruikt de informatie die u verstrekt om verbinding te maken met de ICE Chat SFTP-site en e-mailberichten over te brengen naar de bijbehorende postvakken van gebruikers in Microsoft 365. Als u deze stap wilt voltooien, moet u kopieën hebben van dezelfde privésleutels en wachtwoordzinnen die u hebt gebruikt om uw ICE Chat SFTP-site in te stellen.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **de pagina Gegevensconnectors** onder **ICE Chat** op **Weergeven.**

3. Klik op **de pagina ICE Chat-productbeschrijving** op **Verbindingslijn toevoegen**

4. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

5. Klik op **de pagina Referenties toevoegen voor inhoudsbron** op Ik wil PGP- en **SSH-persoonlijke** sleutels gebruiken.

6. Voer onder Stap 3 de vereiste gegevens in de volgende vakken in en klik vervolgens **op Verbinding valideren**.

      - **Naam:** De naam voor de verbindingslijn. Deze moet uniek zijn in uw organisatie.

      - **Vaste code:** De id voor uw organisatie die wordt gebruikt als gebruikersnaam voor de ICE Chat SFTP-site.

      - **Wachtwoord:** Het wachtwoord voor de ICE Chat SFTP-site van uw organisatie.

      - **SFTP-URL:** De URL voor de ICE Chat SFTP-site `sftp.theice.com` (bijvoorbeeld). U kunt ook een IP-adres voor deze waarde gebruiken.

      - **SFTP-poort:** Het poortnummer voor de ICE Chat SFTP-site. De verbindingslijn gebruikt deze poort om verbinding te maken met de SFTP-site.

      - **PGP-privésleutel:** De persoonlijke PGP-sleutel voor de ICE Chat SFTP-site. Zorg ervoor dat u de volledige persoonlijke sleutelwaarde op moet nemen, inclusief de begin- en eindlijnen van het sleutelblok.

      - **Wachtwoordzin PGP-toets:** De wachtwoordzin voor de persoonlijke PGP-sleutel.

      - **SSH-privésleutel:** De SSH-privésleutel voor de ICE Chat SFTP-site. Zorg ervoor dat u de volledige persoonlijke sleutelwaarde op moet nemen, inclusief de begin- en eindlijnen van het sleutelblok.

      - **SSH-toets passphrase:** De wachtwoordzin voor de SSH-privésleutel.

7. Nadat de verbinding is gevalideerd, klikt u op **Volgende.**

8. Schakel op **de pagina ICE Chat-gebruikers** toewijzen Microsoft 365 gebruikers automatisch toewijzen in en geef zo nodig aangepaste gebruikerstoewijzing aan.

   > [!NOTE]
   > Zoals eerder uitgelegd, bevat het CSV-bestand met aangepaste toewijzingsbestand de ICE Chat imid en het bijbehorende postvakadres Microsoft 365 elke gebruiker. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing biedt, wordt in de verbindingslijn voor elk chatitem eerst naar aangepast toewijzingsbestand gekijken. Als er geen geldige Microsoft 365-gebruiker wordt gevonden die overeenkomt met de ICE Chat-imid van een gebruiker, importeert de connector het item in de postvakken voor de gebruikers die zijn opgegeven in de eigenschappen *SenderEmail* en *RecipientEmail* van het chatitem. Als de connector geen geldige gebruiker Microsoft 365 door automatische of aangepaste gebruikerstoewijzing, wordt het item niet geïmporteerd.

9. Klik **op Volgende,** bekijk de instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

10. Ga naar de **pagina Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken. Klik op de verbindingslijn om de flyoutpagina weer te geven, die informatie over de verbindingslijn bevat.
