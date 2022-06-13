# hse22_project
# **Индивидуальная часть проекта. Галкина Мария, группа №4**

## Введение:
> Целью работы над проектом является поиск и изучение консервативных участков генома Z-ДНК в геномах прокариот и эукариот. В процессе выполнения проекта будут получены важные практические навыки биоинформатика -- работа в командной строке с утилитой bedtools, визуализация данных, конвертация координат участков между разными версиями генома (разными организмами) и т.п.

## **Вводные данные**
> - Таксон: Apicomplexans
> - Род: Babesia
> - Виды организмов и информация о них:
>
>| № | Вид организма:                    | Сборка:          | Общая длина: | GC%:     | Хромосомы:| Скаффолды:  | Контиги:  |
>|---|----------------------------------|-----------------|-------------|---------|----------|------------|----------|
>| 1 | Babesia bovis T2Bo               | GCF_000165395.1 | 8,179,706   | 41,6972 | 2        |         14 | -        |
>| 2 | Babesia microti strain RI        | GCF_000691945.2 | 6,434,485   | 36,1847 | 4        |          6 | 5        |
>| 3 | Babesia bigemina                 | GCF_000981445.1 | 13,840,936  | 50,6137 | 5        |        483 | 483      |
>| 4 | Babesia sp. Xinjiang             | GCF_002095265.1 | 8,447,544   |    43,9 | 0        |        215 | 261      |
>| 5 | Babesia ovata                    | GCF_002897235.1 | 14,453,397  |    49,3 | 0        |         91 | 91       |
>
> - Результат подсчёта общей длины:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173415154-e317a118-e315-47fc-858e-f167f0391b0d.png)

> - **Мой google-colab:** https://colab.research.google.com/drive/1Y9_OCHg6UPkT9n2TLpq3DKhLcciGAvCp?usp=sharing

## **Аннотированные гены**
> **Результат работы кода:**
> ![image](https://user-images.githubusercontent.com/59726719/173414573-849cf215-d792-4889-aedf-00e8de2e89aa.png)
> ![image](https://user-images.githubusercontent.com/59726719/173414697-ac12a4f5-d10a-41bf-a112-da79c6901212.png)
>
> **Общая таблица:**
>| № | Вид организма:                    | Количество аннотированных генов: | Доля аннотированных генов: | Количество экзонов: | Доля экзонов: |
>|---|----------------------------------|---------------------------------|---------------------------|--------------------|--------------|
>| 1 | Babesia bovis T2Bo               | 3781                            | 0.755367                  | 3781                | 0.755367     |
>| 2 | Babesia microti strain RI        | 3685                            | 0.823407                  | 3685               | 0.823407     |
>| 3 | Babesia bigemina                 | 5080                            | 0.666147                  | 5080               | 0.666147     |
>| 4 | Babesia sp. Xinjiang             | 3107                            | 0.71065                   | 3107               | 0.71065    |
>| 5 | Babesia ovata                    | 5108                            | 0.724485                  | 5108               | 0.724485     |

## **Z-DNA**
> **Результат работы кода:**
> ![image](https://user-images.githubusercontent.com/59726719/173414197-6374796a-5f8e-4b40-bc1d-8970a57e1172.png)
> ![image](https://user-images.githubusercontent.com/59726719/173414254-bbf7efd5-e169-47ed-b893-398e94b6e628.png)
>
> **Общая таблица:**
>| № | Вид организма:                    |Количество предсказанных Z-ДНК | Общая длина предсказанных Z-ДНК | Количество предсказанных Z-ДНК с ZH-Score >= 500 | Общая длина предсказанных Z-ДНК с ZH-Score >= 500 |
>|---|----------------------------------|---------------------------------|---------------------------|--------------------|--------------|
>| 1 | Babesia bovis T2Bo               | 35107                           | 299852                  | 793462                | 7378938     |
>| 2 | Babesia microti strain RI        | 28657                          | 238156                     | 3841               | 38540     |
>| 3 | Babesia bigemina                 | 2862                            | 25544                  | 55025               | 548282     |
>| 4 | Babesia sp. Xinjiang             | 1259                            | 11508                   | 13013               | 129464    |
>| 5 | Babesia ovata                    | 1262                            | 11460                  | 42212               | 419888     |
>
> **Примечание:** для орагнизма Babesia bovis T2Bo оганичение ZH-Score было равно 8, так как изначально количество предсказанных Z-ДНК было 0. Для этого было найдено максимальное значение длины:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173416709-08e4c42a-93bb-443a-86e8-6f50fa78d9df.png)
>
> И после было подобрано оптимальное ограничение ZH-Score (данный случай поднимался в беседе, решать его посоветовал преподаватель именно таким образом).

## **Гистограммы с распределением ZH-Score**
> <img width="238" alt="zh-score 1" src="https://user-images.githubusercontent.com/59726719/173419267-cfc437f3-b42e-4c51-ae17-106899b2f563.png">
> <img width="232" alt="zh-score 2" src="https://user-images.githubusercontent.com/59726719/173419301-94bb3be4-e7f5-415d-a91b-b858f8e158ac.png">
> <img width="230" alt="zh-score 3" src="https://user-images.githubusercontent.com/59726719/173419392-a8939b5e-9b06-46f1-b7dc-eae419063523.png">
> <img width="233" alt="zh-score 4" src="https://user-images.githubusercontent.com/59726719/173419416-8179fe5f-52fe-47f9-aff0-f311af5cb440.png">
> <img width="235" alt="zh-score 5" src="https://user-images.githubusercontent.com/59726719/173419436-eac29d83-5bc9-420d-a974-5007b02485c9.png">

## **Расположение предсказанных Z-ДНК:**
> ![image](https://user-images.githubusercontent.com/59726719/173420010-f912fbbe-a789-47f0-a947-b49f5d1e13ca.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420121-6aa1f7f2-b849-425b-8abc-6657850d9c11.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420207-28431de5-8302-4944-82d9-9501f1a6a43a.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420277-a41ad2b3-3fa1-4f2a-83f4-58d6ced0a518.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420333-da39409b-285f-4d2c-944d-3beb9d81179c.png)

## **Распределение предсказанных Z-ДНК:**
> ![image](https://user-images.githubusercontent.com/59726719/173420467-5929257d-ea05-4ed5-81d3-08312509d6eb.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420525-cca79392-118e-4019-beaa-f2fdfe892107.png)

## **Гомологичные кластеры:**
> Всего получено 5263 кластера. В качестве визуализации были построены гистограммы.
> - Гистограмма, отражающая кластеры и количество геномов, которые в них входят:  
> ![image](https://user-images.githubusercontent.com/59726719/173426799-ee5ea23b-a809-4435-b1fe-0675fd544f03.png)
>
> - Гистограмма, отражающая количество геномов в кластерах:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173426837-bd07e788-5143-45bf-817d-1ded762d1bce.png)
>
> **Полученные таблицы по 8-ми отобранным кластерам с самым большим средним ZH-Score:**
>
> Кластер №1:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173433729-6e1746f2-d7a3-470c-a4cd-0c8ebe8ac6c6.png)
>
> Кластер №2:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173433814-35c07694-9026-4268-86c8-54a3d6a84827.png)
>
> Кластер №3:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173433866-c4161228-42a5-42f0-9907-df75ca3e97fe.png)
> 
> Кластер №4:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173434113-5c264d98-cab6-4107-ac5b-0e256d4c4970.png)
> 
> Кластер №5:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173434163-0b240449-3f19-4351-9aa4-c0a25f3e0651.png)
>
> Кластер №6:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173434213-f44b245e-6f93-4b7c-afb2-7f0abb2ba314.png)
>
> Кластер №7:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173434267-eacb657d-eadd-44b5-8df7-577fdbe0c403.png)
>
> Кластер №8:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173434293-c977bdc1-1926-49c7-9ce9-2343fd17895a.png)
> 
> **Функции:**
>| № кластера | Функция №1:                  | Функция №2: | Функция №3: | Функция №4: | Функция №5:: |
>|---|----------------------------------|---------------------------------|---------------------------|--------------------|--------------|
>| 1 |RNA recognition motif (RRM)-containing protein |peptidylprolyl isomerase |RNA recognition motif (RRM)-containing protein,putative|Peptidyl-prolyl cis-trans isomerase E|peptidyl-prolyl cis-trans isomerase E|
>| 2 |nucleolar protein Nop56, putative |NOP56, nucleolar protein 56|nucleolar protein Nop56, putative|Nucleolar protein 56|uncharacterized protein|
>| 3 |conserved hypothetical protein  |GAP40|GDP-fucose transporter 1|uncharacterized protein|metabolite drug protein|
>| 4 |rpn2_yeast 26S proteasome regulatory subunit rpn2, putative|Calcineurin-like phosphoesterase|rpn2_yeast 26S proteasome regulatory subunit rpn2, putative|26S proteasome non-ATPase regulatory subunit 1|serine threonine phosphatase|
>| 5 |tRNA binding domain containing protein|translation initiation factor eIF-4A|tRNA binding domain containing protein, putative|putative tyrosine-tRNA ligase|tRNA binding domain-containing protein|
>| 6 |deoxyuridine 5'-triphosphate nucleotidohydrolase, putative |dUTP pyrophosphatase |deoxyuridine 5'-triphosphate nucleotidohydrolase, putative|Deoxyuridine 5'-triphosphate nucleotidohydrolase|deoxyuridine 5 -triphosphate nucleotidohydrolase|
>| 7 |40S ribosomal protein S19, putative |small subunit ribosomal protein S19e |40S ribosomal protein S19, putative|40S ribosomal protein S19-A|40S ribosomal protein|
>| 8 |conserved hypothetical protein |Ribosomal RNA small subunit methyltransferase F|hypothetical protein, conserved|Ribosomal RNA small subunit methyltransferase F|S-adenosyl-L-methionine-dependent methyltransferase superfamily protein|
>
>
> **Распределение Z-ДНК относительно генов в кластере:**
>
> Кластер №1:
> ![image](https://user-images.githubusercontent.com/59726719/173436457-6825f40b-64e8-49f2-a166-54e05179911c.png)
>
> Кластер №2:
> ![image](https://user-images.githubusercontent.com/59726719/173436511-a8710dc5-a2b8-4ae6-bee9-65b62157227c.png)
>
> Кластер №3:
> ![image](https://user-images.githubusercontent.com/59726719/173436548-94a52348-7083-4990-af19-2e2268e066fb.png)
> 
> Кластер №4:
> ![image](https://user-images.githubusercontent.com/59726719/173436629-24ac1ff7-b494-462d-bf02-e1c90d2c3168.png)
> 
> Кластер №5:
> ![image](https://user-images.githubusercontent.com/59726719/173436669-06a93d8d-3848-488c-a1f8-03120c7bf65a.png)
> 
> Кластер №6:
> ![image](https://user-images.githubusercontent.com/59726719/173436755-851d5451-7054-4df6-8c93-cb2d74e40266.png)
>
> Кластер №7:
> ![image](https://user-images.githubusercontent.com/59726719/173436791-2fca60bd-f972-41bf-9733-cf8df309b5af.png)
> 
> Кластер №8:
> ![image](https://user-images.githubusercontent.com/59726719/173436826-383341ec-2425-4e52-9393-d1003269037e.png)
>

## **Множественное белковое выравнивание с помощью muscle**
>
> Все файлы выравнивания находятся [тут](https://github.com/galkinamariia/hse22_project/tree/main/aligned)
>
<details>
  <summary>Кластер # 1</summary>
    
  ```  
  >EDO07437.1 nucleolar protein Nop56, putative [Babesia bovis]
MEKTYFLFETAAGYALYHIDEWDQIGHVDAMDEICRSAERFKESIHFKAFQPFTTAADALENIRAVVDGEVTSMLSAFLS
LNMPK-KGARLAVVDPALGKSLSAKGFQVLYDSNVIEILRGCRQHEMKHIAKLASGASAFDMDKFHVGLGHNYSRTKLQV
DPRRHDKPVVNCVALLDSLTKNLNSFAMRVREWYGWHFPELVKIVPDNKLYCQTVQIIQCKNKFDWSTRIDELKQLLNDD
ELVSSIQKAANQSIGHELSDACMQNIYNFASQVVKLEEMRERLNVHLGNKLAITAPNLSTVAGNVLTARLISHAGSLVNL
AKMSASSIQILGAEKALFRALKTRSNTPKYGLIFQSTFIGKASVKHKGRAARYLANKCALAARLDCFCDVNSNVYGKHMV
DLLAKRMEYL-AGGPVHETSIEVMKAASKEYETLKSQLVSESKSDQ-VVT----------------SLDTTN--------
--DVDNIEPKKSKKQKKNST---------------------------IVDNTVAEVEPEKRKRSKEKKSSE---------
------GKTDDSSVEKSAKKSKSKTDSTP--VED-TSKP--EMGTTSESKAEKKHKKS------KVKEVDLQKSSDSTKK
SKK--QKKGSEST
>XP_028869941.1 Nucleolar protein 56 [Babesia sp. Xinjiang]
MEKTYFLFETAAGYALYLVNQWEQIGHIDAMEEVCCSADRFKEAVQFKAFQPFTTASDALENIRAVVDGEVTAMLSAFLG
LNMPK-KGAQLAVVDPALGKSLTAKGLKVVYDPNVIELVRGCRQHEMKNIAKLASGASAFDMDKFHVGLGHNFSRSKLQI
DPRRHDKPVINCVALLDSLTKNLNSFAMRVREWYGWHFPELVKIVPDNKLYCQVVRIIQCKNKFDWDTRINELKEIIPDD
EVIANINKAARQSIGHELTDACMENIFNFTTQVVKLEEMRERLNDHLSNKLMVTAPNLSTLAGNILTGRLISHAGSLVNL
AKMSASSIQILGAEKALFRALKTRSNTPKYGLIFQSTFIGKASVKHKGRAARYLANKCALAARLDCFCDVNTDVYGKRMV
ELLGKRMEYL-AGGPPHETSIDVMHAASKEYQAIKAKVATEKRKRSDVQKE-------HD----VASADTKNI-SEVTMG
DAVTAEQPSKKSKKQKKKDI---------------------------GVESAVVD--GTSVDKKSKKKREKSEEEAKSPK
KQKLEKSQTDDTRASKKNVTKTEESQGTPESPKE-AAKP--EVKSEPVSEVPKKK-KEKKQKKAATVEADTSEPSESPKK
AKK---SKKKAVE
>XP_028866506.1 uncharacterized protein BOVATA_017560 [Babesia ovata]
MTKTFFLFETAAGYALYQIEQWDQIGHVEAMEEVCSSQERFKETVKFKAFQPFTTASDALENIRAIVEGEVTPMLSAFLS
LNLPK-KGTQLAVVDPGLGKTLTSKGFNVVYDPNVVELLRGCRQHEMKNIARLASGASAFDMDKFHVGLSHNYSRSKLQI
DPRRMDKPVINCVALLDSLTKNLNSFAMRVREWYGWHFPELIKIVPDNKIYCQVVQIICRKDKFDWETGAPELLKVLGDE
ELVASVKKAAGQSIGHELSEPCMQNILNFAKQVVKLEEMREHLNTHLGNKLAITAPNLSEVAGNILTGRLISHAGSLVNL
AKMSASSIQILGAEKALFRALKTKSNTPKYGLIFQANFIGRASLKHKGRAARYLANKCALAARLDCFCDVNSNVYGKRMV
ELLGKRMEYL-AGGPQHETSIEVMKAAAQEYQAIKAQKAAEKRVRD-VSEDAPQKESSHDEPMLPVSADVEPAVPADDAS
SGAVAEKASKKSKKSKKDKSKKADIADKPETEEKTTAVKASPTDKGSSTDAANVD--VTSREKESKKKSKK---------
------AKLEGVASSKDATTALTDTSSTS--VKTATAVPAVEAAVTSAEEAPKKHKKSKKEKSADSTETAVVEAEKPSKK
AKKNKKKAGSEQS
>XP_012649332.1 NOP56, nucleolar protein 56 [Babesia microti strain RI]
MA-LMLLYETAAGYALYKVEEWDRIGNDGSIEELVKNESLFSKMVNFVAFQPFKSSAEALENITAIAAGEATDLLVSFLQ
QNIPQPKKMILAVIEPGLGKSLSNKGFNMKFDSDCLELIRGCRLYESKNIAKFSD--IVLDIERFQVGLAHSYARSKMKQ
DPSRYDKPIINIVATLESVEKNLNTFAMRVREWYGWHFPELNKIIEDHKTYSNVIQFIQFREKFDALEDYTPLLQFVSE-
DVANNIIKASAQSMGQEITEGDMLNILNITKTIIKLSDMRERLTAHLMNKMKFAAPNLTELLGDYLSGRLISHAGSLVNL
AKCPASTIQILGAEKALFRALKTRSNTPKYGFLYQSSYIGKASIKNKGKAARYLANKCALAARLDCFSDNVSNVYGKAMK
MQLNKQLEYVTSGGDKPEQNLNVMREAIANDETRK---------------------------------------------
-----------SNDQEV---------------------------------------------------------------
--------------------------------------------------------------------------------
-----KTTGLLWF
>XP_012649332.1 NOP56, nucleolar protein 56 [Babesia microti strain RI] dupelabel1
MA-LMLLYETAAGYALYKVEEWDRIGNDGSIEELVKNESLFSKMVNFVAFQPFKSSAEALENITAIAAGEATDLLVSFLQ
QNIPQPKKMILAVIEPGLGKSLSNKGFNMKFDSDCLELIRGCRLYESKNIAKFSD--IVLDIERFQVGLAHSYARSKMKQ
DPSRYDKPIINIVATLESVEKNLNTFAMRVREWYGWHFPELNKIIEDHKTYSNVIQFIQFREKFDALEDYTPLLQFVSE-
DVANNIIKASAQSMGQEITEGDMLNILNITKTIIKLSDMRERLTAHLMNKMKFAAPNLTELLGDYLSGRLISHAGSLVNL
AKCPASTIQILGAEKALFRALKTRSNTPKYGFLYQSSYIGKASIKNKGKAARYLANKCALAARLDCFSDNVSNVYGKAMK
MQLNKQLEYVTSGGDKPEQNLNVMREAIANDETRK---------------------------------------------
-----------SNDQEV---------------------------------------------------------------
--------------------------------------------------------------------------------
-----KTTGLLWF
  ```
</details>

<details>
  <summary>Кластер # 2</summary>
    
  ```  
  >XP_028866060.1 peptidyl-prolyl cis-trans isomerase E [Babesia ovata]
MA-DTSGQKRTLFVRELADEVNKEILYAAFLPFGNILHIDMPVDKEKGTNRGIAFIEFEDEEDAKHAIFNHNESELYGRV
IKVAYSTKSHVKQARTAGVRHRAVWHDDPTFGHDLRPDDEDAPPAEQSKP---EQQQQ
>XP_021338081.1 peptidylprolyl isomerase [Babesia microti strain RI]
MDSNDIDSKRTLFVRGLAEGVTKEVLYAAFIPYGEIRHLEVPLDKTTGKHKGFGFVEFEEGEDASHAVFNRNNSELYGKV
LRVTYSTHADVYEKKS--YKNKAIWADPEYYKQKLVEAGVEVPGGEQQTGVDIGTDNG
>XP_021338081.1 peptidylprolyl isomerase [Babesia microti strain RI] dupelabel1
MDSNDIDSKRTLFVRGLAEGVTKEVLYAAFIPYGEIRHLEVPLDKTTGKHKGFGFVEFEEGEDASHAVFNRNNSELYGKV
LRVTYSTHADVYEKKS--YKNKAIWADPEYYKQKLVEAGVEVPGGEQQTGVDIGTDNG
>EDO06776.1 RNA recognition motif (RRM)-containing protein [Babesia bovis]
MA-DSAGQKRTLFVRELADEVNKEILYASFIPFGNIINIDLPVDKEKGTNRGIAFIEFEDEEDAKHAIFNHNESELYGRV
IKVAYSTKAHVKQVKSANVRHRAVWHDDPTFGHDLRPDDEDPPHDEAN--------KS
>XP_028870260.1 Peptidyl-prolyl cis-trans isomerase E [Babesia sp. Xinjiang]
MS-EAAGQKRTLFVRELADEVNKEILYAAFLPFGNIINIDMPVDKEKGTNRGIAFIEFEEEEDAKHAIFNHNESELYGRV
IKVAYSTKAHVKQVKAATVRHRAVWHDDPTFGHELRPDDEDPPKEEQ----------N
  ```
</details>

<details>
  <summary>Кластер # 3</summary>
    
  ```  
  >XP_028867193.1 tRNA binding domain-containing protein [Babesia ovata]
MLEVVVYKDCVEGRLATLLWGYGKFTN--VTLSFAPSRAAMVVKEDGAITPMIWPTLLELAVKDAPTESVLVPSTEAHKR
TMYSWIDFAYQRDFSIMEPASLKILDDYILNHTFLAGSTVTLADLVVYVSTHSWMMKSEPQDRSEYVNVVRWFDHIQHLP
GI-VNTFKELPLVSVDKDMDLVTAVMEKTTLSAAAA-PYAKPSKGKKDAVAKKPKEIKPPADDRPVADVSRLNIKVGQIM
SVERHPEADRLYCLKIDLGEPELRDICSGLVDYLKPEQIMSQYVCVLSNMKPKSLRGKMSNGMVLCVSSPDKTELELLHP
ADGTPVGERVVIEDCNGEPDAVLSTKTGKDPFVAVQPVGYRINSLTQSQEFNCKDTVAYYKVW-FIA-------------
--L
>XP_021337505.1 glutamyl-Q tRNA(Asp) synthetase [Babesia microti strain RI]
MIPLEVHKASNYANIVKLLLSYSNIKDDLIKLTLSDNPQLTLTLPNGTQ-YTELPTIMIYIMGQNDTGKILYPDDNLLKA
KIDQWISLANKKDYSICDSESIREIDSSLVHTTFLVCNNITLADIVIYSSLLHWAKKSTTKEKELMCNLSRWYNHIQHLP
GISIGNYIDIPTGTTV---SSLSSMLNNVNVCGDNK-KSNKSAQKAEGKYNKKIQNSNFSNDARPVDDITRLAVRVGLVK
EISKHPDADKIYCLKIDIAESKLRDICSGLVEHLKPEEIINKKVCVLSNLKPRKIRGVDSNGMVLCVSYNDK--VELLEP
PSDSMVGELITWGDLKGEPDVVLSGKSGKNPFEAVQK------------DLVCKNKIGYYKDLPFSTLSGVCSCNTLIKG
TIS
>XP_021337505.1 glutamyl-Q tRNA(Asp) synthetase [Babesia microti strain RI] dupelabel1
MIPLEVHKASNYANIVKLLLSYSNIKDDLIKLTLSDNPQLTLTLPNGTQ-YTELPTIMIYIMGQNDTGKILYPDDNLLKA
KIDQWISLANKKDYSICDSESIREIDSSLVHTTFLVCNNITLADIVIYSSLLHWAKKSTTKEKELMCNLSRWYNHIQHLP
GISIGNYIDIPTGTTV---SSLSSMLNNVNVCGDNK-KSNKSAQKAEGKYNKKIQNSNFSNDARPVDDITRLAVRVGLVK
EISKHPDADKIYCLKIDIAESKLRDICSGLVEHLKPEEIINKKVCVLSNLKPRKIRGVDSNGMVLCVSYNDK--VELLEP
PSDSMVGELITWGDLKGEPDVVLSGKSGKNPFEAVQK------------DLVCKNKIGYYKDLPFSTLSGVCSCNTLIKG
TIS
>EDO08580.1 tRNA binding domain containing protein [Babesia bovis]
MLEIVVYSDCVEGRLARLLWGYGKFNN--ATLSLSSTRTETLVKENGEQSLKQWPDIIEIAVKGASTEDVLVPPTPDQKN
KMYSWIDFAFQRNFMINQKDSLKILNVYLEPNTFLVGNNVTLADLVAYVSIHSWMLMSEPHDRIEFSNIVRWFDHIQHLP
GI-VNTFKDLPLVVVDKDMDLVTAVMDNVTVTAPSA---KNPTKGAIDAKSKKEKSPKPVVDERPIADVSRLNIRVGQVM
SVDRHPEADRLYCLKIDLGEPELRDICSGLVGYLQPDEIMSKYVCVLSNMKPKNLRGRVSNGMVLCVSNADHTQIELLHP
ANGTPIGERVTIEGFDGEPDAVLSTKTGKDPFVAVQP------------DFNCRDTIAYYKDHRFMTTLGPCHCNSFTSG
TIS
>XP_028872272.1 putative tyrosine-tRNA ligase [Babesia sp. Xinjiang]
MLEVIVFSDCVEGRLARLLWSYGKFKN--VSLSLSPSRTETIVKEDGEVSLKQWPSVLEDAIKGAPTEEVLVPSTQIQKD
TMYSWIDFAFQRDFSINQRASIETLNAYLVSHTFLVGSTITLADLVMYVSTHSWMMKSEAHDRAEFTNVVRWFDHVQHLP
GI-VNNFKDLPLVTIEKDMDLVTAVMENMSVATAAAPPSVKPTKGAADSGSKKQKSPKPVADDRPIADVSRLHIKVGQVM
SVERHPEADRLYCLKIDLGEPDLREICSGLVDYLKPEQIMSQYVCVLSNMKPKSLRGKTSNGMVLCVSNADHTVVELLHP
AEGTAVGERVVVEGCEGEPDAVLSTKTGKDPFVAVQP------------EFNCKDTFAYYKDQRFMTKCGPCRCISLKEG
TIS
  ```
</details>

<details>
  <summary>Кластер # 4</summary>
    
  ```  
  >EDO08658.1 hypothetical protein BBOV_III011060 [Babesia bovis]
MDT----------QSQVSSSQKKCRHVAFIKSQFLGNVLKFVQNEVVDENKDKCFIPSCHGTDMEKLKEFFKMGQPPIRT
YHPINYIGIGLHNNKEDTVDNETDSGASMEPPDNV-----------------------F--SIPVITND---AT------
--------------------------------------------------------------------------------
---YFKQHIFASPSCMYATLPEMASALDFEGLNVGLRIVIEVLVKPASYVTGPASVK---NIKNGFDCCFDNQNIEWFVK
NLDHIVPHRLLFRIMKKEDV------------VVPMTREPVFNDVKQVTISKEDGVSLI---TVLPSSS----TKFLDES
GFQSLKGAVADSGTHEDA-VTILESPSNTL--------------------------------------------------
--GSQNQLNYMVIGFKYKWTDSNNKIIYYLKTIIGSKWLEWDNDKKQWKIKGTYIYECVKYALYLGLRINDKVLFALWSW
LRSIDMRNVGEVFSKVQLIEFMQSNKIWLFQRVDLKVTPGYNPSIHGDLGKGATPALQAAARESAETVHISLVPYNRDIV
AKFKDRNG------AYVWNKADGCWQT-----GNLITALE-DLMAVLPHLKEC--------------SQSDTYLSSRGI-
NLRDIN-KLAKRKDSGSKRKDSAKRRELMIDDNDVDDDFTTVTTLMLTAAGKEPHLMRIRDKIKTVVEKIAPPMSSISAS
GKIMEGGAGTGGIEFVEAPRGSEAWNKISLCVVPNESDGELPVDEYDPQLLASLIAEVFIVKEAAIDYLLANFKRWPGPH
DTVGYLRWTTFMARQEPTF-AELSFDARQRLAQSRLFCDEDFYISGSPESAEASLCHMLIELGNGKIVQEAKDAEYVIIT
DKTSPEALELKQKFANNDEDLISATHGARHSTLVTPKYIYDCIKTWQLQRPTKSSGHMAF
>XP_012650020.1 conserved Plasmodium protein, unknown function [Babesia microti strain RI] dupelabel1
MVEGFSTGLTESSQPNKTCDNFLCKHVDFVKRNFVEGVLRISHNEVLQSALDICYIPGCSAAKILAL--PNDMGEPPIKT
VSPINFIGIGLKTNQ--CIKSLLDKWYIAYLPINFNSMGHDLYNISMRLVDIIGTGSLF--KSGVIDKSYQLPW------
--------------------------------------------------------------------------------
---HSQSSIFTTPSCAYAGLDELASMIDYPKLRCKLQLVIQVLEQPGTYSVSKRSLYYETHADRGKDKHFLDNEIEWHST
SIDTIIPLRLLVRILPQNAQTFAQKNSLRLQLSIPRSNEVIQSGVKLSGKTGSDKSQILNLYLSIPVYSGELGLELVREE
PFTKLKGCIKNNEVCLRW-YTCITNCVNVVDYVLTNCIRSDGLE------------------------------------
KGISLEDPQYGVLGFCLPWCSEQNRILFYFKSLLNSRHVEWSPNEKIWKVPSIHIYTVAKFVQYLGGSIDPSVESHVAAY
ISKLKGKAV-------NAYEELCSTGVWKYTHILL------------------------ASKNKYQQLNFSFYPFDKRIV
ELAKSC--------KMKWNQNGNLWEMQLVQLPQLISHLKRSFETILPHGKLD----AIAAQFGVKIHKTNSSISKHTL-
NYVSVD-KVANSTR------------------NTIKRERNEVTCILITAAGKEPHLHRIVSKIVSVICTISPPASSIDDC
GNIVTGGPGTGGIKFIQSPRGIEEWNQISFCVIPSGERIDDLLSKYDINILCSLVGEVFIFTEKALDWLLSNCERWPDPS
DSIRYKHWNEVMLENEGALWDGNNFNSRQQLAQERLFCDEEFHIVGERNDPTVRLCTLLIQLGNGKLVSNPKHAEYVVIT
DSKSDDAMLMKSKFWKNDEDIISRTHGARHSTLVTPKFIYDCITTWKLQRPSRGQKHLAF
>XP_012650020.1 conserved Plasmodium protein, unknown function [Babesia microti strain RI]
MVEGFSTGLTESSQPNKTCDNFLCKHVDFVKRNFVEGVLRISHNEVLQSALDICYIPGCSAAKILAL--PNDMGEPPIKT
VSPINFIGIGLKTNQ--CIKSLLDKWYIAYLPINFNSMGHDLYNISMRLVDIIGTGSLF--KSGVIDKSYQLPW------
--------------------------------------------------------------------------------
---HSQSSIFTTPSCAYAGLDELASMIDYPKLRCKLQLVIQVLEQPGTYSVSKRSLYYETHADRGKDKHFLDNEIEWHST
SIDTIIPLRLLVRILPQNAQTFAQKNSLRLQLSIPRSNEVIQSGVKLSGKTGSDKSQILNLYLSIPVYSGELGLELVREE
PFTKLKGCIKNNEVCLRW-YTCITNCVNVVDYVLTNCIRSDGLE------------------------------------
KGISLEDPQYGVLGFCLPWCSEQNRILFYFKSLLNSRHVEWSPNEKIWKVPSIHIYTVAKFVQYLGGSIDPSVESHVAAY
ISKLKGKAV-------NAYEELCSTGVWKYTHILL------------------------ASKNKYQQLNFSFYPFDKRIV
ELAKSC--------KMKWNQNGNLWEMQLVQLPQLISHLKRSFETILPHGKLD----AIAAQFGVKIHKTNSSISKHTL-
NYVSVD-KVANSTR------------------NTIKRERNEVTCILITAAGKEPHLHRIVSKIVSVICTISPPASSIDDC
GNIVTGGPGTGGIKFIQSPRGIEEWNQISFCVIPSGERIDDLLSKYDINILCSLVGEVFIFTEKALDWLLSNCERWPDPS
DSIRYKHWNEVMLENEGALWDGNNFNSRQQLAQERLFCDEEFHIVGERNDPTVRLCTLLIQLGNGKLVSNPKHAEYVVIT
DSKSDDAMLMKSKFWKNDEDIISRTHGARHSTLVTPKFIYDCITTWKLQRPSRGQKHLAF
>XP_028867342.1 uncharacterized protein BOVATA_025920 [Babesia ovata]
MATDWGAS-----QAYDADLPRQCRHIEYIEANLLKKVLMLEQMEVVNASNHRCFIPTCQGGDLNDLKVFFNMGTPPMNT
YHPINYIGIGLHYDD--TVDT--SGWYTAYVPLHLKCFNNDLYALKHTLIRLIGSGKFWLPRDKHTDRATQGSQNDSSSS
APELPSGAAGAHSAVGMDGPQYHAQQGIKNTQDDATIDSKTSTQATSDDISSPVVNLFDTTDIDIGGDDTNVFMPACTPL
GVTDPNRYIFVTPSCMYATLPELASVLTFEGLQVSLRMVIQVVVKPRSYIAAGASVQ---NLKNNFDCCFPNDAIEWYVD
DVENVIPQRLLARILRKEEGV-VRHESCDSPIKPPQE----------ITAPQV------------------HGVNLITVM
PSTNVLFACENNFLAMRGAYSSVGGTEDAVTFLDATSPKANTASVSGSTTPIRATSSVQKVQDTAKQGDPSPKRAATAGN
TGDGSTEHGAPLLALKLKWTEHNNRVVYYLKSIIGSKFLEWDSELKIWRINAAFLYECVKYAIFLGLRVCDRVLYALWSW
LRSIDMRAIGDVFSKVHLIDWLGTNKIWQFQRVSVRVTPGFNPAVHRDTDNGATPAVQAMSRENAETVEIKLLPFNKDIV
TKFKERNAATGSSSTYVWDKESGSWLT-----GRLLSALE-DLLAVLPHLRESNLGDTFLSSRGINLRDINREQKKRQFP
GQISVPLKRPNATP---------------GDDSDSESEFATVTKLLITAAGKEPHLMRIRDKIRRVVENVAPPTSSISAS
GKVISGGAGTGGIEFVEAPRGCEWWNKVSLCVVPDEQDGEIPVDPYDPQLLASLIGEVYLVKEGALDYLLANFKRWPGPH
DAVGYSRWTSVMTRHEPNCWGGLTFDGRQNLAQSRLFCDEDFFVSGTNENRDAALCRLLIQLGSGKIVTSARDAEYVIIT
DRTSQEALELQRQFGANDEDLIAKTHGARHSTLVTPKFIYDCILGWRLQRPTRSHGHMAF
  ```
</details>

<details>
  <summary>Кластер # 5</summary>
    
  ```  
  >EDO08649.1 cytochrome c oxidase subunit Vb, putative [Babesia bovis]
MAYRIG----RALSRPLKAFNGCVT--NKYDI-ISKRTYVHFSRTQTHDFELPIDTMPKDIDALMKSDPKTMDYFGSYWY
WRIRGESSLMDPESLPKKSYKQLAVDLGMQVVNEPSEHMLGLLELYEYLKSSSFVGPFGTIKNPVLVPSILTERIVGCTG
GAGEHEHLPLWFRCREGFLYRCGECDQIFMLVRVLYSLPDGEDPFPVDPDIDDVFNKDIIAKGHFKWNAGDYIRWPVGNA
TYKQLFLQGKWGNPVPEISASMSDSSDPAHLDKFRPQNSV----EK
>XP_012650013.1 cytochrome c oxidase subunit Vb [Babesia microti strain RI] dupelabel1
MNGILG--VVNRLLIPSQNLQFSLRNGKKYIHTTNRYLYQHFDVGRPHDYWLPVETMPKDVDTLMKTDPSQMDYFGNYWY
WRIRGESTLMDSENLPKKTYKQLTRDLGMQVVSEESEHMLGLLELYEYLKSSPFVGPFGTIKNPVLVPSMNVERVVGCTG
GSGDREHVPLWFRCREGFLYRCGECDQIFMLVRLLLSLPDGEEPFPIDPDIDDVFDAQVLERGHIQWNTGDYIFWPIGNA
TYKQLFLQGKWGNPIPDTS--MYDQTGPENSINMQPLDKHKKFAQY
>XP_012650013.1 cytochrome c oxidase subunit Vb [Babesia microti strain RI]
MNGILG--VVNRLLIPSQNLQFSLRNGKKYIHTTNRYLYQHFDVGRPHDYWLPVETMPKDVDTLMKTDPSQMDYFGNYWY
WRIRGESTLMDSENLPKKTYKQLTRDLGMQVVSEESEHMLGLLELYEYLKSSPFVGPFGTIKNPVLVPSMNVERVVGCTG
GSGDREHVPLWFRCREGFLYRCGECDQIFMLVRLLLSLPDGEEPFPIDPDIDDVFDAQVLERGHIQWNTGDYIFWPIGNA
TYKQLFLQGKWGNPIPDTS--MYDQTGPENSINMQPLDKHKKFAQY
>XP_028867307.1 cytochrome c oxidase subunit [Babesia ovata]
MTPNMAYRIISSLSRPFKPTCGVSK--TDFFR-NSARGYVHFSRTQTHDFELPIDTMPKDIDALMKTDPKKMDYFGSYWY
WRIRGESTLMDADSLPKKSYKQLAVDLGMQVVNEPSEHMLGLLELYEYLKTSPFVGPFGTIKNPVLVPSVLTERVVGCTG
GAGEHEHVPLWFRCREGFLYRCGECDQIFMLVRVLYSLPDGEDPFPVDPDIDDVFNKDVLAKGHLKWNSGEYLRWPVGNA
TYKQLFLQGKWGNPVPEITASNDGNADPNRL---------SEFRPQ

  ```
</details>

<details>
  <summary>Кластер # 6</summary>
    
  ```  
  >XP_021338301.1 AFG3 family protein [Babesia microti strain RI] dupelabel1
ML---------PLRLLRQANIARLKRC-------------IS--------------------------TCSNFHSCCYLL
SLKHNDNYKYFADKTKKDDKSTSNDKKDSKQDTDSSQ---RYEHP----PNQPYDPS-------------IG--LSLMII
-FGGSLLLELVNSGFYRNEITFQEFFVKYLSMGQVDKIHVVNREYAKCFIKNGKE---NKIVYFRIGSIEHFETRLNQIQ
QSLDIHPDEYIPVQYVTGVNVVNELKKFIPFGILFFLIALGFRKLMMKGPPGMDKFFRMGKAVTVQAKDLKVKTSFKDVA
GMNEAKMEISEFVDFLKNPERFKSLGAKIPKGALLCGPPGTGKTLLAKAVAGEAQVPFYSISGSDFIEVFVGIGPSRVRD
LFENARKNAPSIIFIDEIDAIGKKRARGGFAGGSNDERENTLNQILVEMDGFKSSSGVVVMAGTNRADILDPALVRPGRF
DRTINISKPDIGERYEIFKVHLKPIKFSQNTDVDDLARRMAALTPGFVGAEIANVINEAAIVAARRKAEDGVEMRDFDAA
VERCIGGMVRSSGLLSNEQKRVIAYHETGHALTGWWLEYADPVLKVSIVPRSSGALGFSQQMPDDIALFSKEAILDKIAV
ILGGRAAEEIFIGKITTGATDDLNKVTKLCHSFVSQWGMNAKIGLVSYNTEG--EQDFYRNYSESTAQMIDNEVKNIITA
QYERVKKVLCDKADLVHKLSNLLYDKETLTYHDIANCVGERPFPPNEKYKAFIEAN------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
---------------------PHKIAVNSSN
>XP_028865343.1 AFG3 family protein [Babesia ovata]
MAMPALTLGRQAMRRLFGAEGYRLLRSGELELAGGALPSLASRGRPFHSSICNAS-FI--LNTNLHVC--YAGVRGSRHF
SKKVPTGFGRFAGRGGSSDTGASEDQADSGPSSGTKKPEGKMGNY----PGKPTDPNGSKNDGNSPFAALCAAPFRLLFY
GLLALGSLKFFYSSDLPNEITMQEFLKKYLMRGLVDNIVIVNGKICRCLLRSDSK-TERKVVTFRIQSVDSAERKLDEIQ
RSLGVRPEDFIPVKHVEEVEWLRVLKYAIAVGIPVVSMALIAWRI-LSSSQYIDRIHRMRNLNLTNAKDIKVGVRFKDVA
GMHEAKREISEFVDYLKNPKSYEQYGAKIPKGALLCGAPGTGKTLLAKAVAGEANVPFYFISGSDFVEIYVGVGPSRVRS
LFQKARENAPSIVFIDEIDAVGKRRG-GKNGTGSHDERDSTLNQILVEMDGFKASSGVIVLAGTNRHEILDPALVRPGRF
DRIITINSPDLDERYEIFKVHLAPLKLNKLLDVDDLARRLAALTPSFVGAQIANVANEAALQAARRNSTDGVELVDFEAS
IERVIAGLRRSNQLLSPEQKLVVAYHEVGHALVGWWLEHADPVLKVSIIPRSSGSLGYSQQIADETPLFSREALLDRIAV
ILGGRASEEIFVGRITTGATDDLNKVTRMCYAFVSKWGMNPALGLVSYQRDGDEGPGFYRAYSESTAQLIDQEVRSIIEG
QYARVKALLGEKAELVHKLARLLFERESLSYQDIASCVGERQFPMQERLRPYVLGSISDVPELPRLPDA-EP--------
----------------------------------------------------------------------AT--------
--------------------------------------------------------------------------------
---------------PPGDGNTG-LVSEGSL
>XP_021338301.1 AFG3 family protein [Babesia microti strain RI]
ML---------PLRLLRQANIARLKRC-------------IS--------------------------TCSNFHSCCYLL
SLKHNDNYKYFADKTKKDDKSTSNDKKDSKQDTDSSQ---RYEHP----PNQPYDPS-------------IG--LSLMII
-FGGSLLLELVNSGFYRNEITFQEFFVKYLSMGQVDKIHVVNREYAKCFIKNGKE---NKIVYFRIGSIEHFETRLNQIQ
QSLDIHPDEYIPVQYVTGVNVVNELKKFIPFGILFFLIALGFRKLMMKGPPGMDKFFRMGKAVTVQAKDLKVKTSFKDVA
GMNEAKMEISEFVDFLKNPERFKSLGAKIPKGALLCGPPGTGKTLLAKAVAGEAQVPFYSISGSDFIEVFVGIGPSRVRD
LFENARKNAPSIIFIDEIDAIGKKRARGGFAGGSNDERENTLNQILVEMDGFKSSSGVVVMAGTNRADILDPALVRPGRF
DRTINISKPDIGERYEIFKVHLKPIKFSQNTDVDDLARRMAALTPGFVGAEIANVINEAAIVAARRKAEDGVEMRDFDAA
VERCIGGMVRSSGLLSNEQKRVIAYHETGHALTGWWLEYADPVLKVSIVPRSSGALGFSQQMPDDIALFSKEAILDKIAV
ILGGRAAEEIFIGKITTGATDDLNKVTKLCHSFVSQWGMNAKIGLVSYNTEG--EQDFYRNYSESTAQMIDNEVKNIITA
QYERVKKVLCDKADLVHKLSNLLYDKETLTYHDIANCVGERPFPPNEKYKAFIEAN------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
---------------------PHKIAVNSSN
>EDO08086.1 ATP-dependent metalloprotease FtsH family protein [Babesia bovis]
MT----ILSRQALRRVFGASGHRFLRNNGIGTVR-----VLPEHHHLGSSLPRQYGTTVVLDLSAIQPKSKRFVTSYQVL
AAKPPTGFGKFTRKDDATEDTNNKETPAASDDKNPSE---KGKDN-------TNETKDQKNDDDRKGFGRLMEPYTLIII
GIGSMLLLDVLDSGGLRNEITLQEFIGKYLMKGLVERIQIVNKEFCRCSLVTGVDHTMPRVVSFRIGSLEAFEQKLDDIQ
ASMGIHPQDYIGIHYVNEVNVLGELKHYIPFMVVMMLLGLGLRKLTVRSTGGMDRFFRMGKMNIVDAKDVKVDVKFKDVA
GMHEAKKEISEFVDFLKNPKAYEHYGAKIPKGALLCGAPGTGKTLLAKAVAGEANVPFYSISGSDFIEVFVGVGPSRVRD
LFEKARKNAPAIVFIDEIDAVGKKRAKGGFSAGANDERENTLNQILVEMDGFKSSSGVIVLAGTNRADILDPALVRPGRF
DRTITINKPDLDERFEIFKVHLSPIKLNKNLDMDDVARRLAALTPSFVGAEIANVSNEAAIQAVRRKSTDGVSLADFDAA
IERVMAGLRRSNALLSPAQKLAVAYHEVGHALIGWWLEHADPVLKVSIIPRSSGALGFSQQLPDEAMLFSREALLDKVAV
MLGGRAAEDIFIGRITTGATDDLNKVTRMCYAFVSQWGMNPALGLVSYQRGSGDEPEFYRTYSENTAQLIDTEVRTMIES
QYARVKSMLREKAELVHKLSKLLYQRETITYHDIASCIGEREFPVEEKLRPYVLSGIEGRVEPIKLPET-TGEAINEIK-
----------------------------------------------------------------------GT--------
--------------------------------------------------------------------------------
---------------EKSDDNTQETNSEVSK
>XP_028872379.1 AFG3-like protein 2 [Babesia sp. Xinjiang]
MY---------ALRRIFGASGHRLLRNHGIQDVC-----FVAIGRANYCGIVKPYGIS--VDTQRILCRYKRSIWNTHTF
SSKDPDGFGKFTKRDGTSEPKSSKEATDST---NSST---KGKETDRGGRSESQDPKEPKNEDERKLLSRLMEPYTLILL
GIGTVLFLDVLDSGGLRNEITLQEFLGKYLMRGLVERIQIVNKDFCRCSIVNGADYKLPRIVSFRIGSLEAFEQKLDDIQ
ASMGLHPQDYIGVQYVNEVNIIGELKRYIPFMVAMLLLGIGLRKLTVRSTGGMDRFFRMGKMNVVDAKDIKVDVRFKDVA
GMHEAKREISEFVDFLKNPKAYEHYGAKIPKGALLCGAPGTGKTLLAKAVAGEANVPFYSISGSDFIEVFVGVGPSRVRD
LFEKARKNAPAIVFIDEIDAVGKKRAKGGFSAGANDERENTLNQILVEMDGFKTSSGVIVLAGTNRADILDPALVRPGRF
DRTITINRPDLDERFEIFKVHLAPLKLHKSLDMDDVARHLAALTPNFVGAEIANVSNEAAIQAVRRKSTDGVSLVDFDAA
IERVMAGLRRSNALLSPAQKLAVAYHEVGHALVGWWLEHADPVLKVSIIPRSNGALGFSQQLPDEAMLFSREALLDKVAV
MLGGRAAEDIFIGRITTGATDDLNKVTRMCYAFVSQWGMNPSLGLVSYQRDSGDEPDFYRTYSETTAQLIDNEVRTMIES
QYSRVQSLLREKADLVHKLSKLLYQRETITYHDIASCVGEREFPVQEKLRPYVLSGMEGESDPLKLPGSGEGSALNDSSV
LSEPGKVTGAMGKATVAAESSPAEDVPPMEPVTVEYCPRCGMPFDFCDFGDKWETGECRAECSRRYPEIFGTAEEVAEQL
LKISISPPPAPRKKKPEVRQEVTVQRSTRSKRKIVTTVTGLHLFGVKLEVAAKLFAKQFASGAGVVKGVPGQMDHIDCQG
DVEDQVIDLILAQYPDITEDNIVRLPS-KIK
  ```
</details>

<details>
  <summary>Кластер # 7</summary>
    
  ```  
  >XP_028867804.1 lipid-binding transfer protein [Babesia ovata]
MVDEM--NNNAPSDPCSTEPL--SPELSYLVGCLKNGIPFEGWNYVRDFEANNNTLHISSRCRGS-----GTLKEFLVHG
DIDVSKEKLVELILTMNQRSEWDETYVEHKIIRPSENATDIVYTVSKYPFPLSKRVYTIKRSLYGSMDDVVVLATKVIPY
DYPLSSRWITRVDDFESNLIVSDIKDKPDHCRMIATLYEDPRVILPNMYLNLIIESLVPRILNKMFAAAKQ---------
-----YGSDKSTEFCRQLFCVPLDYKGESP-----------------SATEDSA
>XP_012649100.1 hypothetical protein BMR1_03g02445 [Babesia microti strain RI]
MDI-------------EVDYFDIPETQWELVEHASNGTIPESYKKISDFDVMSSKITLYYRNKIDAKGNNRNLNEYFIKG
TLNVPRDDFLFLVMDESMRAAWDTTLLSSRTLVKE-PEYDLGFYVSKYPFPLLRRTYLTARTFF-TKNDIGVIFSRAIEG
AVPFKISWSTRVTDYISSVSIRPLSD--NTSEMYFYHYEDPKTFLPDAMLNRVIVTIIPTIISKLLNACRPTTPQERETV
YKIFKFGTD-----CNKFKDIPLEKRSIKYVNYDLPDKLEMLECS-DKDDLSDN
>XP_012649100.1 hypothetical protein BMR1_03g02445 [Babesia microti strain RI] dupelabel1
MDI-------------EVDYFDIPETQWELVEHASNGTIPESYKKISDFDVMSSKITLYYRNKIDAKGNNRNLNEYFIKG
TLNVPRDDFLFLVMDESMRAAWDTTLLSSRTLVKE-PEYDLGFYVSKYPFPLLRRTYLTARTFF-TKNDIGVIFSRAIEG
AVPFKISWSTRVTDYISSVSIRPLSD--NTSEMYFYHYEDPKTFLPDAMLNRVIVTIIPTIISKLLNACRPTTPQERETV
YKIFKFGTD-----CNKFKDIPLEKRSIKYVNYDLPDKLEMLECS-DKDDLSDN
>EDO06316.1 conserved hypothetical protein [Babesia bovis]
MSRVFIDGGAINGDPLEVEPF--PPDLVDLVQQFKSGGNFTAWKWVRDYKLHPNTLKLYSKPHVD-----STLKNFLVHG
EVDVTKEKMIELIVQMTQRSKWDETYVEHQILHKSTKGTDIMFSVSKYPFPLAKRTYVIKRSLYGSMDDVVVLVSKVIPY
EYTTKYKWSTKVDDFESILMVRNHKPGEEACEMLATYFENPKVILPNMYLNQIIETLVPRILEKLVIASKK---------
-----FGTDQSPIYCRGLYLTPLDSTGQSTGG----GP---HHSDDAQEDTNES
>XP_028871147.1 Phosphatidylcholine transfer protein [Babesia sp. Xinjiang]
MASLTTTNQCADGDPCATEPL--TPEMCKLLEQFKNGGNFTDWQWVRDYHVKPSTLKLFSRLRGT-----STLKEFLVYG
EIDACKEKLVELIVEMSQRSKWDDTYVEHQIVKPAVNGTDVLFSVSKYPFPLAKRTYVVKRTIYGSVDDIIVLLSKVIPY
NYNSKYKWSTKVDEFESILMVRNTKEGQEACEMLATYYENPRVILPNMYLNSIIENLVPRILEKMIIACKK---------
-----YGSDKSTDYCRGLYCVPLPDTETAESD-NITSK---EETNDMPMPTDGA
  ```
</details>

<details>
  <summary>Кластер # 8</summary>
    
  ```  
  >EDO05485.1 conserved hypothetical protein [Babesia bovis]
MSTV---VYLTSLLHIIAVVCFSTADCTLSSRWWYIC----NFACALGLTKLVPPRVYGFILTGP------------SRG
LQCTH-LLASKKNKVNDHSRNKRAVSDD---DD-DPTAVSEAELDSLYVNLKSRLKEAEEHLRYKISRLTLHRATPSLVD
SLTVELPGEKKEKQLQYVARIISKGPYELQVLPLDIHHLDAVFVSLSTKLVDYKVSMQPDRISVVIPSMTELMIQQARSV
VKETHNEVKTRVRTIRLDFAKKLKGMRKGLSDDMYFRQEKELDSIVKQSERVVDQIANGALKSLG
>XP_012648641.1 hypothetical protein BMR1_03g00150 [Babesia microti strain RI]
MQQR---CINRPA--------------IIASFALFIC-------------------------------------------
-------NNSLDKFANSHLARKRQNTSE---IE-YTDSENLELVDSIMDNLSKKLKQSNEFLISELEKLPTNKANPRLVE
NLILDC----EKKPIKYLART-TVNQSTIKIQPYNKEHVKHLLDLVHKTFPESQTKSDSENVWITISALSDDLKEGVKAA
VKELLLNTKNKHRVARQDAINALKNAKDRLSDDFYHMKLQEVDETSKKLYGEVEKLCNKKIELSA
>XP_012648641.1 hypothetical protein BMR1_03g00150 [Babesia microti strain RI] dupelabel1
MQQR---CINRPA--------------IIASFALFIC-------------------------------------------
-------NNSLDKFANSHLARKRQNTSE---IE-YTDSENLELVDSIMDNLSKKLKQSNEFLISELEKLPTNKANPRLVE
NLILDC----EKKPIKYLART-TVNQSTIKIQPYNKEHVKHLLDLVHKTFPESQTKSDSENVWITISALSDDLKEGVKAA
VKELLLNTKNKHRVARQDAINALKNAKDRLSDDFYHMKLQEVDETSKKLYGEVEKLCNKKIELSA
>XP_028870914.1 uncharacterized protein BXIN_1951 [Babesia sp. Xinjiang]
MVHLRTCFISWPP--------------SYGQRTNYTL-------------------------------------------
-------AASKKKRGHEHSRSRKYSSDDELDTDITPTAVSEADLDVVFSVLRKKLHENEEFLRSKISRLTLHRATPSLVE
SLTVELPNEKKEKQLQYAARIMTAGNYELHVLPLSPEHLDAIFVALSTKLVDYKVIMMQDRVSVVIPSMTEVMIRQARTV
VKETLHEVRSRIRVARQDALKKLKSLHKGLSDDMFYRQQKEVDTTVKQSENRVEKVANDALRSLG
>XP_028868477.1 ribosome recycling factor, putative [Babesia ovata]
MVPR---WILAQV--------------IWLVIALAFTLRRDPYAVALSAYSLSRSRFVSFV-TGPIIDRVCTFILRRSEA
PRCLQQLDASRKKKSKSQGRIGRGGEDGGSDDD-EEFVVSEADLEAVFAGLRSKLKESEQFLSNKISRLALHRATPSLIE
SLTVELPGESKEKQLQYVAQIMSKGPYELHVVPLSPGHLDSIFVCLSTKLVDYKVSMMPDRVSVVVPSMTEAMVRQARSV
VKETLNEVKTQIRLTRQAVIKKLKHMHQALSDDMFFRQQKEVDAVVKQSEKRVDDIANDTLRGLG
  ```
</details>


## **Визуализация расположение Z-ДНК для каждого выбранного кластера**
>
> ![image](https://user-images.githubusercontent.com/59726719/173436945-10053caa-b842-4a0f-9cb4-caf4e3578edc.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437000-532ca3ba-1b46-4cae-a7ba-79e7ce5d8675.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437068-a7eaad74-19d3-4166-beb4-215bce4eba67.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437125-9a4203de-c9ac-46f0-85f2-8e534a2b4364.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437191-b340a804-0d70-420f-92d8-1280963e653a.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437241-e7387252-26a9-4bcf-9851-0ad38b21c3fc.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437474-a09d8c37-e2d0-40c7-805b-cf4223844175.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173437533-0c42283e-e0d7-4613-829f-4c8f8e39b2b2.png)
