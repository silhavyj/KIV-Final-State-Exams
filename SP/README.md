## SP - Systémové programování

### KIV/OS

01) [Jádro operačního systému a uživatelský režim procesu, zavedení vybraného typu jádra a uživatelského procesu. [KIV/OS, (KIV/ZOS)]](01.md)
    - co je OS (planovani procesu + rizeny pristup ke zdrojum)
    - jadro kernelu (co to je, zavedeni, interface - syscally, typy jadra)
    - uzivatelsky proces (CPL0, RTL, privelegovani instrukce, bootstrap)
    - real mode (adresovani - baze + offset = 20b)
    - protected mode (PAE, prepnuti do 32b modu - GDT/LDT + PE bit v CR0, segment selectory - adresace)
    - unreal
    - zavedeni MSDOS (IO.SYS, MSDOS.SYS, zavedeni jadra > 1MB - XMS a EMS)
    - UEFI (GPT, EFI binarky - zajisteni integrity)

02) [Virtuální adresový prostor – implementace sdílené paměti, sdílených knihoven a copy-on-write. [KIV/OS, (KIV/ZOS)]](02.md)
    - virtualni prostor (k cemu to je, MMU, TLB+ flush)
    - segmentace (vyhody + nevyhody, segment selector, segment descripor, segmentove registry, fragmentace)
    - strankovani (vyhody + nevyhody, TLB, CR3, swapping - RR, MRU, LRU, dirty bit, present bit, access bit, granulatira velikosti stranky, page fault)
    - princip prikladu virtualni adresy (virtualni -> linearni -> fyzicka, segmentace + strankovani)
    - Symbol resolving (dll, so, PLT, GOT, __declspec(dllimport/dllexport))
    - Copy-on-Write (princip, vyuziti - napr. fork, sdilene knihovny)

03) [Přerušení, systémová volání, výjimky, V/V zařízení – jejich implementace a obsluha. [KIV/OS, (KIV/ZOS)]](03.md)
    - co je preruseni (IDT, typy - SW, HW, a vyjimky, CPL, maskovani)
    - co je to systemove volani (RTL, STL, INT, IRET, TSS)
    - top-half & bottom-half (kriticke, tasklet)
    - zpracovani prerusni (postup)
    - vyjimky (try-catch -> handlery v PCB, typy - trap, fault, abort)
    - IO/zarizeni (IRQ, PIC, PMOI, MMIO - backplane bus, Linux VFS - vse se tvari jako soubor)
    - komunikace s I/O (prime, radic (+ preruseni), DMA, ovladac)

04) [Vlákna na symetrickém multiprocesoru, jejich synchronizace a implementace. [KIV/OS]](04.md)
    - vlakno (co to je - planovaci jednotka? implementace TCB + obsah TCB, crt0)
    - concurrency vs parallelism
    - kooperativni (napr. MS-DOS, yield) vs preemtivni planovani (IRQ0, kontext switch, TSS)
    - SMP bootstrap (MPFPS - _MP_signature, MP Config - seznam dostupnych CPU, bootstrap, BSP, AP, APIC)
    - synchronizace na SMP (teoreticky - sbernice, atomic operace (+ strojove slovo), prkaticky - TLS, spinlock)
    - fork() + copy on write, exec(), clone(), zombie, sirotek, init proces
    - stavove fronty vlakna
    - kernelova vs userspace vlakna (RTL planovac, kernel planovac)

05) [Plánovač – Process Control Block, Thread Control Block, stavová fronta a algoritmus plánovače. [KIV/OS, (KIV/ZOS)]](05.md)
    - PCB (struktura - co obsahuje, afinita, ACL, ...)
    - TCB ve Windows (TEB, TLS = Thread Local Storage)
    - stavy vlakna (zjednoduseni vs realita - SMP, afinita)
    - stavove fronty (prosovani ukazatele na PCB)
    - planovac (RR, RR s prioritama, staticka vs dynamicka priorita)
    - Linux planovac (Active, Expired, epocha, => CPF - red/black, vrtuntime)
    - Windows (RR s prioritami - staticka + dynamicka)

06) [Meziprocesová synchronizace – princip a implementace semaforu, mutexu, roury, zpráv a signálů. [KIV/OS]](06.md)
    - k cemu je meziprocesova komunikace
    - spinlock (= jedina moznost synchronizace, implementovano v userspace - RTL)
    - semafor (struktura - co obsahuje, kod, Acquire (while (counter == 0)), TryAcquire, Release, notify_all_threads, binarni semafor)
    - producent konzument (3 semafory inicializovane na 0, N, 1)
    - mutex (binarni semafor vs mutex, implementace)
    - pipe (in/out, buffer, producent-konzument, pojmenovava pipe)
    - zpravy (PostMessage, SendMessage, PeekMessage(), GetMessage(), WM_COPYDATA  - IParam, fronty zprav)
    - signaly (handlery - obdoba IDT, Process-Directed Signals, Thread-Directed Signals, sigmask & pending_mask => implementace, signaly u fork() a exec(), realtime signaly 0-31, 32-63 (determinismus))

07) [Souborový systém - Virtual File System, Installable File System, FAT, Ext2, NTFS. [KIV/OS, (KIV/ZOS)]](07.md)
    - VFS (userspace, FS, driver = 3 urovne, pointery na funkce -> close, read, write, atd.)
    - IFS (FS, MiniFilter (FilterDriver - legacy), registrace filtru (FilterManager))
    - IORP (IO Manager, fronta pozadavku driveru, FastIO, obsluha IO pozadavku - postup)
    - APIC (nedostatky PICu, MSI = {ID, IRQ}, APIC bus)
    - top-half & bottom-half (SoftIRQ, Tasklet, polling vs interrupt, workqueue - Linux)
    - IO_uring, userspace drivery
    - FAT (struktura, FAT tabulka, typy FAT, root folder)
    - EXT2 (struktura, bitmapy, obsah inodu, obsah slozky, prime vs neprime odkazy, ACL od ext4, symlink vs hardlink)
    - NTFS (struktura, obsah MTF a jeji zalohovani, nastupce FAT, sifrovani, komprese, ACL, kodovani delkou behu, MBR vs VBR, $BOOT)

08) [Emulace, paravirtualizace, binární překlad, hardwarová virtualizace (Intel VT-x), Virtualization for aggregation. [KIV/OS]](08.md)
    - simulace vs emulace vs virtualizace
    - emulace (preklad ISA_1 na ISA_2, nemusi byt stejna architektura)
    - virtualizace (musi byt stejna architektura, VMM, typy VMMM - 1.,2.)
    - V86 (proc? princip, ISR, vyjimky, privilegovane a citilive instrukce, problem 2 OS)
    - paravirtualizace (instrukce co meni HW jsou nahrazeny volanim hypervizoru; vyzaduje modifikaci OS)
    - binarni preklad (priklad, int 10h, problemy, staticky a dynamicky preklad; OS se nemodifikuje, za runtime hledame instrukce ktere nepodporuje nase architektura => nahradime temi co podporujeme = emulace)
    - HW virtualizace (VT-x, VMX-root, VMX-non-root, OS v CPL0, strankovani, VPID, read-only tabulka stranek - CoW, EPT, EPT base pointer)
    - VT-d (routovani I/O mezi virtualizovanymi OS)
    - VfA (vSMP, VMM, sitove uzly)

09) [Systémy reálného času - typy úloh, plánování a rizika. [KIV/OS]](09.md)
    - non-real-time, soft-real-time, hard-real-time
    - terminologie (task, job, plan, parametry (ai, ci, si, fi), odvozene parametry Di, Ri, ...)
    - typy tasku (periodicky, aperiodicky, sporadicky)
    - RMA (Rate Monotonic Analysis, RMS planovac)
    - RMS test naplanovatelnosti (kolektivni vyuziti < 70%)
    - Response time test (ri < di)
    - EDF (pocita i s aperiodickymi a sporadickymi tasky, existence splnitelneho planu)
    - rizika (cache, dynamicka alokace, IRQ, inverze priorit, rekurze, vyjimky, fragmentace)

### KIV/PPR

10) [Flynnova taxonomie – architektury a jejich urychlení. Amdahlův a Gustafsonův zákon, Karp-Flattova metrika – odvození a jejich limity. [KIV/PPR]](10.md)
    - Flynnova taxonomie (SISD, SIMD, SIMT, MISD (fail-stop, fault-tolerant), MIMD, SPMD (JSON; machine learning), MPMD (JSON + XML))
    - Ahmdaluv zakon (fixni velikost problemu, vzorecek, graf urcyhleni, graf efektivity, celkove urychleni)
    - Gustafsonuv zakon (teoreticke urcyhleni oproti exekuci na jednojadrovem CPU, zakladni vzorecek urcyhleni + dve cesty odvozeni, fixni cas => stejne vyuziti zdroju + zvetsovani velikosti problemu)
    - Karp-Flattova metrika (vzorecek - analogie ke Gustafsonovi, paralelni overhead, chceme konstantni e a co nejmensi, graf prubehu e s poctem CPU, odvozeni)

11) [Paralelismus na úrovni instrukcí, predikce skoků, paměťová závislost, falešné sdílení a transakční paměť (Intel TSX) – jejich princip a význam pro urychlení   sekvenčních a konkurenčních částí algoritmů. [KIV/PPR]](11.md)
    - ILP (HW - scoreboarding vs SW pritup - prekladac, out-of-order execution)
    - pipeline a hazardy (strukturalni, datovy (RAW, WAR, WAW), ridici)
    - predikce skoku (prediktory, metaprediktor, saturacni citac, BHT, BTB, cmov)
    - false sharing (cache line)
    - TSX (transakcni pamet, princip, L1 cache, fallback path, reseni SW vs HW, HLE - HW lock elision (xacquire , xrelease), RTM - restricted transaction mode (xbegin, xend, xabort))

12) [Paralelizace cyklů, typy proměnných a paralelizace výpočtu součtů prefixů – charakteristika a řešení. [KIV/PPR]](12.md)
    - typy promennych (lokalni, sdilene - zavisle, nezavisle - redukcni, usporadany, zamykani (min))
    - parallel prefix sum (zaklad pro paralelni algo., popis problemu, naivni reseni, reinterpretace -> odstraneni usporadany promenny (strom, nevyhody, graf urychleni), first-stop algo (inkluzivni, exkluzivni)
    - SIMD instrukce (staticka - prekladac vs maualni, AVX-512)
    - verktorizace cyklu (loop unrolling, problemy (break, continue, pointery, ...), maska pro odstraneni if)
    - SoA a AoS (usporadni pameti -> linerarni uruychleni jen teoreticke!!)
    - segmented scan (maska, custom operator, reset algoritmu)

13) [Programové prostředky pro multithreading – POSIX, WinAPI, C++11 (s využitím STL a RAII). [KIV/PPR]](13.md)
    - POSIX (kontrakt funci .h, objekty + atributy, mapovani POSIX na WinAPI)
    - WinAPI
        - Job
        - Thread (__declspec(thread) int a; TLS)
        - Thread pool
        - Fiber (FLS, kooperativni planovani -> nema prioritu, SwitchToFiber(), princip vytvoreni)
        - UMS (user-mode planovac, Java, vlastni kontext, light-weight)
    - WinAPI synchronizace
        - Objects (event, mutex, pipe, file, semafor, KS, podminkova promenna, SWR (duvod vstupu do KS - R/W => optimalizace), messages (post, send, peek, get))
        - Wait (single/multiple objects, timeout, callback)
    - APC (alertable, pole pointeru na fce v TCB)
    - SMP fetching (load/store | fence | load/store)
    - DLL shared section (RWS = read/write/shared)
    - C++11 (API pro mulithreading, synchronizacni primitiva, RAII, STL)

14) [Intel Threading Building Blocks – task-stealing plánovač, dekompozice úloh, redukční operace, flow-graph. [KIV/PPR]](14.md)
    - TBB (= knihovna, tasky, cache-cooling efekt (schema cache), task-stealing)
    - task-stealing planovac (graf rozdeleni na podtasky, zasobnik odlozenych uloh, depth-first, breadth-first)
    - redukcni operace
        - tbb::task, tbb::parallel_for, tbb::parallel_reduce (neni const), tbb::parallel_do (+ feeder)
        - tbb:parallel_pipeline (filtery - serial-in-order, serial-out-of-order, paralell)
        - tbb::flow_graph (continue_msg, OpenCL node, make_edge())

15) [Práce s GPGPU – princip, faktory ovlivňující výsledné urychlení, přesun dat, redukční operace, využití OpenCL a C++ AMP. [KIV/PPR]](15.md)
    - GPGPU (task paralelismus vs data paralelismus, SIMD vs SIMT)
    - aligned memory access, memory prefetching (random access)
    - OpenCL (prumyslovy standard, heterogenni zarizeni, __kernel void, priklad souctu dvou vektoru c[i]=a[i]+b[i])
    - work-group (WG), work-item (WI), wavefronta, ND-range
    - OpenCL buffery (clEnqueueWriteBuffer, CL_MEM_WRITE_ONLY | CL_MEM_HOST_READ_ONLY, clEnqueueKernel)
    - redukcni operace (vektorova suma na GPGPU)
    - OpenCL volani (global id, locacl id, group id, global size, local size)
    - OpenCL memory (globalni, lokalni, privatni; preteceni privatni do lokalni)
    - OpenCL barrier vs fence (R/W | fence | RW; synchronizace WI v ramci WG)
    - faktory urychleni (vetveni if else, bank-conflict, nechceme globalni pamet - read-only, |work group| == |wave front|, velikost data - rezie)
    - C++ AMP (= C++ Accelerated Massive Parallelism, restrict(cp, amp), predchudce SYCL)
    - SYCL (jeden codebase, vice backendu, programovaci model)
    - DPC++ (= Data Parallel C++, implementace SYCL od Intelu, soucasti OneAPI toolkitu)

16) [Spurious wakeup – charakteristika a ošetření. Rendez-Vous, vč. konstrukce “select” v jazyce Ada a jejího porovnání s Java monitorem. [KIV/PPR]](16.md)
    - spurious wakeup (falesne vzbuzeni, notify_all, rezie, notify_one + signal = problem, reseni ne v kernelu ale userpacu (if => while))
    - Ada (historie, popis jazyka, zpusob synchronizace, tasky, subtasky, begin end = telo tasku)
    - Entry (blokujici - ceka na accept = bod setkani = randez-vous)
    - Priklad Ada task (accept Start; num *= 2; accept Report)
    - Ada select (loop, terminate, podminky, reakce na vicero vstupnich bodu, vyzozeni podminky misto blokace tasku)
    - Ada protected objects (vynuceni exkluzivniho pristupu, priklad semafor - Acquire = vstupni volani accept, Release = procedure, Get_Num = funkce)
    - Monitor (co to je, problem funkce signal/release - Hoare, Hansen, Java si planuje vlakne sama => nemozne vynut poradi vzbuzeni)

17) [Výpočetní prostředí s distribuovanou pamětí - topologie, možnosti komunikace a relokace procesů, vektorové hodiny. Přidělování práce v prostředí s distribuovanou pamětí, možnosti urychlení výpočtu a přiřazení procesů na jednotlivé uzly. [KIV/PPR]](17.md)
    - topologie (komunikacni kanal, overlay network, cluster, uzly, toroid, mrizka (Dij, Dmax), krychle, Network Node Address)
    - vykon zavisi na (kvalita SW, granularita dat (chunk size), efektnivni alokace vzhledem k HW)
    - univerzalni pocitacova sit (skolni laborator)
    - SETI@Home (farmer-work, dynamicke zapojovani podvytizenych PC, mimozemstani)
    - univerzalni paralelni PC (MPI = Message Passing Interface, single-purpose computer - LED)
    - moznosti komuniace (Worm Swithing - flit, cut-through switching, store & forward, adaptive switching)
    - lampartovi hodiny (castecne usporadani, timestamp)
    - vektovove hodiny (detekce poruseni kauzality, vektor lamparovych timestampu)
    - load sharing (Worm (staticke), Condor (dynamicke))
    - load balancing (staticky (vime co mame za HW, hodne info o siti, problem vypadku uzlu), dynamicky - preemptivni, centralizovani (arbiter), kooperativni, sender-initiated, receiver-initiated, adaptivni)
    - problem load balancingu a load sharingu (masova migrace, oscilace (reseni pres kredity), zbytecna migrace -> stejny vykon nodu)
    - mobilni agenti (ANT routovani, OSPF)
    - aktivni site (capsule, code distribution protocol)

### KIV/FJP

18) [Základní struktura překladače, datové struktury potřebné pro překlad. [KIV/FJP]](18.md)
    - vyuziti prekladacu (IDE, SQL, MS Word, silikon)
    - vicevrstvy prekladac (LLVM, frontend, backend)
    - struktura prekladace vs interpretu
    - lexikalni analyza (DKA, lexem, token, bile znaky, rohrani pro syntakticnou analyzu)
    - syntakticka analyza (AST vs derivacni strom, automaticke/formalni (ANTLR, yacc + bison) vs rekurzivni sestup, shora dolu vs ze spoda nahoru)
    - semanticka analyza (atribuovana gramatika (syntetizovany vs zdedeny attr) vs rekurzivni prochazeni AST)
    - tabulka symbolu (obsah, linked list hashmap, rozsah viditelnosti, B-strom (super, this), operace nad tabulkou symbolu, dynamicky rozsah (tabulka + zasobnik), vyuziti (-g -O0))
    - typova kontrola (silna vs slaba, staticka vs dynamicka, odpozeni typu (var/auto), formalni odvozeni)
    - optimalizator (kde, cile, priklady (inlining, zjednoduseni algebry, autovekrotizace, mrtvy kod)
    - generovani kodu (jazyk trojic, jazyk ctveric)

19) [Definice regulární gramatiky, vztah regulárních gramatik a konečných automatů, implementace automatu, způsoby a příklady využití. Nástroje pro práci s regulárními výrazy. [KIV/FJP]](19.md)
    - gramatika (definice - G = (𝑁, Σ, 𝑃, 𝑆), prepisovaci pravidla, L(G), derivace, vetna forma, slovo/veta)
    - klasifikace gramatik (viz tvar prepisovacich pravidel, rekurzivne spocetna, kontextova, bezkontextova, regularni (typ 3), podmnoziny, BNF)
    - regularni gramatiky (prava + leva = gramatika typu 2, nedostatky KA, NKA vs DKA (prevod - obraceni pravidel, nakreslit, obratit hrany, NDK na DKAm, nakreslit))
    - regularni vyrazy (konkantenace ab, sjednoceni a+b, uzavera a*, vylepsni - a?, a{4}, popis tokenu lexeru, validace vstupu (email, ip), formalni struktura lexeru (= automaticke generovani, paralelni DKA))
    - implementace DKA (= tabulka prechodu, curr_state = [curr_state, next_intput])

20) [Definice bezkontextové gramatiky, vztah bezkontextové gramatiky a obecného zásobníkového automatu. Využití bezkontextových gramatik. Nástroje pro generování automatu a překladače, jejich výhody a omezení. [KIV/FJP]](20.md)
    - bezkontextove gramatiky (definice, tvar prepisovaciho pravidla)
    - obecny zasobnikovy automat (𝑃𝐷𝐴 = { 𝑄, Σ, Γ, 𝛿, 𝑞0 , 𝑧0 , 𝐹 }, schema, pamet, konfigurace, vlastnosti (jednocestky, nedeterministiky - backtracking, akceptacni), kazda BKG lze prevest do GNF => lze sestavit jednoduchy LL(1) ale n^4 pravidel)
    - GNF (= Greinbachove Normalni forma, S -> e, prave strany zacinaji neterminalnem, ruzny 1. neterminal pravych stran)
    - analyza shora dolu (first-first kolize (leva faktorizce/vytikani), first-folow (pohlceni terminalu) kolize, FIRST (E.), FOLLOW(E -> E.))
    - analyza zdole nahoru (reduce-reduce kolize, shift-reduce kolize, SLR(k), LALR(k))

21) [Metody syntaktické analýzy. Výhody a nevýhody rekurzivního sestupu. [KIV/FJP]](21.md)
    - gramatika (G = (𝑁, Σ, 𝑃, 𝑆), obecny tvar prepisovacich pravidel, L(G), derivace (prava/leva), vetna forma, slovo, fraze vzhledem k F)
    - viceznacnost gramatiky (nutna podminka, postup odstraneni, NP problem, priorita vyhodnocovani derivacniho stromu)
    - syntakticka analyza (shora dolu, ze spoda, backtracking, rekurzivni sestup, zasobnikovy automat)
    - rekurzivni sestup (case, switch, pruhledna implementace, derivacni strom v RAM)
    - problemy rekurzivniho sestupu (prvni neterminal, leva rekurze, e-pravidla, first-first kolize, first-follow kolize)

22) [Ekvivalence gramatik, transformace gramatik vč. transformace do podoby LL gramatiky. Důvody pro transformace. Úlohy algoritmicky nerozhodnutelné. [KIV/FJP]](22.md)
    - ekvivalence gramatik (S->aS | S->Sa | S->e, L(G1)=L(G2))
    - FIRST & FOLLOW funkce (vstup, vystup)
    - ekvivalentni upravy
        - gramatika porad generuje stejny jazyk
        - hledani zbytecnych symbolu (od listu ke koreni, nepodili se na generovani jazyka, O1={a,b} -> pridavame leve strany slozeny z kombinace v O1 (rekurzivne))
        - hledani nedostupnych symbolu (od korene k listum, nedosazitelne z S, N0={S} -> pridame vsechny jeho prave strany (rekurzivne))
        - odstraneni e pravidel (nalezeni Ne mnoziny -> stejny jako hledani zbytecnych symbolu ale zaciname z A->e, substituce - bud tam A je nebo neni, odstranime A->e, opakujeme rekurzivne, pokus S->e => S'->S | e)
        - odstraneni jednoduchych pravidel (S->A => misto A dame vsechny jeho prave strany)
        - odstraneni cyklu = odstraneni jednoduchych pravidel
        - odstraneni leve rekurze (A->Aα1 | Aα2 | β1 | β2)
            - A->β1A' | β2A'
            - A' -> α1A' | α2A' | e (nebo α1, α1, a v A pak β1, β2, ...)
    - transformace gramatiky (GNF (n^4), duvody = odstraneni kolizi, zacykleni pri reseni first-first nebo first-follow kolizi)
    - ulohy algoritmicky nerozhodnutelne (nalezeni ekvivalentni jednoznacne gramatiky)

23) [Využití zásobníkového automatu k analýze shora dolů. Konstrukce deterministického automatu, vhodný tvar gramatiky. Vyjadřovací síla LL a LR gramatik. [KIV/FJP]](23.md)
    - zasobnikovy automat (𝑃𝐷𝐴 = { 𝑄, Σ, Γ, 𝛿, 𝑞0 , 𝑧0 , 𝐹 }, konfigurace, jednocestny, nedeterministicky, akceptacni, nekonecna pamet)
    - analyza shora dolue (redukce/srovnani, GNF (definice), implementace tabulky prechodu, FIRST, FOLLOW)
    - LL analyzator (FIRST(α U FOLLOW(A)) ∩ FIRST(β U FOLLOW(A), nesmi obsahovat levou rekurzi, first-first kolize (substituce + leva faktorizace), first-follow kolize (pohlceni symbolu)), FIRST_k, FOLLOW_k)
    - silna vs slaba LL(k) (rozhodnuti na zaklade k symbolu na vstupu + zasobnik, CELY NACTENY VSTUP + k symbolu na vstupu + zasobnik => v praxi nepouzitelne)
    - vyjadrovaci sila LL a LR (|LR| > |LL|, |LR| > |LALR| > |SLR(k)| > |SLR(1)| > |LR(0)|)

24) [Využití zásobníkového automatu k analýze zdola nahoru. Konstrukce nedeterministického automatu, třídy gramatik pro deterministickou analýzu zdola nahoru. Vyjadřovací síla LL a LR gramatik. [KIV/FJP]](24.md)
25) [Vnitřní jazyky překladače. Interpretace a generování cílového kódu, výhody a nevýhody obou přístupů. [KIV/FJP]](25.md)
26) [Přidělování paměti pro data programu - způsoby, použití, související datové struktury. Volání podprogramů a předávání parametrů, řešení rekurze a paralelních výpočtů. [KIV/FJP, (KIV/PPR)]](26.md)
