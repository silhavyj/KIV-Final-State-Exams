## VS - Vývoj softwarových systémů

### KIV/ASWI

01) [Životní cyklus softwarového produktu (informačního systému), jeho modely a jejich charakteristiky. Softwarový proces, jeho klíčové prvky. [KIV/ASWI, (KIV/ZSWI)]](01.md)
    - zivotni cyklus SW produktu (LCO (vize, PoC, PoT, ramcove pozadavky), LCA (diagramy), IOC (demo, feature-complete), GA (DoD, UAT, prechod do podpoty - L1 (helpdesk), L2 (service desk, admin), L3 (vyvojar)), odstavka)
    - SW proces (definice, sklada se z aktivit (technicke/podpurne), roli (technicke/manazerske/podpurne), artefaktu (uroven formalnosti))
    - SW proces vs metodika (definice projektu)
    - metriky SW procesu (cyklicnost, ceremonie - viz XP, atd.)
    - stupne volnosti pri planovani (klasicke modely (pevny rozsah, vodopad, V-model) vs iterativni modely (dynamicky rozsah, RUP, agilni metodiky, spiralovy model))
    - adaptivni metodiky (napr. SCRUM, modifikace dle potreby, komunikace a zpetna vazba od zakaznika)
    - delivery strategie (one-time, inkrementalni, evolucni, kontinualni - CI/CD)
    - latentni potreba -> pojmenovana potreba -> nakup -> nasazeni -> udrzba (IT, uzivatele, manager, ITIL)

02) [Iterativní vývoj software, jeho prvky a postupy, výhody a nedostatky. Příklady iterativních metodik, jejich složky a fáze. [KIV/ASWI]](02.md)
    - iterativni vyvoj (schopnost reagovat na menici se pozadavky, nestabilni prostredi, inkrementalni dodavani SW (demo, iteracni release), opakovani aktivit a testovani)
    - struktura iterace (planovani, zpresnovani pozadavku, implementace, verifikace/validace, review, retrospektiva; uzavrena na zmeny z venci, pevny deadline; faze projektu porad stejne (LOC, LCA, IOC, GA))
    - UP (napr. RUP - prolinani aktivit, late design breakage, aktivity, role, artefakty)
    - SCRUM (rizeni riziky a pozadavky od zakaznika, role - product owner, scrum master, team, sprint = jedna iterace, DoD)
    - XP (mala ceremonie, eliminovani defektu)
    - planovani (prediktivni (napr. statni zakazky, pevny rozsah) vs adaptivni (dynamicky rozsah), na zaklade zkusenosti, pocker game, analyticky - WBS, MH, story point, CMP, Gantt, PERT => navaznost aktivit; priority - MOSCOW, plan projektu vs plan iterace, product backlog vs iteracni backlog)
    - rizeni rizik (prime vs neprime)
    - epics => user stories => tasky
    - sledovani prubehu iterace (burndown, team velocity)

03) [Definice účelu softwarového produktu. Metody získávání a definice požadavků, související dokumenty, modely a standardy. [KIV/ASWI, (KIV/ZSWI, KIV/EITM)]](03.md)
    - faze zahajeni (LCO milnik, definice ucely, stakeholdery, ramcovy plan projektu, komunikace, seznam rizik = {ppst, dopad}, omezeni, standardy, klicove pozadavky)
    - faze konstrukce (LCA milnik, banchmark, PoC, PoT, MVP)
    - sber pozadavku (pozadavek -> jednoznacny, uplny, jedinecny, trasovatelny, overitelny, specifikace pozadavku = rozhrani zakaznik / dodavatel; pozadavek -> new, reviewed, accepted, released; zpusoby ziskavani pozadavku = interaktivni / neinteraktivni; RFI)
    - epic (abstraktni) <- user-story <- feature <- task
    - use-case diagram (akteri, preconditions (aktualni stav), trigger, sekvence akci, vysledny stav), model uziti
    - pozadavky na data (logicky vs fyzicky diagram, CRUD matice (kdo co muze))
    - diagram nasazeni, domenovy model, kontextovy diagram
    - vlastnosti systemu (FURPS+)

04) [Architektura softwarového systému, vztah k požadavkům na systém, formy popisu a modely. Způsoby ověření architektury, pojem „spustitelná architektura“. [KIV/ASWI, KIV/SAR, (KIV/EITM)]](04.md)
    - LOC = co a proc?; LCA = jak?
    - SW architektura (hlavni architektonicka rozhodnuti, analogie k staveni domu, komponenty, konektory -> configurace, struktura, chovani, interakce; mimofunkcni pozadavky)
        - funkci pozadavky => definice komponent, rozhrani a interakce
        - mimofunkci pozadavky => definice datoveho modelu
        - 20% vsech pozadavku = architektonicky vyznamne
    - architektonicky styl vs vzor
    - 4+1 (logicky (struktura), vyvojovy (technologie, projekty, tymy), fyzicky (nasazeni, kontext), procesni (komunikace, paralelismus); + ostatni)
    - C4 (= zoomovani -> kontext systemu -> kontejnery (napr. UI + backend) -> komponenty (napr. vrstvy backendu) -> kod (diagramy mapovatelne na kod))
    - preskriptivni (as intented) vs deskriptivni (as implemented) - drift vs eroze
    - dokumentace (SAD, oponentura, SoC = validace ze splnuje pozadavky zakaznika)
    - spustitelna architektura (GCA, automaticke generovani, AADL, model-driven architecture, PIM, PSM)

05) [Postupy pro správu a řízení změn v projektu vývoje software, typy a možnosti nástrojů. Souvislost správy změn s ostatními disciplínami vývoje software. [KIV/ASWI, KIV/EITM]](05.md)
    - konfiguracni management (sklada se z spravy zmen a spravy verzi, ve vsech fazi vyvoje, po GA je hlavnim faktorem rizeni vyvoje)
    - ticket (submitter, CCB (cross-functional), developer, tester; stavy pozadavku na zmenu - vytvoreny, schvaleny, zamitnuty, naplanovany, uzavreny, overeny => zavisi na metodice; struktura - shrnuti, metadata, popis, log, vstupni data, zavaznost)
    - nastroje (bug trackery (napr. BugZilla) vs ALM (Jira, Redmine), VCS (ClearCase, Git, atd.))
    - ITIL (= framework pro ITMS, oprativni rizeni)
        - incident management (incident) -> problem management, change management (CR), configuration management (CMDB), release managemet (DSL)
        - plni roli L1 podpory, koordinuje L2 a L3

06) [Správa verzí, základní pojmy a postupy (hlavní vývoj, použití větví, značky). Struktura úložiště pro projekty různé velikosti. Nástroje pro správu verzí, jejich možnosti. [KIV/ASWI]](06.md)
    - konfiguracni management (sklada se z spravy zmen a spravy verzi, ve vsech fazi vyvoje, po GA je hlavnim faktorem rizeni vyvoje)
    - prvek konfigurace, granularita verzovani (verzovani komponent -> uplne verzovani (git tagy)), verze (revize vs varianta), verzovani podle stavu vs podle zmen, extenzionalni vs intenzionalni, delta, changeset, tag (label), baseline, codeline
    - VCS (centralizovany vs distribuovany), pracovni prostor, merge, konvence, branch strategie (RCS, CVS, SVN)
    - pravidla sestavovani (jednoznacnost, opakovatelnost, uplnost, konzistence; PROJEKT_v2_BUILD2134_20180612; in-house vs remote; maven, cmake)
    - typy sestaveni (prirustkovy vs uplny; soukromy, integracni, release)

07) [Měření kvantitativních a kvalitativních charakteristik sw produktu či procesu, metoda GQM, příklady metrik. Využití metrik při řízení a zajištění kvality vývoje. [KIV/ASWI]](07.md)
    - vnitrni (architektura, udrzovatelnost, testovatelnost) => vnejsi (bezpecnost, rychlost) kvalita
    - Six Sigma (-> 99% vyrovku chceme mit v dobre kategorii, hodnoceni kvality vyrobniho procesu; klk % vyrobku spada do naseho chtene intervalu)
    - opak kvality (error, defekt, chybovy stav, selhani)
    - drivejsi odstraneni chyb => levnejsi; verifikace vs validace
    - IDS vs IPS; unit testy, regresni testky, funkci testy, stress testy, smoke testy, monkey testy, staticka analyza kodu
    - best practices (navrhove vzory, jmenne konvence, formalni proces)
    - technicka opopentura (moderator, pruvodce, autor, zapisovatel, opnenti), peer-review
    - metriky (kvantifikace GQM, FURPS+, LOC, pokryti testy, MTBF = MTTF + MTTR, staticka analyza, burndown, velocity) => co merit, jak proc?
    - GQM (goal, question, metric; napr. zlepsit spravedlnost v ocenovani prace na projektu)
    - CMMI (initial, managed, defined, quantitatively managed, optimizing)

### KIV/EITM

08) [Postupy a techniky související s nasazením produktu do provozu. Postup vyřazení softwarového produktu z provozu. [KIV/ASWI, (KIV/EITM)]](08.md)
    - GA milnik (automatizovane nastroje - Docker, Kubernetes, field testing, smoke testy, stress testy, zatezove testy, DoD, post-mortem review)
    - produkt v provozu (monitorovani, zalohovani, patchovani, L1, L2, L2 podpora, ITIL (incident management, problem management, change management, CMDB, DSL), helpdesk vs servicedesk)
    - typy udrzby (adaptivni (skalovani), preventivni (monitoring), korektivni (bug-fix), perfektivni (UX))
    - DEVOPS (CI/CD, automatizace; DEVS (plan, code, build, test) => (release) OPS (deploy, operate, monitor))
    - odebrani systemu (doziti, zamrazeni investic, akvizice noveho systemu; strategie (big-bang, po etapach, paralelne s nasazovani noveho), aktualizace documentace, migrace dat, archivace)

09) [Přehled činností při provozu sw (IS/IT) produktu. Řízení, dodávka a podpora IT služeb (ITSM), řízení změn a incidentů, související metodiky (ITIL a další). [KIV/ASWI, KIV/EITM]](09.md)
    - porizeni SW produktu (latentni potreba -> pojemenovana potreba -> vyber/nakup -> nasazeni -> provoz; planovani IS (vnitrni vs vnejsi vlivy) -> analyza IS -> vyber IS (RFP, RFI, krabicove reseni) -> dodavka (viz ASWI) -> podpora (L1, L2, L3) -> provoz (napr. ITIL) -> odebrani systemu)
    - ITSM (rozhrani pro spravu IT, neni technicky orientovany, dodavani sluzeb zakaznikovi)
    - ITIL (rika co nerika jak (viz proces vs metodika), implementace ITSM, v2-v5, 8 knih - Service Support & Service Delivery (= zaklad ITILu), infrastructure management, application management, security management, business perspective, atd.)
        - Service Support (operativni rizeni, incident = neplanovane selhani, service desk, incident management, problem management, znalostni DB, change management, release management (DSL), CMDB)
        - Service Delivery (takticke rizeni, service-level management, financial management, availability managment, capacity management, CMDB, SLA, OLA, UC (underpinning contract), DRP = RPO (napr. denni zalohy) + RTO (napr. obnova do dvou hodin))

10) [Strategické řízení firem, poslání a role IT v organizaci, tvorba strategie IT/IS. Koncepce a metody řízení IT -- Enterprise architektura (EA) a IT governance. [KIV/EITM]](10.md)
    - podnik (= jednotka ekonomiky), cile (primarni, odvozeny, dilci)
    - strategicke rizeni (dlouhodobe, poslani podniku (kdo jsme?) = vize (kde chceme byt?) + mise (jak toho dosahneme?), mise = cile (takticke rizeni, SMART cile) + zamery)
    - tvorba strategie = analyza vnitrniho prostredi, vnejsiho prostredi a zajmovych skupin
        - analyza vnejsiho prostredi (porterova analyza 5 sile, STEP)
        - analyza vnitrniho prostredi (bostonska matice (relativni podil na trhu X mira rustu odvetvi; => otazniku -> hvezdy -> dojne kravy -> bidni psi); SWOT (interni - silne/slabe stranky, externi - prilezitosti/hrozby; => strategie vyuziti, hledani, vyhybani, konfrontace))
        - analyza zajmovych skupin (idenfikace + zjisteni predpokladu, kontexty - kulturni, politicky, eticky; (zanedbatelny, vyznamky) X (nejisty, jisty))
        - => cilem je si vymezit postaveni na trhu, najit vhodnou strategii
    - volba strategie (generovani alternativ, brainstorming, porovnani, vyber (prijatelnost, vhodnost, realizovatelnost, poskytnuti vyhody))
    - organizacni struktura firmy (funkci, divizni, maticova)
    - produktova vs projektova vrstva
    - teorie vitality (uzitecna -> efektivni -> stabilni (vice noh businessu) -> flexibilni)
    - firemni rozhodovani (majority rule, consensus, hirearchicky (chain of command)), role (CEO, CFO, COO, CIO, CTO, CMO, politicke role (napr. generalni reditel, viceprezident, atd.))
    - rizeni (strategicke, takticke, operativni)
    - ITS (business strategie, integrace -> vizi, podniku s okolim, technologie, atd.)
    - stary vs novy model IT (shadow IT - unik dat, bezpecnost, flexibilita)
    - business strategie (kde jsme? co to znamena? kde chceme byt? jak toho dosahneme? => SMART cile)
    - role IT v podniku (motor/strojovna, poskytovatel sluzeb, soucast businessu)
    - EA (urbanisticka koncepce, neni IT disciplina, 4 vrstvy = business -> information -> application -> technology; zachman - 6 pohledu, UML diagramy)
    - IT governance (management (ITIL) vs governance (COBIT))
    - COBIT (4 domeny, metriky, mezinarodni framework pro governance, Balanced Scorecards)

11) [Proces akvizice IS/IT systému. Výběrové řízení, poptávka a nabídka, výběr a nákup řešení, studie proveditelnosti, PoC, PoT, poptávkové řízení (RFI, RFP, RFQ).[KIV/EITM]](11.md)
    - akvizice IS (latentni potreba, potreba, nakup, nasazeni, provoz; planovani IS, analyza IS, vybere (nakup), dodavka/implementace, podpora, ukonceni)
    - obchodni parametry dodavky (cas, cena, kvalita => rozsah, TCO = porizovaci naklady + provozni naklady)
    - studie proveditelnosti (metadata (historie uprav, zkraty, klicova slova, obsah), kontaktni udaje, executive summary, soucastny stav, problem, moznosti reseni (funkcionalita, technologie, SWOT, hruby plan, cena, rizika -> {ppst, dopad} => ignorovat, prijmout (protokol jak resit?), protiopatreni, delegovat))
    - RFI (case study, studio proveditelnosti, osloveni firem)
    - poptavka (= RFP) (metadata, zadavatel + kontakt pro dotazy, predmet (preferovane reseni, omezeni, ramcovy casovy a financni odhad), doba/misto plneni, platebni podminky, kriteria hodnoceni, kriteria na uchazece, misto a zpusob doruceni nabidek, povinnosti zadavatel/dodavatel, struktura odpovedi - sablona)
    - nabidka (= RFQ) (metadata (zadavatel/dodavatel), executive summary, popis reseni, diskuze splneni pozadavku, navrh harmonogramu, cenova nabidka, prilohy - navrh smlouvy o dilo, reference, vypis z rejstriku)
    - obchodni dokumenty (certifikace (statni, oborova (ISO), vendorova), reference (slepe/zakaznicke), case study)
    - hodnoceni nabidek (vahy, vzorce, postup znam dopredu, kriteria (tvrda, mekka))
    - PoT (zameren na technologie, obecna/vygenerovana data) vs PoC
    - zakon o verejnych zakazkach (transparentnost, utraceni verejnych penez, rozsah (maly rozsah, podlimitni, nadlimitni) => druhy rizeni (zjednodusenne podlimitni, otevrene, uzsi, jednaci rizeni bez uverjneni))
    - zjednodusenne podlimitni rizeni (predpoklady - zakladni, profesni, ekonomicke, technicke)

12) [Projektové a multiprojektové řízení, projektová kancelář, metody hodnocení projektů, PMBOK. [KIV/EITM, (KIV/ASWI)]](12.md)
    - definice projektu, projektovy trojuhelnik (cas, cena, kvalita => rozsah, projekt vs proces, artefakt, milnik, proces vs metodika (+ priklady - RUP, waterfall, V-model, agilni, atd.), PM)
    - faze projektu (LCO (vize), LCA (pozadavky, architektura), IOC (MVP, demo), GA/REL (DoD))
    - kriticke faktory uspechu/neuspechu
    - PMBOK (mezinarodni standard jak vest projekty, 9 oblasi projektoveho rizeni, pojmy, znalosti, techniky, procesy, atd.)
        - rozsah (MOSCOW, WBS, typy pozadavku)
        - cas (PDM, Gantt, PERT, kriticka cesta)
        - nakladu (sunk cost, prime, neprime, optimalizace)
        - lidskych zdroju (vzdelavani, nabor, planovani)
        - kvality (definice kvality -> metriky -> referencni hodnoty -> monitorovani -> korekce/rizeni)
        - rizik ({ ppst, dopad }; ignorovat, prijmout, protiopatreni, delegovat)
        - komunikace (RAM, tok predavani informaci)
        - obstaravani projektu (smlouvy, hodnoceni projektu, vyberove rizeni, CMMI, PPM)
        - integrace => vsechno dohromady
    - projektove rizeni (PPM, hlavni ukoly, standardizace procesu/nastroju, PMO - projektova kancelar vs EA)
    - metody hodnoceni projektu (NPV, ROI, payback analysis, WSM)

13) [Způsoby integrace informačních systémů, přístupy a technologie pro jednotlivé vrstvy. [KIV/EITM, (KIV/PIA)]](13.md)
    - duvody pro integraci
    - integrace na datove vrstve
        - SQL import, export, data vs informace vs znalost, EDI (point-to-point vs EDI via VAN, AS2, sifrovani, podpisy), ETL (heterogenita zdroju, nastroje, konverze formatu, agregace), kavlita dat (definici kvality -> metriky, monitorovani, rizeni, MDM, MDM server, MD, odstraneni duplicit, validate platnosti)
    - integrace na aplikacni vrstve
        - vznik rozhrani (RPC, REST, SOAP, WebServicer, WSDL, konektory, adaptery, middleware, SOA (bezstavovat, znovupouzitelnost, skryvani informace, SOA governance, SIMM, atd.), konceptialni model, ESB (transformace, smerovani, monitoring))
    - integrace na prezentacni vrstve
        - portaly (agregace, customizace, autorizace; typy - B2E, B2C, B2B, portlet (UI element); cile - propojit, zlepsit, zrychlit, usetrit, SSO, dashboard)
        - mashupy, Web 2.0, Low-code, No-code, Pro-code

14) [Integrace IS na datové vrstvě, datová pumpa, EDI, proces extrakce, transformace a vložení dat (ETL). [KIV/EITM, KIV/DBM2]](14.md)
    - duvody pro integraci (datova, aplikacni, prezentacni)
    - SQL export/import, cron, presun dat z ruznych systemu do DW, data -> informace -> znalost
    - zpusoby - presun souboru, sdilena DB, datove pumpy (ETL), replikace dat, EDI
    - EDI (komunikace dvema nezavislymi subjekty, stanardni dokumenty, elektronicka podoba, automatizace, formy - point-to-point vs EDI via VAN (HTTP, sifrovani, podpisy, atd.))
    - datova pumpa = ETL (heterogenni zdroje, "klikaci" nastroje, extrakce (notifikace, inkrementalni, uplna), periodicka, transformace (konverze, agregace, XML -> JSON, cisteni), loading -> naplneni DW/MDM serveru)
    - data governance (standardizovane formaty, unikanost, overeni vuci autorite, dlouhodoby proces, postup: porozumeni datum, definicie metrik a referencnich hodnot, mereni kvality, MDM, MD (business critical), MDM server = Single Source of Truth)

15) [Správa dat v podniku (Data Management). Kvalita dat a její řízení, master data management (MDM). Nestrukturovaná podniková data, správa podnikového obsahu (ECM). [KIV/EITM, (KIV/DBM2)]](15.md)
    - EDM, data governance, DMBOK, MDM, MD (business critical), Single Source of Truth
    - kvalita a rizeni dat (standardizace, unikatnost, aktualnost (autorita), integritni omezeni, porozumeni datum, metriky, referencni hodnoty, kontiualni proces)
    - kvalita dat = pristupnost, spravnost, relevantnost, auktualnost, konzistence, unikatnost
    - normalni formy
        - 1 NF (kazdy atribut je automicky (viz 2 telefonni cisla))
        - 2 NF (kazdy neklicovy attr je plne zavisli na kazdem kandidatnim klici)
        - 3 NF (vsechny neklicove attr jsou navzajem nezavisle)
        - BCNF (vsechny attr tvorici primarni klic musi byt nezavisle)
    - DW <=> Data Mart pomoci ETL = datova pumpa
    - analyza nad DW (OLAP krychle, dimenzionalni tabulky)
    - ECM (nestruktorovana data = zaznamy ze schuzek, screenshoty, dokumentace, atd. => chceme zkratit cas vyhledavani; sber (OCR) -> uchovani -> rizeni pristupu -> archivace)

16) [Analytické nástroje pro sledování výkonu organizace, KPI a dashboardy, podpora rozhodování, Business Inteligence (BI). [KIV/EITM, (KIV/DBM2)]](16.md)
    - BI (mereni -> SW/HW -> znalosti, rizeni podniku, vizualizace dat, dashboardy)
    - data -> infomace -> znalost (data mining = AI)
    - performance management (kde jsme? co to znamena? co a jak upravit? kontinualni analyza v case)
    - KPI (sledovani cilu, vizualizace v dashboardu = BAM)
    - OLAP (multidimenzionalita dat, provozni DB => DW, podpora pro BI)
    - OLAP krychle (dimenze = cas, level = mesic, member = kveten, fact = 15 (neceho); operace - slicing, dicing, drill-up, drill-down, pivoting)
    - DW (casove nemenny, predmetove orientovany (zakaznik), integrovany, historicky)
    - OLTP processing, Six Sigma

17) [Řízení komunikace a spolupráce v organizaci, workflow, ESN. Business process management (BPM). [KIV/EITM, (KIV/ZIM)]](17.md)
    - ECM (nestrukturovana data, rychlost vyhledavani dokumentu, funkce - ziskani, sprava, distribuce, archivace)
    - BPM (systematicke zavadeni a definovani BP; definice procesu = sled akci (workflows) vedouci k nejakemu vysledku)
        - postup: definice BP => BPMN => BPEL (vyuziva BR)
        - navrh, modelovani, implementovani, monitorovani, optimalizace
    - BR ("promenna" typu if then), BRMS, BRE (wrapper, sprava BR)
    - mereni procesu (z hlediska pridane hodnoty, z hlediska vykonnosti - doba trvani, propustnost)
    - struktura firmy (funkci, divizni, meticove)
    - socual business (ESN, profily, komentare, viz Facebook, Web 2.0 (neni spojeni s technologii ale s principem pouzivani))

18) [Přehled problematiky bezpečnosti IT/IS, komplexní přístupy a nástroje pro řízení bezpečnosti [KIV/EITM, (KIV/BIT)]](18.md)
    - safety vs security
    - security (kontinualni proces, musi byt soucasti navrhu systemu, kompromis - bezpecnost, pohodli, pouzitelnost, zodpovedny clovek = CSO)
    - oblasti podnikove bezpecnosti (hashovani vs sifrovani, symetricka (EAS, DES, blowfish) vs asymetricka sifra (RSA, ECC), legislativa, zabezpecni site, fishing, OS zabezpeceni, IDM (autentizace vs autorizace))
    - sledovani bezpecnosti (IDS vs IPS, reaktivni, proaktivni, prediktivni, logy, penetracni testovani)
    - elektronicky podpis (hash, privatni klic vs verejny klic)
    - TLS certifikat (obsah, hash, princip overeni spojeni)
    - typy malwaru (ransomware, spyware, adware, worms, rootkit, keylogger)

19) [Outsourcing IT. Poskytování IT jako služby (ITaaS), výhody a nevýhody cloudových technologií. [KIV/EITM]](19.md)
    - outsourcing (co se outsourcuje - podpurne metody, BP, vztah mezi poskytovatelem a uzivatelem)
    - typy: off-shore (indove), on-site (uklizecka), near-shore (nemecko)
    - duvody: chci (expanze), musim (nemam know-how), zkousim
    - prinosy: snizeni nakladu, flexibilita, soustredeni se na kriticke cinnosti
    - rizika: vendor-lockin, overhead, unik citlivych informaci, komunikace, casova pasma
    - insourcing: nabyti znalosti nazpatek
    - platebni model (man hour, za kus, pausal, penale)
    - SLA (definice cinnosti, casovy ramec, QLA, komunikace, zadavani pozadavku, platebni model, definice kvality, zpusob reportingu)
    - cloud (vyuzivani hw pres internet), cloud vs hosting
        - chyby: licencni podminky, chyby strategie
        - vyhody: snadne skalovani, nemusim se starat o hw, podpora 24/7
        - nevyhody: cena, unik dat, zavislost na poskytovateli
    - distribucni modely: XaaS, IaaS (servery), PaaS (IDE), SaaS (Microsoft Office), ITaaS (cely IT)

### KIV/DB2

20) [Standardizace vývoje databázové technologie, norma ISO/IEC 9075 – rozšíření možností relačního modelu a trend vývoje databázové technologie - procedurální prostředky v rámci jazyka SQL. Kurzory – definice, klasifikace, použití kurzorů. Uložené procedury a funkce, balíky (packages), kompilace, spouštění. Standard SQL/PSM. [KIV/DB2]](20.md)
    - norma ISO 9075 (nutne minimum SQL, definice dat, editace dat, vyber dat, pristupova prava, transakce)
    - relacni model (ACID, silna konzistence, spatny vykon/skalovatelnost, DDL (CREATE, DROP), DML (INSTERT, UPDATE, DELETE))
    - NoSQL (distribuovane, necentralizaovanost, dynamicke skalovani, BigData (4V), nerelacni datovy model, vysoky vykon, typy - klic-hodnota (Redis, session), dokumentove (MongoDB, XML, JSON), grafove (Neo4J), sloupcove, CAP, ACID vs BASE)
    - NewSQL (kombinace ACID a BASE, zamezeni nutnosti pouziti specialniho HW)
    - PL/SQL (zavadeni imperativnosti do jinak deklarativniho jazyka (co? vs jak?), aplikacni logika v DB, integrritni omezeni, FOR, LOOP, IF-THEN, EXCEPTION)
        - DECLARE (funkce/procedure) AS DECALARE -> BEGIN -> EXCEPTION -> END
        - kurzory (iterator, implicitni vs explicitni (CREATE, OPEN, FETCH, CLOSE, %FOUND, %NOTFOUND, %ROWCOUNT))
        - zaznamy (struktura v C), funkce (presne jedna navratova hodna) vs procedura, balicky (analogie k namesace/package, public vs private, stavovy vs bezstavovy, kompilace)

21) [Dynamické a statické SQL, aktivní databáze – charakteristika, význam, příklady využití, porovnání s jinými možnostmi ovládání integrity a konzistence databáze. [KIV/DB2]](21.md)
    - staticke SQL (SQL zname v dobe prekladu, kompilace neni za runtime => efektivnejsi, mensi flexibilita, "bezpecnejsi" (SQL injection))
    - dynamicke SQL (SQL definovane jako string, binding promennych, kompilace za runtme => pomalejsi, SQL injection, EXECUTE IMMEDIATE <sql_string> USING <x1, ..., xn>)
    - aktivni DB (triggery)
        - PL/SQL blok spusteni s danou udalosti nad DB objektem (view, table, schema, ...)
        - aktivacni bod (BEFORE/AFTER INSERT OR UPDATE salary ON emplyees -> BEGIN switch END)
        - kontrola integritniho omezeni, pridana rezije, logovani, statistika, business logika
        - systemove (napr. start DB) vs DML trigery
        - prikazove vs radkove triggery (BEFORE prikazovy -> BEFORE radkovy -> SQL -> AFTER radkovy -> AFTER prikazovy)

22) [Objektové vlastnosti jazyka SQL99, rozšíření datových typů. Vlastnosti objektově orientovaného datového modelu, možnosti použití, porovnání s relačním a objektově-relačním modelem. Standard SQL/OLB. [KIV/DB2]](22.md)
    - SQL/OLB (Object Language Bindings - standard pro integraci SQL v Jave)
    - objektove vlastnosti SQL99 (motivace, pridavani OOP principu/objektu do SQL, OOSRDB, rekurzivni struktury, slozite transakce, zapouzdreni, ADT, UDT (CREATE TYPE \<name\> AS OBJECT), OID, TYPE vs BODY -> procedure, function, FINAL, NOT FINAL, VARRAY, REF \<adt_name\>)
    - objektovy vs relacni svet (vazby - one-to-many atd. vs dedicnost)
    - ORM (JDBC - "kurzor" pristup, JPA (repository), tridy = tabulky, sloupce = atributy, plne automatizovane ORM vs manualni ORM (resi jen mapovani cloupec -> atribut), SELECT N+1, LAZY vs EAGER loading)
    - problemy ORM (public/private, DTO, dedicnost - kazda trida = 1 tabulka (hodne SQL), vse v 1 tabulka (prazdna pole), zvlast tabulka pro rodice a zvlast pro kazdeho potomka (kompromis))
    - JOINy (INNER, LEFT, RIGHT, OUTER)

23) [SQL/MM – multimediální databáze - základní rámec normy ISO/IEC 13249, full-textová data, prostorová data, obrázky (statické i videa). Možnosti dotazování, oblasti využití. XML databáze – charakteristické vlastnosti, výhody a nevýhody. Standard SQL/XML. [KIV/DB2]](23.md)
    - klasicke relacni DB vs multimedialni DB (dotaz na uplnou shodu, metrika, porovnani cisel vs porovnani obrazku, semantika, relevantnost)
    - priklady: obrazove DB, video kolekce, geometricke kolekce, casove rady, audio, biologicke DB, melodie, text
    - dotazy (klasicky realacni vs multimedialni -> dotaz na uplnou shodu, relevance)
    - typy MDB: text-base (analotace), content-based (pixely obrazku), hybridni (= kombinace)
    - modality vyhledavani (dotazovani vs browsing, query-by-example (viz Google images))
    - kriteria metrikovych vlastnosti (reflexivita, symetrika, pozitivni definitiva, tranzitivita)
    - 6 casti
        - full-text (CONTAINTS, SOUNDS-LIKE)
        - spatial (priklad prostoroveho dotazu: vsechna mesta rozdelena rekou)
        - general purpose facilities?
        - still image (porovnavani obrazku, pixel, textura, barva)
        - data mining (AI, zisk znalosti)
    - SQL/XML (zalozene na XML, efektivnejsi nez XML-enabled, vyhledvani, atd.)

24) [NoSQL databáze – charakteristika, porovnání ACID a BASE, CAP teorém. Kategorie NoSQL databází na základě datového modelu, příklady architektur. [KIV/DB2]
](24.md)
25) [Problém zpracování velkých dat, Big Data – charakteristické vlastnosti (5V), příklady uvedeného typu dat, alternativy zpracování, princip Map Reduce, Hadoop. [KIV/DB2, (KIV/DBM2, KIV/EITM)]](25.md)
26) [Distribuované databáze – koncepce distribuovaného databázového systému, replikace a fragmentace dat, distribuovaná správa transakcí. [KIV/DB2]](26.md)
27) [Temporální databáze, porovnání klasických a temporálních databází, modely času, vztah událostí a času (snapshot), temporální SQL. [KIV/DB2]](27.md)
