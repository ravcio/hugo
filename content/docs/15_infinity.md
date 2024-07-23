---
title: Nieskończoność
type: docs
math: true
weight: 3
prev: docs/folder/
---

Granica pomiędzy mało a dużo dla komputera nie jest
tak rozmyta czy nieokreślona jak może się wydawać.




## 2**64 to nieskończenie dużo

Dla pojedynczego komputera $2^{64}$ to jest nieskończona liczba.
Natomiast liczba $2^{32}$ to jest bardzo mało.

- Ilość ram $2^{32}$ bajtów jest zerowany w mniej niż 1 sekundę. Ilość ram $2^{64}$ bajtów jest zerowany przez 100 lat.
- Pętla która robi $2^{64}$ nie skończy się w ciągu 100 lat.
- Ilość danych wygenerowana przez ludzkość to więcej niż $2^{64}$, 
  więc dla chmury obliczeniowej czy dużej serwerowni jest to siągalna liczba. 
  Wtedy musimy przyjąć wyższą wartość nieskończoności: $2^{128}$.

Liczba ziaren piasku na plażach świata to 7.5e18 sztuk. To mniej niż $2^{64}$.

```python {filename="python"}
from math import log
log(7.5e18) / log(2)  # 62.7
```

## 2**-64 to zero

To około 9 odchyleń standardowych rozkładu normalnego.

```python
from mpmath import mp
mp.dps = 50
mp.pretty=True
print(1-ncdf(9)) # 1.1e-19
print(2**-64) # 5.4e-20
```

Wylosuj 32 razy reszkę pod rząd (czas działania: kilka/kilkanaście sekund)

```py
import numpy as np

for i in range(1000):
    a = np.random.randint(0,2**32, 100_000_000, dtype=np.uint32)
    if 0 in a:
        break
    print(i)

idx = np.where(a==0)[0][0]
list(a[idx-2:idx+3])  # [2957777043, 958089629, 0, 3150515941, 957238589]
```

Wylosuj 64 razy reszkę pod rząd (czas działania: kilka/kilkanaście tysięcy lat)

```py
for i in range(1000):
    a = np.random.randint(0,2**64, 100_000_000, dtype=np.uint64)
    if 0 in a:
        break
    print(i)

idx = np.where(a==0)[0][0]
list(a[idx-2:idx+3])
```






##


|     2^ | typ danych | opis                                                                                      |
| -----: | :--------- | :---------------------------------------------------------------------------------------- |
|      1 | bit        | wyniki rzutu monetą                                                                       |
|      2 |            |                                                                                           |
|      3 |            | wyniki rzutu kostą 6/8 sześcienną                                                         |
|      4 |            |                                                                                           |
|      5 |            |                                                                                           |
|      6 |            |                                                                                           |
|      7 |            |                                                                                           |
|      8 | int8       | bajt (256 wartości) , 3 sigma                                                             |
|      9 |            |                                                                                           |
|     10 |            |                                                                                           |
|     11 |            |                                                                                           |
|     12 |            |                                                                                           |
|     13 |            |                                                                                           |
|     14 |            | 4 sigma                                                                                   |
|     15 |            |                                                                                           |
|     16 | int16      |                                                                                           |
|     17 |            |                                                                                           |
|     18 |            |                                                                                           |
|     19 |            | ram w Atari65xe (64K) tyle bitów                                                          |
|     20 |            |                                                                                           |
|     21 |            | 5 sigma                                                                                   |
|     22 |            |                                                                                           |
|     23 |            |                                                                                           |
|     24 |            |                                                                                           |
|     25 |            | ludność Polski                                                                            |
|     26 |            |                                                                                           |
|     27 |            | liczba sekund życia człowieka                                                             |
|     28 |            |                                                                                           |
|     29 |            | 6 sigma                                                                                   |
|     30 |            |                                                                                           |
|     31 |            |                                                                                           |
|     32 | int32      | CD (700MB) liczba bitów                                                                   |
|     33 |            | liczba ludzi na świecie                                                                   |
|     34 |            |                                                                                           |
|     35 |            | DVD (4.7GB)                                                                               |
|     36 |            | liczba neuronów w mózgu człowieka <br> liczba sekund od zasiedlenia Australii (50000 lat) |
|     37 |            | 16GB                                                                                      |
|     38 | 32GB       | liczba gwiazd w drodze mlecznej, 7 sigma                                                  |
|     39 |            |                                                                                           |
|     40 |            |                                                                                           |
|     41 | 256GB      | liczba galaktyk we wszechświecie                                                          |
|     42 |            |                                                                                           |
|     43 | 1TB        |                                                                                           |
|     44 |            | liczba czerwonych krwinek u człowieka                                                     |
|     45 |            |                                                                                           |
|     46 | 8TB HDD    |                                                                                           |
|     47 |            |                                                                                           |
|     48 |            |                                                                                           |
|     49 |            | 8 sigma                                                                                   |
|     50 |            |                                                                                           |
|     51 |            |                                                                                           |
|     52 |            |                                                                                           |
|     53 |            |                                                                                           |
|     54 |            | liczba sekund od początku wszechświata                                                    |
|     55 |            |                                                                                           |
|     56 |            |                                                                                           |
|     57 |            |                                                                                           |
|     58 |            |                                                                                           |
|     59 |            |                                                                                           |
|     60 |            |                                                                                           |
|     61 |            |                                                                                           |
|     62 |            |                                                                                           |
|     63 |            | liczba ziaren piasku na ziemi                                                             |
| **64** | int64      | bezpieczny klucz kryptografii z tajnym kluczem , 9 sigma                                  |  |
|     65 |            |                                                                                           |
|     66 |            |                                                                                           |
|     67 |            |                                                                                           |
|     68 |            |                                                                                           |
|     69 |            |                                                                                           |
|     70 |            | liczba gwiazd we wszechświecie                                                            |
|     71 |            |                                                                                           |
|     72 |            |                                                                                           |
|     73 |            |                                                                                           |
|     74 |            |                                                                                           |
|     75 |            |                                                                                           |
|     76 |            |                                                                                           |
|     77 |            |                                                                                           |
|     78 |            |                                                                                           |
|     79 |            | liczba Avogadro (atomów w 12g węgla)                                                      |
|     80 |            |                                                                                           |
|     81 |            |                                                                                           |
|     82 |            |                                                                                           |
|     83 |            |                                                                                           |
|     84 |            |                                                                                           |
|     85 |            | liczba cząsteczek wody w litrze                                                           |
|     86 |            |                                                                                           |
|     87 |            |                                                                                           |
|     88 |            |                                                                                           |
|     89 |            |                                                                                           |
|     90 |            |                                                                                           |
|     91 |            |                                                                                           |
|     92 |            |                                                                                           |
|     93 |            |                                                                                           |
|     94 |            |                                                                                           |
|     95 |            |                                                                                           |
|     96 |            |                                                                                           |
|     97 |            |                                                                                           |
|     98 |            |                                                                                           |
|     99 |            |                                                                                           |
|    100 |            |                                                                                           |
|    101 |            | liczba bakterii na świecie                                                                |
|    102 |            |                                                                                           |
|    103 |            |                                                                                           |
|    104 |            |                                                                                           |
|    105 |            |                                                                                           |
|    106 |            |                                                                                           |
|    107 |            |                                                                                           |
|    108 |            |                                                                                           |
|    109 |            |                                                                                           |
|    110 |            |                                                                                           |
|    111 |            |                                                                                           |
|    112 |            |                                                                                           |
|    113 |            |                                                                                           |
|    114 |            |                                                                                           |
|    115 |            |                                                                                           |
|    116 |            |                                                                                           |
|    117 |            |                                                                                           |
|    118 |            |                                                                                           |
|    119 |            |                                                                                           |
|    120 |            |                                                                                           |
|    121 |            |                                                                                           |
|    122 |            |                                                                                           |
|    123 |            |                                                                                           |
|    124 |            |                                                                                           |
|    125 |            |                                                                                           |
|    126 |            |                                                                                           |
|    127 |            |                                                                                           |
|    128 | int128     | md5 oraz klucz kryptografii publicznej/asymetrycznej                                      |
|    129 |            |                                                                                           |
|    130 |            |                                                                                           |
|    131 |            |                                                                                           |
|    132 |            |                                                                                           |
|    133 |            |                                                                                           |
|    134 |            |                                                                                           |
|    135 |            |                                                                                           |
|    136 |            |                                                                                           |
|    137 |            |                                                                                           |
|    138 |            |                                                                                           |
|    139 |            |                                                                                           |
|    140 |            |                                                                                           |
|    141 |            |                                                                                           |
|    142 |            |                                                                                           |
|    143 |            |                                                                                           |
|    144 |            |                                                                                           |
|    145 |            |                                                                                           |
|    146 |            |                                                                                           |
|    147 |            |                                                                                           |
|    148 |            |                                                                                           |
|    149 |            |                                                                                           |
|    150 |            |                                                                                           |
|    151 |            |                                                                                           |
|    152 |            |                                                                                           |
|    153 |            |                                                                                           |
|    154 |            | liczba cząsteczek wody na ziemi                                                           |
|    155 |            |                                                                                           |
|    156 |            |                                                                                           |
|    157 |            |                                                                                           |
|    158 |            |                                                                                           |
|    159 |            |                                                                                           |
|    160 | sha1       |                                                                                           |
|    161 |            |                                                                                           |
|    162 |            |                                                                                           |
|    163 |            |                                                                                           |
|    164 |            |                                                                                           |
|    165 |            |                                                                                           |
|    166 |            | liczba atomów na ziemi                                                                    |
|    167 |            |                                                                                           |
|    168 |            |                                                                                           |
|    169 |            |                                                                                           |
|    170 |            |                                                                                           |
|    171 |            |                                                                                           |
|    172 |            |                                                                                           |
|    173 |            |                                                                                           |
|    174 |            |                                                                                           |
|    175 |            |                                                                                           |
|    176 |            |                                                                                           |
|    177 |            |                                                                                           |
|    178 |            |                                                                                           |
|    179 |            |                                                                                           |
|    180 |            |                                                                                           |
|    181 |            |                                                                                           |
|    182 |            |                                                                                           |
|    183 |            |                                                                                           |
|    184 |            |                                                                                           |
|    185 |            |                                                                                           |
|    186 |            |                                                                                           |
|    187 |            |                                                                                           |
|    188 |            |                                                                                           |
|    189 |            | liczba atomów w Słońcu                                                                    |
|    190 |            |                                                                                           |
|    191 |            |                                                                                           |
|    192 |            |                                                                                           |
|    193 |            |                                                                                           |
|    194 |            |                                                                                           |
|    195 |            |                                                                                           |
|    196 |            |                                                                                           |
|    197 |            |                                                                                           |
|    198 |            |                                                                                           |
|    199 |            |                                                                                           |
|    200 |            |                                                                                           |
|    201 |            |                                                                                           |
|    202 |            |                                                                                           |
|    203 |            |                                                                                           |
|    204 |            |                                                                                           |
|    205 |            |                                                                                           |
|    206 |            |                                                                                           |
|    207 |            |                                                                                           |
|    208 |            |                                                                                           |
|    209 |            |                                                                                           |
|    210 |            |                                                                                           |
|    211 |            |                                                                                           |
|    212 |            |                                                                                           |
|    213 |            |                                                                                           |
|    214 |            |                                                                                           |
|    215 |            |                                                                                           |
|    216 |            |                                                                                           |
|    217 |            |                                                                                           |
|    218 |            |                                                                                           |
|    219 |            |                                                                                           |
|    220 |            |                                                                                           |
|    221 |            |                                                                                           |
|    222 |            |                                                                                           |
|    223 |            |                                                                                           |
|    224 |            | liczba atomów w drodze mlecznej                                                           |
|    225 |            | liczba permutacji talii kart (52!)                                                        |
|    226 |            |                                                                                           |
|    227 |            |                                                                                           |
|    228 |            |                                                                                           |
|    229 |            |                                                                                           |
|    230 |            |                                                                                           |
|    231 |            |                                                                                           |
|    232 |            |                                                                                           |
|    233 |            |                                                                                           |
|    234 |            |                                                                                           |
|    235 |            |                                                                                           |
|    236 |            |                                                                                           |
|    237 |            |                                                                                           |
|    238 |            |                                                                                           |
|    239 |            |                                                                                           |
|    240 |            |                                                                                           |
|    241 |            |                                                                                           |
|    242 |            |                                                                                           |
|    243 |            |                                                                                           |
|    244 |            |                                                                                           |
|    245 |            |                                                                                           |
|    246 |            |                                                                                           |
|    247 |            |                                                                                           |
|    248 |            |                                                                                           |
|    249 |            |                                                                                           |
|    250 |            |                                                                                           |
|    251 |            |                                                                                           |
|    252 |            |                                                                                           |
|    253 |            |                                                                                           |
|    254 |            |                                                                                           |
|    255 |            |                                                                                           |
|    256 |            |                                                                                           |
|    257 |            |                                                                                           |
|    258 |            |                                                                                           |
|    259 |            |                                                                                           |
|    260 |            |                                                                                           |
|    261 |            |                                                                                           |
|    262 |            |                                                                                           |
|    263 |            |                                                                                           |
|    264 |            |                                                                                           |
|    265 |            |                                                                                           |
|    266 |            | liczba atomów we wszechświecie                                                            |
