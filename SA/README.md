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
    - Moduly (coupling - provázanost: Tight, Loose), interakce mezi modulami = konector
    - Inversion of Control - odstranění tight coupling - lepší vývoj, testování, znovupoužitelnost
      - Lazy, Eager init
    - Dependency Lookup - závislosti v XML, tabulka..., komponenta sama hledá závislosti
      - MyClass c = ctx.getBean("myClass");
    - Dependency Injection
      - závislosti dohledává framework (Construktor injection (povinný), Setter injection(nepovinný), interface injection)
    - Kontrakt - dohoda mezi klientem a programátorem
      - syntaktická, sémantická, synchronizační, kvalitativní
    - SOLID - Single responsibility, Open-closed principle, Liskov substitution principle, Interface segregation principle, Dependency inversion principle
        - => lepší spravovatelnost, čitelnost, testování, rozšíření, vývoj
        - realizace přes návrhové vzory

04) [Architektonické styly, architektonické vzory a produktové řady – principy, účel a použití, způsoby
    realizace. [KIV/SAR]](04.md)
    - Architektonický styl (soubor design. rozhodnutí, obecné řešení ne detaily, přenositelný mezi doménama)
      - monolit
      - Hlavní program a podprogramy (jazyk C - volání procedur)
      - Objektově orientovaný styl (java - posílání zpráv, volání metod)
      - Component-based (Blackbox, glassbox, greybox, whitebox)
      - Service-oriented architecture (SOAP, XML, WSDL - definice služby)
      - Mikroservisová architektura (nástupce SOA, mini komponenty)
      - Vrstvený architektonický styl(Komunikace s vyšší vrstvou) - TCP/IP, klient-server(tlustý, tenký klient)
      - Filtry a roury (unix shell) - nejslabší komponenta->bottleneck
      - Dávkově Sekvenční Styl - filtr->filtr->filtr
      - Black Board - styl tabule,centrální, konzistence dat, př rezervační systém
      - Rule Based Architecture - znalostní db (ITIL), pravidlo x dotaz x odvození pravidel
      - Implicit invocation/Publisher-Subscriber - publisher posílá subům
      - Event-based - viz ESB
      - Interpreter - parsuje, vykonává příkazy, konektor-stream,data access, př.Excel
      - Mobile code - remote místo výkonu kódu
        - code on demand(JS), remote evaluation(validátor), mobile agent(PPR)
      - Peer-to-peer - komunikace přímo mezi uzly, robustní,rovnost uzlů
    - Architektonický vzor (doménově specifický)
      - 3-vrstvá architektura (prezenční, bussiness, datová)
      - MVC - uživatel->view(HTML/CSS), controler(PHP skript), model(DB)
      - MVP - vše přes presenter
      - MVVM - na základě notifikací. př Widget
      - Sensor-Controller-Actuator - vstup senzor->počítač->motor/ventil
    - Produktové řady - stejné jádro (stabilní), přidávání změn, př. Auta, iPhone

5) [5. Vícevrstvé a servisně orientované architektury – struktura a vlastnosti, příklady použití a technologie používané pro realizaci. [KIV/SAR, KIV/PIA]](05.md)
    - Architektonický styl (soubor design. rozhodnutí, obecné řešení ne detaily, přenositelný mezi doménama)
      - Service-oriented architecture (SOAP, XML, WSDL - definice služby, HTTPS, izolovanost)
      - Mikroservisová architektura (modulárnost,izolovanost,škálování,komunikace po síti - režie, bezpečnost)
      - Vrstvený architektonický styl(Komunikace s vyšší vrstvou) - TCP/IP, klient-server(tlustý, tenký klient)
        - Klient-Server(tlustý,tenký klient) - Škálovatelnost,oddělení odpovednosti, flexibilita
          - Webové, databázový, aplikační, souborový
      - Architektonický vzor(doménově specifický)
        - 3-vrstvá architektura (prezenční, bussiness, datová)
        - MVC - uživatel->view(HTML/CSS), controler(PHP skript), model(DB)
        - MVP - vše přes presenter
        - MVVM - na základě notifikací. př Widget
        - Sensor-Controller-Actuator - vstup senzor->počítač->motor/ventil
      - Realizace
        - Prezenční: HTML/CSS, Angular, React
        - Aplikační: Java-Spring, C#ASP.NET, Python-Django/FastAPI
        - Datová: SQL(Postgres,MySQL,MariaDB), NoSQL(Cassandra,MongoDB)

6) [6. Způsoby modelování, vizualizace a dokumentace architektury softwarových systémů a programových rozhraní (API), související standardy. [KIV/SAR, (KIV/ASWI)]](06.md)
    - Architektura (popis, preskriptivní(as intended architecture)/deskriptivní(as implemented architecture))
    - Architektonický model(popis přirozený jazyk, UML, ADL(jazyk pro popis architektur)) - komponenty, konektory, rozhraní, konfigurace, dataflow
    - UML(struktury, chování, interakce)
        - struktury-(Tříd(asociace,agregace,kompozice,dědičnost), komponent, nasazení, balíčků(Java), instancí)
        - chování -Aktivit, Use Case, Stavový(KA)
        - interakce-Sekvenční, (komunikace),
    - Architecture Description Language (formální popis architektur, výhody, nevýhody)
      - viz. generování překladačů, PIM, PSM
      - záměření - struktura(komponent,konector,rozhraní), analýza(konzistence, nejednoznačnost, výkon)
      - požadavky->UML->Implementace
      - př. AADL(popis SW i HW)
    - Dokumentace API
      - JavaDoc,DoxyGen,WSDL(XML),Swagger(YAML/anotace)

7) [Charakteristiky a metriky kvality softwarové architektury. Metody a nástroje pro analýzu a ověření kvality architektury. [KIV/SAR, (KIV/ASWI)]](07.md)
    - Kvalita(levnější opravit na začátku, primární uživatelské požadavky, vnitřní->vnější)
    - Opak kvalita - Omyl->Defekt->Chybový stav->selhání
    - Analýza architektury(zkoumání mimofunčních vlastností systému)
      - úroveň formálnosti(neformální(sketch) x formální(ADL))
      - Spustitelná architektura(ADL->graf+implementace)
      - PoC, PoT
    - Analyzovatelné vlastnosti architektury
      - účinnost, složitost, škálovatelnost, přenositelnost, spolehlivost, Dostupnost, Odolnost proti selhání, Možnost přežití
    - The four "C" - Completeness, Consistency, Compatibility, Correctness
    - Kategorie analýz - Založené na:
      - Modelu(ADL, hard vlastnosti)
      - Simulaci(složité-mnoho parametrů, simulační jazyk)
      - Inspekci a kontrole(stakeholdeři, soft vlastnosti systému)
    - ATAM(Architecture Tradeoff Analysis Method)
      - zmírnění rizika, diskutace se stakeholdery, mimofunkční požadavky
      - bezpečnost, výkonnost, spolehlivost, modifikace(dynamický škálování podle zátěže)

8) [Role architektury v rámci vývoje software, vztah k dalším disciplínám a modelům vývoje. Principy vývoje software řízeného návrhem (MDA, MDD). [KIV/SAR,KIV/ASWII]](08.md)
    - Architektura (popis, preskriptivní(as intended architecture)/deskriptivní(as implemented architecture))
    - Turbínová vizualizace - množství a typ artefaktů zachycena v čase(požadavky až vývoj a testování)
      - průřez=zachycení stavu v čase, průměr=množství artefaktů, tělo/vnitřek=typ artefaktu
    - Proces:
      - Analýza požadavků(sledování existujících řešení, úplné požavky, levné při návrhu)
        - Twin Peaks(architektura a požadavky jsou vrcholy->rozvijí se vzájemně)
      - Design a architektura(popis)
        - Architecture-Centric design - architektura centrální prvek, zachycení rizik,požadavků
          - Separation of concern, abstrakce, modularita
      - Implementace
        - automatické generování, manuální, outsourcing, middlewaqre, reuse-base
      - Analýza a testování
        - zhodnocení kvality, PoC, PoT, ATAM, ověření správnosti
      - Evoluce a údržba
    - Degradace architektury (architektonický drift a eroze)
    - Principy vývoje software řízeného návrhem
      - Model Driven Development (MDD) - paradigma
      - Model Driven Architecture (MDA)-oddělení business logiky od implementace
        - PIM (Platform Independent Model)-business logika,chování,přenositelnost, technologická nezávislost
        - PSM (Platform Specific Model)
      - PIM(UML)->PSM(.NET)

9) [9. Architektonické principy, standardy a technologie tvořící technický základ WWW, vývoj v této oblasti, důsledky pro tvorbu webových aplikací. [KIV/PIA]](09.md)
    - WWW(klient(požadavek),server(odpověď),http,tcp/ip,soap,frontend,backend,URI=URL+URN)
    - vývoj WWW-HTML+CSS,javascript,verze(1.1->1 TCP=soubor,1.2->1 TCP=soubory,1.3->UDP)
    - Požadavky(GET,HEAD(metadata),POST,PUT,DELETE,TRACE,CONNECT,OPTIONS(endpointy))
    - Struktura požadavku
      - hlavička(host,origin,content-type,accept,authorization,content-lenght,cookies)
      - tělo
    - HTTP odpověď
      - stavy(1xx,2xx,3xx,4xx,5xx)
    - HTTPS(SSL/TLS, symetrická/asimetrická šifra, certifikát, certifikační autorita(let's encrypt))
    - Důsledky pro vývoj web. aplikací
      - nejdříve jen PC, postupem mobily, tablety -> responzivní web
      - omezené technologie- statické weby->dynamické weby
      - formuláře,interaktivita,databáze,příchod CSS a JS, HTML5(multimédia)
      - frameworky/knihovny - React,Angular
      - web 2.0(obsah vytváří uživatelé - fórum)

10) [10. Protokoly pro komunikaci a přenos dat mezi klientskou a serverovou částí webu, řešení zabezpečení a udržování sezení (session), základní funkčnost webového serveru. [KIV/PIA, (KIV/UPS, KIV/WEB)]](10.md)
    - HTTP/S
    - Session(stavovost do bezstavového protokolu,data na serveru,mapa/tabulka,info o uživateli,sessionID)
    - Cookies(data u klienta, sessionID)
        - správa relací, sledování uživatelů, personalizace stránek
        - odesílají se všechny s každým http/s, musí odpovídat doména/cesta/protokol
        - Set-Cookie: name=value
          - Expires,Domain,Path,Secure(HTTPS only)
    - HTML WebStorage API
      - uložené v prohlížeči, neposílají se s požadavky
      - Session storage, Local storage
    - Websockety(obousměrná komunikace)
      - Polling, Long-Polling
      - založena na TCP, navázání přes HTTP(upgrade connection)
      - parametry websocket packetu: FIN(konec zprávy),opcode(typ zprávy), payload lenght/data
    - Heartbeat-kontrola spojení,periodický vs před odesláním požadavku
    - Ukončení spojení
    - RESTful WebService
      - návrhový vzor pro návrh API, není protokol, formáty: XML,JSON,YAML, struktura, bezstavový, operace(GET,PUT..)
    - HTTP Proxy
      - nahrazuje IP svojí vlastní IP
      - Forward(do externí sítě-omezení stránek), Reverse(z externí sítě-load balancer)
      - X-Forwarded-For(původní IP), X-Forwarded-Host(cílová adresa), X-Forwarded-Proto(prokotol)

11) [11. Struktura klientské části webových systémů, technologie webových stránek pro prezentační a aplikační weby. Zásady pro tvorbu stránek (přístupnost, SEO, ...). [KIV/PIA , (KIV/WEB)]](11.md)
    - Základní rozdělení
      - Server Side Render - posílá celou HTML,znovunačtení celé stránky při interakci,horší odezva na vstupy
      - Client Side Render - generování u klienta, asynchroní získání dat,lepší odezva
      - kombinace
    - Prezentační weby - neměnné,HTML+CSS,životopis nebo portfolio,často Server-Side render
    - Aplikační (dynamické weby)
      - webové aplikace,zabezpečení(session),HTML,CSS,PHP,JS,JAVA
    - HTML,XHTML(přísnější, založené na XML), HTML5(multimédia, localstorage,sessinstorage)
    - CSS(vizuální vzhled, kaskádově přepisované podle pravidel)
    - PHP
      - kód přímo v HTML, skript proveden na serveru, multiplatformní
    - Zásady pro tvorbu webů
      - Navigace, Přístupnost(i pro mobili), Použitelnost
    - Search Engine Optimization
      - snaha mít co nejlepší pozici při vyhledávání
      - neetické metody: Spamování odkazu na fórech, oklamání botů, skrytý text

12) [12. Zpracování klientských požadavků na webovém serveru, základní mechanismus a varianty řešení (statický a dynamický obsah). Realizace v různých jazycích a technologiích. [KIV/PIA,(KIV/WEB, KIV/NET)]](12.md)
    - Webový server(pool vláken, zpracování HTTP)
    - Statický x dynamický obsah
    - LAMP(Linux,apache,MySql,PHP), Apache vs Nginx
    - Java Servlets - třída obsluhující Http požadavek, cyklus zpracování,kontejner
    - Šablony(teplate engine-thymeleaf,JSP)
    - Spring(@Controller),Node.js(JS+Chrome V8 prostředí, Single Page Application)
    - CGI(jednotné rozhraní, zastaralé, dynamický generování)

13) [13. Struktura (architektura) serverové části webové aplikace, související návrhové a architektonické vzory. Předávání dat mezi vrstvami aplikace, techniky pro oddělení  obsahu a prezentace. [KIV/PIA (KIV/WEB)]](13.md)
    - architektury-monolit,SOA,mikroslužby
    - základní principy-aplikační vrstvy(UI,business,datová)
    - Clean Architecture-z vnější dovnitřní(drivers/frameworks->rozhraní->use-case->entities)
    - Návrhové vzory-MVC, MVP, MVVM, IoC, DI, Aspect-oriented programming
    - Datová vrstva-DTO, DAO(JDBC,JPA-Hibernate)

14) [14. Tvorba webových aplikací s použitím základních knihoven a pokročilých aplikačních rámců, obsluha požadavků a generování klientské (prezentační) části. Dopady na efektivitu. [KIV/PIA,(KIV/WEB, KIV/NET)]](14.md)
    - Framework(popis, obsah, co řeší, frozen/hot spots)
      - řeší útoky XSS, CSRF
      - Angular, Node.JS, Laravel, Symfony, Spring (Boot)
    - Knihovna - popis, React
    - Balíčkovací systémy(Composer,NPM,Bower)
    - Dopady na efektivitu
      - výhody - rychlejší vývoj,SoC, standard, podpora
      - nevýhody - ne pro malé apky, režie, znalost, ztráta kontroly, ORM

15) [15. Řešení persistence dat, základní mechanismy. ORM, jeho výhody a nedostatky. Související standardy a technologie. [KIV/PIA]](15.md)
    - Perzistence dat(trvalé uložení dat, dopad na nefunkční požadavky)
      - Relační - MariaDB,PostgreSQL
      - NoSQL(Distribuovaný systémy, škálování) - Document-based(MongoDb), Key-Value(Redis), Wide-Column(Cassandra, Graph(Giraph)
    - Souborový systém(Alfresco)
    - Základní mechanismy
      - manuální(JDBC)
      - ORM(výhody,nevýhody,plně/částečně generovaný SQL)
        - problém
          - Select N+1(Lazy/Eager init)
          - dědičnost(tabulka=třída, jedna tabulka pro všechno, tabulka(rodič)->potomci samostatně))
          - public/private
        - třídy->tabulky,atributy->sloupce
        - př: JPA-Hivernate

16) [16. Formy integrace na aplikační vrstvě, webové služby. Technologie, příklady realizace. [KIV/PIA, (KIV/EITM)]](16.md)
    - Webová služba(komunikace mezi apps, SOAP, HTTP, kontrakt, WSDL, ESB)
    - SOAP(service: registry, provider, requester)
    - SOA(govenance, lifecycle,Service Integration Maturity Model)
    - REST(popis, metody(GET,PUT,POST...), formát zpráv, HATEOAS, overfetching)
    - GraphQL(řešení over/under fetching)
    - Webové sockety(ws, (long) polling, http connection: upgrade, formát zprávy, Heartbeat, Ukončení spojení)

17) [17. Základní pojmy a modely v oblasti spolehlivosti a výkonnosti softwarových systémů, jejich příklady a souvislost se specifikací požadavků, návrhem architektury a implementaci. [KIV/VSS,(KIV/ASWI)]](17.md)
    - spolehlivost (mimofunkci pozadavky, kvantifikace, metrika (MTBF = MTTF + MTTR), SLA)
      - MTTF = 1 / λ; MTTR = 1 / μ
    - stav systemu ((bez)poruchovy), provoz systemu ((ne)obnovovany, poruchy (systematicke/nahodne), mistake -> fault -> error -> failure)
    - vykonnost (doba odezvy, delka odezvy, ...)
    - modelovani budouciho systemu (analyticky (vyhody/nevyhody; konstantni λ (cas t1 az cas t2)), simulacni (analyticky (vyhody/nevyhody), verifikace vs validace, zjednoduseni)
    - SW (= systematicke chyby, metriky (MISRA, AUTOSAR, ...), metodiky)
    - HW (= nahodne chyby, rozsah senzoru, zaseknuti ADC, modelovani, redundance, typy zaloh - horka, tepla, studena)
    - fail-safe, fault-folerant
    - neobnovane systemy: Q(t), R(t) => diferencialni rovnice
    - obnovovane systemy: prumer casu kdy system (ne)bezi, koeficient pohotovosti vs prostoje
    - trik s diferencialnimi rovnicemi = spocitame ppst a cas kazde cesty od zdroje ke stoku => Ts = vazeny prumer
    - obnovovane systemy: silne souvisly graft, konstantni ppst setrvani ve stavech

18) [18. Způsoby zajištění spolehlivosti systému na úrovni hw a sw, spolehlivostní modely. Normy související s tvorbou spolehlivých softwarových systémů. [KIV/VSS]](18.md)
    - zpusoby zjisteni spolehlivosti
      - SW (systematicke chyby, testovani - jednotkove, funkci, atd., formalni dokazovani, review, metriky (pokryti testy, ...), oponentura, normy - ISO, MISRA, AUTOSAR, IEEE)
      - HW (nahodne chyby, redundance, bezpecnost vs cena, horka, studena, tepla zaloha)
    - poissonovo vs exponencialni rozdeleni
    - systemy s nezavislymi prvky
      - seriove zapojeni (nasobime R(t))
      - parlaleni zapojeni (nasobime Q(t)); + kombinace
      - stavovy graf (R = R1R2R3 + R1R2Q3 + ...)
      - root-cause analysis (strom poruch)
    - systemy se zavislymi prvky
      - simulace (hod kostkou T = min{t1 + t1', t2 + t2'})
      - markovske modely (obnovovane vs neobnovovane)

19) [19. Metody generování náhodných a pseudonáhodných čísel, jejich vlastnosti a omezení, využití náhodných čísel [KIV/VSS].](19.md)
    - vyuziti generovani nahodnych cisel (kryptografie, hry, testovani, simulace - napr. Monte Carlo)
    - zdroje nahody (statisticke tabulky, fyzikalni generatory, algebraitske generatory)
    - fyzikalni generator (sum, pocasi, castice, "tiche selhani", /dev/random vs /dev/urandom, /dev/hwrnd)
    - pseudo-nahodne (vlastnosti: algebraticke, deterministicke, konecne; idealni vlastnosti: mala pamet, velka rychlost, dlouha perioda)
    - statistika (nahodna velicina, stredni hodnota E(X), rozptyl D(X) vs smerodatna odchylka σ)
      - diskretni (funkce ppst, kumulativni distribucni fce; hod kostkou)
      - spojite (funkce hustotu, kumulativni distribucni fce, vyska osoby)
    - rovnomerne vs kvazirovnomerne rozdeleni
    - metoda prostrednich radu (nevyhody: akumulace 0 (generovani malych cisel), generovani stejneho cisla)
    - LCG (multiplikativni, aditivni, prodlouzeni periody, modulo m, volba parametru, rychlost => jedna instrukce, mala pamet)
    - smisene generatory
    - Mersenne Twister (vetsi pamet, kryptograficky bezpecny, implementovan v C++, Pythonu, ...)
    - kryptograficky test generatoru (ppst dalsiho bitu < 50%, nelze zpetne dekryptovat)
    - trnsformacni metoda (transformace distribucne fce)
    - vylucovaci metoda (2 generatory, prijmuti/odmitnuti hodnoty, funkce hustoty)
    - centralni limitni veta (12 LCG, soucet, Sn -= 6)
    - generovani obecneho diskretniho rozdeleni (viz transformacni metoda)
    - testovani generatoru (E(X), D(X), histogram (vizualne), Chi-Square test dobre shody)

20) [20. Modely systémů pro analýzu výkonnosti – sítě front, markovské modely. Abstraktní (formální) reprezentace, možnosti programové realizace. Způsoby využití. [KIV/VSS]](20.md)
    - makrovske modely
      - fronta lidi, nemocnice, router, buffery, page rank, SIR modely
      - neco jako KA ale s ppsti prechodu (nahoda), markovska vlastnost
      - poisson vs exponencialni rozdeleni, matice ppsti prechodu, matice intenzit prechodu
      - obecny model odvozeni (podminena ppst prechodu - pij = λ \* dt (dt -> 0); pi(t+dt) = pi(t) - λij \* pi(t) dt)
      - doba setrvani ve stavu, frekvence pruchodu stavem, frekvence pruchodu hranou
      - kolmogorovy rovnice (pi(t)' = pi(t) * matice intenzit prechodu, linarne zavisle rovnice => p1 + p2 + p3 = 1; pocatecni podminka, absorpcni stav, absence absorpcniho stavu => pi(t)' = 0 => diferencialni rovnice odpadnou, silne souvisly graf)
      - priklad dvou procesu a KS, producent-konzument
    - SHO (aplikace markovskych modelu)
      - modelovani nemocnic, prapazek na pokladne, krizovatky, atd.
      - elementarni SHO (schema)
        - vstupni proud λ (pro pouziti markovskych modelu musi byt: homogeni a ordinalni, pokud nezname => odmerit pro zjisteni statistickych udaju, koeficient variace)
        - fronta (politika (napr. FIFO), konecne vs omezena, Tw, Lw)
        - kanal(y) obsluhy μ (koeficient variace, realne vs teoreticke ρ)
        - vystupni proud (silne zavisi na ρ, stacionarni vs nestacionarni rezim)
      - zatizeni systemu ρ = 1/m \* λ/μ
      - Littlovy vzorce (plati zakon zachovani, propojuji cas a delku, Lq = Lw + Ls; Tq = Tw + Ts; Lq = λ \* Tq; plati pouze ve stacionarnim rezimu (fronty nerostou do nekonecna))
      - Kandellova klasifikace (X/Y/m/I/disc. napr. M/M/1/n/FIFO)
    - site front
      - propojeni vicero SHO
      - otevrene site front (trivialni dosazeni do vzorecku, rovnice toku (velke lambda = zapocitani i zpetnych vazeb), vaha hrany = ppst; vytizeni dilcich SHO = misto male lambdy vezmeme velkou lambdu; stationarni stav = pro ani jeden SHO neni ρ > 1)
      - uzavrene site front (tezsi analyza, lisi se priklad od prikladu, lepsi skoro az pouzit simulace; viz n terminalu ktere se pripojuji na server)
    - reprezentace markovskych modelu (matice podminnych ppsti, matice intenzit prechodu, graf)
  
21) [21. Softwarové simulace – základní pojmy a techniky, práce s časem. Využití, výhody a nedostatky simulace. [KIV/VSS]](21.md)
    - simulacni model (zjednoduseni reality, uroven detailu, verifikace/validace)
    - deleni simulaci
      - dle ucelu (analyticke / virtualni prostredi (simulatory))
      - dle chovani (deterministicke (3 telesa) / stochasticke (monte carlo))
      - dle casu (staticke (vypocet PI) / dynamicke (SHO))
      - dle reprezentace casu (spojite (let rakety), diskretni (udalostni simulace - kalendar, interpret, command pattern))
      - dle urovne detailu (makroskopicke (tok silnic), mesoskopicke (kolony), mikroskopicke (auta), nanoskopicke (ridici))
      - dle typu modelu (analyticke, numericke, logicke (celularni automaty))
      - hybridni simulace
    - vyhody pouziti simulace / nevyhody pouziti simulace (kdy je dobre ji pouzit a kdy ne)
    - zakladni pojmy (entita, stav, aktivita, udalost)
    - navrh simulacniho modelu (cile, tvorba modelu (validace), navrh experimentu, beh, agregace vysledku, zaver; citlivostni analyza)
    - nastroje pro tvorbu simulace (prog. jazyky (Java), knihovny (JSim), nastroje (Simulink))
    - simulace markovskych (KS, bariera, randez-vous)

22) [22. Tvorba a parametrizace simulačního modelu, simulace paralelních systémů, okolí simulovaného systému. [KIV/VSS]](22.md)
23) [23. Hodnocení a metriky výkonnosti, dostupnosti a spolehlivosti softwarových systémů, způsoby získání hodnot, jejich analýza a prezentace. [KIV/VSS, (KIV/VID)]](23.md)
24) [24. Techniky měření výkonnostních a zátěžových parametrů software, zajištění opakovatelnosti testů, benchmarking. [KIV/VSS, (KIV/ASWI, KIV/OKS)]](24.md)
25) [25. Metody, modely a nástroje pro statickou a pro dynamickou analýzu software. Použití pro ověření spolehlivosti, výhody a omezení. [KIV/VSS]](25.md)
