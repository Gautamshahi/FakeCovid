
<h1 id="datacollection">Data Collection</h1>
                <p> For data collection, we used the <strong>Poynter and Snopes</strong> as a
bridge to get the links to the original fact-checking website.
The steps involved in the process of data collection:</p>
<p><strong>Fact-check articles</strong> We weekly scraped the list of factchecked news mentioned at reference sources (Poynter &
Snopes) and collected the list of the fact-checked news
articles mentioned on their website. We have assigned a
unique identifier to each of them and its denoted by FCID.</p>
<p><strong>Source of articles</strong> From the list of fact-checked news
articles, we fetched the reference to the source of the
fact-checked article which was published by the Poynter
and Snopes. This is represented by article source.</p>
<p><strong>Title</strong> From the collected link, we fetched the tile of the news
article. In many cases, the title provided by the reference
provided(Poynter & Snopes) is different from the original
title given by the fact-checking website. Title provided
by the reference provide is defined by reference title and
denoted by ref title. Similarly, source title is defined source
title and represented as source title.</p>
<p><strong>Published Date</strong> We collected the published date, which
refers to the date of publication of fact-checked articles
by the fact-checking websites. It is represented by published date.</p>
<p><strong>Content of articles</strong> Once we have a source of a news
article, then we used Beautiful shop (Richardson 2007),
python-based library to crawl the HTML Document Object
Model(DOM) to gather other information like textual content, country, date of the article. It is defined by source title.</p>
<p><strong>Class</strong> The fact checking website assign a class for each
fact checked article. Each fact checking website have a set
of classes designed by them, for instance the classes may
be ’true’, ’false’, ’partially false’ meaning that the article
is true, false or partially false respectively. The articles are
then elucidated by them into one of their designed classes.
A detailed description is mentioned in table 6. This attribute
is denoted by class.</p>
<p><strong>Social media link</strong> Fake news is primarily circulated over
social media to be spread among a large number of people,
and the fact-checker provides a reference to social media
posts, so we have collected the presence of social media
on the fact-checked articles. Once we extracted the content
from the web page, we looked for the social media presence
in the news article. To check the twitter presence, we
look for keyword twitter and status in the hyperlink. For
YouTube, we look for the keywords ”youtube” and ”watch”.
For Reddit, we look for the keyword ”Reddit” and the
pattern ”reddit.com/r/” using regex. Similarly we check the
presence of Facebook and Instagram using regex pattern.
This property is denoted by SM Link.</p>
<p><strong>Fact checking website</strong> From the fact-checked references,
we also fetch the source of the article, which is the factchecking company. This property is denoted by verifiedby.</p>
<p><strong>Country</strong> We fetched the country of the articles, which tells
in which country the article was circulated. Sometimes the
same articles were circulated in several countries. In our
dataset, the maximum number of countries that an article
appeared to be circulated around was four, hence we divided
the country attribute into 4 sub attributes, namely country1,
country2,country3 and country4 to identify each country
separately.</p>
<p><strong>Category</strong> Fake news are circulated regarding several topics
for instance, origin or virus, or international response. The
category attribute has been used to denote under which
topic the article falls into. The value of the attribute has
been assigned by us after manually annotating the articles.
A detailed description of the annotations is mentioned in
section ”Data Annotation”.</p>
<p><strong>Language</strong> The fact check articles are circulated in different
countries in several languages. To identify the language
of the article we created the attribute lang which denotes
the language of the fact checked articles. The process of
language detection is discussed in section ”Data cleaning
and Prepossessing”.</p>
<p>We have collected 5182 articles circulated in 105
countries from 92 fact-checkers. Articles published were
from 04.01.2020 to 15.05.2020 in 40 languages among
which 40.8 % articles are in the English language.
</p>
<br><br>
<h1 id="dataannotation">Data Annotation</h1>
                <p>For annotation of news articles, we selected
three people, based on background knowledge and linguistic
knowledge. Data is being annotated by one annotator and the
second annotator annotates the randomly chosen news article according to the language to calculate the intercoder reliability (Lombard, Snyder-Duch, and Bracken 2002) agreement.
</p>
<br><br>
<h1 id="datacleaning">Data Cleaning, Processing and Exploration</h1>
                <p><strong>Data Cleaning:</strong> To remove unwanted information from the collected data, articles with faulty URLs, a missing title or duplicates have been excluded.</p>
				<p><strong>Data Processing:</strong> In this step, we applied the basic Natural Language Processing(NLP) preprocessing techniques to remove unwanted
information from the data like lowercase, removal of short word, tokenization etc. We performed language detection using langdetect and spelling correction using Textblob.</p>
				<p><strong>Data Exploration:</strong> We performed the exploratory analysis of the dataset regarding circulation across countries and languages, fact-checking websites, word distributions and social media links, as displayed in the images below. Find more info in the FakeCovid paper, found via the button below.</p>
		<div class="button-container">
                    <button class="button button-pill button-primary"
			    onclick="location.href='./assets/doc/FakeCovid.pdf';">
                        <strong>FakeCovid paper (Shahi & Nandini, 2020)</strong>
                    </button>
                </div>
		<br>
		<div>
					<figure style="max-width:400px;float:left;margin-right:50px">
						<img src="https://gautamshahi.github.io/FakeCovid/assets/img/factcheker.png" stye="min-widht:284" height="auto">
						<figcaption style="text-align:left;">Figure 1: Distribution of Top 10 fact-checking websites</figcaption>
					</figure>
					<figure style="max-width:400px;float:left">
						<img src="https://gautamshahi.github.io/FakeCovid/assets/img/lang_dist.png" width="200" height="auto">
						<figcaption style="text-align:left;">Figure 2: Distribution of Top 10 languages of the fact-checking articles</figcaption>
					</figure>
					<figure width="200" style="float:left">
						<img src="https://gautamshahi.github.io/FakeCovid/assets/img/wordcloud.png" width="200" height="auto">
						<figcaption style="text-align:left;">Figure 3: Wordcloud of the Top 100 words used in the dataset</figcaption>
					</figure>
			 	</div>
