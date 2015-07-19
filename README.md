Web Scraper

Using Goutte Class, we can now easily get data with an ease.
You can check our tutorial about this Web Scraper.


<a href="http://iapdesign.com/webdev/laravel-4-webdev/superb-web-scraping-tutorials-using-laravel-4/">Web Scraping Tutorial using Laravel 4</a>


__construct() – This will used for instantiating our new classes that we want to used and others. In this part i used a simple design pattern called Dependency Injection.

getIndex() – We used this as our default rendering View for our application, which used our blade templates and some css styling.

setScraperUrl() – Setting up our url that we want to be scrape

getContents() – this will be used for getting all the returned result and send to our getIndex() method and render to our user.

startScraper() – Handling web scraping logic, filtering, and returning array of results that will be processed by our getIndex() for rendering.

howTo::

Use.....
Go to our getIndex() method and lets add our View and setup our url that will be scrape.

For this demo, i used code.tutplus.com to get the first page of data. i check the defined classes and attributes of the html so i can get the exact data.

Goutte Class used filter() method that gets html data attributes that based on DomCrawler used by symfony that manipulates html/xml components and easy extraction of data. Goutte Class can also act as a human that can simulates user click, can submit form etc.

Right now, im using CssSelector same as jquery selection of classes, but you can used also filterXPath() that works also for HTML and XML Dom Manipulation.

Example you want to select all tags inside your body tag. you can do like this.

$crawler = $this->crawler->filter('body > p');

////////////////////////////////////////////////////////////////

Other thoughts.......
Alright, works like a charm…
Now I do get hardcore and I scrap a website that has 100s of links.
I get a timeout from php after 30sec of execution (default)
Beside increasing the time of php execution in php.ini, do you have any cleaner way to still output the page but prevent the timeout ??

???????????????????????????????????????????????????????????????

Well, the most cleaner way is to process it in the background.. If you’re running this scrapping in browser, It will hit the php timeout or it will make your browser crash..

If you know how to use laravel queue with the used of Beanstalkd for fast work queue. I’ve been doing that all time…

Even though its running in the background, functionality wise make sure you put a timeout for each run, Example for the first 50 scrape links you should put a delay then run the next 50 again.. so on and so fort… In that case your IP address will not be banned for that website.. thats an example only.. :)


:):):):):):):):):):):):):):):):):):):):):):):):):):):):):):):):)


