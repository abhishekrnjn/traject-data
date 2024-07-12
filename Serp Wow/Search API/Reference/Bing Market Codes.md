Bing Market Codes
-----------------

SerpWow allows you to query Bing using any [Bing-supported market worldwide](https://docs.microsoft.com/en-gb/rest/api/cognitiveservices-bingsearch/bing-custom-search-api-v7-reference#market-codes) using the`market_code`[search parameter](/docs/search-api/searches/bing/search). For example, to search for the phrase`pizza`using the `English - United States` market the SerpWow search request would be:

  
:::hint



**Bing Market Codes**  
The Bing `market_code`is the locale & country the user is making the request from. The market code is expressed in the form `language-country`. For example `en-US` for English, United States. See the  [Bing docs](https://docs.microsoft.com/en-gb/rest/api/cognitiveservices-bingsearch/bing-custom-search-api-v7-reference#market-codes) for more info.  
  
We recommend you always specify `market_code` as it helps Bing display results in the context of the correct market.  
  
This parameter and the `country_code` query parameter are mutually exclusive and cannot be used in the same request.  
:::

### Bing Market Codes

The following values are valid for the`market_code`[search parameter](/docs/search-api/searches/bing/search).

| Market Code | Country Name | Language |
| --- | --- | --- |
| prs-AF | Afghanistan | |
| sq-AL | Albania | |
| ar-DZ | Algeria | |
| en-AS | American Samoa | |
| ca-AD | Andorra | |
| pt-AO | Angola | |
| en-AI | Anguilla | |
| en-AG | Antigua and Barbuda | |
| es-AR | Argentina | |
| hy-AM | Armenia | |
| nl-AW | Aruba | |
| en-AU | Australia | |
| de-AT | Austria | |
| az-LATN | Azerbaijan | |
| en-BS | Bahamas | |
| ar-BH | Bahrain | |
| bn-BD | Bangladesh | |
| en-BB | Barbados | |
| be-BY | Belarus | |
| nl-BE | Belgium - Dutch | |
| fr-BE | Belgium - French | |
| en-BZ | Belize | |
| fr-BJ | Benin | |
| en-BM | Bermuda | |
| bo-BT | Bhutan | |
| es-BO | Bolivia | |
| bs-LATN | Bosnia and Herzegovina | |
| en-BW | Botswana | |
| pt-BR | Brazil | |
| en-VG | British Virgin Islands | |
| ms-BN | Brunei | |
| bg-BG | Bulgaria | |
| fr-BF | Burkina Faso | |
| en-BI | Burundi | |
| pt-CV | Cabo Verde | |
| km-KH | Cambodia | |
| en-CM | Cameroon | |
| en-CA | Canada - English | |
| fr-CA | Canada - French | |
| en-KY | Cayman Islands | |
| fr-CF | Central African Republic | |
| fr-TD | Chad | |
| es-CL | Chile | |
| zh-CN | China | |
| en-CX | Christmas Island | |
| en-CC | Cocos (Keeling) Islands | |
| es-CO | Colombia | |
| fr-KM | Comoros | |
| fr-CG | Congo | |
| fr-CD | Congo (DRC) | |
| en-CK | Cook Islands | |
| es-CR | Costa Rica | |
| hr-HR | Croatia | |
| nl-CW | Curaçao | |
| en-CY | Cyprus | |
| cs-CZ | Czechia | |
| fr-CI | Côte d’Ivoire | |
| en-DK | Denmark | |
| fr-DJ | Djibouti | |
| en-DM | Dominica | |
| es-DO | Dominican Republic | |
| es-EC | Ecuador | |
| ar-EG | Egypt | |
| es-SV | El Salvador | |
| es-GQ | Equatorial Guinea | |
| en-ER | Eritrea | |
| et-EE | Estonia | |
| en-SZ | Eswatini | |
| am-ET | Ethiopia | |
| en-FK | Falkland Islands | |
| fo-FO | Faroe Islands | |
| en-FJ | Fiji | |
| en-FI | Finland | |
| fr-FR | France | |
| fr-GF | French Guiana | |
| fr-PF | French Polynesia | |
| fr-GA | Gabon | |
| en-GM | Gambia | |
| ka-GE | Georgia | |
| de-DE | Germany | |
| en-GH | Ghana | |
| en-GI | Gibraltar | |
| el-GR | Greece | |
| kl-GL | Greenland | |
| en-GD | Grenada | |
| fr-GP | Guadeloupe | |
| en-GU | Guam | |
| es-GT | Guatemala | |
| en-GG | Guernsey | |
| fr-GN | Guinea | |
| pt-GW | Guinea-Bissau | |
| en-GY | Guyana | |
| fr-HT | Haiti | |
| es-HN | Honduras | |
| en-HK | Hong Kong SAR | |
| hu-HU | Hungary | |
| is-IS | Iceland | |
| en-IN | India | |
| en-ID | Indonesia | |
| fa-IR | Iran | |
| ar-IQ | Iraq | |
| en-IE | Ireland | |
| en-IL | Israel | |
| it-IT | Italy | |
| en-JM | Jamaica | |
| ja-JP | Japan | |
| en-JE | Jersey | |
| ar-JO | Jordan | |
| kk-KZ | Kazakhstan | |
| sw-KE | Kenya | |
| en-KI | Kiribati | |
| ko-KR | Korea | |
| ar-KW | Kuwait | |
| ky-KG | Kyrgyzstan | |
| lo-LA | Laos | |
| lv-LV | Latvia | |
| ar-LB | Lebanon | |
| en-LS | Lesotho | |
| en-LR | Liberia | |
| ar-LY | Libya | |
| de-LI | Liechtenstein | |
| lt-LT | Lithuania | |
| fr-LU | Luxembourg | |
| en-MO | Macao SAR | |
| fr-MG | Madagascar | |
| en-MW | Malawi | |
| en-MY | Malaysia | |
| dv-MV | Maldives | |
| fr-ML | Mali | |
| mt-MT | Malta | |
| en-MH | Marshall Islands | |
| fr-MQ | Martinique | |
| ar-MR | Mauritania | |
| en-MU | Mauritius | |
| fr-YT | Mayotte | |
| es-MX | Mexico | |
| en-FM | Micronesia | |
| ro-MD | Moldova | |
| fr-MC | Monaco | |
| mn-MN | Mongolia | |
| sr-ME | Montenegro | |
| en-MS | Montserrat | |
| ar-MA | Morocco | |
| pt-MZ | Mozambique | |
| en-NA | Namibia | |
| en-NR | Nauru | |
| ne-NP | Nepal | |
| nl-NL | Netherlands | |
| fr-NC | New Caledonia | |
| en-NZ | New Zealand | |
| es-NI | Nicaragua | |
| fr-NE | Niger | |
| en-NG | Nigeria | |
| en-NU | Niue | |
| en-NF | Norfolk Island | |
| mk-MK | North Macedonia | |
| en-MP | Northern Mariana Islands | |
| nb-NO | Norway | |
| ar-OM | Oman | |
| en-PK | Pakistan | |
| en-PW | Palau | |
| ar-PS | Palestinian Authority | |
| es-PA | Panama | |
| en-PG | Papua New Guinea | |
| es-PY | Paraguay | |
| es-PE | Peru | |
| en-PH | Philippines | |
| en-PN | Pitcairn Islands | |
| pl-PL | Poland | |
| pt-PT | Portugal | |
| es-PR | Puerto Rico | |
| ar-QA | Qatar | |
| ro-RO | Romania | |
| ru-RU | Russia | |
| rw-RW | Rwanda | |
| fr-RE | Réunion | |
| fr-BL | Saint Barthélemy | |
| en-KN | Saint Kitts and Nevis | |
| en-LC | Saint Lucia | |
| fr-MF | Saint Martin | |
| fr-PM | Saint Pierre and Miquelon | |
| en-VC | Saint Vincent and the Grenadines | |
| en-WS | Samoa | |
| it-SM | San Marino | |
| ar-SA | Saudi Arabia | |
| fr-SN | Senegal | |
| sr-latn-rs | Serbia | |
| sr-LATN | Serbia | |
| en-SC | Seychelles | |
| en-SL | Sierra Leone | |
| en-SG | Singapore | |
| nl-SX | Sint Maarten | |
| sk-SK | Slovakia | |
| sl-SI | Slovenia | |
| en-SB | Solomon Islands | |
| so-SO | Somalia | |
| en-ZA | South Africa | |
| en-SS | South Sudan | |
| es-ES | Spain | |
| si-LK | Sri Lanka | |
| en-SH | St Helena, Ascension, Tristan da Cunha | |
| en-SD | Sudan | |
| nl-SR | Suriname | |
| sv-SE | Sweden | |
| fr-CH | Switzerland - French | |
| de-CH | Switzerland - German | |
| ar-SY | Syria | |
| pt-ST | São Tomé and Príncipe | |
| zh-TW | Taiwan | |
| tg-CYRL | Tajikistan | |
| en-TZ | Tanzania | |
| th-TH | Thailand | |
| fr-TG | Togo | |
| en-TK | Tokelau | |
| en-TO | Tonga | |
| en-TT | Trinidad and Tobago | |
| ar-TN | Tunisia | |
| tr-TR | Turkey | |
| tk-TM | Turkmenistan | |
| en-TC | Turks and Caicos Islands | |
| en-TV | Tuvalu | |
| en-VI | U.S. Virgin Islands | |
| en-UG | Uganda | |
| uk-UA | Ukraine | |
| ar-AE | United Arab Emirates | |
| en-GB | United Kingdom | |
| en-US | United States - English | |
| es-US | United States - Spanish | |
| es-UY | Uruguay | |
| uz-LATN | Uzbekistan | |
| en-VU | Vanuatu | |
| it-VA | Vatican City | |
| es-VE | Venezuela | |
| vi-VN | Vietnam | |
| fr-WF | Wallis and Futuna | |
| ar-YE | Yemen | |
| en-ZM | Zambia | |
| en-ZW | Zimbabwe | |
