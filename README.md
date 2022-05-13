# TextCalssificationUsingBERT

# Team member 
####
1-  محمود رمضان احمد عبده               20180557
####
2-  احمد ايهاب محمد محمد                20180024
####
3-   كريم عوض مكرم بهجات                20180434
####
4-   مصطفي حمدي خليل محمود              20180593
####
5-   محمود عبد الرحمن محمد محمود       20180565


## Fine-Grained Hate Speech Detection on Arabic Twitter
Disclaimer: Some examples have offensive language and hate speech!



Detecting offensive language and hate speech has gained increasing interest from researchers in NLP and computational social sciences communities in the past few years. For example, at the ACL 2021 main conference, there were 3 papers about offensive language and 10 papers about hate speech (https://aclanthology.org/events/acl-2021/). Additionally, there was a dedicated workshop on online abuse and harm with a shared task on hateful memes (https://www.workshopononlineabuse.com/home#h.czplpodomjyq).



Detecting offensive language and hate speech is very important for online safety, content moderation, etc. Studies show that the presence of hate speech may be connected to hate crimes (Hate Speech Watch, 2014).



Given the success of the shared task on Arabic offensive language detection at OSACT 2020 (https://edinburghnlp.inf.ed.ac.uk/workshops/OSACT4/), we decided to continue our effort to enhance the detection of offensive language and hate speech on Arabic Twitter. We share with the research community the largest annotated Arabic tweets without being biased towards specific topics, genres, or dialects. Each tweet is judged by 3 annotators using crowdsourcing for offensiveness. Offensive tweets were classified into one of the hate speech types: Race, Religion, Ideology, Disability, Social Class, and Gender. Also, annotators judged whether a tweet has vulgar language or violence.



Hate speech is defined as any kind of offensive language (insults, slurs, threats, encouraging violence, impolite language, etc.) that targets a person or a group of people based on common characteristics such as race/ethnicity/nationality, religion/belief, ideology, disability/disease, social class, gender, etc.



Hate Speech types in our dataset are:

HS1 (race/ethnicity/nationality). خطاب كراهية ضد العِرْق أو دولة معينة أو جنسية الدولة، مثلا: يا زنجي، في بلدك النساء عاهرات

HS2 (religion/belief). خطاب كراهية ضد الدين والمذهب، مثلا: دينك القذر

HS3 (ideology). خطاب كراهية ضد الانتماء الحزبي أو الفكري أو الرياضي، مثلا: أبوك شيوعي، ناديك الحقير

HS4 (disability/disease). خطاب كراهية ضد الإعاقة الجسدية، مثلا: يا معوق، يا قزم

HS5 (social class). خطاب كراهية ضد وظيفة أو جزء من المجتمع، مثلا: يا بواب، البدو متخلفين، أصله فلاح لا يفهم

HS6 (gender). خطاب كراهية ضد النوع (ذكر/أنثى)، مثلا: الله يأخذ الرجال، النساء صاروا بلا حياء



The corpus contains ~13K tweets in total: 35% are offensive and 11% are hate speech. Vulgar and violent tweets represent 1.5% and 0.7% of the whole corpus.



Percentages of offensive language and hate speech in the corpus are the highest among other corpora without using pre-specified keywords or selecting a specific domain.



After the competitions ended, details about the dataset were announced at: https://arxiv.org/pdf/2201.06723.pdf



We will have 3 shared subtasks:



Subtask A: Detect whether a tweet is offensive or not.

Labels for this task are: OFF (Offensive) or NOT_OFF (Not Offensive)

Example: الله يلعنه على هالسؤال (May God curse him for this question! )



Subtask B: Detect whether a tweet has hate speech or not.

Labels are: HS (Hate Speech) or NOT_HS (Not Hate Speech).

Subtask B is more challenging than Subtask A as 11% only of the tweets are labeled as hate speech.

Example: أنتم شعب متخلف (You are a retarded people)



## Dataset
Download training data from: https://alt.qcri.org/resources/OSACT2022/OSACT2022-sharedTask-train.txt

Download development data from: https://alt.qcri.org/resources/OSACT2022/OSACT2022-sharedTask-dev.txt

## Preprocessing 
we clean data set from any emotions and any labels like HS/NotHs tags and other tags 
##
We convert HS/Not HS to 0/1 number in dataset labels
##
We convert OFF/Not OFF tags to 0/1 number in dataset labels 
##
you can find the Preprocessing File in 
## Model 
we used MaraBert and is Deep Bidirectional Transofrmers For Arabic  from HuggingFace 
> https://huggingface.co/UBC-NLP/MARBERT
**MARBERT** is one of three models described in our **ACL 2021 paper** 
![Arabic-BERT-model-architecture](https://user-images.githubusercontent.com/95087747/168382695-77575676-ac0b-405b-abdd-84cc59dfcf32.png)
## Preformance Evaluation 
### Evaluate Task A
![OFF_NOTOFF](https://user-images.githubusercontent.com/95087747/168384425-21068f1a-a58e-40c4-9232-552747d629ef.PNG)

F1-score of Task A 88%

### Evaluate Task B 
![HSAndNotHS](https://user-images.githubusercontent.com/95087747/168384990-08b0e5ba-bc6f-4c15-8327-88e9e4842ea2.PNG)
F1-score of Task B 92%
