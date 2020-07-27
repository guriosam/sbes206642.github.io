---
title: Revealing the Social Aspects of Design Decay
---

# Abtract

The pull-based development model, popularized by social coding environments like GitHub, is widely used by open-source communities. In this model, developers actively communicate and share their knowledge or opinions through the exchange of comments. Their goal is to improve the change under development, including its positive impact on design structure. In this context, two central social aspects may contribute to combating or adversely amplifying design decay. First, design decay may be avoided, reduced or accelerated depending whether the communication dynamics among developers -- who play specific roles -- is fluent and consistent along a change. Second, the discussion content itself may be decisive to either improve or deteriorate the structural design of a system. Unfortunately, it has not been studied so far the role these key social aspects play on avoiding or amplifying design decay. Previous work either investigates technical aspects of design decay or confirms the high frequency of design discussions in pull-based software development. This paper reports a retrospective study aimed at understanding the role of communication dynamics and discussion content on design decay. We focused our analysis on 11 social metrics related to these two aspects as well as 4 control technical metrics typically used as indicators of design decay. We analyzed more than 11k pull request discussions mined from five large open-source software systems. Our findings reveal that many social metrics can be used to discriminate between design impactful and unimpactful pull requests. Second, various factors of communication dynamics are related to design decay. However, temporal factors of communication dynamics outperformed the participant roles' factors as indicators of design decay. Finally, we noticed certain social metrics tend to be indicators of design decay when analyzing both aspects together.

# Design Decay Symptoms

| File         | Description       | Link     |
|:-------------|:------------------|:---------|
| Design Symptoms Description | DesignateTool and Symptoms Descriptions | [Download](https://github.com/sbes206642/sbes206642.github.io/master/description_and_detection_mechanisms.zip) |

# RQ1: Are social metrics related to design decay?

| File         | Description       | Link     |
|:-------------|:------------------|:---------|
| Density | High Level Smells | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/design_changed/design_change_on_density_high_level_smells.rar) |
| Density | Low Level Smells   | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/design_changed/design_change_on_density_low_level_smells.rar) |
| Diversity           | High Level Smells      | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/design_changed/design_change_on_diversity_high_level_smells.rar) |
| Diversity           | Low Level Smells | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/design_changed/design_change_on_diversity_low_level_smells.rar) |
| Script for Wilcoxon Analysis   | - | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/wilcoxon_analysis.R) |

# Data for RQ2 and RQ3

| File         | Link     |
|:-------------|:---------|
| Design Decay per Pull Request | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/design_decay_per_pull_request.rar) |
| Pull Request Decay Classification | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/pull_request_decay_classification.rar) |
| Only Social Metrics | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/only_metrics.rar) |
| Metrics with Decay | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/metrics_with_decay.rar) |
| Script for Multiple Logistic Regression Analysis | [Download](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/multiple_regression_R.rar) |


# RQ2: To what extent the communication dynamics influence the design decay?

![RQ2](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/rq2.png)

# RQ3: To what extent the discussion content influence the design decay?

![RQ3](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/rq3.png)

# Model with Both Social Aspects

![both](https://raw.githubusercontent.com/sbes206642/sbes206642.github.io/master/all_data_tabl.png)

# Rebuttal Responses

## Reviewer 1:

Q: The authors could explain this sentence better: "However, social activities in pull-based development may contribute to avoiding, reducing or accelerating design decay." How? What are the available evidence about it

A: There is no previous evidence about it, as we assess on the 3rd and 4th paragraphs of the introduction.

'These two social aspects may be related to design quality for various reasons, such as two examples described as follows. First, design decay may be avoided, reduced or accelerated depending whether the communication dynamics of developers with specific roles is fluent and consistent along a change. Second, the characteristics of content of comments can determine the quality of the discussion, and therefore be decisive to either improve or deteriorate the structural design of a system.'
'Unfortunately, the relationship between these key social aspects and design decay have not been studied so far. [...] Despite this vast body of knowledge, no study has performed a retrospective investigation on the relationship between key social aspects in pull-based development and design decay. Hence, it is unclear if social aspects, such as communication dynamics and discussion contents, have apositive or negative relationship with design decay.'

However, in Sections 1 and 3, we explain and present a real example in which social activities contribute to the design decay. Moreover, our findings reveal that there is a correlation between social activities and design decay.

Q: Section 2.1. Could be better explained with practical examples

A: We would like to thank the reviewer for this suggestion. However, due space restrictions, we were not able to present an example in this section. Moreover, we tried to make our motivating example the best possible in order to cover most of the topics we presented on 2.1. Finally, if the paper is accepted, we would gladly include more practical examples on this replication package.


Q: Why only two categories of symptoms were selected? What is the rational for the choices?

A: We rely on a theory [Sousa,ICSE’18] that indicates developers consider multiple occurrences (density) and categories (diversity) of symptoms to identify structural decay in a program location. Also, these symptoms can be detected automatically (via DesignateJava) and observed across different scopes, such as classes, methods and code blocks. 

[Souzam ICSE'18] Sousa, Leonardo, Anderson Oliveira, Willian Oizumi, Simone Barbosa, Alessandro Garcia, Jaejoon Lee, Marcos Kalinowski et al. "Identifying design problems in the source code: A grounded theory." In Proceedings of the 40th International Conference on Software Engineering, pp. 921-931. 2018.


Q: Table 1 could show the size of the systems (LOC)

A: We will add this information to Table 1.


Q: The authors could discuss recommendations for researchers and practitioners based on the findings presented

A: We tried to discuss some recommendations right above each finding. For instance, the paragraph before the Finding 1 box:
"This result evidence the rationale that pull requests with high values for these metrics need more attention and concern of software organizations. For such cases, software organizations could monitor significant changes in the values of these metrics. Such changes may indicate an increase or decrease in design quality." 
We discuss the recommendation for software organizations in this case. However, we focus on identifying the best metrics to represent the aspects, this also works as a recommendation to researchers and practitioners to 'where to look'.

Q: Regarding Discussion Length, does it have any impact depending on the number of core contributors?

A: We looked into a possible correlation between the #CoreDevs, Discussion Length and #Comments metrics using spearman’s correlation. The results were 0.14 and 0.57, respectively, for the data of all projects combined. 

### Spearman's Correlation Test between Core Devs and other metrics.
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky"></th>
    <th class="tg-0pky">number_core_devs</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">number_comments</td>
    <td class="tg-0pky">0.57</td>
  </tr>
  <tr>
    <td class="tg-0pky">number_users</td>
    <td class="tg-0pky">0.14</td>
  </tr>
  <tr>
    <td class="tg-0pky">number_contributors</td>
    <td class="tg-0pky">-0.04</td>
  </tr>
  <tr>
    <td class="tg-0pky">number_core_devs</td>
    <td class="tg-0pky">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">opened_by</td>
    <td class="tg-0pky">-0.01</td>
  </tr>
  <tr>
    <td class="tg-0pky">number_of_patches</td>
    <td class="tg-0pky">0.19</td>
  </tr>
  <tr>
    <td class="tg-0pky">words_in_discussion</td>
    <td class="tg-0pky">0.28</td>
  </tr>
  <tr>
    <td class="tg-0pky">words_per_comment_in_discussion</td>
    <td class="tg-0pky">0.09</td>
  </tr>
  <tr>
    <td class="tg-0pky">snippets_size</td>
    <td class="tg-0pky">0.09</td>
  </tr>
  <tr>
    <td class="tg-0pky">mean_time_between_replies</td>
    <td class="tg-0pky">0.08</td>
  </tr>
  <tr>
    <td class="tg-0pky">discussion_length</td>
    <td class="tg-0pky">0.14</td>
  </tr>
</tbody>
</table>


Q: Is it good or bad to have core developers in the discussion? Based on their participation, do we have more discussion (number of words, etc.)? What are the implications?

A: The results of RQ2 were not conclusive about the # Core Devs. However, when we look at Table 7, we can see that the presence of more core developers is a good thing since they indicate a decrease in the design decay.


Q: Any consideration about gender in the discussions? Any impact on this?

A: Since it is an initial study, we focused on less controversial metrics, but we intend to address gender related analysis on future work.


Q: Number of core contributors is important. However, what about peripheral contributors? How it impact the Communication Dynamics Aspect?

A: We did analyze the peripheral contributors on three metrics: Opened By Temporaries, Number of Users and Number of Contributors. Moreover, we will include on the paper the information about the user classification for these metrics. But they were implemented as follows:
- Users are developers that do not have any tag associated or have not committed to the repository yet. They consist of developers that have the tags NONE, FIRST_TIME_CONTRIBUTOR or FIRST_TIMER.
- Contributors are developers that have already authored a commit on the repository or have been invited to collaborate in the repository (push permission). They consist of developers that have the tags CONTRIBUTOR or COLLABORATOR.
- Core Developers are the developers who own the repository or are members of the organization that owns the repository analyzed (Elastic is organization, in the case of the Elasticsearch project). They consist of developers that have the tags MEMBER or OWNER.

The Number of Users and Number of Contributors uses the two first categories  and the Opened By Temporaries consists only of developers with the tags NONE, FIRST_TIME_CONTRIBUTOR or FIRST_TIMER.

As we can see in Table 5 (Number of Users), the impact of these contributors is an indication of increasing on the design decay symptoms.

More information about the tags can be found here: https://docs.github.com/en/graphql/reference/enums#commentauthorassociation


Q: Regarding Discussion Length, does it have any impact depending on the number of core contributors?

A: We did not find evidence that the Number of Core Devs impacts on the Discussion Length.


Q: Is it good or bad to have core developers in the discussion? Based on their participation, do we have more discussion (number of words, etc.)? What are the implications?

A: The results of RQ2 were not conclusive about #CoreDevs. However, by looking at Table 7, we observe that the presence of more core devs is positive as they indicate a design decay decrease. Moreover, we didn’t find evidence that #CoreDevs impacts Discussion Length. 


## Reviewer 2:

Q: Section 4.2.: It is not clear why the authors decided to select only active projects for the study. Non-active projects also include history pull requests that could be used.

A: We had several reasons: we built our dataset without relying on known databases (i.e.,GHTorrent); we addressed mining perils, i.e., active projects avoid known perils [Kalliamvakou,EMSE’16]; a similar amount of projects is used in [1,2,4,9,29]. Note we did collect a very high # of pull requests (PRs) and a wide range of project domains to favor generalization.


Q: Section 4.2.: Studies that mine software repositories often use datasets with dozens of projects. The study of the paper uses only five. Since no manual validation was required in the evaluation process, I wonder why the authors decided to work with such a small number of projects. The Threats to Validity section should discuss this limitation and its impact on generalization.

A: Same as the answer right above.


Q: Section 4.2.: I would like to see a deeper discussion on why using DesigniteJava instead of similar tools. Moreover, what the expected precision and recall? Since this tool is key for the study, those are important information to help us figure if we should trust the found results

A: Although we didn’t assess the accuracy of DesignateJava, previous work [Sharma,EMSE’20] indicated a precision of 96% and a recall of 99%. Moreover, we did analyze the rationale behind each detection strategy used by DesignateJava (available on [20]). 


Q: Section 4.2.: "For this purpose, for each target system, we computed the difference in this indicator of each decay symptom, i.e., high-level and low-level structural smells, by considering all merged pull requests that we have collected."
I am not sure if I fully understand how decay values are calculated. If I understood correctly, each decay symptom considers the whole project in the moment of the pull request. If that is the case, a design issue in class X could be masked by a design improvement performed in class Y? I would like to see a discussion in this sense and details in the text (perhaps with examples)

A: We calculate decay values by collecting the symptoms of each commit of a PR, where each commit was compared to its parent (i.e., the version before the commit); then, we analyze the difference between the symptoms of the versions (after vs. before). To understand the PR impact, we sum the results of each version and get the overall of the design decay for the PR. Yes, a given class masks issues from another. 


Q: Table 2: How the lower-level symptoms differentiate from regular code smells?

A:  Most of the regular code smells focus on class level. The idea behind low-level is to identify symptoms at levels of method and code block (e.g. Complex Method and Empty Catch Block).


Q: Table 4: The Netty and RxJava projects seem to be the ones that differ from the rest in the analysis. Are there specific characteristics (structural, social, etc) that could justify this behavior? I would like to see a discussion about that

A: We couldn't find reasons that justify this difference on Netty and RxJava projects. The sample size of both are the smaller ones, thus a possible justification.


Q: Section 5.2.; 4th paragraph: I wonder if the reasoning for the design decay in the example (#1388 from the OkHttp project) is due to long response time, instead of the size of the discussion.

A: We think that our sentence was not clear enough, since that the discussion in the 4th paragraph is about long response time, not number of comments (size of discussion). We will try to make it more clear.


Q: Section 5.3.: has a high number of comments and a high number of words, however. What is the proper threshold for one to consider a discussion too long or a comment too big? It is not clear the thresholds used in the study. Moreover, a discussion on this topic could also help developers on how to behave.

A: We do not have any threshold computed. We only based our assertives on the logic of our model. Our response outcome says that 'the far from 1 is our odds ratio (higher indicates increase on the design symptoms and lower indicates the opposite), the bigger the chance of an event to happen'.


Q: Why working only with active projects? 

A: To avoid a known peril (Perill III from [Kalliamvakou, EMSE’16]).


Q: Why not use a more comprehensive data set? What is the impact on generalization?

A: We had several reasons: we built our dataset without relying on known databases (i.e.,GHTorrent); we addressed mining perils, i.e., active projects avoid known perils [Kalliamvakou,EMSE’16]; a similar amount of projects is used in [1,2,4,9,29]. Note we did collect a very high # of pull requests (PRs) and a wide range of project domains to favor generalization.


Q: How decay values are calculated? Can design improvements in a given class mask issues from another?

A: We calculate decay values by collecting the symptoms of each commit of a PR, where each commit was compared to its parent (i.e., the version before the commit); then, we analyze the difference between the symptoms of the versions (after vs. before). To understand the PR impact, we sum the results of each version and get the overall of the design decay for the PR. Yes, a given class masks issues from another. 


Q: Is there a reason for results from Netty and RxJava to be significantly different from the others?

A: We couldn't find reasons that justify this difference on Netty and RxJava projects. The sample size of both are the smaller ones, thus a possible justification.


Q: Why DesigniteJava? Was there any study on false positives and false negatives and how they might impact the found results?

A: Although we didn’t assess the accuracy of DesignateJava, previous work [Sharma,EMSE’20] indicated a precision of 96% and a recall of 99%. Moreover, we did analyze the rationale behind each detection strategy used by DesignateJava

## Reviewer 3:

Q: I liked the motivating example; it might be better placed after the Introduction. It is promising, to get a glimpse of the social aspects that will be studied: different participant roles (developers, contributors, and users), and the content of the comments. I wondered: how would the research collect "content" of the discussions? That would require a very burdensome manual analysis. Likewise, I am not sure the commentator's role would be feasible to collect. Is this data available in Github?

A: We thank the reviewer for the suggestion of moving the Motivating Example to after the Introduction. However, our storytelling needs some better clarification of some terms before presenting the example, that is why we placed after the background and related work. Yes, the data is available in GitHub, is the author_association tag on the GitHub API that is nested on users objects.


Q: Next, when looking at Table 3, we can see that the type of user was not directly collected. I think I didn't understand how you different the kinds of users from these metrics. Please clarify this in the paper. Same with discussion content: snippet and word counts are the available data. I'm not sure I agree this means content. Consider making that clearer from the beginning

A: We’ll include extra info about the user classification in the paper. However, the methodology is the same as the peripherical contributors question from above.


Q: The variable design decay is presented as a difference of density of specific detected symptoms, before and after merged PRs. A positive difference indicates an increase in design decay, while a negative difference yields decrease of decay. It seems to me you're measuring design impact, not decay. Decay would be yes/no; impact could be measured as negative or positive. It is confusing to grasp "decrease of decay", as it is a double negation. It is also confusing to read "risk-increasing tendency"  it is not clear how this is related to design impact

A: RQ1 was built around the design impact approach. However, if our approach was building the argument around design impact (regardless of the effect), we wouldn’t be able to separate the ‘good’ and ‘bad’ behaviors.


Q: In measuring the design impact, the DesigniteJava tool makes a distinction between low- and high-level smells. Although the paper does not analyze this distinction, I'd suggest the authors explore how the results would be measured for either type of smell. These groups were used in the statistical results (Tables 4,5,6), but the discussion doesn't seem to consider that

A: The results were equal for both categories, we assess this on the footnote of page 4: "We also compute diversity as an indicator. However, we did not observe any differencein the results of density and diversity. Thus, we decided to use only density."


Q: Still, on the discussion, I miss a more precise account of the results used as evidence for the most important conclusions. For instance, for supporting Finding 1, Metrics are "good indicators", evidencing that pull requests "with high values for these metrics need more attention". It would be better if those values are explicitly showed. Sometimes, the conclusions get too imprecise, such as "Social aspects can differentiate impactful pull requests from the unimpactful ones". Which ones? In which degree?

A: Results from RQ1 show that all social aspects were able to differentiate impactful pull requests from the unimpactful ones. However, the Number of Comments, MTBC, Number of Snippets, NWD, NWPCD, and Snippets Size were statistically significant in all cases. This may indicate that such metrics are able to differentiate impactful from unimpactful pull requests at a higher degree.


Q: The analysis of long discussions having an impact on design decay is very interesting. I tend to agree that "long discussions do not increase the developer's engagement on being conscious with the design structure, increasing the chances of design decay". However, I miss a more detailed rationale behind it. If the more extended discussions are not about design, what would they be about? Maybe it lacks some more speculation about this relationship. Should we analyze the balance within these comments, only a few commentators or indication of too many changes? What does it mean for PRs?

A: We agree with the reviewer about the need for more speculation, our feeling is that each community has its own reason for this kind of behavior. However, since this is an initial study about social aspects and design decay, we focused on seeing which aspects could affect the design decay, instead of speculating things that would require further analysis in this current work. We intend to address this kind of speculation on future work, preferentially with some qualitative analysis.


Q: In Finding 6, instead of measuring words and implying, from that, the complexity of changes, why not measuring change complexity directly? Have you thought about that?

A: Since we ran a MLR and used control variables, i.e., DiffComplexity and PatchSize, we already addressed the complexity using the change itself. However, since the NWD was not collinear with the control variables, there are cases where this metric is acting as an indicator (without the control variables). Then, if a discussion is complex, the change wouldn’t be able to indicate it.


Q: Page 2: "Github, mainly use the pull request mechanism for code contribution". Is it really the case? Any evidence to support?

A: We do not have a strong evidence about it, then, we will change the sentence to a less strong one.


Q: Pag 3, "discussion evidence(s) of the existence of multiple concerns being addressed": please make a case for this conclusion.

A: Our motivating example is a case for this kind of conclusion.


Q: Pag. 7: "These results confirm "...It would be better to say "indicate" or something like it. Avoid "huge"

A: We thank the reviewer for the suggestion, we will address this on the final version of the paper.


Q: How does the result for low and high-level smells could change the conclusions?

A: Although we considered low and high-level smells as symptom categories[22] rather than analyzing each type of smell in particular. However, we agree that analysis by smell type can reveal additional observations, but since we have smells as part of our symptoms, our conclusions would not change much. As mentioned by all reviewers, we have applied an appropriate statistical method to investigate the symptoms that may have a relationship with design decay.


Q: Is there a good reason for building the argument around design decay, instead of a more neutral account of design impact?

A: RQ1 was built around the design impact approach. However, if our approach was building the argument around design impact (regardless of the positive/negative effect), we wouldn’t be able to separate the ‘good’ and ‘bad’ behaviors.


Q: Which numbers from the statistical analysis could enrich the discussion?

A: About statistical analysis, we could argue over the odds ratio of the metrics on the Multiple Logistic Analysis; this ratio could fortify the results of some metrics. However, as we aimed to understand which aspects would be better to work as indicators of design decay, we thought that these odds ratios would simply rank the metrics, information that can be clearly seen on the tables, undermining the importance of the aspects. In order words, we would basically rank which metric has a higher power of indicate the design decay inside each aspects. However, since each metric only has this odds ratio in the presence of the others in the model, saying that this metric alone would be a better fit for this type of analysis would only be true inside this model alone.


Q: Do you think metrics like the number of snippets and words in a discussion truly embody content?

A: Our metrics selection was based on a set of related studies (Sec2.3). Moreover, Number of Snippets and Number of Words in Discussion indeed have their value, since they help us to identify certain discussion content aspects that may lead to design decay. Moreover, we observed that at least the Number of Words in Discussion worked as an indicator of increase in design decay. Good point: the addition of metrics to fully represent discussion content dimensions is certainly part of our future work; the purpose of present study was to first reveal whether aspects may play a role in design decay.

