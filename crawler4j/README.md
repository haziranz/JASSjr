# crawler4j

Crawler4J is an open source web crawler for java. It distributes under Apache 2.0 license. IntelliJIdea, Maven and java are required to follow below steps.
New java project can be created in IntellijIdea using maven as given in below 

1. create new java project
2.Following dependency should be added to pom.xml
        <dependencies>
            <dependency>
               <groupId>edu.uci.ics</groupId>
               <artifactId>crawler4j</artifactId>
               <version>4.4.0</version>
            </dependency>
        </dependencies>
        
3.Custom crawler class should be added by extending the WebCrawler class provided by Crawler4j framework. Two methods, “shouldVisit” and “visit” methods should be overridden to provide expected behavior for the crawler
4. Main class is created as given below to configure and start the crawler
5.Once you run the program, crawler will start to crawl web starting from the seed URL. Crawler output will be as follows,

#Crawler4j Evaluation

Crawler4j achieves politeness by using a variable called “politenessDelay”. Default value of this is set to 200 milliseconds. User can tune this according to their requirement. Crawler4j will wait at least the amount specified in “politenessDelay” between requests.

Crawler4j evaluates each fetched URL against the robots.txt file of corresponding host.

Crawler4J achieves robustness by crawling sites according to given robots.txt. It minimizes the chance of getting trapped. Also user can specify a limit for the depth of crawling from seed page. By doing so, chances of getting trapped can be reduced to a greater extent.

Crawler4j natively does not support distributed operations. But there are extended projects written based on crawler4j which support distributed operations.

Even though Crawler4j does not support distributed operations it can be scaled up by adding multiple threads.

Performance and efficiency of Crawler4j can be increased by increasing number of crawler threads and reducing politeness delay

#Focused Crawling with Crawler4j

Usually seed web page and other web pages have a lot of outgoing links. So if we allow web crawler to crawl freely, it will crawl large amount of unnecessary pages. To focus crawler to crawl only required pages, following things can be followed,

 add an appropriate filter to should visit method: in above example, crawler will not download pages with unnecessary extensions.
 set an appropriate crawl depth: in above example, crawler depth is set to one. So that crawler will only consider one level of depth from seed page for crawling.
