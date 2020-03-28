# Midterm Feedback

## Overall Score: 
43 / 50

Overall you did a great job.  The work was easy to follow and ran well.  There are a couple of notes below on design that could have made your solution a little bit more easy to adapt to changing requirements and a couple of things that would have prevented errors when unexpected inputs (e.g. age < 0) are encountered.  I especially liked your use of easy to read and understand variable names.

## Part 1: Creating a JSON Rules File
Comments - This is well organized.  The only thing that I see missing in your JSON is some sort of specification under FiO2 to indicate when A-a Gradient and PaO2 should be used.  I expect that I'll find that bit of busines logic in your FiO2 function rather than here in the JSON configuration.  Ideally it would be here.  (-1)

## Part 2: Functions to evaluate rules
### 2A Organ Failure History
Comments - You'll see that I tested what would happen if an invalid organ history event was provided as a parameter.  Rather than returning none, your code causes an error.  If you'd provided a default value for history_score, that would have prevented the error.  (-1)

The comments in the description suggest that the function will take a list of values, but I see it behaving like it will take a single string.  (-1)

### 2B Age
Comments - Well done.  There's a similar condition here, where your age_score should have some kind of default, but it only causes an error with a negative age value... which no one should have.

### 2C Temperature
Comments - Great.

### 2D pH
Comments - Great.

### 2E Heart Rate
Comments - Great.

### 2F Respiratory Rate
Comments - Great.

### 2G Sodium
Comments - Great.

### 2H Potassium
Comments - Great.

...But have you noticed, yet, that most of these functions so far look almost excatly the same?  The way you coded the rules in JSON is great work and follows a fairly consistent structure and pattern regardless of what kind of value is being tested.  So, you could have written a generic function and reused it in each of your smaller functions.  (-1)

### 2I Creatinine
Comments - Great work dealing with the acute / chronic difference.  Again, you're missing a default value for creatinine_score, but no points off for that here.

### 2J Hematocrit
Comments - Great.

### 2K White Blood Count
Comments - Great.

### 2L FiO2
Comments - Here, as I suspected when I read the JSON, you have the conditions for when to use A-a Gradient or PaO2 embedded within the function.  In the walkthrough, I'll share another approach to this that keeps the logic in the JSON.  Nice job setting a default for the fio2_score!  (-1)


## Part 3: Put it all together
Comments - Nice work.


## Part 4: Accessing and processing the patient file
Comments - Nice work.  One nuance here is that I was expecting you to be able to read the patients and scores files directly from the internet addresses rather than downloading them and storing them in your folder.  That's OK, though.

The few you didn't match on were the result of some differences in the interpretation of <= versus < in some cases.  So, no points off for these.