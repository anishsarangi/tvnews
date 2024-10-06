# Article 2 TV News

Article2TVNews allows users to find TV news clips on subjects related
to an article they are reading.  It provides methods to extract text from an
article and get tv news clips based on the article's subject.  This package is
written for the Internet Archive's WayBack Machine and its Context browser
extension. Typical usage looks something like this::

    #!/usr/bin/env python

    from article2tvnews import ArticleExtraction, NewsRecommender

    url = <news-article-url>
    html = ArticleExtraction.getHTML(url)
    article = ArticleExtraction.extract(html)
    for clip in NewsRecommender.makeRecommendations(article):
        print(clip)


## Entity Extraction
By default, NewsRecommender uses SpaCy for entity extraction. However, one can choose to use the [OpenCalais API](http://www.opencalais.com/).  First, the user must [register to get an API key](http://www.opencalais.com/opencalais-api/).  Then pass it as `calais_token` when you call `makeRecommendations()`::

    #!/usr/bin/env python

    from article2tvnews import ArticleExtraction, NewsRecommender

    url = <news-article-url>
    html = ArticleExtraction.getHTML(url)
    article = ArticleExtraction.extract(html)
    for clip in NewsRecommender.makeRecommendations(article, calais_token = <api_key>):
        print(clip)


## Possible Changes:
- Time period for videos
- extract embedded tweets (possible added weight)


## Thanks


Thanks to the wonderful people at *The Internet Archive* for giving me this
opportunity, and a special thanks to:

* Mark

* Dvd

* Vangelis

* Anish

* And of course, Brewster Kahle
