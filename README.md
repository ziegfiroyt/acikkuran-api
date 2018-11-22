

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
        "slug": "fatiha",
        "verse_count": 7
      },
      {
        "id": 2,
        "name": "Bakara",
        "slug": "bakara",
        "verse_count": 286
      }
    ]
}
```
## GET `/surah/[surah_id]`

> Gets surah's detail and lists verses of this surah.

Example: `https://api.acikkuran.com/surah/6`

Response body:

```json
{
  "data": {
    "id": 6,
    "name": "Enam",
    "slug": "enam",
    "verse_count": 165,
    "audio": {
      "mp3": "https://archive.org/download/INDIRILIS_SIRASINA_GORE_SESLI_KURAN_MEALI/55-enam.mp3",
      "duration": 2995
    },
    "verses": [
      {
        "id": 790,
        "surah_id": 6,
        "verse_number": 1,
        "verse": "الْحَمْدُ لِلّهِ الَّذِي خَلَقَ السَّمَاوَاتِ وَالأَرْضَ وَجَعَلَ الظُّلُمَاتِ وَالنُّورَ ثُمَّ الَّذِينَ كَفَرُواْ بِرَبِّهِم يَعْدِلُونَ",
        "transcription": "Elhamdu lillahillezi halakas semavati vel arda ve cealez zulumati ven nur, summellezine keferu bi rabbihim ya'dilun.",
        "translation": {
          "id": 133504,
          "author": {
            "id": 50,
            "name": "Erhan Aktaş",
            "description": "Kerim Kur'an",
            "language": "tr"
          },
          "text": "Hamd[1], gökleri ve yeri yaratan, karanlıkları ve aydınlığı var eden Allah'a özgüdür. Gerçeği yalanlayan nankörler ilahlarını Rabb'leriyle denk tutuyorlar.",
          "footnotes": [
            {
              "id": 965,
              "number": 1,
              "text": "Yüce, Güçlü ve Övgüye Değer Yegane Varlık."
            }
          ]
        }
      }
    ]
  }
}
```
    
## GET `/surah/[surah_id]/verse/[verse_number]`

> Gets verse's detail.

Example: `https://api.acikkuran.com/surah/6/verse/1`

Response body:

```json
{
  "data": {
    "id": 790,
    "surah_id": 6,
    "verse_number": 1,
    "char_count": 69,
    "word_count": 14,
    "total_abjad": 7057,
    "words_abjad": "(83)(65)(741)(730)(539)(1038)(109)(1402)(293)(540)(791)(307)(249)(170)",
    "word_chars_abjad": "(1 30 8 40 4)(30 30 5)(1 30 700 10)(600 30 100)(1 30 60 40 1 6 1 400)(6 1 30 1 200 800)(6 3 70 30)(1 30 900 30 40 1 400)(6 1 30 50 6 200)(500 40)(1 30 700 10 50)(20 80 200 6 1)(2 200 2 5 40)(10 70 4 30 6 50)",
    "verse": "الْحَمْدُ لِلّهِ الَّذِي خَلَقَ السَّمَاوَاتِ وَالأَرْضَ وَجَعَلَ الظُّلُمَاتِ وَالنُّورَ ثُمَّ الَّذِينَ كَفَرُواْ بِرَبِّهِم يَعْدِلُونَ",
    "verse_without_vowel": "الحمد لله الذي خلق السماوات والأرض وجعل الظلمات والنور ثم الذين كفروا بربهم يعدلون",
    "transcription": "Elhamdu lillahillezi halakas semavati vel arda ve cealez zulumati ven nur, summellezine keferu bi rabbihim ya'dilun.",
    "translation": {
      "id": 133504,
      "author": {
        "id": 50,
        "name": "Erhan Aktaş",
        "description": "Kerim Kur'an",
        "language": "tr"
      },
      "text": "Hamd[1], gökleri ve yeri yaratan, karanlıkları ve aydınlığı var eden Allah'a özgüdür. Gerçeği yalanlayan nankörler ilahlarını Rabb'leriyle denk tutuyorlar.",
      "footnotes": [
        {
          "id": 965,
          "number": 1,
          "text": "Yüce, Güçlü ve Övgüye Değer Yegane Varlık."
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
      "author": {
        "id": 8,
        "name": "Bayraktar Bayraklı",
        "description": "Yeni Bir Anlayışın Işığında Kur'an Meali",
        "language": "tr"
      },
      "text": "Her türlü övgü, gökleri ve yeri yaratan, karanlıkları ve aydınlığı var eden Allah'a aittir. Bunca delilden sonra hakikati inkar edenler, başka güçleri Rabbleri ile denk tutarlar.",
      "footnotes": null
    },
    {
      "id": 13412,
      "author": {
        "id": 13,
        "name": "Edip Yüksel",
        "description": "Mesaj: Kuran Çevirisi",
        "language": "tr"
      },
      "text": "Övgü, gökleri ve yeri yaratan, karanlığı ve ışığı vareden ALLAH'a yaraşır. Buna rağmen, inkarcılar Rab'lerini başkalarıyla denk tutuyor.",
      "footnotes": null
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
      }
    ]
  }
}
```

## GET `/rootdiff/[id]`

> Lists all verses related to this root differentiation.

Example: `https://api.acikkuran.com/rootdiff/28`

Response body:

```json
{
  "data": {
    "id": 28,
    "diff": "حَمْد",
    "count": 43,
    "verse_words": [
      {
        "id": 823,
        "surah_id": 1,
        "verse_number": 2,
        "sort_number": 1,
        "arabic": "الْحَمْدُ",
        "transcription": "el-hamdu",
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
