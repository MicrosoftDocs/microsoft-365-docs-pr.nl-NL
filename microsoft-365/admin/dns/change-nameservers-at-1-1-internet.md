---
title: Naamservers wijzigen voor het instellen van Microsoft met 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Meer informatie over hoe u Office 365, beheerd door 21Vianet, kunt instellen voor het beheren van DNS-records wanneer 1&1 Internet de DNS-hosting provider is.
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658030"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>Naamservers wijzigen voor het instellen van Microsoft 365 met 1&1 IONOS

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Volg deze instructies als u wilt dat Microsoft 365 uw DNS-records van Microsoft 365 voor u beheert. (Als u wilt, kunt u [al uw DNS-records voor Microsoft 365 beheren bij 1&1 IONOS](create-dns-records-at-1-1-internet.md).) 
  

    
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie


Voordat u uw domein met Microsoft 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
Volg onderstaande stappen of [bekijk de video (start op 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS via [deze koppeling](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). U wordt gevraagd u aan te melden. 
    
2. Selecteer onder **MY DOMAINS** de optie **Manage domains**.
    
3. Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken. Selecteer vervolgens het besturingselement **panel** ( **v**) voor het domein.
    
4. Selecteer in het gebied **Domain Settings** de optie **Edit DNS Settings**.
    
5. Selecteer in de sectie **txt and SRV records** de optie **add record**.
    
    (Mogelijk moet u omlaag schuiven.) 
    
6. Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. 
    
||||
|:-----|:-----|:-----|
|**Type** <br/> |**Voorvoegsel** <br/> |**Naamwaarde** <br/> |
|TXT  <br/> |(Laat dit veld leeg.)  <br/> |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. Selecteer **Opslaan** en **Sla** het bestand opnieuw op. 
    
8. Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.
    
9. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.
  
Wanneer in Microsoft 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Zie [problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md)als u problemen hebt met de e-mail stroom of andere problemen nadat u DNS-records hebt toegevoegd. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Als u het instellen van uw domein met Microsoft 365 wilt voltooien, moet u de DNS-records van uw domein bij uw domeinregistratie wijzigen zodat deze verwijzen naar de primaire en secundaire naamservers van Microsoft 365. Hiermee stelt u Microsoft 365 in om de DNS-records van het domein voor u bij te werken. We toevoegen alle records, zodat e-mail, Skype voor bedrijven online en uw openbare website met uw domein werken, en u bent klaar.
  
> [!CAUTION]
> Wanneer u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Microsoft 365-naamservers, worden deze beïnvloed. Alle e-mailberichten die naar uw domein zijn verzonden (zoals rob@ *your_domain*  . com) gaan bij microsoft 365 na dat u deze wijziging hebt aangebracht. 
  
Bent u klaar voor het wijzigen van uw NS-records zodat Microsoft 365 uw domein kan instellen? Volg onderstaande stappen of [bekijk de video (start bij 365)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
> [!IMPORTANT]
>  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS met behulp van [deze koppeling](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). U wordt gevraagd u aan te melden. 
    
2. Selecteer onder **MY DOMAINS** de optie **Manage domains**.
    
3. Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken en selecteer het besturingselement **panel** ( **v**) voor het domein.
    
4. Selecteer in het gebied **Domain Settings** de optie **Edit DNS Settings**.
    
5. In de sectie **Name Server Settings** selecteert u **Other name servers**.
    
    (Mogelijk moet u omlaag schuiven.)
    
6. Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:
    
  - Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).
    
  - Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Als er nog GEEN naamservers worden vermeld

1. Typ of kopieer en plak de waarde uit de volgende tabel in het vak **Name server 1**. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![Een waarde invoeren in het vak Name Server 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. In de vervolgkeuzelijst **Additional name servers** kiest u **My secondary name servers**.
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. Typ of kopieer en plak de waarde uit de volgende tabel in het vak **Name server 2, 3, and 4**. 
    
|||
|:-----|:-----|
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![Waarden invoeren voornaam server](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. Kies **Opslaan**.
    
    ![Opslaan selecteren op de pagina name Server Settings](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.
    
    ![Opslaan selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Als er WEL naamservers worden vermeld

> [!CAUTION]
> Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.) 
  
1. Als er al naamservers in de **Name server**-vakken worden vermeld, verwijdert u elke vermelding door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. Typ of kopieer en plak de waarden uit de volgende tabel in het vak **Name server 1, 2, 3, and 4**. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Waarden invoeren voornaam server](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. Kies **Opslaan**.
    
    ![Opslaan selecteren op de pagina name Server Settings](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.
    
    ![Opslaan selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  


