# Demo Web Crawler

## Description
This project is using **edu.uci.ics.crawler4j** internally to crawl pages.

## Setup
    git $ clone https://github.com/rushsontakke/web-crawler.git or Download project from https://github.com/rushsontakke/web-crawler
    $ cd DemoWebCrawler/
    $ mvn package

## Usage

Run:

    $ java -jar target/DemoWebCrawler-0.0.1-SNAPSHOT.jar --url="www.abc.com"

Mandatory parameter:

    -u,--url <arg>           website url
    
Optional parameters:

    -c,--crawlers <arg>      number of crawlers (1 by default)
	-e,--externalURL <arg>	 If you need external urls 
    -d,--delay <arg>         delay in ms (200 by default)
    -m,--max-pages <arg>     max pages to fetch
    -o,--output-file <arg>   output file by default sitemap.xml
    -t,--temp-dir <arg>      temporary directory
    
    
Example:

    $ java -jar target/DemoWebCrawler-0.0.1-SNAPSHOT.jar --url="https://www.vodafone.in/"


## Example output XML file format

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?><response><pageLinks><url>https://www.vodafone.in/</url><url>https://www.vodafone.in/postpaid/quick-online-bill-payment</url></pageLinks><mediaLinks><url>https://www.vodafone.in/</url><url>https://www.vodafone.in/content/dam/vap/10.png</url><url>https://www.vodafone.in/content/dam/vap/Amazon_logo_m.png</url><url>https://www.vodafone.in/content/dam/vap/BuyConnection.svg</url><url>https://www.vodafone.in/content/dam/vap/IR.svg</url><url>https://www.vodafone.in/content/dam/vap/Pay%20bill%202-01.svg</url><url>https://www.vodafone.in/content/dam/vap/Recharge.svg</url><url>https://www.vodafone.in/content/dam/vap/amazon_logo_d.png</url><url>https://www.vodafone.in/content/dam/vap/auto-pay-icon.png</url><url>https://www.vodafone.in/content/dam/vap/broadband.svg</url><url>https://www.vodafone.in/content/dam/vap/card_1_desktop.png</url><url>https://www.vodafone.in/content/dam/vap/card_1_mobile.png</url><url>https://www.vodafone.in/content/dam/vap/facebook_icon_footer.svg</url><url>https://www.vodafone.in/content/dam/vap/getSmartphone.svg</url><url>https://www.vodafone.in/content/dam/vap/getTheApp.svg</url><url>https://www.vodafone.in/content/dam/vap/get_app_icon.svg</url><url>https://www.vodafone.in/content/dam/vap/google_plus_icon_footer.svg</url><url>https://www.vodafone.in/content/dam/vap/instagram.svg</url><url>https://www.vodafone.in/content/dam/vap/mobile_my_Account.png</url><url>https://www.vodafone.in/content/dam/vap/mpesa_icon_in_small_banner.png</url><url>https://www.vodafone.in/content/dam/vap/mpesa_logo_mobile.png</url><url>https://www.vodafone.in/content/dam/vap/my_vodafone_logo_in_banner.png</url><url>https://www.vodafone.in/content/dam/vap/phon-eicon.jpg</url><url>https://www.vodafone.in/content/dam/vap/search_icon.svg</url><url>https://www.vodafone.in/content/dam/vap/twitter_icon_footer.svg</url><url>https://www.vodafone.in/content/dam/vap/user_icon.svg</url><url>https://www.vodafone.in/content/dam/vap/vodafone_logo.svg</url><url>https://www.vodafone.in/content/dam/vap/vodafone_logo_mobile.png</url><url>https://www.vodafone.in/content/dam/vap/youtube_icon_footer.svg</url><url>https://www.vodafone.in/etc/designs/vap/vodafonebase/images/FooterScroll.png</url><url>https://www.vodafone.in/etc/designs/vap/vodafonebase/images/cityLocator.svg</url><url>https://www.vodafone.in/etc/designs/vap/vodafonebase/images/close_icon.png</url><url>https://www.vodafone.in/etc/designs/vap/vodafonebase/images/hamburger_icon.png</url><url>https://www.vodafone.in/etc/designs/vap/vodafonebase/images/icn-top.png</url><url>https://www.vodafone.in/etc/designs/vap/vodafonebase/images/location_icon.svg</url></mediaLinks></response>
```

## Example console log output

    D:\Study\Workspace\MyWorkspace\DemoWebCrawler>java -jar target/DemoWebCrawler-0.0.1-SNAPSHOT.jar --url="https://www.vodafone.in/"
	Jan 14, 2019 11:22:52 AM edu.uci.ics.crawler4j.url.TLDList <init>
	INFO: Obtained 6791 TLD from packaged file tld-names.txt
	Jan 14, 2019 11:22:52 AM edu.uci.ics.crawler4j.crawler.CrawlController <init>
	INFO: Deleted contents of: tmp\frontier ( as you have configured resumable crawling to false )
	Jan 14, 2019 11:22:53 AM edu.uci.ics.crawler4j.crawler.CrawlController start
	INFO: Crawler 1 started
	Jan 14, 2019 11:22:54 AM com.demo.webcrawler.Spider visit
	INFO: visiting: https://www.vodafone.in/
	Jan 14, 2019 11:23:02 AM com.demo.webcrawler.Spider visit
	INFO: visiting: https://www.vodafone.in/postpaid/quick-online-bill-payment
	Jan 14, 2019 11:23:13 AM edu.uci.ics.crawler4j.crawler.CrawlController$1 run
	INFO: It looks like no thread is working, waiting for 10 seconds to make sure...
	Jan 14, 2019 11:23:23 AM edu.uci.ics.crawler4j.crawler.CrawlController$1 run
	INFO: No thread is working and no more URLs are in queue waiting for another 10 seconds to make sure...
	Jan 14, 2019 11:23:33 AM edu.uci.ics.crawler4j.crawler.CrawlController$1 run
	INFO: All of the crawlers are stopped. Finishing the process...
	Jan 14, 2019 11:23:33 AM edu.uci.ics.crawler4j.crawler.CrawlController$1 run
	INFO: Waiting for 10 seconds before final clean up...
	Jan 14, 2019 11:23:43 AM com.demo.webcrawler.Application saveXMLDocument
	INFO: document saved to: sitemap.xml
  