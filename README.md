<p align="center"><img src="https://raw.githubusercontent.com/ziegfiroyt/acikkuran-api/master/logo.png" alt="Apaçık Kur'an'a andolsun!" /></p>
<h2 align="center">Açık Kuran API</h2>
<p align="center"><a href="https://acikkuran.com">https://acikkuran.com</a></p>
<p align="center">
  Böylece sen, batıl olan her şeyden arınmış olarak, yüzünü kararlı bir şekilde Allah'ın, insanları üzerinde yarattığı doğa/fıtrat kanununa/dine çevir! Allah'ın, insanın doğasına yerleştirdiği fıtrata uygun davran ki, Allah'ın yaratmasında bir değişime meydan verilmesin. Bu, gerçek dinin amacıdır; fakat insanların çoğu bilmez. (<a href="https://acikkuran.com">30:30</a>)
</p>

## GET `/authors`

> Lists all authors.

Example: `https://api.acikkuran.com/authors`

Response body:

```json
{
    "data": [
      {
        "id": 50,
        "name": "Erhan Aktaş",
        "description": "Kerim Kur'an",
        "language": "tr"
      }
      {
        "id": 102,
        "name": "The Monotheist Group",
        "description": "The Quran: A Monotheist Translation",
        "language": "en"
      }
    ]
}
```

## GET `/surahs`

> Lists all surahs.

Example: `https://api.acikkuran.com/surahs`

Response body:

```json
{
  "data": [
    {
      "id": 1,
      "name": "Fatiha",
      "name_en": "Al-Faatiha",
      "slug": "fatiha",
      "verse_count": 7,
      "page_number": 0,
      "name_original": "سُورَةُ ٱلْفَاتِحَةِ",
      "audio": {
        "mp3": "https://archive.org/download/INDIRILIS_SIRASINA_GORE_SESLI_KURAN_MEALI/05-fatiha.mp3",
        "duration": 38
      }
    },
    {
      "id": 2,
      "name": "Bakara",
      "name_en": "Al-Baqara",
      "slug": "bakara",
      "verse_count": 286,
      "page_number": 1,
      "name_original": "سورة البقرة",
      "audio": {
        "mp3": "https://archive.org/download/INDIRILIS_SIRASINA_GORE_SESLI_KURAN_MEALI/87-bakara.mp3",
        "duration": 5982
      }
    }
  ]
}
```

## GET `/surah/[surah_id]?author=[author_id]`

> Gets surah's detail and lists verses of this surah.

Example 1: `https://api.acikkuran.com/surah/6` Default translation

Example 2: `https://api.acikkuran.com/surah/6?author=8` Author can be select with `author` parameter

Response body:

```json
{
  "data": {
    "id": 6,
    "name": "Enam",
    "slug": "enam",
    "verse_count": 165,
    "pageNumber": 127,
    "audio": {
      "mp3": "https://archive.org/download/INDIRILIS_SIRASINA_GORE_SESLI_KURAN_MEALI/55-enam.mp3",
      "duration": 2995
    },
    "zero": {
      "id": 1,
      "surah_id": 1,
      "verse_number": 1,
      "verse": "بِسْمِ اللّهِ الرَّحْمَنِ الرَّحِيمِ",
      "page": 0,
      "juzNumber": 1,
      "transcription": "Bismillahir rahmanir rahim.",
      "translation": {
        "id": 180482,
        "author": {
          "id": 105,
          "name": "Erhan Aktaş",
          "description": "Kerim Kur'an",
          "language": "tr"
        },
        "text": "Rahmeti Bol ve Kesintisiz Olan Allah'ın Adıyla",
        "footnotes": null
      }
    },
    "verses": [
      {
        "id": 790,
        "surah_id": 6,
        "verse_number": 1,
        "verse": "الْحَمْدُ لِلّهِ الَّذِي خَلَقَ السَّمَاوَاتِ وَالأَرْضَ وَجَعَلَ الظُّلُمَاتِ وَالنُّورَ ثُمَّ الَّذِينَ كَفَرُواْ بِرَبِّهِم يَعْدِلُونَ",
        "page": 127,
        "juz_number": 7,
        "transcription": "Elhamdu lillahillezi halakas semavati vel arda ve cealez zulumati ven nur, summellezine keferu bi rabbihim ya'dilun.",
        "translation": {
          "id": 181271,
          "text": "Hamd[1],  gökleri ve yeri yaratan,  karanlıkları ve aydınlığı var eden Allah'a özgüdür. Yine de Kafirler[2] ilahlarını Rabb'leriyle denk tutuyorlar.",
          "author": {
            "id": 105,
            "name": "Erhan Aktaş",
            "language": "tr",
            "description": "Kerim Kur'an"
          },
          "footnotes": [
            {
              "id": 24157,
              "text": "Övgüye ve teşekküre layık yegane varlık. Bir nimetin ve güzelliğin kaynağı ve sahibi olan gücü, övgü ve yüceltme sözleriyle anmaktır. Bu anlamıyla \"hamd\", verilen bir nimetten yararlanma veya yapılan bir yardımla feraha çıkma karşılığı olmaktan çok, o nimeti veren yaratıcının sonsuz güç ve kuvvetine duyulan hayranlık sebebiyle dile getirilen bir övgüdür.",
              "number": 1
            },
            {
              "id": 24158,
              "text": "Kafir: İnançsız, inanmayan, gerçeğin üzerini örten, gerçeği kabul etmeyen, nankör. Allah'ı ve vahyi reddeden. Küfr, İman'ın karşıtıdır.",
              "number": 2
            }
          ]
        }
      },
      ...,
      ...
    ]
  }
}
```

## GET `/surah/[surah_id]/verse/[verse_number]?author=[author_id]`

> Gets verse's detail.

Example 1: `https://api.acikkuran.com/surah/6/verse/1` Default translation

Example 2: `https://api.acikkuran.com/surah/6/verse/1?author=8` Author can be select with `author` parameter

Response body:

```json
{
  "data": {
    "id": 790,
    "surah": {
      "id": 6,
      "name": "Enam",
      "slug": "enam",
      "verse_count": 165,
      "page_number": 127,
      "name_original": "سورة الأنعام",
      "audio": {
        "mp3": "https://archive.org/download/INDIRILIS_SIRASINA_GORE_SESLI_KURAN_MEALI/55-enam.mp3",
        "duration": 2995
      }
    },
    "verse_number": 1,
    "verse": "الْحَمْدُ لِلّهِ الَّذِي خَلَقَ السَّمَاوَاتِ وَالأَرْضَ وَجَعَلَ الظُّلُمَاتِ وَالنُّورَ ثُمَّ الَّذِينَ كَفَرُواْ بِرَبِّهِم يَعْدِلُونَ",
    "page": 127,
    "juz_number": 7,
    "verse_without_vowel": "الحمد لله الذي خلق السماوات والأرض وجعل الظلمات والنور ثم الذين كفروا بربهم يعدلون",
    "transcription": "Elhamdu lillahillezi halakas semavati vel arda ve cealez zulumati ven nur, summellezine keferu bi rabbihim ya'dilun.",
    "translation": {
      "id": 181271,
      "author": {
        "id": 105,
        "name": "Erhan Aktaş",
        "description": "Kerim Kur'an",
        "language": "tr"
      },
      "text": "Hamd[1],  gökleri ve yeri yaratan,  karanlıkları ve aydınlığı var eden Allah'a özgüdür. Yine de Kafirler[2] ilahlarını Rabb'leriyle denk tutuyorlar.",
      "footnotes": [
        {
          "id": 24157,
          "text": "Övgüye ve teşekküre layık yegane varlık. Bir nimetin ve güzelliğin kaynağı ve sahibi olan gücü, övgü ve yüceltme sözleriyle anmaktır. Bu anlamıyla \"hamd\", verilen bir nimetten yararlanma veya yapılan bir yardımla feraha çıkma karşılığı olmaktan çok, o nimeti veren yaratıcının sonsuz güç ve kuvvetine duyulan hayranlık sebebiyle dile getirilen bir övgüdür.",
          "number": 1
        },
        {
          "id": 24158,
          "text": "Kafir: İnançsız, inanmayan, gerçeğin üzerini örten, gerçeği kabul etmeyen, nankör. Allah'ı ve vahyi reddeden. Küfr, İman'ın karşıtıdır.",
          "number": 2
        }
      ]
    }
  }
}
```

## GET `/surah/[surah_id]/verse/[verse_number]/translations`

> Lists all translations of this verse.

Example: `https://api.acikkuran.com/surah/6/verse/1/translations`

Response body:

```json
{
  "data": [
    {
      "id": 13410,
      "text": "Her türlü övgü, gökleri ve yeri yaratan, karanlıkları ve aydınlığı var eden Allah'a aittir. Bunca delilden sonra hakikati inkar edenler, başka güçleri Rabbleri ile denk tutarlar.",
      "author": {
        "id": 8,
        "name": "Bayraktar Bayraklı",
        "language": "tr",
        "description": "Yeni Bir Anlayışın Işığında Kur'an Meali"
      },
      "footnotes": null
    },
    {
      "id": 175035,
      "text": "Hamd (övgü), gökleri ve yeri yaratan, karanlıkları ve aydınlığı var eden Allah içindir. (Bunca delilden) sonra kâfir olanlar (hâlâ putları) Rableri ile denk tutuyorlar.[1]",
      "author": {
        "id": 107,
        "name": "Mehmet Okuyan",
        "language": "tr",
        "description": "Kur’an Meal-Tefsir"
      },
      "footnotes": [
        {
          "id": 19751,
          "text": "Burada geçen [ya‘dilûne] fiili \"adaletli davranmak\" değil, putperestlerin putlarını Yüce Allah'a denk tutmaları yani şirk koşmaları anlamındadır.",
          "number": 1
        }
      ]
    }
  ]
}
```

## GET `/surah/[surah_id]/verse/[verse_number]/words`

> Lists all words of this verse along with descriptions and root infos.

Example: `https://api.acikkuran.com/surah/6/verse/1/words`

Response body:

```json
{
  "data": [
    {
      "id": 15996,
      "sort_number": 1,
      "transcription": "el-hamdu",
      "arabic": "الْحَمْدُ",
      "turkish": "hamdolsun",
      "root": {
        "id": 3,
        "latin": "Hmd",
        "arabic": "حمد"
      }
    },
    {
      "id": 15997,
      "sort_number": 2,
      "transcription": "lillahi",
      "arabic": "لِلَّهِ",
      "turkish": "o Allah'a",
      "root": null
    }
  ]
}
```

## GET `/root/latin/[latin_chars]`

> Gets detail of this root with latin char and lists all differentiations.

Example: `https://api.acikkuran.com/root/latin/Hmd  `

Response body:

```json
{
  "data": {
    "id": 3,
    "latin": "Hmd",
    "arabic": "حمد",
    "transcription": "Ha-Mim-Dal",
    "mean": "To praise or eulogize or commend someone, speak well of someone, mention someone with approbation, approve of a thing, recompense/pay someone his due, to be praiseworthy or commendable. Verb form 8: said of heat: to burn or burn fiercely, to be vehement.",
    "diffs": [
      {
        "id": 28,
        "diff": "حَمْد",
        "count": 43
      },
      {
        "id": 30,
        "diff": "حَٰمِدُون",
        "count": 1
      },
      {
        "id": 29,
        "diff": "حَمِيد",
        "count": 17
      },
      {
        "id": 31,
        "diff": "مَّحْمُود",
        "count": 1
      },
      {
        "id": 32,
        "diff": "يُحْمَدُ",
        "count": 1
      }
    ],
    "rootchar_id": 3
  }
}
```

## GET `/root/latin/[latin_char]/verses?page=[page_number]&author=[author_id]`

> Gets verses of this root with latin char, author and page parameters and repsonse them with pagination meta.

Example: `https://api.acikkuran.com/root/latin/Hmd/verses`

Response body:

```json
{
  "links": {
    "first": "/root/latin/Hmd/verses?page=1",
    "prev": "/root/latin/Hmd/verses?page=1",
    "next": "/root/latin/Hmd/verses?page=3",
    "last": "/root/latin/Hmd/verses?page=4"
  },
  "meta": {
    "current_page": 2,
    "from": 20,
    "last_page": 4,
    "path": "/root/latin/Hmd/verses",
    "per_page": 20,
    "to": 40,
    "total": 63
  },
  "data": [
    {
      "id": 835,
      "rootdiff_id": 28,
      "root": {
        "id": 3,
        "latin": "Hmd",
        "arabic": "حمد"
      },
      "surah": {
        "id": 17,
        "name": "İsra",
        "slug": "isra",
        "verse_count": 111,
        "page_number": 281,
        "name_original": "سورة الإسراء",
        "audio": {
          "mp3": "https://archive.org/download/INDIRILIS_SIRASINA_GORE_SESLI_KURAN_MEALI/50-isra.mp3",
          "duration": 1423
        }
      },
      "verse": {
        "id": 2140,
        "page": 292,
        "surah_id": 17,
        "verse_number": 111,
        "verse": "وَقُلِ الْحَمْدُ لِلّهِ الَّذِي لَمْ يَتَّخِذْ وَلَدًا وَلَم يَكُن لَّهُ شَرِيكٌ فِي الْمُلْكِ وَلَمْ يَكُن لَّهُ وَلِيٌّ مِّنَ الذُّلَّ وَكَبِّرْهُ تَكْبِيرًا",
        "transcription": "Ve kulil hamdu lillahillezi lem yettehız veleden ve lem yekun lehu şerikun fil mulki ve lem yekun lehu veliyyun minez zulli ve kebbirhu tekbira.",
        "juz_number": 15,
        "translation": {
          "id": 182621,
          "author": {
            "id": 105,
            "name": "Erhan Aktaş",
            "description": "Kerim Kur'an",
            "language": "tr"
          },
          "text": "Ve de ki: \"Hamd[1],  çocuk edinmeyen Allah'a özgüdür. O'nun mülkte[2] ortağı yoktur. O'nun acizlikten dolayı bir veliye[3] de ihtiyacı yoktur.\" O'nu tam bir yüceltme ile yücelt.",
          "footnotes": [
            {
              "id": 25287,
              "text": "Yandaş, yardımcı, destekçi.",
              "number": 3
            },
            {
              "id": 25286,
              "text": "Egemenlikte.",
              "number": 2
            },
            {
              "id": 25285,
              "text": "Bütün övgüler.",
              "number": 1
            }
          ]
        }
      },
      "sort_number": 2,
      "arabic": "حمد",
      "transcription": "l-hamdu",
      "turkish": "hamdolsun",
      "prop_1": "isim",
      "prop_2": "",
      "prop_3": "",
      "prop_4": "",
      "prop_5": "eril",
      "prop_6": "",
      "prop_7": "merfu` isim",
      "prop_8": ""
    }
  ]
}
```

## GET `/root/[id]`

> Gets detail of this root and lists all differentiations.

Example: `https://api.acikkuran.com/root/3`

Response body:

```json
{
  "data": {
    "id": 3,
    "latin": "Hmd",
    "arabic": "حمد",
    "transcipriton": "Ha-Mim-Dal",
    "mean": "To praise or eulogize or commend someone, speak well of someone, mention someone with approbation, approve of a thing, recompense/pay someone his due, to be praiseworthy or commendable. Verb form 8: said of heat: to burn or burn fiercely, to be vehement.",
    "diffs": [
      {
        "id": 28,
        "diff": "حَمْد",
        "count": 43
      },
      {
        "id": 29,
        "diff": "حَمِيد",
        "count": 17
      },
      ...,
      ...
    ]
  }
}
```

## GET `/rootchars`

> Lists all Arabic letters.

Example: `https://api.acikkuran.com/rootchars`

Response body:

```json
{
  "data": [
    {
      "id": 1,
      "arabic": "س",
      "latin": "s"
    },
    {
      "id": 2,
      "arabic": "ر",
      "latin": "r"
    },
    {
      "id": 3,
      "arabic": "ح",
      "latin": "H"
    }
  ]
}
```

## GET `/rootchar/[id]`

> Lists all roots which begins with this letter.

Example: `https://api.acikkuran.com/rootchar/1`

Response body:

```json
{
  "data": [
    {
      "id": 1,
      "latin": "smw",
      "arabic": "سمو"
    },
    {
      "id": 32,
      "latin": "swy",
      "arabic": "سوي"
    },
    {
      "id": 36,
      "latin": "smE",
      "arabic": "سمع"
    }
  ]
}
```
