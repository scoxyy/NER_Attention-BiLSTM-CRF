# NER_Keras

###using keras + tensorflow for NER###

requirement：tensorflow == 1.14  ,keras = 2.2.0, keras-self-attention, keras_multi_head, keras_contrib

##Model

embedding + MultiHeadAttention + BiLSTM + CRF


## Data Set
中	O
华	O
人	O
民	O
共	O
和	O
国	O

data from MSRA

You can use yourself's  data, and need to change some code:
1.run.py:
row110 crf = CRF(7, sparse_target=True),because this data set has "O", "B-PER", "I-PER", "B-LOC", "I-LOC" ,"B-ORG", "I-ORG"
you can update "7" to any values based on your data set

2.data.py
row5 tag2label = {"O": 0,
             "B-PER": 1, "I-PER": 2,
             "B-LOC": 3, "I-LOC": 4,
             "B-ORG": 5, "I-ORG": 6
             }
you should update based on your data set

## Use

`python run.py --mode=train `

## Reference
[https://github.com/stephen-v/zh-NER-keras](https://github.com/jiangfeng13/NER_Keras)
