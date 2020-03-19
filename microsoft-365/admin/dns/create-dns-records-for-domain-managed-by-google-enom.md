---
title: DNS-records maken wanneer uw domein wordt beheerd door Google (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Meer informatie over toegang tot eNom en DNS maken via de pagina Google Domeinen.
ms.openlocfilehash: 566b3990c6cc3080eac9d1367531eea42ab135d1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810487"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>DNS-records maken wanneer uw domein wordt beheerd door Google (eNom)

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als u uw e-mailaccounts wilt migreren naar Office 365, moet u een DNS-record aanmaken bij uw domeinregistrar.
  
Als u uw domein via Google hebt gekocht terwijl u zich aanmeldt voor uw **Google Apps for Work-account,** worden uw DNS-records beheerd door Google, maar geregistreerd bij eNom. 
  
U hebt toegang tot eNom en maakt DNS via de pagina Google **Domeinen.** Voer gewoon de stappen in dit artikel uit. 
  
## <a name="create-the-dns-record"></a>De DNS-record maken

1. Selecteer **Aanmelden**op de [Console van Google-beheer.](https://www.google.com/work/apps/business)
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Voer uw domeinnaam in en selecteer **Ga**.
    
    ![Knopafbeelding](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. Selecteer onder aan de pagina **meer besturingselementen**.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Selecteer **Domeinen**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. Selecteer op de pagina **Domeinen** de optie **Domeinen toevoegen/verwijderen**.
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. Selecteer op de pagina **Domeinen** de optie **Geavanceerde DNS-instellingen**.
    
    > [!NOTE]
    > Als u geen domeinnaam via Google hebt aangeschaft terwijl u zich registreerde voor uw account bij **Google Apps for Work**, hebt u geen **Geavanceerde DNS-instellingen** op uw pagina **Domeinen**. U moet dan rechtstreeks naar de website van uw domeinhost gaan voor toegang tot uw DNS-instellingen, en vervolgens deze en de volgende stappen uitvoeren. Zie [Toegang tot de domeininstellingen van g suite](https://support.google.com/a/answer/54693?hl=en) voor meer informatie. 
  
    ![Google-Apps-eNom-Configureren-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. Selecteer **aanmelden bij DNS-console**op de pagina **Geavanceerde DNS-instellingen.** Noteer de **aanmeldingsnaam** en het **wachtwoord**. U hebt deze nodig in de volgende stap. 
    
    ![Google-Apps-eNom-Configureren-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Meld u op de pagina **Geavanceerde DNS-instellingen** aan bij **Domeinbeheer** van Google met de **aanmeldingsnaam** en het **wachtwoord**. 
    
    ![Google-Apps-eNom-Configureren-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. Selecteer op de ***pagina domain_name*** in de sectie **Hostrecords** de optie **Bewerken**.
    
    ![Google-Apps-eNom-Configureren-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. Selecteer in de sectie **Hostrecords** de optie **Nieuw toevoegen**.
    
    ![Google-Apps-eNom-Configureren-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**HOST**|**TXT VALUE**|**RECORDTYPE**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365. 
  
    [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)
  
12. Kies **Opslaan**.
    
    ![Google-Apps-eNom-Configureren-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Selecteer **Wijzigingen opslaan**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
