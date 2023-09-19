# Creating prompts in watsonx.ai's Prompt Builder

Complete the following exercies using Watsonx.ai's Prompt Builder.

**Exercises**
<table>
<tr>
<td><a href="#1-generate">1. Generate</a></td>
<td>Write three sentences about donkeys</td>
</tr>
<tr>
<td><a href="#2-rewrite">2. Rewrite</a></td>
<td>Transform Markdown to HTML</td>
</tr>
<tr>
<td><a href="#3-summarize">3. Summarize</a></td>
<td>Summarize a short story</td>
</tr>
<tr>
<td><a href="#4-summary-points">4. Summary points</a></td>
<td>Create a list of topics from a meeting transcript</td>
</tr>
<tr>
<td><a href="#5-study-questions">5. Study questions</a></td>
<td>Anticipate potential customer questions</td>
</tr>
<tr>
<td><a href="#6-text-extraction">6. Text extraction</a></td>
<td>Extract verbs from a sentence</td>
</tr>
<tr>
<td><a href="#7-compare">7. Compare</a></td>
<td>Identify what passages have in common</td>
</tr>
<tr>
<td><a href="#8-text-search">8. Text search</a></td>
<td>Find which page contains the sought-after text</td>
</tr>
<tr>
<td><a href="#9-classify">9. Classify</a></td>
<td>Detect chatbot users' intent</td>
</tr>
<tr>
<td><a href="#10-anomaly-detection">10. Anomaly detection</a></td>
<td>Spot the odd entry out</td>
</tr>
<tr>
<td><a href="#11-math-question">11. Math question</a></td>
<td>How many minutes are there in a day?</td>
</tr>
<tr>
<td><a href="#12-write-like-shakespeare">12. Write like Shakespeare</a></td>
<td>Rewrite a passage like Shakespeare</td>
</tr>
</table>

<p>&nbsp;</p>


## 1. Generate
**Goal** 
<table>
<tr>
<td>
Write three sentences about donkeys
</td>
</tr>
</table>
  
**Samples**
```
3 sentences about puppies:
- The puppy spun in circles, trying to catch his tail, but ended up tumbling over and over.
- His antics had his owners laughing out loud, and even the other puppies at the park stopped to watch the silly sight.
- As soon as the two puppies met at the park, their tails began to wag and they bounded around each other with glee.
```
```
3 sentences about kittens:
- The little kitten lapped up the milk with her tiny pink tongue, making a cute slurping sound.
- The kitten nibbled on the treat, savoring every morsel of the delicious flavor.
- As soon as the package was opened, the little kitten's eyes lit up with excitement.
```

See: [Example answer](prompt-engineering-exercise-answers.md#1-generate)

<p>&nbsp;</p>


## 2. Rewrite
**Goal** 
<table>
<tr>
<td>
Transform one of these Markdown passages to HTML
</td>
</tr>
</table>

**Markdown passages**
```
## Background
The [IBM Watson Natural Language Processing library](https://dataplatform.cloud.ibm.com/docs/
content/wsj/analyze-data/watson-nlp.html) is a Python library that provides basic natural 
language processing (NLP) such as syntax analysis and keyword extraction with out-of-the-box, 
pre-trained models. The Watson NLP library also makes it simple to customize the language 
models with dictionaries of your domain-specific terms.
```
```
[MURAL](https://mural.co) is an online tool that is like a virtual whiteboard: you can draw 
shapes, stick notes, and move things around. It’s a fabulous tool for visually organizing ideas, 
designing solutions, and collaborating with teammates — in real time or asynchronously.
```
```
## Function
Using LLMs is pretty easy: prompt the model with text (eg. "I took my dog") and the model 
generates text as output (eg. "for a walk").
```
```
## Hall of shame: when LLMs go wrong
Even the creators of LLMs cannot always fully anticipate or explain these models' output: 
[ChatGPT's creators can’t figure out why it won’t talk about Trump](https://www.semafor.com/
article/02/03/2023/how-chatgpt-inadvertently-learned-to-avoid-talking-about-trump)
```

See: [Example answer](prompt-engineering-exercise-answers.md#2-rewrite)

<p>&nbsp;</p>


## 3. Summarize
**Goal** 
<table>
<tr>
<td>
Summarize one of these short stories
</td>
</tr>
</table>
  
**Short stories**

```
A little bird chirped as she gathered twigs and bits of moss in her beak, flitting back and 
forth between the trees. With each trip, her nest took shape, becoming cozier and more inviting. 
And soon enough, she had created a snug home to raise her brood of chirping chicks.
```
```
As soon as the package was opened, the little cat's eyes lit up with excitement. She pounced 
on the new toy, batting it around the room with joyous abandon. With a contented purr, she 
snuggled up with her toy, feeling grateful for the love and attention of her caring owner.
```
```
The ship heaved and tossed on the angry sea as the storm raged on. Waves as tall as mountains 
crashed against the hull, threatening to capsize the vessel. But the captain and crew held 
steady, navigating the treacherous waters with skill and determination, until finally, the 
storm subsided and the ship emerged triumphant, battered but unbroken.
```
```
As soon as the two dogs met at the park, their tails began to wag and they bounded around 
each other with glee. Their owners struck up a conversation, and soon found that they had 
much in common, bonding over their shared love of dogs and the outdoors. By the end of the 
day, new friendships had been formed, and both the dogs and their owners left the park with 
happy hearts and wagging tails.
```

See: [Example answer](prompt-engineering-exercise-answers.md#3-summarize)

<p>&nbsp;</p>


## 4. Summary points
**Goal** 
<table>
<tr>
<td>
Create a list of topics from one of these meeting transcripts
</td>
</tr>
</table>

**Transcripts**
```
00:00   [sam]   I wanted to share an update on project X today.
00:15   [sam]   Project X will be completed at the end of the week.
00:30   [erin]  That's great!
00:35   [erin]  I heard from customer Y today, and they agreed to buy our product.
00:45   [alex]  Customer Z said they will too.
01:05   [sam]   Great news, all around.
```
```
00:00   [ali]   The goal today is to agree on a design solution.
00:12   [alex]  I think we should consider choice 1.
00:25   [ali]   I agree
00:40   [erin]  Choice 2 has the advantage that it will take less time.
01:03   [alex]  Actually, that's a good point.
01:30   [ali]   So, what should we do?
01:55   [alex]  I'm good with choice 2.
02:20   [erin]  Me too.
02:45   [ali]   Done!
```
```
00:00   [alex]  Let's plan the team party!
00:10   [ali]   How about we go out for lunch at the restaurant?
00:21   [sam]   Good idea.
00:47   [sam]   Can we go to a movie too?
01:04   [alex]  Maybe golf?
01:15   [sam]   We could give people an option to do one or the other.
01:29   [alex]  I like this plan.  Let's have a party!
```

See: [Example answer](prompt-engineering-exercise-answers.md#4-summary-points)

<p>&nbsp;</p>


## 5. Study questions
**Goal** 
<table>
<tr>
<td>
Create a list of questions a customer might have about one of these topic passages
</td>
</tr>
</table>

**Topic passages**

[Creating notebooks](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/creating-notebooks.html)
```
You can add a notebook to your project by using one of these methods: creating a notebook file, 
copying a sample notebook from the Gallery, or adding a notebook from a catalog. You must have 
the Admin or Editor role in the project to create a notebook.
```
[Using Spark in RStudio](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/rstudio-spark.html)
```
Although the RStudio IDE cannot be started in a Spark with R environment runtime, you can use 
Spark in your R scripts and Shiny apps by accessing Spark kernels programmatically. RStudio uses
the sparklyr package to connect to Spark from R. The sparklyr package includes a dplyr interface
to Spark data frames as well as an R interface to Spark’s distributed machine learning pipelines.
```
[AutoAI overview](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/autoai-overview.html)
```
The AutoAI graphical tool in Watson Studio analyzes your data and discovers data transformations, 
algorithms, and parameter settings that work best for your predictive modeling problem. AutoAI 
displays the results as model candidate pipelines ranked on a leaderboard for you to choose from.
```

See: [Example answer](prompt-engineering-exercise-answers.md#5-study-questions)

<p>&nbsp;</p>


## 6. Text extraction
**Goal** 
<table>
<tr>
<td>
Extract verbs from one of these sentences
</td>
</tr>
</table>

**Sentences**
```
As soon as the two dogs met at the park, their tails began to wag and they bounded 
around each other with glee.
```
```
Their owners struck up a conversation, and soon found that they had much in common, 
bonding over their shared love of dogs and the outdoors.
```
```
As soon as the package was opened, the little cat's eyes lit up with excitement.
```
```
She pounced on the new toy, batting it around the room with joyous abandon.
```

See: [Example answer](prompt-engineering-exercise-answers.md#6-text-extraction)

<p>&nbsp;</p>


## 7. Compare
**Goal** 
<table>
<tr>
<td>
Choose one pair of passages and identify what the passages have in common
</td>
</tr>
</table>

**Passage pairs**
```
"The little bird spent days gathering twigs, leaves, and feathers, carefully 
crafting her new home. When she finally settled into her cozy nest, she felt a 
sense of pride and contentment, knowing she had created a safe haven for 
herself and her future chicks."

"The little bird tried to carry a twig that was too big for her, and she 
ended up tumbling backward, legs sticking up in the air. Her feathered friends 
tweeted with laughter, and the little bird joined in, knowing that sometimes 
even the best-laid plans can go awry."
```
```
"The little kitten lapped up the milk with her tiny pink tongue, making a cute 
slurping sound. Her fuzzy face was covered in a white mustache, and she let 
out a tiny purr of contentment as she finished her meal."

"The little kitten nibbled on the treat, savoring every morsel of the delicious 
flavor. Her big round eyes widened with delight, and she purred contentedly, 
grateful for the simple pleasure of a yummy snack."
```
```
"The puppy spun in circles, trying to catch his tail, but ended up tumbling 
over and over. His antics had his owners laughing out loud, and even the other 
dogs at the park stopped to watch the silly sight."

"The dog chased after the ball, wagging his tail with excitement. His owner 
threw the ball again and again, and the dog happily retrieved it each time, 
barking with joy."
```
```
"The naughty donkey nudged the gate open with his nose and ran out into the 
meadow, braying with delight. His owner shook his head in amusement, knowing 
that the playful donkey always found a way to bring a smile to his face."

"The mischievous donkey chased after the butterfly, but ended up 
braying in alarm as it flew too close to his face. He stumbled backward and 
tripped over his own hooves, earning a few giggles from the nearby chickens."
```

See: [Example answer](prompt-engineering-exercise-answers.md#7-compare)

<p>&nbsp;</p>


## 8. Text search
**Goal** 
<table>
<tr>
<td>
Find which page contains the sought-after text
</td>
</tr>
</table>

**Pages to search**
```
Page 1: "A little bird chirped as she gathered twigs and bits of moss in her beak, flitting back and forth between the trees."
Page 2: "With each trip, her nest took shape, becoming cozier and more inviting."
Page 3: "And soon enough, she had created a snug home to raise her brood of chirping chicks."
```
**Sample search terms**
```
cozier
little
enough
```

See: [Example answer](prompt-engineering-exercise-answers.md#8-text-search)

<p>&nbsp;</p>


## 9. Classify
**Goal** 
<table>
<tr>
<td>
Detect chatbot users' intent
</td>
</tr>
</table>

**Class samples**<br/>
[Sample data source](https://github.com/spackows/CASCON-2017_Analyzing_chat/blob/master/sample-data/sample-NLC-training-data.csv)

Class: "hi"
```
Hello
Hi there
Good evening
Hi
Hi good morning
```
Class: "question"
```
Hi I wanted to know how to export data from python notebooks?
Hi there can i recover a deleted notebook?
Hi how do you add a folder of files to a project?
Hi team How can you change the name of a Notebook?
How to upload a dataset from local to RStudio
Good morning can you help me upload a shapefile?
How to start creating R notebook?
```
Class: "problem"
```
Hi cant login today with this err The owners accout is not active. This might be caused by expired membership.
I am not able to register my account need your help
Hi I got the message failed to prepare Object-Storage. Would you please give me a suggestion. Thank you.
Hi I am trying to request a new API access key but I dont know what the ID should be for me
When I try to add a model to any project I get an Unauthorized error.
```
**Test input**
```
Hi  Anyone there?
```
```
Having issues setup WML service
```
```
Hi team how can i import data into a project?
```

See: [Example answer](prompt-engineering-exercise-answers.md#9-classify)

<p>&nbsp;</p>


## 10. Anomaly detection
**Goal** 
<table>
<tr>
<td>
Spot the odd entry out
</td>
</tr>
</table>

**Data set**
```
1: "donkey"
2: "donkey"
3: "kitten"
4: "donkey"
5: "donkey"
6: "donkey"
```

See: [Example answer](prompt-engineering-exercise-answers.md#10-anomaly-detection)

<p>&nbsp;</p>


## 11. Math question
**Goal** 
<table>
<tr>
<td>
How many minutes are there in a day?
</td>
</tr>
</table>

See: [Example answer](prompt-engineering-exercise-answers.md#11-math-question)

<p>&nbsp;</p>


## 12. Write like Shakespeare
**Goal** 
<table>
<tr>
<td>
Rewrite this story in the style of Shakespeare
</td>
</tr>
</table>

**Story**
```
Despite their love for each other, the young couple's relationship was doomed from
the start. Friends and family stood in the way, fueling a tragic misunderstanding 
that ultimately led to their heartbreaking separation.
```

See: [Example answer](prompt-engineering-exercise-answers.md#12-write-like-shakespeare)

<p>&nbsp;</p>


## Note
All of the sentences and stories - about birds, puppies, kittens, donkeys, and shakespeare - were generated using chatGPT.

<p>&nbsp;</p>

