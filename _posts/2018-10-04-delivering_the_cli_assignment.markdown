---
layout: post
title:      "Delivering the CLI assignment"
date:       2018-10-04 14:55:56 +0000
permalink:  delivering_the_cli_assignment
---

"What a nice little project this is..." is the thought I was having while reading the description/instructions of the CLI project. Although the experience proved a bit more challenging than I had initially expected.

The day before I started the design/coding of the application I had finalized the idea that this project was going to be based on. I had decided to scrape the [EdX](https://www.edx.org/course/?program=all&availability=starting_soon) website and report on the upcoming programs and allow the user to drill-down one level and check out the courses that each of the aforementioned programs entailed.

"Fantastic! What a brilliant idea...", I was thinking while I was implementing my object model for this assignment. I created my Program class and also my Course class and their association, while trying to utilize all the best practices that I had come across on Learn.co so far. All done! I was ready to program my Scraper class, a singleton that would help me scrape the EdX website and populate the instances of my two main classes.

"Whooohoo! Almost there!" I said, when I finished inspecting the source of the EdX page that I had planned to scrape. It was time to test my scraper and adjust it accordingly so that I would get the expected results. "Empty arrays everywhere..." No matter what class or id names or css elements I tried in order to find the info I wanted I would always end up with empty arrays. After a long troubleshooting session, I realized that what I was seeing on my browser's page and what Nokogiri was reading as the page's HTML contents, were two completely different things.

"AJAX!!!" was the only logical solution that I could think of at the time. Open Uri + Nokogiri were accessing the webpage at a point in time, but the page would be altered by the responses of various AJAX calls at a later stage. I had certainly hit a wall with my idea, but I had already coded most of it.

It was getting late and I needed to find a workaround that would require the least amount of work. After a bit of searching I was able to find another website called [FutureLearn](https://www.futurelearn.com/programs) which also listed academic online programs, each comprised of several individual courses. Therefore, I could reuse my object model without significant changes to it. Moreover, the site was fully scrapable via Open Uri + Nokogiri.

"Great success!" I thought, although I would have to change the name of my GitHub repository as well as some filenames and directory names of my project, so that it would be fully consistent. I finalized my scraper class and coded the rest of my application's controller / CLI class, which would handle the presentation and user input. It was really late when I finished debugging but I was happy with the result, so I went straight to bed.

The next day one thought was dominating all my other coding related thoughts. "How does one scrape an AJAX filled website?" AJAX seems to be everywhere these days, most sites nowadays seem to dynamically update themselves without a whole page refresh. So there must be a way to accomplish this task somehow. So I started searching...

"Out goes Open Uri, in comes [Watir](http://watir.com/)!" It seems that people were able to accomplish similar tasks by opening up the webpage in a browser instance, reading the final HTML and forwarding it to Nokogiri. Although Watir is used mainly as a testing framework, it could help me implement my initial idea. However, the tradeoffs would be considerably slower access (with higher memory usage), further gems to be installed and incorporated into the application as well as a browser driver that needed to be installed beforehand in any machine that would want to run my CLI application. 

Basically Watir loads up a browser instance and it can collaborate with most widely used browsers as long as the appropriate drivers are installed. A headless browser mode is also supported (which was what I was after) however phantomJS (well known headless browser) usage with the latest versions of Watir has been deprecated. Therefore, I needed to download and install the [mozilla geckodriver](https://github.com/mozilla/geckodriver/releases) in order to utilize a headless firefox instance in my application.

I ended up developing two different applications for the CLI assignment, both of them fully working and covering the assignment requirements. I will be submitting the EdX one, but if anyone is interested I got a link to the GitHub repo of each application below.

[EdxCli](https://github.com/kpediad/EdxCli)

[FutureLearnCli](https://github.com/kpediad/FutureLearnCli)

