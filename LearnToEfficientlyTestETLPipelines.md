# Learn to Efficiently Test ETL Pipelines

## Talk Resources
* [Slides](https://github.com/jmasonlee/Talks/raw/master/Slides/Learn%20to%20efficiently%20test%20ETL%20pipelines.pptx)
* Code:
  * [Starting Point](https://github.com/jmasonlee/saff_squeezing_pyspark_tests)
  * [Ending Point](https://github.com/jmasonlee/saff_squeezing_pyspark_tests/blob/saff_squeeze/test/review_count_tests.py)
### Saff Squeeze
1. Inline Everything
1. Move asserts up and delete everything that's not needed from the bottom.
2. Keep going until you find the code important for your bug
3. Delete anything that's unused from the top
4. Cache or refactor to reduce what's needed from the top
5. Simplify your inputs until they are the minimum needed to reproduce your bug
6. You have a smaller test!

After Jay and I had our conversation, J.B. Rainsberger wrote a really good blog describing this technique in detail. [Check it out here!](https://blog.thecodewhisperer.com/permalink/the-saff-squeeze)

[Kent Beck's original blog post on the wayback machine](https://web.archive.org/web/20090301204625/http://www.threeriversinstitute.org/HitEmHighHitEmLow.html)


## Jay Bazuzi shares bits of wisdom on his... ##
* [Blog](https://jay.bazuzi.com/)
* [Twitter](https://twitter.com/jaybazuzi)
* [Regular Meetups with the Seattle Software crafters](https://www.meetup.com/seattle-software-craftsmanship/)
* [Mobbing pattern language](https://jay.bazuzi.com/Mobbing-Pattern-Language/)
* [LinkedIn](https://www.linkedin.com/in/jay-bazuzi-07936414/)

[Ask Jay about the Saff Squeeze (or other things) July 13!](https://www.meetup.com/seattle-software-craftsmanship/events/286844095/)

## Jacqueline's <!-- include: jacqueline.md -->

* [Blog](http://jmasonlee.github.io/)
* [Calgary Software Crafters](https://www.meetup.com/Calgary-Software-Crafters/)
* [Twitter](https://twitter.com/jmasonlee)


 <!-- endInclude -->

## Given At
* Upcoming:
  * 2022-06-28 [Databricks Data & AI Summit 2022](https://databricks.com/dataaisummit/session/learn-efficiently-test-etl-pipelines)
* Past:
  * 2022-06-21 [Calgary Software Crafters](https://www.meetup.com/calgary-software-crafters/events/286497968/)
  * 2022-05-28 [Software Developers of Calgary](https://www.meetup.com/software-developers-of-calgary/)  
  * 2022-04-21 [Women in Data Calgary](https://www.meetup.com/women-in-data-calgary/events/285039460/)
