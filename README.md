# hse22_project
# **Индивидуальная часть проекта. Галкина Мария, группа №4**

> ## Введение:
> Целью работы над проектом является поиск и изучение консервативных участков генома Z-ДНК в геномах прокариот и эукариот. В процессе выполнения проекта будут получены важные практические навыки биоинформатика -- работа в командной строке с утилитой bedtools, визуализация данных, конвертация координат участков между разными версиями генома (разными организмами) и т.п.

> ## **Вводные данные**
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

> ## **Аннотированные гены**
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

> ## **Z-DNA**
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

> ## **Гистограммы с распределением ZH-Score**
> <img width="238" alt="zh-score 1" src="https://user-images.githubusercontent.com/59726719/173419267-cfc437f3-b42e-4c51-ae17-106899b2f563.png">
> <img width="232" alt="zh-score 2" src="https://user-images.githubusercontent.com/59726719/173419301-94bb3be4-e7f5-415d-a91b-b858f8e158ac.png">
> <img width="230" alt="zh-score 3" src="https://user-images.githubusercontent.com/59726719/173419392-a8939b5e-9b06-46f1-b7dc-eae419063523.png">
> <img width="233" alt="zh-score 4" src="https://user-images.githubusercontent.com/59726719/173419416-8179fe5f-52fe-47f9-aff0-f311af5cb440.png">
> <img width="235" alt="zh-score 5" src="https://user-images.githubusercontent.com/59726719/173419436-eac29d83-5bc9-420d-a974-5007b02485c9.png">

> ## **Расположение предсказанных Z-ДНК:**
> ![image](https://user-images.githubusercontent.com/59726719/173420010-f912fbbe-a789-47f0-a947-b49f5d1e13ca.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420121-6aa1f7f2-b849-425b-8abc-6657850d9c11.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420207-28431de5-8302-4944-82d9-9501f1a6a43a.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420277-a41ad2b3-3fa1-4f2a-83f4-58d6ced0a518.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420333-da39409b-285f-4d2c-944d-3beb9d81179c.png)

> ## **Распределение предсказанных Z-ДНК:**
> ![image](https://user-images.githubusercontent.com/59726719/173420467-5929257d-ea05-4ed5-81d3-08312509d6eb.png)
>
> ![image](https://user-images.githubusercontent.com/59726719/173420525-cca79392-118e-4019-beaa-f2fdfe892107.png)

> ## **Гомологичные кластеры:**
> Всего получено 5263 кластера. В качестве визуализации были построены гистограммы.
> - Гистограмма, отражающая кластеры и количество геномов, которые в них входят:  
> ![image](https://user-images.githubusercontent.com/59726719/173426799-ee5ea23b-a809-4435-b1fe-0675fd544f03.png)
>
> - Гистограмма, отражающая количество геномов в кластерах:
> 
> ![image](https://user-images.githubusercontent.com/59726719/173426837-bd07e788-5143-45bf-817d-1ded762d1bce.png)
>
> 



















