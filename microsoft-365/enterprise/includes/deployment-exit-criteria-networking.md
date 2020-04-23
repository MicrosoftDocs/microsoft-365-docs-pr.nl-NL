<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Vereist: Uw netwerk is gereed voor Microsoft 365 Enterprise

- Uw kantoren hebben een adequate internet-bandbreedte voor Microsoft 365-verkeer, waaronder Office 365-, Microsoft Intune- en Windows 10 Enterprise-installatie en -updates.
- Uw hele netwerk is gekoppeld aan een [Microsoft 365-referentiearchitectuur](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).
- De wijzigingen in uw netwerk zijn getest en voldoen aan de vereisten voor uw netwerklatentie.

[Stap 1](../networking-provide-bandwidth-cloud-services.md) kan u desgewenst helpen bij deze vereiste.

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Vereist: Uw lokale kantoren hebben lokale internetverbindingen en naamomzetting

U hebt elk lokaal kantoor voorzien van een internetverbinding van een lokale internetprovider, met DNS-servers die een lokaal openbaar IP-adres gebruiken waarmee de locatie op internet wordt aangeduid. Dit garandeert de best mogelijke prestaties voor gebruikers die toegang hebben tot de cloudservices van Microsoft 365.

Als u geen lokale internetprovider gebruikt voor elk filiaal, kan het zijn dat de prestaties hieronder lijden, aangezien het netwerkverkeer dan moet worden omgeleid langs de backbone van de organisatie of gegevensaanvragen door front-end servers moeten worden verwerkt.

#### <a name="how-to-test"></a>Testen
Gebruik een hulpprogramma of website vanaf een apparaat in dat kantoor om te bepalen welk openbaar IP-adres wordt gebruikt door de proxyserver. Gebruik bijvoorbeeld de webpagina [Wat is mijn IP-adres](https://www.whatismypublicip.com/). Dit openbare IP-adres dat is toegewezen door uw internetprovider, moet een lokaal adres zijn. Het moet niet afkomstig zijn van een openbaar IP-adresbereik voor een centraal kantoor of een netwerkbeveiligingsleverancier in de cloud.

[Stap 2](../networking-dns-resolution-same-location.md) kan u desgewenst helpen bij deze vereiste.

<a name="crit-networking-step3"></a>
### <a name="optional-unnecessary-network-hairpins-are-removed"></a>Optioneel: Onnodige netwerkhairpins worden verwijderd

U hebt uw netwerkhairpins onderzocht en de effecten ervan op de prestaties van al uw kantoren bepaald. U hebt de netwerkhairpins waar mogelijk verwijderd of met uw externe netwerk- of beveiligingsprovider samengewerkt om optimale Microsoft 365-peering voor het netwerk te implementeren.

[Stap 3](../networking-avoid-network-hairpins.md) kan u desgewenst helpen bij deze optie.


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Optioneel: U hebt het omleiden van verkeer op uw internetbrowsers en randapparaten geconfigureerd

U hebt de nieuwste PAC-bestanden geïmplementeerd in uw on-premises internetbrowsers, zodat verkeer naar DNS-domeinnamen van Microsoft 365 niet via de proxyservers wordt geleid.

U hebt de apparaten voor uw netwerkperimeter geconfigureerd - zoals firewalls, SSL Break and Inspect en inspectieapparaten voor pakketten - om verkeer om te leiden of om het verkeer te beperken tot de categorieën Optimaliseren en toestaan van Microsoft 365-eindpunten.


#### <a name="how-to-test"></a>Testen

Gebruik de hulpprogramma's voor logboekregistratie op de apparaten voor uw netwerkperimeter om ervoor te zorgen dat verkeer naar Microsoft 365-bestemmingen niet wordt gecontroleerd, gedecodeerd of anderszins wordt belemmerd.

[Stap 4](../networking-configure-proxies-firewalls.md) kan u desgewenst helpen bij deze optie.


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Optioneel: Uw clients en Office 365-toepassingen zijn geconfigureerd voor optimale prestaties

U hebt de TCP-instellingen (Transmission Control Protocol) geoptimaliseerd op uw clientapparaten en voor Exchange Online-, Skype voor Bedrijven Online-, SharePoint Online- en Project Online-services.

[Stap 5](../networking-optimize-tcp-performance.md) kan u desgewenst helpen bij deze optie.
