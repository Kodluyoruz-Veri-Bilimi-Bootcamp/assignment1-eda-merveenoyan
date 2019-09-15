
import numpy as np

import pandas as pd

data = pd.read_csv("C:/Users/betul/Desktop/assignment/athlete_events.csv")
data.head()
df=pd.DataFrame(data)
kadin=df.loc[df['Sex'] == "F"]
erkek=df.loc[df['Sex'] == "M"]
yearfemale=kadin.loc[kadin['Year']==1992]
yearmale=erkek.loc[erkek['Year']==1992]
minagef=yearfemale['Age'].min()
minagem=yearmale['Age'].min()


maletwelve=erkek.loc[erkek['Year']==2012]
malebasketball=maletwelve.loc[maletwelve['Sport']=="Basketball"]
percentagee=len(malebasketball)/len(maletwelve)

tennisf=kadin[(kadin.Year==2000) & (kadin.Sport =="Tennis")]
ortalama=tennisf['Height'].mean(axis=0,skipna=True)
stddev=tennisf['Height'].std(axis=0,skipna=True)


maxinyear=(df['Year']==2006)
maks=maxinyear.loc[maxinyear['Weight']==maxinyear['Weight'].max()]
spor=maks["Sport"]

john=df.loc[df['Name']=="John Aalberg"]
howmanytimes=john.Year.value_counts()
len(howmanytimes)


switzerland_medals=df.loc[(df.Team=="Switzerland") & (df.Year==2008) & (df.Medal=="Gold")]
switzerland_medals=switzerland_medals.Medal.value_counts()
len(switzerland_medals)


spain_medals=df.loc[(df['Team']=="Spain") & (df['Year']==2016) & (df.Medal.isna()==False)]
spain_medals=spain_medals.Medal.value_counts()
italy_medals=df.loc[(df['Team']=="Italy")& (df['Year']==2016) & (df.Medal.isna()==False)]
italy_medals=italy_medals.Medal.value_counts()
istrue=(len(spain_medals)<len(italy_medals))



atlantasummerr=df.loc[(df['City']=="Atlanta")&(df['Season']=="Summer")]
wintersquaw=df.loc[(df['City']=="Squaw Valley")&(df['Season'=="Winter"])]



eightysix=df.loc[df.Year==1986]
two=df.loc[df.Year==2002]

eightysix=eightysix.Sport.value_counts()
two=two.Sport.value_counts()
difference=abs(eightysix-two)

minage=df.Age.min()
maxage=df.Age.max()
eightolympics=df.loc[df['Year']==2008]
agegroup=pd.cut(x=eightolympics.Age, bins= [14.5,24.5,34.5,44.5,56],include_lowest=True)
counts=agegroup.value_counts()







