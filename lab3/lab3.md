# Lab Report 3 - Researching Commands

I will be exploring the options that can be used with the `grep` command. The input file with the following path will be used in the examples: `docsearch/technical/biomed/1468-6708-3-1.txt`. I obtained information about all of these options at the GeeksforGeeks website: https://www.geeksforgeeks.org/grep-command-in-unixlinux/#. 

## -c option

The -c option prints out the number of lines that match to the given string pattern.

**Example 1:** 
```
$ grep -c "Introduction" docsearch/technical/biomed/1468-6708-3-1.txt
1
```

We may only want to print the number of lines that contain matches rather than the actual lines if we just want to check that the file contains something. In this example, we might want to check to see if the "Introduction" section is in the text in order to ensure that there is a high-level description of the study. 

**Example 2:**
```
$ grep -c "[ ]" docsearch/technical/biomed/1468-6708-3-1.txt
431
```

In this case, we are looking for how many lines contain brackets, which indicates that the text is citing another source. This could be useful for checking the credibility and depth of research within a paper by checking to see how many times it references/cites another source.

## -w option

The -w option only returns exact matches to the string pattern given, rather than also counting the strings that contain the string pattern and might have other characters in the word. This is useful because there are many characters or group of characters that are contained in several different words, but we may only be interested in the instances of one specific word.

**Example 1:** 
```
$ grep -w "n" docsearch/technical/biomed/1468-6708-3-1.txt
        follow-up (n = 5,201) and the second (all African
        American, n = 687) with 4 years of follow-up to date.
```
In the example above, someone might want information on the sample size for the medical study that was conducted and since "n" is a variable that stands for sample size, we can search for this character. Since "n" could be in many different words, we need to use the -w option to ignore those other words. 

**Example 2:**
```
$ grep -wc "the" docsearch/technical/biomed/1468-6708-3-1.txt
122
```
We combine the -c and -w options to obtain the number of times that "the" appears in the file. This example demonstrates a possible common usage of this option because "the" is a word that is contained within many other words, such as "there," "then," and "therefore." 

## -i option

The -i option ignores the case of the string when searching for matches. 

**Example 1:** 
```
$ grep -i "clinical" docsearch/technical/biomed/1468-6708-3-1.txt
        decreased mortality. Clinical trials powered to detect
        whom risk factors, subclinical disease, and morbidity are
        baseline. Clinical covariates include hypertension,
        significantly greater than zero. A clinical trial of a
        Implications for clinical trials
        YHL, but not YOL. Clinical trials of weight modification
        found for underweight older adults. Clinical trials whose
        outcome measure. Both YOL and YHL would be clinically
        YHL as the outcome measure in clinical trials involving
```

This option is useful if we want to find all instances of a word, no matter where it is in the sentence. This is because we must account for the fact that words are capitalized at the beginning of sentences. 

**Example 2:**
```
$ grep -i "BMI" docsearch/technical/biomed/1468-6708-3-1.txt
    between body mass index (BMI) and mortality, controlling
    excess risk for persons with very low BMI, but that persons
    with moderately high BMI had little or no extra risk except
    because few studies have examined the relation of BMI to
    events [ 10 ] . In this paper we study whether BMI at
        BMI was calculated as measured weight in kilograms
        BMI of 18.5 to 24.9; overweight as 25 to 29.9; and
        separately the group with BMI between 18.5 and 20, which
        with BMI. To adjust for possible confounding we chose
        and likely to be related to BMI. Self-reported covariates
        plotted mean adjusted YOL and YHL against BMI, and tested
        for difference among BMI groups using confidence
        the effect size for each measure, comparing each BMI
    smokers. Black women had a higher mean BMI and higher
    percent obese (BMI ≥ 30) than the other three groups. Black
    statistically significant (p <.05) except for BMI and
    significant differences between black and white for BMI,
    the difference in BMI was no longer statistically
    significantly on BMI, BMI>30, weight loss since age 50,
    We next examined the relationship of BMI to YOL and YHL.
    BMI below 18.5, but averaged 6.6 years for women with a BMI
    only discrepancy is for men with BMI < 18.5, a category
    with BMI from 18.5 to 20 would be considered 'normal' by
    increase sample size for those with low BMI, we combined
    the two lower categories, defining underweight as a BMI
    BMI. For each BMI category the mean and its 95% confidence
    between BMI and YOL for BMI above 20. Underweight women
    normal group. The relationship of BMI to YHL for men is
    similar, but differences among BMI groups were not
    to the normal BMI group. The effect sizes are shown in
        et al proposed a desirable BMI of
    BMI Body mass index
```

We might want to check whether a certain word is correctly capitalized for each time that it is used. In this example, we search for the abbreviation "BMI" to make sure that all letters are correctly capitalized and there are no cases in which one or more letters are accidentally lowercase. 


## -R option 

This option recursively searches for the pattern for all files within a directory. It returns the files that contain the pattern along with one line from each text that contains a match. 

**Example 1:**

```
$ grep -R "Alzheimer's" docsearch/technical/biomed/
docsearch/technical/biomed//1471-2415-3-5.txt:          Parkinson's disease [ 53 ] and Alzheimer's disease [ 54 ]
docsearch/technical/biomed//1471-2210-1-10.txt:        might be beneficial in the treatment of Alzheimer's disease
docsearch/technical/biomed//1471-2202-4-16.txt:        diseases, including Parkinson's, Alzheimer's and prion
docsearch/technical/biomed//1471-2202-4-16.txt:        other neurodegenerative conditions, including Alzheimer's
docsearch/technical/biomed//1471-2377-2-6.txt:        Patients with Alzheimer's disease experience a
docsearch/technical/biomed//1471-2377-2-6.txt:        cognitive part of the Alzheimer's Disease Assessment Scale
docsearch/technical/biomed//1471-2377-2-6.txt:          mild-to-moderate Alzheimer's disease studied in two
docsearch/technical/biomed//1471-2377-2-6.txt:          these trials were diagnosed with Alzheimer's disease
docsearch/technical/biomed//1471-2377-2-6.txt:          dependency of patients with Alzheimer's disease [ 9 ] .
docsearch/technical/biomed//1471-2377-2-6.txt:          typically observed in patients with Alzheimer's disease.
docsearch/technical/biomed//1471-2377-2-6.txt:          disability of patients with Alzheimer's disease.
docsearch/technical/biomed//1471-2377-2-6.txt:        daily activities is an important aspect of Alzheimer's for
docsearch/technical/biomed//1471-2377-2-6.txt:        Alzheimer's disease [ 18 ] and antipsychotic medications
docsearch/technical/biomed//1471-2377-2-6.txt:        in patients with Alzheimer's disease [ 9 10 ] . The
docsearch/technical/biomed//1471-2377-2-6.txt:        conducted to study treatments for Alzheimer's disease have
docsearch/technical/biomed//1471-2377-2-6.txt:        diagnosed with Alzheimer's disease. Moreover, this
docsearch/technical/biomed//1471-2164-3-29.txt:        in early-onset familial Alzheimer's disease. There is
docsearch/technical/biomed//1471-2202-2-16.txt:        cholinergic cells. Alzheimer's disease (AD) is
docsearch/technical/biomed//1471-2202-2-14.txt:        visual spatial attention [ 19 ] . Patients with Alzheimer's
docsearch/technical/biomed//1471-2202-2-14.txt:        at risk for Alzheimer's disease have been shown to have a
docsearch/technical/biomed//1471-2202-2-14.txt:        same direction as the Alzheimer's patients [ 28 ] . Other
docsearch/technical/biomed//1471-2202-2-14.txt:        influence orienting in a task similar to ours. Alzheimer's
docsearch/technical/biomed//1475-2832-1-1.txt:        Alzheimer's Disease Research Clinical Center, by the
docsearch/technical/biomed//1477-7827-1-46.txt:        Alzheimer's disease.
docsearch/technical/biomed//1477-7827-1-46.txt:          Neurodegenerative diseases, including Alzheimer's
docsearch/technical/biomed//1477-7827-1-46.txt:          is the most obvious consequence of Alzheimer's disease [
docsearch/technical/biomed//1477-7827-1-46.txt:        such as Alzheimer's disease, cerebral ischemia, prion
docsearch/technical/biomed//1477-7827-1-46.txt:        the prevention and treatment of Alzheimer's disease [ 72 73
docsearch/technical/biomed//1477-7827-1-46.txt:        contribute to the development of Alzheimer's disease and
docsearch/technical/biomed//1477-7827-1-46.txt:        Alzheimer's disease.
docsearch/technical/biomed//1471-2202-2-20.txt:        neurological disorders such as, Alzheimer's disease [ 4 5 ]
docsearch/technical/biomed//1471-2202-2-20.txt:        pathophysiologic events in Alzheimer's disease: deposition
docsearch/technical/biomed//1471-2202-2-20.txt:        pathophysiologic event(s) in Alzheimer's disease [ 53 54 55
docsearch/technical/biomed//1471-2202-2-20.txt:        inflammatory factor prevalent in Alzheimer's disease)
docsearch/technical/biomed//1471-2172-2-10.txt:        on Alzheimer's disease as well since cytokines may
docsearch/technical/biomed//gb-2003-4-2-r8.txt:        Alzheimer's disease (FAD) [ 48]. 
docsearch/technical/biomed//1472-6947-1-5.txt:            patients with Alzheimer's Disease found improved
docsearch/technical/biomed//1472-6947-1-5.txt:        Alzheimer's Disease. The most studied area in home-based
docsearch/technical/biomed//1471-2350-2-8.txt:        Alzheimer's disease [ 5, 6, 7].
docsearch/technical/biomed//gb-2002-3-10-research0055.txt:          Alzheimer's disease) through the analysis of their
```

In this example, we might want to find all the studies in this database that are related to Alzheimer's disease in order to help gather more information about a study that we are conducting on Alzheimer's. 

**Example 2:**
```
$ grep -Ri "Alzheimer's Disease" docsearch/technical/biomed/                   
docsearch/technical/biomed//1471-2415-3-5.txt:          Parkinson's disease [ 53 ] and Alzheimer's disease [ 54 ]
docsearch/technical/biomed//1471-2210-1-10.txt:        might be beneficial in the treatment of Alzheimer's disease
docsearch/technical/biomed//1471-2202-4-16.txt:        diseases, including Parkinson's, Alzheimer's and prion
docsearch/technical/biomed//1471-2202-4-16.txt:        other neurodegenerative conditions, including Alzheimer's
docsearch/technical/biomed//1471-2377-2-6.txt:        Patients with Alzheimer's disease experience a
docsearch/technical/biomed//1471-2377-2-6.txt:        cognitive part of the Alzheimer's Disease Assessment Scale
docsearch/technical/biomed//1471-2377-2-6.txt:          mild-to-moderate Alzheimer's disease studied in two
docsearch/technical/biomed//1471-2377-2-6.txt:          these trials were diagnosed with Alzheimer's disease
docsearch/technical/biomed//1471-2377-2-6.txt:          dependency of patients with Alzheimer's disease [ 9 ] .
docsearch/technical/biomed//1471-2377-2-6.txt:          typically observed in patients with Alzheimer's disease.
docsearch/technical/biomed//1471-2377-2-6.txt:          disability of patients with Alzheimer's disease.
docsearch/technical/biomed//1471-2377-2-6.txt:        daily activities is an important aspect of Alzheimer's for
docsearch/technical/biomed//1471-2377-2-6.txt:        Alzheimer's disease [ 18 ] and antipsychotic medications
docsearch/technical/biomed//1471-2377-2-6.txt:        in patients with Alzheimer's disease [ 9 10 ] . The
docsearch/technical/biomed//1471-2377-2-6.txt:        conducted to study treatments for Alzheimer's disease have
docsearch/technical/biomed//1471-2377-2-6.txt:        diagnosed with Alzheimer's disease. Moreover, this
docsearch/technical/biomed//1471-2164-3-29.txt:        in early-onset familial Alzheimer's disease. There is
docsearch/technical/biomed//1471-2202-2-16.txt:        cholinergic cells. Alzheimer's disease (AD) is
docsearch/technical/biomed//1471-2202-2-14.txt:        visual spatial attention [ 19 ] . Patients with Alzheimer's
docsearch/technical/biomed//1471-2202-2-14.txt:        at risk for Alzheimer's disease have been shown to have a
docsearch/technical/biomed//1471-2202-2-14.txt:        same direction as the Alzheimer's patients [ 28 ] . Other
docsearch/technical/biomed//1471-2202-2-14.txt:        influence orienting in a task similar to ours. Alzheimer's
docsearch/technical/biomed//1475-2832-1-1.txt:        Alzheimer's Disease Research Clinical Center, by the
docsearch/technical/biomed//1477-7827-1-46.txt:        Alzheimer's disease.
docsearch/technical/biomed//1477-7827-1-46.txt:          Neurodegenerative diseases, including Alzheimer's
docsearch/technical/biomed//1477-7827-1-46.txt:          is the most obvious consequence of Alzheimer's disease [
docsearch/technical/biomed//1477-7827-1-46.txt:        such as Alzheimer's disease, cerebral ischemia, prion
docsearch/technical/biomed//1477-7827-1-46.txt:        the prevention and treatment of Alzheimer's disease [ 72 73
docsearch/technical/biomed//1477-7827-1-46.txt:        contribute to the development of Alzheimer's disease and
docsearch/technical/biomed//1477-7827-1-46.txt:        Alzheimer's disease.
docsearch/technical/biomed//1471-2202-2-20.txt:        neurological disorders such as, Alzheimer's disease [ 4 5 ]
docsearch/technical/biomed//1471-2202-2-20.txt:        pathophysiologic events in Alzheimer's disease: deposition
docsearch/technical/biomed//1471-2202-2-20.txt:        pathophysiologic event(s) in Alzheimer's disease [ 53 54 55
docsearch/technical/biomed//1471-2202-2-20.txt:        inflammatory factor prevalent in Alzheimer's disease)
docsearch/technical/biomed//1471-2172-2-10.txt:        on Alzheimer's disease as well since cytokines may
docsearch/technical/biomed//gb-2003-4-2-r8.txt:        Alzheimer's disease (FAD) [ 48]. 
docsearch/technical/biomed//1472-6947-1-5.txt:            patients with Alzheimer's Disease found improved
docsearch/technical/biomed//1472-6947-1-5.txt:        Alzheimer's Disease. The most studied area in home-based
docsearch/technical/biomed//1471-2350-2-8.txt:        Alzheimer's disease [ 5, 6, 7].
docsearch/technical/biomed//gb-2002-3-10-research0055.txt:          Alzheimer's disease) through the analysis of their
```

We combine the -R and -i options in order to recursively search for "Alzheimer's" in all the files within the directory while allowing for capitalization errors. In such a case, we might want to make sure that we don't miss instances of the word just because the writer made a typo. 
