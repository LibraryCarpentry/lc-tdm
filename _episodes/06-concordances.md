---
title: "Tokens in Context: Concordance Lists"
teaching: 0
exercises: 0
questions:
- "What is a concordance list?"
- "How can a concordance list be created for a particular search term?"
objectives:
- "Understand what a concordance list is."
- "Learn how to create one."
keypoints:
- "A concordance list is a list of all contexts in which a particular token appears in a corpus or text."
- "A concordance list can be created using the ``concordance()``` method of the ```Text``` class in NLTK."
---

## Concordance list for a text collection

Next, we will display concordances for a particular token, i.e. all contexts a particular token appears in. We can do this using the ```Text``` class in NLTK's ```text``` package. We can represent our list of lowercased tokens in the document collection loaded previously using the ```Text``` class. The concordance list of a token can be displayed using the ```concordance()``` method on this class as shown below.

```python
from nltk.text import Text
t = Text(lower_india_tokens)
t.concordance('woman')
```

```
Displaying 20 of 20 matches:
s of age , a sweeper , who married a woman who had leprosy , and at the age of
e of sitabu , aged 40 , a muhammadan woman . her grand- father and father were
ung man deliberately married a leper woman , and became himself a leper at the
contrary . in no . 6 a man marries a woman whose grandfather and father had bee
 lepers . in no . 10 a man marries a woman whose father had died of leprosy . i
applies to these cases . in no . 2 a woman marries a man whose father and elder
n in the case of a man who marries a woman of notoriously leper family . in no
toriously leper family . in no . 5 a woman marries a man whose elder brother wa
d continued to cohabit with a native woman after she had been attacked with lep
isen from intermarriage of a man and woman in both of whom leprosy was heredita
s a leper ; he is now married to the woman , and they both live in the asylum .
een accompanied by a healthy looking woman , and by this means , although all h
editary transmission . in one case a woman got the disease about two years afte
 passed their thirtieth year , one a woman about 25 years of age , and the seve
 fracture of femur in middle third . woman well nourished and skin healthy , no
 ; had a brother with same disease . woman recovered and able to move about ; o
re or less related to each other . a woman got leprosy first from a leprous hus
s village assured me that before the woman returned home after her husband 's d
against it . this case was that of a woman with two leprous children , aged abo
ions had been lepers , who married a woman with tubercular leprosy , he being a
 ```
 {: .output}

 In the output for the next bit of code which creates a concordance list for the word "he", we can see that there are many more results in the list than displayed on screen (```Displaying 25 of 170 matches```). The ```concordance()``` method only prints the first 25 results by default (or less if there are less).

```python
t = Text(lower_india_tokens)
t.concordance('he')
```

```
Displaying 25 of 170 matches:
leprosy treated by gurjun oil , which he was able to watch for a length of tim
 diminished . during these two months he gained three pounds in weight , which
does not seem much , considering that he did no work and was fairly well fed o
se from jail on the 23rd january 1876 he was again suffering from the sores th
n 5th and died on 20th october 1875 . he was seriously ill when he was brought
ober 1875 . he was seriously ill when he was brought to the hospital , and cou
itted on the 8th september 1875 , and he went home of his own accord on 20th d
is own accord on 20th december 1875 . he was much improved under treat- ment b
evalence of leprosy in the district , he had had but very few opportunities of
even half this number . the natives , he says , call every chronic skin diseas
in the legs , the feet and the ears . he has perfect taste , hearing , sight a
te laboured under it . the leper says he was quite free from leprosy until he
 he was quite free from leprosy until he associated with this man and took din
prosy of 15 years ' standing . states he had first gonorrha , then syphillis ,
been affected 6 years ; was well when he married . had two children who died ,
ve of the territory beyond the hubb . he had lost some parts of his hands and
 feet previous to his incarceration . he was treated with large doses of iodid
ease be removed . dr. bloomfield says he sent two interesting specimens of thi
ant medical college museum , but that he never heard of them after , nor did h
e never heard of them after , nor did he discover them in the museum when he v
d he discover them in the museum when he visited it afterwards . should the di
er and elder sister were lepers , and he himself became a leper at 30 years of
. his elder brother was a leper , and he himself became a leper at 32 . his wi
one year after she was affected , and he suffered from leprosy . no . 7.-the c
ied . afterwards , at the age of 43 , he him- self was attacked with leprosy .
```
{: .output}

You can specify the number of lines using an additional ```lines``` parameter, e.g.:

```python
t.concordance('he',lines=170)
```

<!--
> ## Task
>
> Create a concordance list for a different search term, e.g. the word "great" or choose your own.
>
> > ## Solution
> >
> > ~~~
> > t.concordance('great')
> > ~~~
> {: .solution}
{: .challenge}-->

{% include links.md %}
