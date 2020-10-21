---
title: Naamservers wijzigen voor het instellen van Microsoft bij Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Meer informatie over hoe u Microsoft kunt instellen voor het beheren van uw DNS-records bij Amazon Web Services (AWS). '
ms.openlocfilehash: 9f5bfd54020dfb793bbaad9aa8e081e87abc5ce8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646485"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>Naamservers wijzigen voor het instellen van Microsoft bij Amazon Web Services (AWS)

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Voer de volgende instructies uit als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u wilt, kunt u [al uw Microsoft DNS-records beheren op AWS](create-dns-records-at-aws.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **resources** de optie **hosted zones**.
    
3. Selecteer op de pagina **hosted zones** , in de kolom **domain name** , de naam van het domein dat u wilt bewerken. 
    
4. Selecteer **Create Record set**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.) 
    
    > [!TIP]
    > De aanhalingstekens die zijn vereist volgens de instructies op het scherm, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
|(Laat dit veld leeg)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple <br/> |
   
6. Selecteer **Maken**. 
    
7. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en vraagt u naar de record.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
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
>  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **resources** de optie **hosted zones**.
    
3. Selecteer op de pagina **hosted zones** , in de kolom **domain name** , de naam van het domein dat u wilt bewerken. 
    
4. Selecteer de **Nameserver**-recordset. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. Verwijder in de recordset **NS - Name server** in het vak **Value** alle naamservers door ze allemaal te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
    > [!CAUTION]
    > Ga als volgt te werk als u een bestaande naamservers hebt dan de vier juiste naamservers. (Dat wil zeggen dat u alleen huidige naamservers met de  *naam* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **ns3.BDM.microsoftonline.com**of **ns4.BDM.microsoftonline.com**) verwijdert. 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. Selecteer in het gebied **TTL (seconds):** de optie **1U** (1 uur). 
    
    ![Selecteer de 1U voor één uur](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. In de recordset **NS - Name server** en het vak **Value** typt of kopieert en plakt u bovendien de waarde uit **Eerste regel** uit de volgende tabel, drukt u op **Enter** op het toetsenbord en typt of kopieert en plakt u de waarde van de volgende **regel**. 
    
    > [!IMPORTANT]
    > Elke naamserverwaarde  *moet*  op een afzonderlijke regel in het vak **Value** staan, zoals wordt weergegeven in de volgende afbeelding. 
  
|||
|:-----|:-----|
|**Eerste regel** <br/> |ns1.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
|**Tweede regel** <br/> |ns2.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
|**Derde regel** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
|**Vierde regel** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
   ![Typ of plak de eerste Regelwaarde in het vak waarde.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Selecteer **Recordset opslaan**.
    
    ![Record sets selecteren](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
