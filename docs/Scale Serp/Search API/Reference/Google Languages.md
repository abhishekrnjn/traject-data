Google Languages
----------------

Scale SERP allows you to display query results in any worldwide language using the`hl`[search parameter](/docs/search-api/searches/google/search). For example, to search for the phrase`pizza`and return results in`French`the Scale SERP search request would be:



**Localized Results**  
You should use the`hl (language)`parameter in combination with the `google_domain` and `gl` (country) [parameters](/docs/search-api/searches/google/search) to achieve correctly localized results. Alternatively use the `location` [parameter](/docs/locations-api) and Scale SERP will set the`google_domain`,`gl`and`hl`parameters automatically to match the given location.### Download Languages

As well as searching in the list below you can download a full list of all of the Scale SERP Google result languages in JSON format here:



[scaleserp\_google\_languages.json (10kb)](https://assets.api-cdn.com/scaleserp/scaleserp_google_languages.json)### List Languages

The following values are valid for the`hl`[search parameter](/docs/search-api/searches/google/search).

Language CodeNameafAfrikaansakAkansqAlbanianamAmharicarArabichyArmenianazAzerbaijanieuBasquebeBelarusianbemBembabnBengalibhBiharibsBosnianbrBretonbgBulgariankmCambodiancaCatalanchrCherokeenyChichewazh-cnChinese (Simplified)zh-twChinese (Traditional)coCorsicanhrCroatiancsCzechdaDanishnlDutchenEnglisheoEsperantoetEstonianeeEwefoFaroesetlFilipinofiFinnishfrFrenchfyFrisiangaaGaglGaliciankaGeorgiandeGermanelGreekgnGuaraniguGujaratihtHaitian CreolehaHausahawHawaiianheHebrewiwHebrewhiHindihuHungarianisIcelandicigIgboidIndonesianiaInterlinguagaIrishitItalianjaJapanesejwJavaneseknKannadakkKazakhrwKinyarwandarnKirundikgKongokoKoreankriKrio (Sierra Leone)kuKurdishckbKurdish (Soranî)kyKyrgyzloLaothianlaLatinlvLatvianlnLingalaltLithuanianlozLozilgLugandaachLuomkMacedonianmgMalagasymsMalaymlMalayalammtMaltesemiMaorimrMarathimfeMauritian CreolemoMoldavianmnMongoliansr-MEMontenegrinneNepalipcmNigerian PidginnsoNorthern SothonoNorwegiannnNorwegian (Nynorsk)ocOccitanorOriyaomOromopsPashtofaPersianplPolishptPortuguesept-brPortuguese (Brazil)pt-ptPortuguese (Portugal)paPunjabiquQuechuaroRomanianrmRomanshnynRunyakitararuRussiangdScots GaelicsrSerbianshSerbo-CroatianstSesothotnSetswanacrsSeychellois CreolesnShonasdSindhisiSinhaleseskSlovakslSloveniansoSomaliesSpanishes-419Spanish (Latin American)suSundaneseswSwahilisvSwedishtgTajiktaTamilttTatarteTeluguthThaitiTigrinyatoTongaluaTshilubatumTumbukatrTurkishtkTurkmentwTwiugUighurukUkrainianurUrduuzUzbekviVietnamesecyWelshwoWolofxhXhosayiYiddishyoYorubazuZulu