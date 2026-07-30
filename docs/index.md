# Jobs-pocalypse now?
### What does the dawn of the AI age mean for your career prospects?

In the roughly three and a half years have passed since ChatGPT launched, the consensus has emerged that its economic impacts will fall somewhere in between the creation of endless abundance and the extinction of humankind ([e.g. see Dallas Fed]("https://www.dallasfed.org/research/economics/2025/0624")).

With each new frontier model release, it becomes harder to doubt that AI will have a significant impact on work and daily life. the timing and direction of that impact is very much up for debate. At first thought it seems sensible to assume that as AI becomes more capable and widely adopted, employment in AI exposed industries will fall in a relatively linear fashion: AI gets adopted by firms -> tasks get automated -> workers get replaced -> employment goes down. 

## Measuring AI Exposure

I attempt to extract signal from all the noise (both in the data and the media) by comparing recent employment growth across 197 US industries with different levels of exposure to artificial intelligence.from changes in employment across different industries that have varying degrees of exposure to AI.

I make use of AI industry exposure scores calculated by Felten, Raj, and Seamans[^1] by matching AI capabilities (such as language processing and image recognition) to the skills and abilities required in different occupations, then aggregating those occupational scores to create an industry-level exposure measure.

## What Does the Data Say?

Despite widespread concerns about automation, highly AI-exposed industries have not experienced consistently weaker employment growth. The estimated relationship between AI exposure and employment growth is slightly positive, but the explanatory power is extremely weak (R<sup>2</sup> of c.0.01). Knowing how exposed an industry is to AI tells us almost nothing about how employment in that industry has changed so far.

<iframe src="./assets/emp_growth_ai_anim.html" width="100%" height=800 frameborder="0"></iframe>

# Winners and Losers

The most AI-exposed industries are concentrated in the professional and business services and finance sectors, but their employment outcomes variedy widely: `legal services` grew by 4.9% and `insurance agencies and brokerages` grew by 3.1%, while `credit intermediation` fell by about 12% and `computer systems design` fell by 4.5%.

Some of the strongest employment growth is in private education and health services. Several of these have moderate to positive AI exposure scores, but are typically associated with in-person service delivery that is unlikely to be automated away any time soon.

## Why hasn't employment fallen?
There are two concepts related to technology adoption that offer up explanations as to why AI exposed firms  firing their workers:

J-Curve: AI initially reduces productivity as firms invest capital and effort in reorganisation, training, and process redesign, before generating larger productivity gains and labour market adjustments. 2019-04JCurvebrief.final2_.pdf

If the J-Curve effect is playing out, we could be seeing employment increase in the industries with most to gain from AI adoption as firms hire workers to implement the changes that will allow them to replace workers with AI in the future (i.e. it may not be the same _types_ of workers that are being hired within those industry groups).

Jevons paradox: AI makes tasks more efficient and cheaper, which increases demand for those products and services enough that overall employment in related sectors grows rather than shrinks. 

More optimistically, Jevon's paradox implies that the productivity gains from AI will find their way to workers in exposed industries, and also benefit consumers of their products and services through lower prices.
(Torsten Slok at Apollo has compiled a number of examples where this has already happened as a result of recent technology adoption: )

## Limitations
AI adoption remains relatively early. Many firms are still experimenting with AI rather than fully integrating it into production processes. Employment effects may emerge gradually over several years.

The emergence of AI is not the only structural change that the US labour market has faced recently, with the emergence from the Covid pandemic and substantial shifts in US trade and immigration policy having overlapping impacts on many of the same industries ([Torsten Slok maps these out here](https://www.apollo.com/content/dam/apolloaem/images/daily-spark/2026/feb/26/feb26-chart2.jpg))

The AIIE scores measure how exposed an occupation is to AI capabilities, not whether firms in that industry have actually adopted AI.

Employment growth is measured at the industry level, which may conceal significant changes within occupations. AI could reduce demand for some jobs while increasing demand for others within the same industry.

The AIIE scores also do not match perfectly to the industry categories used by the BLS - both due to differences in aggregation and as a result of an update to the North American Industry Classification following the publication of the AIIE scores. As a result, I was only able to match 197 BLS industries to the 250 AIIE scores.

## Conclusion
Of course, the most likely explanation to draw from this particular set of data is that measuring AI’s impacts is hard and imperfect, and distinguising these from broader factors like industry demand, macro conditions, and sector-specific shocks would require better data or more sophisticated analysis.

AI exposure alone is not a reliable predictor of employment decline. While some highly exposed industries have lost jobs, others have grown, and the overall relationship between exposure and employment growth is weak. This supports the idea that, at least so far, AI is more likely to reshape tasks within industries than produce immediate, uniform job losses across exposed sectors.

The data does not support the "robots taking all the jobs" narrative. While AI exposure varies substantially across industries, those differences have so far translated into remarkably little variation in employment growth. Whether this reflects a temporary J-curve effect, a Jevons-style demand response, or simply the early stage of AI adoption remains an open question. What is clear is that, for now, exposure to AI is not a predictor of which industries are adding or losing jobs.

[^1]: Felten E, Raj M, Seamans R (2021) Occupational, industry, and geographic exposure to artificial intelligence: A novel dataset and its potential uses. Strategic Management Journal 42(12):2195–2217.