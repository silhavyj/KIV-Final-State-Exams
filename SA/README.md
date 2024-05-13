## SA - Softwarové architektury

01) [Principy správného strukturování software (modularita, skrývání informace, separation of concerns, SOLID), způsoby realizace a význam pro kvalitu sw systémů. [KIV/SAR; KIV/OOP]](01.md)
    - Imperativní(Procedurální) programování (píšeme jak má program dělat) vs deklarativní (SQL, specifikujeme co ale ne jak)
    - Modularita (rozdělení kódu, testování, čitelnost, znovupoužitelnost, nahrazení)
    - Skrávání informace (rozhraní x implementace, popis rozhraní, specifikace - verifikace = rozhraní programátor-klient)
    - Kontrakt (úrovně - syntaktická(hlavička, parametry, výjimky), sémantická (vedlejší efekty, pre/postconditions, bod xy od jakého rohu), synchronizační, kvalitativní)
    - Separation of concern - oddělení nesouvisejícího kódu, redukce duplicit, udržovatelnost, menší složitost a lepší porozumění,TCP/IP nebo CSS+HTML
    - SOLID - Single responsibility, Open-closed principle, Liskov substitution principle, Interface segregation principle, Dependency inversion principle
      - => lepší spravovatelnost, čitelnost, testování, rozšíření, vývoj
      - realizace přes návrhové vzory
    - Návrhové vzory 
      - Creational patterns(vytváření objektů)
        - Singleton, Lazy Initialization, Abstract Factory, Builder, Object Pool
      - Structural Patterns (uspořádání tříd)
        - Proxy, Decorator, Adapter, Facade, Bridge
      - Behavioral Patterns(komunikace mezi objekty)
        - Command, Inversion of Control, Iterator, Observer, Mediator


02) [Prvky struktury softwarových systémů v popisu architektury, koncept softwarových komponent a konektorů. Způsoby jejich realizace v konkrétních jazycích/prostředcích.[KIV/SAR]](02.md)
    - architektura (popis, preskriptivní, deskriptivní, komponenty, konektory)
    - komponentové modely a frameworky (definice, výhody, nevýhody - závislosti)
    - konektor (RPC, pipe, sdílená paměť, REST, SOAP, ESB, event)
      - koordinace, konverze, usnadnění
      - role: komunikační, řídící, konverzní, facilitační
      - příklady: Procedure call, event, data access(JDBC), Arbitrator, distributor
      - Způsob realizace: objekt (OOP), DAO(Spring repository), modul (.c/.h soubory), middleware

03) [Závislosti modulů v sw architekturách, způsob řešení vazeb (dependency resolution), přístup Inversion of Control. Kompatibilita vazeb, kontrakt a Liskov substitution principle. [KIV/SAR, KIV/PIA]](03.md)
04) [Architektonické styly, architektonické vzory a produktové řady – principy, účel a použití, způsoby
    realizace. [KIV/SAR]](04.md)
5) [5. Vícevrstvé a servisně orientované architektury – struktura a vlastnosti, příklady použití a technologie používané pro realizaci. [KIV/SAR, KIV/PIA]](05.md)
6) [6. Způsoby modelování, vizualizace a dokumentace architektury softwarových systémů a programových rozhraní (API), související standardy. [KIV/SAR, (KIV/ASWI)]](06.md)
7) [Charakteristiky a metriky kvality softwarové architektury. Metody a nástroje pro analýzu a ověření kvality architektury. [KIV/SAR, (KIV/ASWI)]](07.md)
8) [Role architektury v rámci vývoje software, vztah k dalším disciplínám a modelům vývoje. Principy vývoje software řízeného návrhem (MDA, MDD). [KIV/SAR,KIV/ASWII]](08.md)
9) [9. Architektonické principy, standardy a technologie tvořící technický základ WWW, vývoj v této oblasti, důsledky pro tvorbu webových aplikací. [KIV/PIA]](09.md)
10) [10. Protokoly pro komunikaci a přenos dat mezi klientskou a serverovou částí webu, řešení zabezpečení a udržování sezení (session), základní funkčnost webového serveru. [KIV/PIA, (KIV/UPS, KIV/WEB)]](10.md)
11) [11. Struktura klientské části webových systémů, technologie webových stránek pro prezentační a aplikační weby. Zásady pro tvorbu stránek (přístupnost, SEO, ...). [KIV/PIA , (KIV/WEB)]](11.md)
12) [12. Zpracování klientských požadavků na webovém serveru, základní mechanismus a varianty řešení (statický a dynamický obsah). Realizace v různých jazycích a technologiích. [KIV/PIA,(KIV/WEB, KIV/NET)]](12.md)
13) [13. Struktura (architektura) serverové části webové aplikace, související návrhové a architektonické vzory. Předávání dat mezi vrstvami aplikace, techniky pro oddělení  obsahu a prezentace. [KIV/PIA (KIV/WEB)]](13.md)
14) [14. Tvorba webových aplikací s použitím základních knihoven a pokročilých aplikačních rámců, obsluha požadavků a generování klientské (prezentační) části. Dopady na efektivitu. [KIV/PIA,(KIV/WEB, KIV/NET)]](14.md)
15) [15. Řešení persistence dat, základní mechanismy. ORM, jeho výhody a nedostatky. Související standardy a technologie. [KIV/PIA]](15.md)
16) [16. Formy integrace na aplikační vrstvě, webové služby. Technologie, příklady realizace. [KIV/PIA, (KIV/EITM)]](16.md)
17) [17. Základní pojmy a modely v oblasti spolehlivosti a výkonnosti softwarových systémů, jejich příklady a souvislost se specifikací požadavků, návrhem architektury a implementaci. [KIV/VSS,(KIV/ASWI)]](17.md)
18) [18. Způsoby zajištění spolehlivosti systému na úrovni hw a sw, spolehlivostní modely. Normy související s tvorbou spolehlivých softwarových systémů. [KIV/VSS]](18.md)
19) [19. Metody generování náhodných a pseudonáhodných čísel, jejich vlastnosti a omezení, využití náhodných čísel [KIV/VSS].](19.md)
20) [20. Modely systémů pro analýzu výkonnosti – sítě front, markovské modely. Abstraktní (formální) reprezentace, možnosti programové realizace. Způsoby využití. [KIV/VSS]](20.md)
21) [21. Softwarové simulace – základní pojmy a techniky, práce s časem. Využití, výhody a nedostatky simulace. [KIV/VSS]](21.md)
22) [22. Tvorba a parametrizace simulačního modelu, simulace paralelních systémů, okolí simulovaného systému. [KIV/VSS]](22.md)
23) [23. Hodnocení a metriky výkonnosti, dostupnosti a spolehlivosti softwarových systémů, způsoby získání hodnot, jejich analýza a prezentace. [KIV/VSS, (KIV/VID)]](23.md)
24) [24. Techniky měření výkonnostních a zátěžových parametrů software, zajištění opakovatelnosti testů, benchmarking. [KIV/VSS, (KIV/ASWI, KIV/OKS)]](24.md)
25) [25. Metody, modely a nástroje pro statickou a pro dynamickou analýzu software. Použití pro ověření spolehlivosti, výhody a omezení. [KIV/VSS]](25.md)
