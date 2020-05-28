---
title: Naamservers wijzigen om Microsoft in te stellen met Hostgator
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Meer informatie over hoe u Microsoft instellen voor het beheren van de DNS-records van uw aangepaste domein bij Hostgator.
ms.openlocfilehash: 787fe5f5e768d9d93cfca9d1644037142822216e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400639"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Naamservers wijzigen om Microsoft 365 in te stellen met Hostgator

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.
  
Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij Hostgator](create-dns-records-at-hostgator.md).)
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Uw domein naar uw hostingaccount laten verwijzen.

> [!IMPORTANT]
> U moet deze procedure uitvoeren voordat u de procedure in de volgende sectie, **Een TXT-record toevoegen voor verificatie**, uitvoert.
  
Volg deze stappen om uw domein en hostingaccounts te koppelen.
  
1. Ga eerst naar uw pagina met de klantenportal bij Hostgator via [deze koppeling](https://portal.hostgator.com/domain/manage). U wordt gevraagd u aan te melden.
    
    ![Takenlijsten verbinden met Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selecteer het tabblad **Domeinen.**
    
    ![Office 2010-lint](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Selecteer op de pagina **Domeinen beheren** in het gebied **Mijn domeinen** het domein dat u wilt bijwerken.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Selecteer op de pagina **Domeinenoverzicht** in het gebied **Naamservers** de optie **Wijzigen**.
    
    ![Afbeelding van knop Doorzichtige kleur instellen](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Kies op de pagina **Naamservers** voor uw domein in de vervolgkeuzelijst **Hostingaccount** selecteren de **hostingaccount** die aan uw domein is gekoppeld.
    
    ![Power BI-dashboards](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selecteer **Naamservers opslaan**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

> [!IMPORTANT]
> Voordat u deze procedure uitvoert, moet u eerst de procedure uitvoeren in het eerste deel van dit artikel, [Uw domein naar uw hostingaccount leiden.](#point-your-domain-to-your-hosting-account)
  
Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. U vindt dit adres in de e-mail die u bij aanmelding van Hostgator hebt ontvangen.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Om aan de slag te gaan, u een hostingaccount kopen bij Hostgator of [de NS-records (nameserver) van uw domein wijzigen](#change-your-domains-nameserver-ns-records) om naar Microsoft te wijzen. 
  
2. Selecteer op de pagina **Configuratiescherm** in het gebied **Domeinen** de optie **Advanced DNS Zone Editor**.
    
    (Mogelijk moet u omlaag schuiven.) 
    
3. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a Record** in de vakken voor de nieuwe record op de pagina **Advanced DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Gebruik uw  *domeinnaam*  (bijvoorbeeld fourthcoffee.com).<br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Selecteer **Record toevoegen**.
    
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen. Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken. We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.
  
> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Alle e-mail die naar uw *your_domain* domein wordt verzonden (zoals rob@ your_domain.com) wordt bijvoorbeeld naar Microsoft verzonden nadat u deze wijziging hebt gewijzigd.
  
> [!IMPORTANT]
> In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. Wanneer u de stappen in deze sectie hebt voltooid, zijn deze vier de enige nameservers: **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**en **ns4.bdm.microsoftonline.com**.
  
1. Ga eerst naar uw pagina met de klantenportal bij Hostgator via [deze koppeling](https://portal.hostgator.com/domain/manage). U wordt gevraagd u aan te melden.
    
    ![Takenlijsten verbinden met Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selecteer het tabblad **Domeinen.** 
    
    ![Office 2010-lint](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Selecteer op de pagina **Domeinen beheren** in het gebied **Mijn domeinen** het domein dat u wilt bijwerken. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Selecteer op de pagina **Domeinoverzicht** in het gebied **Naamservers** de optie **Wijzigen**.
    
    ![Afbeelding van knop Doorzichtige kleur instellen](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Kies op de pagina **Naamservers** voor uw domein in de vervolgkeuzelijst **Hostingaccount** selecteren de **hostingaccount** die aan uw domein is gekoppeld. 
    
    ![Power BI-dashboards](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selecteer **Handmatig mijn naamservers instellen**.
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **LET OP:** Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers. (Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.)
  
        Met de pagina **Name Servers** voor uw domein geopend, verwijdert u elke naamserver in de lijst met naamservers door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
   ![O365_Adddomain_wizard_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. Terwijl u zich nog in de lijst met naamservers bevindt, typt of kopieert en plakt u de eerste twee waarden uit de volgende tabel.
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Voeg de andere waarden voor de naamserver toe.
    
    Selecteer **(+)** toevoegen en typ of kopieer en plak de waarde uit de volgende rij van de tabel in het vak voor de record. 
    
    Herhaal deze procedure totdat u alle vier naamserverrecords hebt gemaakt.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Selecteer **Naamservers opslaan**.
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.
