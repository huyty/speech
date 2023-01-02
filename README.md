# speech.ko
Korean read speech corpus (about 120 hours, 17GB) from National Institute of Korean Language (NIKL)

This repository cleans up NIKL corpus such as voiding unnecessary wav files, matching sampling rate, trimming silence, etc. Details are below.

## Location
http://www.korean.go.kr/front/board/boardStandardView.do?board_id=4&mn_id=17&b_seq=464

https://ithub.korean.go.kr/user/corpus/referenceManager.do

Once you download all corpus files from above, you will find the following zip files.

```
ls *.zip
3-1 #1 (20대 남성) 4-1.zip  3-2 #1 (30대 남성) 5-1.zip  3-2 #2 (40대 여성) 5-5.zip
3-1 #1 (20대 남성) 4-2.zip  3-2 #1 (30대 남성) 5-2.zip  3-3 #3 (50대 이상 남성여성) 6-1.zip
3-1 #1 (20대 남성) 4-3.zip  3-2 #1 (30대 남성) 5-3.zip  3-3 #3 (50대 이상 남성여성) 6-2.zip
3-1 #1 (20대 남성) 4-4.zip  3-2 #1 (30대 남성) 5-4.zip  3-3 #3 (50대 이상 남성여성) 6-3.zip
3-1 #2 (20대 여성) 5-1.zip  3-2 #1 (30대 남성) 5-5.zip  3-3 #3 (50대 이상 남성여성) 6-4.zip
3-1 #2 (20대 여성) 5-2.zip  3-2 #2 (40대 여성) 5-1.zip  3-3 #3 (50대 이상 남성여성) 6-5.zip
3-1 #2 (20대 여성) 5-3.zip  3-2 #2 (40대 여성) 5-2.zip  3-3 #3 (50대 이상 남성여성) 6-6.zip
3-1 #2 (20대 여성) 5-4.zip  3-2 #2 (40대 여성) 5-3.zip
3-1 #2 (20대 여성) 5-5.zip  3-2 #2 (40대 여성) 5-4.zip
```

Transcription file contains 19 topics with the following number of sentences.

| Topic  | # of sentence |
| ------ |:-------------:|
| 1      | 51            |
| 2      | 87            |
| 3      | 69            |
| 4      | 62            |
| 5      | 47            |
| 6      | 54            |
| 7      | 62            |
| 8      | 94            |
| 9      | 60            |
| 10     | 73            |
| 11     | 42            |
| 12     | 28            |
| 13     | 39            |
| 14     | 27            |
| 15     | 17            |
| 16     | 35            |
| 17     | 19            |
| 18     | 27            |
| 19     | 40            |
| Total  | 930           |

When unzipped, you will find speaker ids as follows.

| Gender | Speaker ID    | Age            |
|:------:|:-------------:|:--------------:|
| Female | fv01 to fv20  | 20s            |
| Female | fx01 to fx20  | 40s            |
| Female | fy01 to fy18  | Older than 50s |
| Female | fz05 to fz06  | Older than 50s |
| Male   | mv01 to mv20  | 20s            |
| Male   | mw01 to mw20  | 30s            |
| Male   | my01 to my11  | Older than 50s |
| Male   | mz01 to mz09  | Older than 50s |

## Dependencies
### [sox](http://sox.sourceforge.net/sox.html)
sox is used to check wav file info such as sampling rate and correct format, and used to convert sampling rate if necessary.
### [auditok](https://github.com/amsehili/auditok)
auditok is used to trim unnecessary silence in the beginning and in the end.

## Command

```
git clone https://github.com/homink/speech.ko.git
cd speech.ko
./run.sh --corpus ${corpus_location}
```

Cleaned and trimmed wav files will be found in \$\{corpus_location\}/trimmed_data.
