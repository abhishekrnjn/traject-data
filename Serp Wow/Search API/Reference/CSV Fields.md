CSV Fields Reference
--------------------

SerpWow can return data in CSV format by specifying the `output=csv` request parameter. When setting `output=csv` the `csv_fields`  parameter determines the fields to include in the CSV result.

CSV fields should be specified as a comma seperated list of field names, with **nested fields being expressed in dot notation**.

Here's an example of the `csv_fields` parameter:

`csv_fields=`Below is a full list of all of the supported CSV Fields shown under their group.

| Field Group | Fields in Group |
| --- | --- |
| search | qdevicelocationlocation\_autogoogle\_domainglhllrcrcustom\_idtime\_periodtime\_period\_mintime\_period\_maxshow\_duplicatesflatten\_resultsnews\_typenfprsearch\_typefiltersafestartpagemax\_pagenumamazon\_domainebay\_domainproduct\_iddata\_iddata\_cidcategory\_idtopic\_idnext\_page\_tokenautocomplete\_search\_index |
| search\_information | total\_resultstime\_taken\_displayedquery\_displayeddetected\_locationshowing\_results\_fordid\_you\_meanoriginal\_query\_yields\_zero\_results |
| request\_info | successcredits\_usedcredits\_remainingmessage |
| pagination | currentnextapi\_pagination.nextnext\_page\_token |
| search\_metadata | idengine\_urlcreated\_atprocessed\_attotal\_time\_takenhtml\_urljson\_url |
| organic\_results | positiontitletypesourceblock\_positionimagelinkdisplayed\_linkdomainsnippetcached\_page\_linkrelated\_page\_linksnippet\_matchedprerenderdatedate\_utcfaq.questionfaq.answersitelinks.inline.linksitelinks.inline.titlethumbnails.imagerich\_snippet.top.detected\_extensions.pricerich\_snippet.top.detected\_extensions.symbolrich\_snippet.top.detected\_extensions.in\_stockrich\_snippet.top.detected\_extensions.ratingrich\_snippet.top.detected\_extensions.reviewsrich\_snippet.top.detected\_extensions.currency.coderich\_snippet.top.detected\_extensions.currency.namerich\_snippet.top.detected\_extensions.currency.symbolrich\_snippet.top.attributes\_flatpage |
| top\_stories | block\_positiontitlelinksourcedatedate\_utcthumbnailvideolive |
| ads | positionblock\_positiontitlelinkdomaintracking\_linkdisplayed\_linkdescription |
| autocomplete\_results | valuevalue\_formatted |
| inline\_podcasts | titlepodcastdatedurationlink |
| inline\_images | linkimagesource |
| inline\_tweets | linkstatus\_linktitlesnippetdate |
| inline\_videos | titlelinklengthsourcedate |
| inline\_shopping | linktitlepricemerchantfeed\_namefeed\_linkpositionratingreviewsblock\_positionis\_single\_productimagevisible\_initially |
| image\_results | positiontitlewidthheightimageimage\_typelinksource.linksource.namedescriptionratingreviewsbrandin\_stock |
| news\_results | positiontitledomainlinksourcedatedate\_utcsnippetpage |
| video\_results | positiontitledomainlinkdisplayed\_linkdatedate\_utcsnippetlength |
| places\_results | positiondata\_iddata\_cidtitlelinksponsoredsnippetaddressphoneratingreviewsunclaimedcategorygps\_coordinates.latitudegps\_coordinates.longitudepermanently\_closedpage |
| place\_reviews\_results | sourcebodyratingsource\_linksource\_imagesource\_review\_countdatedate\_utcpositionowner\_reply.bodyowner\_reply.dateowner\_reply.date\_utc |
| place\_photos\_results | thumbnailimageuser.linkuser.textuser.name |
| place\_products\_results | namepricelinkimageposition |
| place\_details | titletypecategorywebsitedescriptionratingreviewsaddressphone |
| place\_posts\_results | imagelinkdatetitleposition |
| shopping\_results | positiontitlelinkpriceprice\_rawmerchantsnippetratingreviewspageidimagehas\_compare\_pricesmerchant\_ratingsmerchant\_positive\_rating\_percentis\_carouselcarousel\_positionmerchant\_idgroup\_header |
| local\_results | positionlinkaddressblock\_positiongps\_coordinates.latitudegps\_coordinates.longitudetitleimageratingreviewstypephonephone |
| local\_map | linkgps\_coordinates.latitudegps\_coordinates.longitudegps\_coordinates.altitudeimage |
| knowledge\_graph | titletypephonepermanently\_closedwebsitereviewsratingaddressopening\_hoursdescriptionsource.namesource.linkgps\_coordinatesbusiness\_availability\_modesbusyness\_hourscategorypricepeople\_also\_search\_formenuorder\_foodreservations |
| related\_questions | questionanswersource.linksource.displayed\_linksource.titlesearch.linksearch.title |
| related\_searches | querylink |
| answer\_box | answers.typeanswers.categoryanswers.answeranswers.source.linkanswers.source.displayed\_linkanswers.source.title |
| amazon\_results | positiontitlelinkratingratings\_totalasinsponsoredprice.valueprice.currencyprice.symbolprice.rawimageis\_primepage |
| ebay\_results | positiontitlelinkratingratings\_totalepidsponsoredprice.valueprice.currencyprice.symbolprice.rawimagepage |
| trends\_interest\_over\_time | trends\_interest\_over\_time.data.date\_utctrends\_interest\_over\_time.data.date\_formattedtrends\_interest\_over\_time.data.values.keywordtrends\_interest\_over\_time.data.values.has\_valuetrends\_interest\_over\_time.data.values.valuetrends\_interest\_over\_time.data.values.value\_formatted |
| trends\_interest\_by\_subregion | trends\_interest\_by\_subregion.geotrends\_interest\_by\_subregion.nametrends\_interest\_by\_subregion.values.keywordtrends\_interest\_by\_subregion.values.has\_valuetrends\_interest\_by\_subregion.values.valuetrends\_interest\_by\_subregion.values.value\_formatted |
| related\_queries | related\_queries.keywordrelated\_queries.top\_queries.positionrelated\_queries.top\_queries.queryrelated\_queries.top\_queries.valuerelated\_queries.top\_queries.value\_formattedrelated\_queries.top\_queries.linkrelated\_queries.rising\_queries.positionrelated\_queries.rising\_queries.queryrelated\_queries.rising\_queries.valuerelated\_queries.rising\_queries.value\_formattedrelated\_queries.rising\_queries.link |
| related\_topics | related\_topics.keywordrelated\_topics.top\_topics.positionrelated\_topics.top\_topics.topic\_titlerelated\_topics.top\_topics.topic\_typerelated\_topics.top\_topics.topic\_idrelated\_topics.top\_topics.valuerelated\_topics.top\_topics.value\_formattedrelated\_topics.top\_topics.linkrelated\_topics.rising\_topics.positionrelated\_topics.rising\_topics.queryrelated\_topics.rising\_topics.valuerelated\_topics.rising\_topics.value\_formattedrelated\_topics.rising\_topics.link |
| product\_results | product\_idtitleratingreviewsdescriptionprimary\_imagespecifications.namespecifications.valuesellers\_online.positionsellers\_online.merchantsellers\_online.linksellers\_online.merchant\_positive\_rating\_percentagesellers\_online.merchant\_reviewssellers\_online.base\_pricesellers\_online.shipping\_pricesellers\_online.tax\_pricesellers\_online.total\_price |
| scholar\_results | scholar\_results.positionscholar\_results.titlescholar\_results.linkscholar\_results.domainscholar\_results.displayed\_linkscholar\_results.snippet |
