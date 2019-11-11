# rusty_batteries
A repo for the Rusty Batteries project at CTC17. 

The aim of this project is to help citizens better understand the best route for disposal of household waste  items - and guide them to the nearest facility for that. 

Early tests of the Aberdeen City Council [Website](https://www.aberdeencity.gov.uk) showed that it was impossible to find even simple terms such as 'batteries' or 'light bulbs' when trying to work out how to dispose of these responsibly. 

========================================
![Search for batteries](https://github.com/CodeTheCity/rusty_batteries/blob/master/images/Screenshot%202019-11-09%20at%2012.47.40.png)
_Screenshot of Aberdeen City Council Website_
============================================
## Functionality

We aim to develop a website or app that someone can use to say: 
* I am _here_
* I have an _item_
* What do I do with it? 

It should offer guidance: 
* Re-use it (including creative uses)
* Re-cycle it at this local facility
* Phone this service to have it picked up
* Put it in your brown / green / black bin etc.

## Useful resources
We've put useful links in [this file](links.md)

## Blog post
We've turned much of the following into a blog post, with more of a call to action. Read it on the [Code The City website](https://codethecity.org/2019/11/10/reuse-recycle/)

## Initial research
There are some apps and services that do most of what we are trying to do. For example [iRecycle - Iphone and Android](https://earth911.com/irecycle/) is a nice app for Android and iOS that would work were it not for US only. 

We couldn't find somthing for Scotland that worked as an app.

### Recycle For Scotland
The website [Recycle For Scotland](http://www.recycleforscotland.com/) is, on the face of it a useful means to identify what to do with a piece of domestic waste. 

BUT ...... it doesn't work as well as it could, and the content, and data behind it have no clear licence to permit reuse by others. 

#### The Issues
Searching the site, or navigating by the menus, for [Electrical Items](http://www.recycleforscotland.com/what-to-do-with/electrical-items) results in a page that is headed "This content was archived on 13th August 2018" - hardly inspiring confidence. 

Searching for what to do with batteries in Aberdeen results in a list of shops, at least one of which, closed down about 18 months ago. 

The main issue, however, is that there is no clear licence regarding reuse of the website's content. The site appears to be a rebadged version of [Recycle Now](https://www.recyclenow.com/), built for [Zero Waste Scotland (ZWS)](https://www.zerowastescotland.org.uk/content/terms-conditions).  According to ZWS's [Terms and Conditions](https://www.zerowastescotland.org.uk/content/terms-conditions) on their own site, you can't (re)use any materials from that site. 

------------------------------------------
![ZWS T&Cs](https://github.com/CodeTheCity/rusty_batteries/blob/master/images/Screenshot%202019-11-09%20at%2013.20.13.png)
_Screenshot of Zero Waste Scotland Website_

------------------------------------------

ZWS are [publicly funded[(https://www.zerowastescotland.org.uk/content/who-we-are)] by the Scottish Government and the European Regional Development Fund - all public money.

------------------------------------------
![ZWS funding](https://github.com/CodeTheCity/rusty_batteries/blob/master/images/Screenshot%202019-11-09%20at%2013.21.17.png)
_Screenshot of Zero Waste Scotland Website_

------------------------------------------
We argue that any website operated by a government agency, or department, or NDPB, should automatically be licensed under the [Open Government Licence](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/) or OGL. And any data behind that site should be licenced as Open Data so that others could reuse the data. 

The Scottish Government's own website is [fully licenced](https://www.gov.scot/crown-copyright/) under OGL. 

Changing the licening of Recycle For Scotland, making its' code open source, and making its data open would have many benefits: 
* it could be improved on by anyone
* the data could be repurposed in new applications
* errors could be corrected by a larger group than a single company maintaining it. 

## Some other outputs 
We were able to use a combination of Google Sheet's "importHTML()" function, Open Refine and some manual hacking to get near to what open data for Aberdeen recycling should look like. I will write another blog post on the process. 

Note: with no open data about recycling, and no Open Government Licence in place for the Aberdeen City Website content this does, on the face of it, contravene the terms of their terms of use. I would be delighted to have a public debate about that. 

Here are the two examples of turning closed data into open (almost well-formed data) which took less than two hours in total including adding geo-referencing: 

### Recycling Points
* [Original page](https://www.aberdeencity.gov.uk/services/bins-and-recycling/recycling-points)
* [Scraped data](https://github.com/CodeTheCity/rusty_batteries/blob/master/data/Aberdeen_Recycling_Points.tsv)
* [Enhanced data](https://github.com/CodeTheCity/rusty_batteries/blob/master/data/Enhanced_Aberdeen_Recycling_Points.csv)

### Recycling Centres
* [Original page](https://www.aberdeencity.gov.uk/services/bins-and-recycling/find-your-nearest-recycling-centre)
* [Scraped data](https://github.com/CodeTheCity/rusty_batteries/blob/master/data/Aberdeen_Recycling_Centres.tsv)
* [Enhanced data](https://github.com/CodeTheCity/rusty_batteries/blob/master/data/Enhanced_Aberdeen_Recycling_Centres.csv)

The enhanced versions of these flat files come close to providing something useful on which to build new apps and services. We can even pull the CSV's and map them in QGIS using open streetmap as a background - which takes all of five minutes. 

------------------------------
![A map of all recycling centres and points](https://github.com/CodeTheCity/rusty_batteries/blob/master/images/Screenshot 2019-11-10 at 14.16.20)
_A map of all recylcing centres and points_

-------------------------------- 

## Next Steps?
This was a hack weekend - testing what we could do to improve access to recycling information in two days, much of which is taken up in research. 

We have two files of data which contain not only the addresses, but also the geo-referencing co-ordinated of all facilities in the city. It also breaks down in a structured format all of the items that can be processed at at each facility. It does't yet deal with opening hours which are still largely a big text blob. 

We need to refine these text files and then work on building an interface to use them - as a web application most likely. 

## Addendum
When I posted a link to the blogpost on linked in I had some feedback along the lines of "people will just use Google" which is a pertinent observation. 

We did test some Google searches - such as "recycle lightbulbs Aberdeen."

We found in that most cases that the results returned were poor. In the above search Google returned three results, all nicely on a map. In reality none of the three suggested locations accept lightbulbs, and the  one which does (at Hazlehead) is not listed. 

If councils put this sort of data out in a machine readable fashion, as open data then, in addition to the potential for innovation and new products and servivces, the Google results would also benefit. And that can only be a good thing for citizens. 








