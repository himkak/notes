# Web Crawler

## Functional Requirements
**What does web crawler do**
1) Picks a/multiple link/s, called a seed url
2) Gets the content by hitting the URL
3) Separates the content into 2 parts : text, links
4) Stores the content for searching operations [search functionality out of scope of web crawler]
5) Checks if the new found links need to be crawled, does some filtering, on different criteria
	- Prevent duplicate url re-crawling
	- prevent storing the page with same content but separate URL
6) Crawls the new found links

**Uses of Web Crawler**
- Search Engine
- Copy write violation detection
- Web Malware detection
- 

## NFR
- 

## Estimation
Assumption
- 900M registered websites in the internet
- 60% are functional : 500M
- Every page has link to 100 internal pages : Total : 500M * 100 = 50B pages
- Per page size : 120 kb


**Database**
50B*120kb = 6E10 kb= 60TB

**Bandwidth**

## Solution 1

![Solution1](https://github.com/himkak/notes/blob/master/SystemDesign/WebCrawler/webCrawler_sol1.jpg)

## Issues in solution 1
- Single queue, single point of failure
- DNS resolving: This minor operation, when crawling on a large scale adds up to a big bottleneck. If not tackled, your system might spend more time on waiting to resolve domain names than on fetching and parsing. It is advisable to maintain local caches to avoid repeated requests.
- Politeness: Every site has different politeness requirements and ignoring might lead to IP blocks. Expect mails from web admins! [5] . You need to cache the robot.txt files for every domain and follow the rules to avoid getting blocked. Also sites usually have time-gap requirements and this means slowing the fetching rate. If you system is distributed, better to aggregate all requests pertaining to a domain on the same node.
- Adversaries: Don't expect the web world to be nice to your bot!. There are many crawler traps, spam sites and cloaked content. Crawler traps have large automated URLS with potential loops which leads to the crawler getting struck there. You need to smartly classify valid domains from spam domains. Domain reputation from user input could be one such. There are other redundant web content (some unintentional) too.
- Seed and Content selection: You need to come up with a good set of seed domains and it is desirable to have some mechanism to rank domains/URL based on content for effective prioritisation.
- Freshness/Coverage dilemma: Some websites like wikipedia/news sites are frequently updated and requires you to update your crawled content too. You need to come up with a strategy to roughly estimate the crawl schedule for each domain. You also need to wisely balance covering new domain and updating covered domains.
- Deep crawling: This is the most challenging one and even internet giants like Google are still solving. The web content hidden behind HTML forms are of several magnitude larger than link based crawlable content on the web. You need to come up a smart query generator apt for the particular HTML form and also a size estimator for the underlying data that is extracted.
- Focussed crawling: If your target content is narrower than the www, then you need to predict domain relevance based on your interests. This ensures higher content quality and lower computation/storage overhead. Solution ranges from simple whitelisting to advanced classifiers.


## References
- https://www.quora.com/How-can-I-build-a-web-crawler-from-scratch-What-language-or-framework-would-you-recommend
