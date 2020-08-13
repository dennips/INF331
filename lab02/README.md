# Lab02 - Data Flow & Mensagens

## Tarefa sobre catálogo de componentes

[Notebook](notebook/notebook_dennis.ipynb)

## Tarefa Web Components 1
~~~html
<dcc-trigger
label="Mundo"
action = "noticia/mundo/politica"
value = "Notícias sobre política no Mundo">
</dcc-trigger>

<dcc-trigger
label="Brasil P"
action = "noticia/brasil/politica"
value = "Notícias sobre política no Brasil"/>
</dcc-trigger>

<dcc-trigger
label="Brasil E"
action = "noticia/brasil/esporte"
value = "Notícias sobre esporte no Brasil"/>
</dcc-trigger>

<dcc-trigger
label="Bahia"
action = "noticia/bahia/esporte"
value = "Notícias sobre esporte na Bahia"/>
</dcc-trigger>

<dcc-lively-talk 
character="doctor"
speech="Noticia: ">
<subscribe-dcc topic="noticia/+/politica"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk 
character="nurse"
speech="Noticia: ">
<subscribe-dcc topic="noticia/brasil/#"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk 
character="patient"
speech="Noticia: ">
<subscribe-dcc topic="noticia/#"></subscribe-dcc>
</dcc-lively-talk>
~~~

## Tarefa Web Components 2
~~~html
<dcc-trigger label="Science News" action="science">
</dcc-trigger>

<dcc-rss publish="rss/science" source="https://www.wired.com/category/science/feed">
  <subscribe-dcc topic="science" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-trigger label="Design News" action="design">
</dcc-trigger>

<dcc-rss publish="rss/design" source="https://www.wired.com/category/design/feed">
  <subscribe-dcc topic="design" role="step"></subscribe-dcc>
</dcc-rss>


<dcc-aggregator publish="aggregate/science" quantity="3">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-aggregator>

<dcc-lively-talk id="doctor"
                 duration="0s"
                 character="doctor"
                 speech="News ">
  <subscribe-dcc topic="aggregate/science"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk id="nurse"
                 duration="0s"
                 character="nurse"
                 speech="News ">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk id="patient"
                 duration="0s"
                 character="patient"
                 speech="News ">
  <subscribe-dcc topic="rss/design"></subscribe-dcc>
</dcc-lively-talk>
~~~