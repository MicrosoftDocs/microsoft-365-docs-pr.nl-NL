---
title: Defender voor Eindpunt implementeren op Linux met Chef
description: Meer informatie over het implementeren van Defender voor Endpoint op Linux met Chef
keywords: microsoft, defender, atp, linux, scans, antivirus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903926"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Defender voor Eindpunt implementeren op Linux met Chef

Voordat u begint:

- Installeer unzip als deze nog niet is geïnstalleerd. De Chef-onderdelen zijn al geïnstalleerd en er bestaat een Opslagplaats voor koks (kok genereert repo) om het kookboek op te slaan dat wordt gebruikt om te implementeren naar Defender for Endpoint op <reponame> door Chef beheerde Linux-servers.

U kunt een nieuw kookboek maken in uw bestaande opslagplaats door de volgende opdracht uit te voeren vanuit de map met kookboeken die zich in uw opslagplaats voor koks vindt:</br>
`chef generate cookbook mdatp`

Met deze opdracht wordt een nieuwe mapstructuur voor het nieuwe kookboek mdatp aangemaakt.  U kunt ook een bestaand kookboek gebruiken als u al een kookboek hebt waar u de MDE-implementatie aan wilt toevoegen.
Nadat het kookboek is gemaakt, maakt u een map met bestanden in de map met kookboeken die u zojuist hebt gemaakt:

`mkdir mdatp/files`

Breng het Zip-bestand Linux Server Onboarding over dat kan worden gedownload van de Microsoft Defender-beveiligingscentrum portal naar deze map met nieuwe bestanden.

Ga op het werkstation van Kok naar de map mdatp/recepten. Deze map wordt gemaakt wanneer het kookboek is gegenereerd. Gebruik de gewenste teksteditor (zoals vi of nano) om de volgende instructies toe te voegen aan het einde van het standaard.rb-bestand:
-   include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

Sla vervolgens het standaard.rb-bestand op en sluit het.
Maak vervolgens een nieuw receptbestand install_mdatp.rb in de map recepten en voeg deze tekst toe aan het bestand:

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

U moet het versienummer, de distributie en de naam van de repo aanpassen aan de versie die u implementeert en het kanaal dat u wilt implementeren.
Vervolgens moet u een onboard_mdatp.rb-bestand maken in de map mdatp/recipies.  Voeg de volgende tekst toe aan dat bestand:

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

Zorg ervoor dat u de padnaam bijwerkt naar de locatie van het onboarding-bestand.
Als u de implementatie wilt testen op het werkstation Van Kok, voer dan gewoon ``sudo chef-client -z -o mdatp`` uit.
Na de implementatie moet u overwegen om een configuratiebestand te maken en te implementeren op de servers op basis van Voorkeuren instellen voor [Microsoft Defender voor Eindpunt op Linux.](/linux-preferences.md)  
Nadat u het configuratiebestand hebt gemaakt en getest, kunt u het in de map kookboek/mdatp/bestanden plaatsen waar u ook het onboarding-pakket hebt geplaatst.  Vervolgens kunt u een settings_mdatp.rb-bestand maken in de map mdatp/recipies en deze tekst toevoegen:

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

Als u deze stap wilt opnemen als onderdeel van het recept, voegt u include_recipe ':: settings_mdatp' toe aan uw standaard.rb-bestand in de receptmap.
U kunt crontab ook gebruiken om automatische updates te plannen Een update van microsoft Defender voor Eindpunt [(Linux) plannen.](linux-update-MDE-Linux.md)

Verwijder MDATP kookboek:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

