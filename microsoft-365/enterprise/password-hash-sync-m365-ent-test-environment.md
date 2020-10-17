---
title: Wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Overzicht: Wachtwoord-hash-synchronisatie en -aanmelding configureren en demonstreren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487456"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Veel organisaties maken gebruik van Azure AD Connect en wachtwoord-hash-synchronisatie om de accounts in hun AD DS-forest (Active Directory Domain Services) op locatie te synchroniseren met de accounts in de Azure AD-tenant van hun Microsoft 365-abonnement. 

In dit artikel wordt beschreven hoe u wachtwoord hash-synchronisatie kunt toevoegen aan uw Microsoft 365-testomgeving, wat resulteert in deze configuratie:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Het instellen van deze testomgeving omvat drie fasen:
- [Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fase 2: Het testlab-domein maken en registreren](#phase-2-create-and-register-the-testlab-domain)
- [Fase 3: Azure AD Connect op APP1 installeren](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken

Volg de instructies in [Basisconfiguratie voor gesimuleerde onderneming in Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). De uiteindelijke configuratie ziet er als volgt uit:
  
![De basisconfiguratie voor een gesimuleerde onderneming](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines in een virtueel Azure-netwerk. DC1 is een domeincontroller voor de testlab. <*uw openbare domeinnaam*> Active Directory-domein.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2: Het testlab-domein maken en registreren

In deze fase voegt u een openbaar DNS-domein toe en voegt u dit toe aan uw abonnement.

U moet eerst werken met uw openbare DNS-registratie provider om een nieuwe openbare DNS-domeinnaam te maken die is gebaseerd op uw huidige domeinnaam en deze vervolgens toe te voegen aan uw abonnement. We raden u aan gebruik te maken van de naam **testlab. <*uw openbare domein* > **. Als uw openbare domeinnaam bijvoorbeeld ** <span>Contoso</span>. com**is, voegt u de naam van het openbare domein toe: ** <span>testlab</span>. contoso.com**.
  
Vervolgens voegt u de **testlab. <*uw openbare domein* > ** domein toe aan uw proefabonnement voor Microsoft 365 of betaald door het domeinregistratie proces te passeren. Dit omvat het toevoegen van extra DNS-records aan **testlab. <*uw openbare domein* > ** domein. Zie voor meer informatie [een domein toevoegen aan Microsoft 365](../admin/setup/add-domain.md).

De uiteindelijke configuratie ziet er als volgt uit:
  
![De registratie van de naam van uw testlab-domein](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Deze configuratie bestaat uit:

- Een Microsoft 365 E5-proefabonnement of een betaald abonnement met de DNS Domain testlab. <*de naam van uw openbare domein*> geregistreerd.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.

U ziet hoe de testlab. <*de naam van uw openbare domein*> nu:

- Ondersteund wordt door openbare DNS-records.
- Geregistreerd is in de Microsoft 365-abonnementen.
- Het AD DS-domein op uw gesimuleerde intranet is.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3: Azure AD Connect op APP1 installeren

In deze fase installeert en configureert u het hulpprogramma van Azure AD Connect op APP1 en controleert u vervolgens of het werkt.
  
Installeer en Configureer eerst Azure AD Connect op APP1.

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\\Gebruiker1-account.
    
2. Open, vanaf het bureaublad van APP1, een Windows PowerShell-opdrachtprompt op beheerdersniveau en voer deze opdrachten uit om verbeterde beveiliging van Internet Explorer uit te schakelen:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Selecteer **Internet Explorer** op de taakbalk en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Selecteer op de pagina Microsoft Azure Active Directory Connect de optie **downloaden**en klik vervolgens op **uitvoeren**.
    
5. Selecteer op de pagina **Welkom bij Azure AD Connect** de optie **Ik ga akkoord**en selecteer vervolgens **Doorgaan**.
    
6. Selecteer op de pagina **expres instellingen** de optie **snelle instellingen gebruiken**.
    
7. Voer op de pagina **verbinding maken met Azure AD** de naam van uw globale beheerdersaccount in de gebruikersnaam in **,** Voer het wacht **woord in en**Selecteer **volgende**.
    
8. Voer op de pagina **verbinding maken met AD DS** **TESTLAB \\ gebruiker1** in **gebruikersnaam in,** Geef het wachtwoord op in het **wachtwoord**en selecteer **volgende**.
    
9. Selecteer **installeren**op de pagina **klaar voor de configuratie** .
    
10. Selecteer op de pagina **configuratie voltooid** de optie **Afsluiten**.
    
11. Ga in Internet Explorer naar het Microsoft 365-beheercentrum ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Selecteer **gebruikers > actieve gebruikers**in het linker navigatiedeelvenster.
    
    Bekijk het account met de naam **Gebruiker1**. Dit account is afkomstig uit het TESTLAB AD DS-domein en is het bewijs dat de adreslijstsynchronisatie heeft gewerkt.
    
13. Selecteer het account **gebruiker1** en selecteer vervolgens **licenties en apps**.
    
14. Selecteer in **product licenties**uw locatie (indien nodig), schakel de licentie voor **Office 365 E5** uit en schakel de **Microsoft 365 E5** -licentie in. 

15. Selecteer **Opslaan** onderaan de pagina en selecteer vervolgens **sluiten**.
    
Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met het **user1@testlab. <*uw domeinnaam* > ** gebruikersnaam van het account gebruiker1:

1. Meld u af bij APP1 en meld u weer aan met een ander account.

2. Wanneer u wordt gevraagd om een gebruikersnaam en wachtwoord, geeft u **user1@testlab op. <*uw domeinnaam* > ** en het wachtwoord gebruiker1. U moet u nu kunnen aanmelden als Gebruiker1.
 
Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar Gebruiker1 is geen globale beheerder. Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie. 

De uiteindelijke configuratie ziet er als volgt uit:

![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Deze configuratie bestaat uit: 
  
- Microsoft 365 E5 of Office 365 E5-proefabonnement of betaalde abonnementen met DNS Domain TESTLAB. <*uw domeinnaam*> geregistreerd.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk. Azure AD Connect wordt uitgevoerd op APP1 om periodiek het TESTLAB AD DS-domein te synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnement.
- Het Gebruiker1-account in het TESTLAB AD DS-domein is gesynchroniseerd met de Azure AD-tenant.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
