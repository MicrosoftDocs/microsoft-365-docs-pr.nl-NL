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
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="39521-104">Defender voor eindpunt implementeren op Linux met Chef</span><span class="sxs-lookup"><span data-stu-id="39521-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="39521-105">Voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="39521-105">Before you begin:</span></span>

- <span data-ttu-id="39521-106">Installeer unzip als deze nog niet is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="39521-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="39521-107">De Chef-onderdelen zijn al geïnstalleerd en er bestaat een Opslagplaats voor koks (kok genereert repo) om het kookboek op te slaan dat wordt gebruikt om te implementeren naar Defender for Endpoint op <reponame> door Chef beheerde Linux-servers.</span><span class="sxs-lookup"><span data-stu-id="39521-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="39521-108">U kunt een nieuw kookboek maken in uw bestaande opslagplaats door de volgende opdracht uit te voeren vanuit de map met kookboeken die zich in uw opslagplaats voor koks vindt:</span><span class="sxs-lookup"><span data-stu-id="39521-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="39521-109">Met deze opdracht wordt een nieuwe mapstructuur voor het nieuwe kookboek mdatp aangemaakt.</span><span class="sxs-lookup"><span data-stu-id="39521-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="39521-110">U kunt ook een bestaand kookboek gebruiken als u al een kookboek hebt waar u de MDE-implementatie aan wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="39521-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="39521-111">Nadat het kookboek is gemaakt, maakt u een map met bestanden in de map met kookboeken die u zojuist hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="39521-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="39521-112">Breng het Zip-bestand Linux Server Onboarding over dat kan worden gedownload van de Microsoft Defender Security Center-portal naar deze map met nieuwe bestanden.</span><span class="sxs-lookup"><span data-stu-id="39521-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="39521-113">Ga op het werkstation van Kok naar de map mdatp/recepten.</span><span class="sxs-lookup"><span data-stu-id="39521-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="39521-114">Deze map wordt gemaakt wanneer het kookboek is gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="39521-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="39521-115">Gebruik de gewenste teksteditor (zoals vi of nano) om de volgende instructies toe te voegen aan het einde van het standaard.rb-bestand:</span><span class="sxs-lookup"><span data-stu-id="39521-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="39521-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="39521-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="39521-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="39521-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="39521-118">Sla vervolgens het standaard.rb-bestand op en sluit het.</span><span class="sxs-lookup"><span data-stu-id="39521-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="39521-119">Maak vervolgens een nieuw receptbestand install_mdatp.rb in de map recepten en voeg deze tekst toe aan het bestand:</span><span class="sxs-lookup"><span data-stu-id="39521-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="39521-120">U moet het versienummer, de distributie en de naam van de repo aanpassen aan de versie die u implementeert en het kanaal dat u wilt implementeren.</span><span class="sxs-lookup"><span data-stu-id="39521-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="39521-121">Vervolgens moet u een onboard_mdatp.rb-bestand maken in de map mdatp/recipies.</span><span class="sxs-lookup"><span data-stu-id="39521-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="39521-122">Voeg de volgende tekst toe aan dat bestand:</span><span class="sxs-lookup"><span data-stu-id="39521-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="39521-123">Zorg ervoor dat u de padnaam bijwerkt naar de locatie van het onboarding-bestand.</span><span class="sxs-lookup"><span data-stu-id="39521-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="39521-124">Als u de implementatie wilt testen op het werkstation Van Kok, voer dan gewoon ``sudo chef-client -z -o mdatp`` uit.</span><span class="sxs-lookup"><span data-stu-id="39521-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="39521-125">Na de implementatie moet u overwegen om een configuratiebestand te maken en te implementeren op de servers op basis van Voorkeuren instellen voor [Microsoft Defender voor Eindpunt op Linux.](/linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="39521-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender for Endpoint on Linux](/linux-preferences.md).</span></span>  
<span data-ttu-id="39521-126">Nadat u het configuratiebestand hebt gemaakt en getest, kunt u het in de map kookboek/mdatp/bestanden plaatsen waar u ook het onboarding-pakket hebt geplaatst.</span><span class="sxs-lookup"><span data-stu-id="39521-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="39521-127">Vervolgens kunt u een settings_mdatp.rb-bestand maken in de map mdatp/recipies en deze tekst toevoegen:</span><span class="sxs-lookup"><span data-stu-id="39521-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="39521-128">Als u deze stap wilt opnemen als onderdeel van het recept, voegt u include_recipe ':: settings_mdatp' toe aan uw standaard.rb-bestand in de receptmap.</span><span class="sxs-lookup"><span data-stu-id="39521-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="39521-129">U kunt crontab ook gebruiken om automatische updates te plannen Een update van microsoft Defender voor Eindpunt [(Linux) plannen.](linux-update-MDE-Linux.md)</span><span class="sxs-lookup"><span data-stu-id="39521-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="39521-130">MDATP-kookboek verwijderen:</span><span class="sxs-lookup"><span data-stu-id="39521-130">Uninstall MDATP cookbook:</span></span>

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

