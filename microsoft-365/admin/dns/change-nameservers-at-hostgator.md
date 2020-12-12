---
title: Naamservers wijzigen voor het instellen van Microsoft met Hostgator
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Meer informatie over hoe u Microsoft kunt instellen voor het beheren van de DNS-records van uw aangepaste domein op Hostgator.
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658018"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Naamservers wijzigen voor het instellen van Microsoft 365 met Hostgator

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.
  
Voer de volgende instructies uit als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u wilt, kunt u [al uw Microsoft DNS-records beheren op Hostgator](create-dns-records-at-hostgator.md).)
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Uw domein naar uw hostingaccount laten verwijzen.

> [!IMPORTANT]
> U moet deze procedure uitvoeren voordat u de procedure in de volgende sectie, **Een TXT-record toevoegen voor verificatie**, uitvoert.
  
Volg deze stappen om uw domein en hostingaccounts te koppelen.
  
1. Ga eerst naar uw pagina met de klantenportal bij Hostgator via [deze koppeling](https://portal.hostgator.com/domain/manage). U wordt gevraagd u aan te melden.
    
    ![Takenlijsten verbinden met Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selecteer het tabblad **Domains** .
    
    ![Office 2010-lint](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Selecteer op de pagina **Manage Domains** in het gebied **My Domains** het domein dat u wilt bijwerken.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Selecteer op de pagina **Domains Overview** in het gebied **name servers** de optie **Change**.
    
    ![Afbeelding van knop Doorzichtige kleur instellen](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Op de pagina **name servers** voor uw domein, in de vervolgkeuzelijst **Select hosting account** , kiest u het **hosting account** dat is gekoppeld aan uw domein.
    
    ![Power BI-dashboards](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selecteer **Save name servers**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

> [!IMPORTANT]
> Voer voordat u deze procedure uitvoert eerst de procedure uit in het eerste gedeelte van dit artikel: [uw domein naar uw hosting account laten verwijzen](#point-your-domain-to-your-hosting-account).
  
Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. U vindt dit adres in de e-mail die u bij aanmelding van Hostgator hebt ontvangen.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Als u aan de slag wilt gaan, kunt u een hosting account kopen bij Hostgator of [de naamserver (NS-records) van uw domein wijzigen zodat deze](#change-your-domains-nameserver-ns-records) verwijzen naar Microsoft. 
  
2. Selecteer op de pagina **Control Panel** , in het gebied **Domains** , de optie **Advanced DNS zone editor**.
    
    (Mogelijk moet u omlaag schuiven.) 
    
3. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a Record** in de vakken voor de nieuwe record op de pagina **Advanced DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Gebruik uw  *domeinnaam*  (bijvoorbeeld fourthcoffee.com).<br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Selecteer **Record toevoegen**.
    
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en vraagt u naar de record.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Om het instellen van uw domein met Microsoft te voltooien, kunt u de NS-records van uw domein bij uw domeinregistratie wijzigen zodat deze verwijzen naar de primaire en secundaire naamservers van Microsoft. Hierdoor wordt Microsoft zodanig geconfigureerd dat de DNS-records van het domein voor u worden bijgewerkt. We toevoegen alle records, zodat e-mail, Skype voor bedrijven online en uw openbare website met uw domein werken, en u bent klaar.
  
> [!CAUTION]
> Als u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Microsoft-naamservers, worden dit van invloed op alle services die op dat moment zijn gekoppeld aan uw domein. Alle e-mailberichten die naar uw domein zijn verzonden (zoals rob@ *your_domain*  . com) worden bijvoorbeeld beschikbaar gemaakt voor Microsoft nadat u deze wijziging hebt aangebracht.
  
> [!IMPORTANT]
> In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. Wanneer u de stappen in deze sectie hebt voltooid, kunt u alleen de volgende vier naamservers in de lijst vinden:  **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **ns3.BDM.microsoftonline.com** en **ns4.BDM.microsoftonline.com**.
  
1. Ga eerst naar uw pagina met de klantenportal bij Hostgator via [deze koppeling](https://portal.hostgator.com/domain/manage). U wordt gevraagd u aan te melden.
    
    ![Takenlijsten verbinden met Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selecteer het tabblad **Domains** . 
    
    ![Office 2010-lint](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Selecteer op de pagina **Manage Domains** in het gebied **My Domains** het domein dat u wilt bijwerken. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Selecteer op de pagina **Domain Overview** , in het gebied **name servers** , de optie **Change**.
    
    ![Afbeelding van knop Doorzichtige kleur instellen](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Op de pagina **name servers** voor uw domein, in de vervolgkeuzelijst **Select hosting account** , kiest u het **hosting account** dat is gekoppeld aan uw domein. 
    
    ![Power BI-dashboards](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selecteer **mijn naamservers handmatig instellen**.
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **Let** op: Volg deze stappen alleen als u een bestaande naamservers hebt dan de vier juiste naamservers. (Dat wil zeggen dat u alleen huidige naamservers met de  *naam* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **ns3.BDM.microsoftonline.com** of **ns4.BDM.microsoftonline.com**) verwijdert.
  
        Met de pagina **Name Servers** voor uw domein geopend, verwijdert u elke naamserver in de lijst met naamservers door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
   ![O365_Adddomain_wizard_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. Terwijl u zich nog in de lijst met naamservers bevindt, typt of kopieert en plakt u de eerste twee waarden uit de volgende tabel.
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator voor een 1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Voeg de andere waarden voor de naamserver toe.
    
    Selecteer **(+)** toevoegen en typ of kopieer en plak de waarde van de volgende rij van de tabel in het vak voor de record. 
    
    Herhaal deze procedure totdat u alle vier naamserverrecords hebt gemaakt.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Selecteer **Save name servers**.
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.
