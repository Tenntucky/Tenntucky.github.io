---
layout: post
title: Sommelier Wine Predictions
subtitle: Applying the Sommelier Deductive Tasting Format
gh-repo: Tenntucky/Tenntucky.github.io
gh-badge: [star, fork, follow]
tags: [sommelier]
comments: true
---


Wine is a fascinating drink dating back millennia to 6,000BC in Georgia and I doubt they found it any less 
obsessive than our current civilization. In time the fermented drink would make its way to the Balkans where 
the Greeks and Romans would celebrate the drink. The Romans believed wine to be a daily necessity and made 
it widely available to the classes. This is where viticulture is believed to have begun, Tuscany region. 
There were numerous writings within the empire on different wine types, best practices, and pruning techniques 
necessary to achieve yields. 


As humans explored, they took with them wine and the practices that were developed thousands of years prior. 
Writings of wine, their descriptions, and ranking vineyards can be traced back to Pliny the Elder and sommeliers 
date back to the 1300’s. A sommelier is an expert in wine, today being certified by a number of respected bodies 
world wide. The Court of Master Sommeliers was established in 1977 to improve standards and knowledge. To become 
a Master Sommelier you must practice for years and eventually be invited to take the exam which consists of three 
parts, service, theory, and tasting. 

I have wondered, if given certain descriptions of wine could one pick out the wine described. The Master Sommeliers 
use a deductive tasting format. 

![]SommelierTasteChart.png

Initially, I went through and cut all of the features except description and score to predict the variety. I would use OneHotEncoder to dummy code the descriptions and kick me out some cool new features, this was a mistake. The Description crashed my run every time because there were thousands of columns and I’m sure they didn’t make that much sense. So starting over I decided to look at the grammar within the description column cutting unneeded words and found that the description actually contains the name of the wine in some of the columns. I then decided that I would hard code checks of the deductive tasting format in the new description column and pass those to become new features themselves. Continuing with the province I created twenty new features. At the beginning my base line showed 10.7% accuracy, after hard coding in the deductive tasting format, I found I would increase my accuracy of my RandomForestClassifier from 26% to 45%. It also helped my LogisticRegression model improve to 18% accuracy versus being stuck in the baseline. 
	The Master Sommelier test normally takes 3 attempts to complete, considering information we are missing a 45% prediction is not bad.  
