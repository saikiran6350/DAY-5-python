# DAY-5-python
import pandas as pd
import numpy as np
​
datascience = ['python', 'sql', 'r']
df = pd.DataFrame(datascience)
print(df)
        0
0  python
1     sql
2       r
storelist = [['vivo',25000],['redmi',18000],['oppo',35000],['oneplus',30000]]
df = pd.DataFrame(storelist,columns=['mobile', 'price'])
​
df
mobile	price
0	vivo	25000
1	redmi	18000
2	oppo	35000
3	oneplus	30000
storedata = {'product':['coffee','milk','tea','boost'],
            'sales':[40000,50000,44000,20000]}
df = pd.DataFrame(storedata, index=['A', 'B', 'C', 'D'])
print(df)
  product  sales
A  coffee  40000
B    milk  50000
C     tea  44000
D   boost  20000
df = pd.read_csv('D:\ADMISSIONS.csv')
df
row_id	subject_id	hadm_id	admittime	dischtime	deathtime	admission_type	admission_location	discharge_location	insurance	language	religion	marital_status	ethnicity	edregtime	edouttime	diagnosis	hospital_expire_flag	has_chartevents_data
0	12258	10006	142345	2164-10-23 21:09:00	2164-11-01 17:15:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME HEALTH CARE	Medicare	NaN	CATHOLIC	SEPARATED	BLACK/AFRICAN AMERICAN	2164-10-23 16:43:00	2164-10-23 23:00:00	SEPSIS	0	1
1	12263	10011	105331	2126-08-14 22:32:00	2126-08-28 18:59:00	2126-08-28 18:59:00	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	DEAD/EXPIRED	Private	NaN	CATHOLIC	SINGLE	UNKNOWN/NOT SPECIFIED	NaN	NaN	HEPATITIS B	1	1
2	12265	10013	165520	2125-10-04 23:36:00	2125-10-07 15:13:00	2125-10-07 15:13:00	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	DEAD/EXPIRED	Medicare	NaN	CATHOLIC	NaN	UNKNOWN/NOT SPECIFIED	NaN	NaN	SEPSIS	1	1
3	12269	10017	199207	2149-05-26 17:19:00	2149-06-03 18:42:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	SNF	Medicare	NaN	CATHOLIC	DIVORCED	WHITE	2149-05-26 12:08:00	2149-05-26 19:45:00	HUMERAL FRACTURE	0	1
4	12270	10019	177759	2163-05-14 20:43:00	2163-05-15 12:00:00	2163-05-15 12:00:00	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	DEAD/EXPIRED	Medicare	NaN	CATHOLIC	DIVORCED	WHITE	NaN	NaN	ALCOHOLIC HEPATITIS	1	1
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
124	41055	44083	198330	2112-05-28 15:45:00	2112-06-07 16:50:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME	Private	ENGL	CATHOLIC	SINGLE	WHITE	2112-05-28 13:16:00	2112-05-28 17:30:00	PERICARDIAL EFFUSION	0	1
125	41070	44154	174245	2178-05-14 20:29:00	2178-05-15 09:45:00	2178-05-15 09:45:00	EMERGENCY	EMERGENCY ROOM ADMIT	DEAD/EXPIRED	Medicare	ENGL	PROTESTANT QUAKER	MARRIED	WHITE	2178-05-14 17:37:00	2178-05-14 22:08:00	ALTERED MENTAL STATUS	1	1
126	41087	44212	163189	2123-11-24 14:14:00	2123-12-30 14:31:00	NaN	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	REHAB/DISTINCT PART HOSP	Medicare	ENGL	UNOBTAINABLE	SINGLE	BLACK/AFRICAN AMERICAN	NaN	NaN	ACUTE RESPIRATORY DISTRESS SYNDROME;ACUTE RENA...	0	1
127	41090	44222	192189	2180-07-19 06:55:00	2180-07-20 13:00:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME	Medicare	ENGL	CATHOLIC	SINGLE	WHITE	2180-07-19 04:50:00	2180-07-19 08:23:00	BRADYCARDIA	0	1
128	41092	44228	103379	2170-12-15 03:14:00	2170-12-24 18:00:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME HEALTH CARE	Private	ENGL	NOT SPECIFIED	SINGLE	WHITE	2170-12-15 02:22:00	2170-12-15 05:25:00	CHOLANGITIS	0	1
129 rows × 19 columns

df.head()
row_id	subject_id	hadm_id	admittime	dischtime	deathtime	admission_type	admission_location	discharge_location	insurance	language	religion	marital_status	ethnicity	edregtime	edouttime	diagnosis	hospital_expire_flag	has_chartevents_data
0	12258	10006	142345	2164-10-23 21:09:00	2164-11-01 17:15:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME HEALTH CARE	Medicare	NaN	CATHOLIC	SEPARATED	BLACK/AFRICAN AMERICAN	2164-10-23 16:43:00	2164-10-23 23:00:00	SEPSIS	0	1
1	12263	10011	105331	2126-08-14 22:32:00	2126-08-28 18:59:00	2126-08-28 18:59:00	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	DEAD/EXPIRED	Private	NaN	CATHOLIC	SINGLE	UNKNOWN/NOT SPECIFIED	NaN	NaN	HEPATITIS B	1	1
2	12265	10013	165520	2125-10-04 23:36:00	2125-10-07 15:13:00	2125-10-07 15:13:00	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	DEAD/EXPIRED	Medicare	NaN	CATHOLIC	NaN	UNKNOWN/NOT SPECIFIED	NaN	NaN	SEPSIS	1	1
3	12269	10017	199207	2149-05-26 17:19:00	2149-06-03 18:42:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	SNF	Medicare	NaN	CATHOLIC	DIVORCED	WHITE	2149-05-26 12:08:00	2149-05-26 19:45:00	HUMERAL FRACTURE	0	1
4	12270	10019	177759	2163-05-14 20:43:00	2163-05-15 12:00:00	2163-05-15 12:00:00	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	DEAD/EXPIRED	Medicare	NaN	CATHOLIC	DIVORCED	WHITE	NaN	NaN	ALCOHOLIC HEPATITIS	1	1
df.tail()
row_id	subject_id	hadm_id	admittime	dischtime	deathtime	admission_type	admission_location	discharge_location	insurance	language	religion	marital_status	ethnicity	edregtime	edouttime	diagnosis	hospital_expire_flag	has_chartevents_data
124	41055	44083	198330	2112-05-28 15:45:00	2112-06-07 16:50:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME	Private	ENGL	CATHOLIC	SINGLE	WHITE	2112-05-28 13:16:00	2112-05-28 17:30:00	PERICARDIAL EFFUSION	0	1
125	41070	44154	174245	2178-05-14 20:29:00	2178-05-15 09:45:00	2178-05-15 09:45:00	EMERGENCY	EMERGENCY ROOM ADMIT	DEAD/EXPIRED	Medicare	ENGL	PROTESTANT QUAKER	MARRIED	WHITE	2178-05-14 17:37:00	2178-05-14 22:08:00	ALTERED MENTAL STATUS	1	1
126	41087	44212	163189	2123-11-24 14:14:00	2123-12-30 14:31:00	NaN	EMERGENCY	TRANSFER FROM HOSP/EXTRAM	REHAB/DISTINCT PART HOSP	Medicare	ENGL	UNOBTAINABLE	SINGLE	BLACK/AFRICAN AMERICAN	NaN	NaN	ACUTE RESPIRATORY DISTRESS SYNDROME;ACUTE RENA...	0	1
127	41090	44222	192189	2180-07-19 06:55:00	2180-07-20 13:00:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME	Medicare	ENGL	CATHOLIC	SINGLE	WHITE	2180-07-19 04:50:00	2180-07-19 08:23:00	BRADYCARDIA	0	1
128	41092	44228	103379	2170-12-15 03:14:00	2170-12-24 18:00:00	NaN	EMERGENCY	EMERGENCY ROOM ADMIT	HOME HEALTH CARE	Private	ENGL	NOT SPECIFIED	SINGLE	WHITE	2170-12-15 02:22:00	2170-12-15 05:25:00	CHOLANGITIS	0	1
df.dtypes
row_id                   int64
subject_id               int64
hadm_id                  int64
admittime               object
dischtime               object
deathtime               object
admission_type          object
admission_location      object
discharge_location      object
insurance               object
language                object
religion                object
marital_status          object
ethnicity               object
edregtime               object
edouttime               object
diagnosis               object
hospital_expire_flag     int64
has_chartevents_data     int64
dtype: object
df.shape
(129, 19)
df.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 129 entries, 0 to 128
Data columns (total 19 columns):
 #   Column                Non-Null Count  Dtype 
---  ------                --------------  ----- 
 0   row_id                129 non-null    int64 
 1   subject_id            129 non-null    int64 
 2   hadm_id               129 non-null    int64 
 3   admittime             129 non-null    object
 4   dischtime             129 non-null    object
 5   deathtime             40 non-null     object
 6   admission_type        129 non-null    object
 7   admission_location    129 non-null    object
 8   discharge_location    129 non-null    object
 9   insurance             129 non-null    object
 10  language              81 non-null     object
 11  religion              128 non-null    object
 12  marital_status        113 non-null    object
 13  ethnicity             129 non-null    object
 14  edregtime             92 non-null     object
 15  edouttime             92 non-null     object
 16  diagnosis             129 non-null    object
 17  hospital_expire_flag  129 non-null    int64 
 18  has_chartevents_data  129 non-null    int64 
dtypes: int64(5), object(14)
memory usage: 19.3+ KB
'df = pd.read_csv('D:\DIAGNOSES_ICD.csv')
df
row_id	subject_id	hadm_id	seq_num	icd9_code
0	112344	10006	142345	1	99591
1	112345	10006	142345	2	99662
2	112346	10006	142345	3	5672
3	112347	10006	142345	4	40391
4	112348	10006	142345	5	42731
...	...	...	...	...	...
1756	397673	44228	103379	7	1975
1757	397674	44228	103379	8	45182
1758	397675	44228	103379	9	99592
1759	397676	44228	103379	10	2449
1760	397677	44228	103379	11	2859
1761 rows × 5 columns

df.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 1761 entries, 0 to 1760
Data columns (total 5 columns):
 #   Column      Non-Null Count  Dtype 
---  ------      --------------  ----- 
 0   row_id      1761 non-null   int64 
 1   subject_id  1761 non-null   int64 
 2   hadm_id     1761 non-null   int64 
 3   seq_num     1761 non-null   int64 
 4   icd9_code   1761 non-null   object
dtypes: int64(4), object(1)
memory usage: 68.9+ KB
df.tail()
row_id	subject_id	hadm_id	seq_num	icd9_code
1756	397673	44228	103379	7	1975
1757	397674	44228	103379	8	45182
1758	397675	44228	103379	9	99592
1759	397676	44228	103379	10	2449
1760	397677	44228	103379	11	2859
df.head()
row_id	subject_id	hadm_id	seq_num	icd9_code
0	112344	10006	142345	1	99591
1	112345	10006	142345	2	99662
2	112346	10006	142345	3	5672
3	112347	10006	142345	4	40391
4	112348	10006	142345	5	42731
df.dtypes
row_id         int64
subject_id     int64
hadm_id        int64
seq_num        int64
icd9_code     object
dtype: object
df.shape
(1761, 5)
​
