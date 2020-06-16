# alexa-nlu-evaluation

The purpose of this guide it's to learn how to use the NLU Evaluation tools for Alexa.

The step 0 is to create yourself an Amazon Developer account, it's free and can be done at [developer.amazon.com](https://developer.amazon.com/).

### Step 1. Create an Alexa Skill

Go to the [Alexa developer dashboard](https://developer.amazon.com/alexa/console/ask) and create a new skill.

Name: **my restaurant**
Language: **English (US)**
Model: **Custom**
Host: **Alexa-Hosted (Python)**

Click next

Template: **Hello World**

Import the interaction code from the example, for that, go to **Build**, **JSON Editor**, copy and paste the json from [interactionmodel.json](interactionmodel.json), hit **Save Model** and finally **Build Model**.

After the build has finished, click on **Evaluate Model**, on **Utterance profiler** and type *I want a spanish restaurant* and check that the returned intent is *searchRestaurant*

### Step 2. Create an NLU Annotation Set

Go to the **Annotation Sets** tab, and select the **NLU Evaluation** option.

Here you can see the annotation sets you have configured for this skill, if you followed the steps in order, you shouldn't have any. So click on create annotation set.

Name it to: **SkillTest.v0**

Add the following utterances, intents and slots:

+ Utterance: *find a restaurant*, Expected intent: *searchRestaurant*
+ Utterance: *book me a restaurant*, Expected intent: *bookingRestaurant*
+ Utterance: *find me a restaurant*, Expected intent: *searchRestaurant*
+ Utterance: *i want a restaurant*, Expected intent: *searchRestaurant*
+ Utterance: *i want a korean restaurant*, Expected intent: *searchRestaurant*

Your annotation set should look like:
![Annotation set](/screenshots/annotation-set.png)

Click **Save Annotation Set** and follow up.

### Step 3. Test an annotation set

Go back to your interaction model, clicking any Intent. Hit the **Evaluate model button**, **NLU Evaluation**, select the annotation set you've just created and run a test, you should get:
![test](/screenshots/test-failed.png)

### Step 3. Improve your model

Fix the issues in the interaction model to make pass the tests. You will also need to update the annotation set to something similar to:
![Improvement](/screenshots/annotation-set-correct.png)

Now, build again the model, **Save Model** and then **Build Model**, wait for it to be done and test again the annotation set, you should see some improvement, like:
![Improvement](/screenshots/test-succesfull.png)


