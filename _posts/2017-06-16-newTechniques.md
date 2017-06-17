---
layout: page
title: New Tools for Shape Analysis
css: "/css/aboutme.css"
tags: [cool papers, new techniques, data]
---

<body>
So, recently I've been interested in looking for new methods to help me analyze my data. Since I got to Georgia Tech almost a year ago, I've been surrounded by all sorts of interesting new models and algorithms. The most interesting buzz-word (get it... because GT?) has been machine learning. One of the undergrads in our lab has been using supervised machine learning along with computer vision to help solve some pretty cool problems with data we have. Basically, he's been trying to train a computer to pick out spots that correspond to single molecule fluorescent in situ hybridization (smFISH) sites in developing embryos. That's a mouthfull, but the gist is that there are lots of little white blips on a screen, each one is a glowing tag (presumably) attached to a single transcript molecule for a gene. So basically, he's teaching computers to count individual gene expression data. After hearing him talk about it enough times at lab meeting, I decided that this is something I should look into for my own data. It sounded reasonable, and the structure of my data seemed to fit. My only problem was that I had no idea where to start. 
<br><br>
Thankfully, there are tons of resources online for teaching yourself about machine learning. For a while, I had this idea on the backburner as something that might be cool, but I had no real idea how to implement it. THEN, I ran into <a href= "https://gigascience.biomedcentral.com/articles/10.1186/s13742-015-0065-6">this paper</a>, that basically solved this issue for me. This was a particularly cool find, because I know all of the authors (which tells me I should have paid more attention while I was a graduate student with them). Also, a big thank you to you guys for keeping the code up on GitHub (I ended up cannibalizing a lot of it. Thank you!). 
<br><br>
In any case, I've been working through the code and reading up on how each of these models work. At this point, I've got a pretty firm grasp on how most of these work. Unfortunately, I don't have a ton of data like they did, but what I found was still pretty informative. 
<br><br>
<div style="width: 33%; height: 33%">
<embed src="/img/ML_post/4-cell_lms.pdf" width="100%" height="100%" align= "right"/> 
</div>
50
<object data="/img/ML_post/4-cell_lms.pdf" type="application/pdf" width="33%" height="50%"></object>

Before I start with the new stuff, I just want to take a second to remind you what my data look like. I'm using a combination of 18 landmarks and semi-landmarks to describe the shape of a 4-cell embryo. One cool new thing I've been able to do recently is pick apart the first 12 Principal Components from a Principal Components Analysis (PCA, a dimension reduction technique), and plot the minimum for each dimension (gray) against the maxixmum for each (black). 
<br><br>
<embed src="/img/ML_post/PC1-12.pdf" width="600px" height="850px"/>
<br>
This gives you a pretty good idea of essentially every type of variation in shape that we see. In fact, the first 12 PCs describe 93% of the total cumulative variation. Pretty cool, huh? 
<br><br>
Now on the the new stuff.
<br><br>
As it turns out, Linear Discriminant Analysis (LDA) performs really well on the training data, but seems to fall apart once you cross-validate with the test data. I would say that it doesn't seem to do a good job predicting species or temperature (yet). 
<embed src="/img/ML_post/LDAplots.pdf" width="100%" height="515px"/>
<br><br>
Other machine learning techniques like Support Vector Machines (SVM), Random Forrest Classification, and Neural Networks how a little more potential. Overall, it seems like Neural Networks do the best job of actually predicting treatment groups, but Random Forests also show some promise (looks like accuracy is best with 500 trees). Below are some of the confusion matrices from these methods. The Neural Network had a precision of ~70%, while SVM was only ~58%.  
<embed src="/img/ML_post/ConfusionMatrices.pdf" width="100%" height="500%"/>
<br><br>
Overall, this was a really informative look into some powerful new techniques. I'm always on the lookout to improve my game and I think this is a really cool direction. I'm looking forward to using these again once I have more data.
</body>
