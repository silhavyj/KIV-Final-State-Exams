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
09) [Přehled činností při provozu sw (IS/IT) produktu. Řízení, dodávka a podpora IT služeb (ITSM), řízení změn a incidentů, související metodiky (ITIL a další). [KIV/ASWI, KIV/EITM]](09.md)
10) [Strategické řízení firem, poslání a role IT v organizaci, tvorba strategie IT/IS. Koncepce a metody řízení IT -- Enterprise architektura (EA) a IT governance. [KIV/EITM]](10.md)
11) [Proces akvizice IS/IT systému. Výběrové řízení, poptávka a nabídka, výběr a nákup řešení, studie proveditelnosti, PoC, PoT, poptávkové řízení (RFI, RFP, RFQ).[KIV/EITM]](11.md)
12) [Projektové a multiprojektové řízení, projektová kancelář, metody hodnocení projektů, PMBOK. [KIV/EITM, (KIV/ASWI)]](12.md)
13) [Způsoby integrace informačních systémů, přístupy a technologie pro jednotlivé vrstvy. [KIV/EITM, (KIV/PIA)]](13.md)
14) [Integrace IS na datové vrstvě, datová pumpa, EDI, proces extrakce, transformace a vložení dat (ETL). [KIV/EITM, KIV/DBM2]](14.md)
15) [Správa dat v podniku (Data Management). Kvalita dat a její řízení, master data management (MDM). Nestrukturovaná podniková data, správa podnikového obsahu (ECM). [KIV/EITM, (KIV/DBM2)]](15.md)
16) [Analytické nástroje pro sledování výkonu organizace, KPI a dashboardy, podpora rozhodování, Business Inteligence (BI). [KIV/EITM, (KIV/DBM2)]](16.md)
17) [Řízení komunikace a spolupráce v organizaci, workflow, ESN. Business process management (BPM). [KIV/EITM, (KIV/ZIM)]](17.md)
18) [Přehled problematiky bezpečnosti IT/IS, komplexní přístupy a nástroje pro řízení bezpečnosti [KIV/EITM, (KIV/BIT)]](18.md)
19) [Outsourcing IT. Poskytování IT jako služby (ITaaS), výhody a nevýhody cloudových technologií. [KIV/EITM]](19.md)

### KIV/DB2

20) [Standardizace vývoje databázové technologie, norma ISO/IEC 9075 – rozšíření možností relačního modelu a trend vývoje databázové technologie - procedurální prostředky v rámci jazyka SQL. Kurzory – definice, klasifikace, použití kurzorů. Uložené procedury a funkce, balíky (packages), kompilace, spouštění. Standard SQL/PSM. [KIV/DB2]](20.md)
21) [Dynamické a statické SQL, aktivní databáze – charakteristika, význam, příklady využití, porovnání s jinými možnostmi ovládání integrity a konzistence databáze. [KIV/DB2]](21.md)
22) [Objektové vlastnosti jazyka SQL99, rozšíření datových typů. Vlastnosti objektově orientovaného datového modelu, možnosti použití, porovnání s relačním a objektově-relačním modelem. Standard SQL/OLB. [KIV/DB2]](22.md)
23) [SQL/MM – multimediální databáze - základní rámec normy ISO/IEC 13249, full-textová data, prostorová data, obrázky (statické i videa). Možnosti dotazování, oblasti využití. XML databáze – charakteristické vlastnosti, výhody a nevýhody. Standard SQL/XML. [KIV/DB2]](23.md)
24) [NoSQL databáze – charakteristika, porovnání ACID a BASE, CAP teorém. Kategorie NoSQL databází na základě datového modelu, příklady architektur. [KIV/DB2]
](24.md)
25) [Problém zpracování velkých dat, Big Data – charakteristické vlastnosti (5V), příklady uvedeného typu dat, alternativy zpracování, princip Map Reduce, Hadoop. [KIV/DB2, (KIV/DBM2, KIV/EITM)]](25.md)
26) [Distribuované databáze – koncepce distribuovaného databázového systému, replikace a fragmentace dat, distribuovaná správa transakcí. [KIV/DB2]](26.md)
27) [Temporální databáze, porovnání klasických a temporálních databází, modely času, vztah událostí a času (snapshot), temporální SQL. [KIV/DB2]](27.md)
