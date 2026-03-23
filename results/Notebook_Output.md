# Task 1

## visiualise 

Image data directory: ./data/oxford-iiit-pet
Total samples: 3680
Number of classes: 37
Classes: ['Abyssinian', 'American Bulldog', 'American Pit Bull Terrier', 'Basset Hound', 'Beagle', 'Bengal', 'Birman', 'Bombay', 'Boxer', 'British Shorthair', 'Chihuahua', 'Egyptian Mau', 'English Cocker Spaniel', 'English Setter', 'German Shorthaired', 'Great Pyrenees', 'Havanese', 'Japanese Chin', 'Keeshond', 'Leonberger', 'Maine Coon', 'Miniature Pinscher', 'Newfoundland', 'Persian', 'Pomeranian', 'Pug', 'Ragdoll', 'Russian Blue', 'Saint Bernard', 'Samoyed', 'Scottish Terrier', 'Shiba Inu', 'Siamese', 'Sphynx', 'Staffordshire Bull Terrier', 'Wheaten Terrier', 'Yorkshire Terrier']

Samples per class:
  Abyssinian: 100
  American Bulldog: 100
  American Pit Bull Terrier: 100
  Basset Hound: 100
  Beagle: 100
  Bengal: 100
  Birman: 100
  Bombay: 96
  Boxer: 100
  British Shorthair: 100
  Chihuahua: 100
  Egyptian Mau: 93
  English Cocker Spaniel: 96
  English Setter: 100
  German Shorthaired: 100
  Great Pyrenees: 100
  Havanese: 100
  Japanese Chin: 100
  Keeshond: 100
  Leonberger: 100
  Maine Coon: 100
  Miniature Pinscher: 100
  Newfoundland: 96
  Persian: 100
  Pomeranian: 100
  Pug: 100
  Ragdoll: 100
  Russian Blue: 100
  Saint Bernard: 100
  Samoyed: 100
  Scottish Terrier: 100
  Shiba Inu: 100
  Siamese: 99
  Sphynx: 100
  Staffordshire Bull Terrier: 100
  Wheaten Terrier: 100
  Yorkshire Terrier: 100

image shown in onefromeachclass.png

## splitting operations 
Total samples: 3680
Train samples: 2576
Validation samples: 552
Test samples: 552
Check total: 3680
15 % of data: 552.0

# Task 2

## extract descriptors
Total training descriptors stacked: (951578, 32)

Extracting train descriptors (with labels)...
Extracting val descriptors...
Extracting test descriptors...

## fit minibatch
Fitting MiniBatchKMeans with K=100...
  Train: (2576, 100), Val: (552, 100), Test: (552, 100)

Fitting MiniBatchKMeans with K=300...
  Train: (2576, 300), Val: (552, 300), Test: (552, 300)

Fitting MiniBatchKMeans with K=500...
  Train: (2576, 500), Val: (552, 500), Test: (552, 500)

# Task 3

## computer info
Manual GPU toggle: True
CUDA available: True
Selected device: cuda
CUDA device count: 1
Current device: 0
Device name: NVIDIA GeForce GTX 1650


## tune boosted classifier 
 Tuning GBC for K=100
Fitting 3 folds for each of 10 candidates, totalling 30 fits
  Best params   : {'subsample': 0.8, 'n_estimators': 200, 'max_depth': 4, 'learning_rate': 0.2}
  CV accuracy   : 0.0850
  Val accuracy  : 0.0833
  Val precision : 0.0760
  Val recall    : 0.0834
  Val F1 score  : 0.0781

 Tuning GBC for K=300
Fitting 3 folds for each of 10 candidates, totalling 30 fits
  Best params   : {'subsample': 0.8, 'n_estimators': 200, 'max_depth': 4, 'learning_rate': 0.2}
  CV accuracy   : 0.0905
  Val accuracy  : 0.1123
  Val precision : 0.1041
  Val recall    : 0.1122
  Val F1 score  : 0.1055

 Tuning GBC for K=500
Fitting 3 folds for each of 10 candidates, totalling 30 fits
  Best params   : {'subsample': 0.8, 'n_estimators': 200, 'max_depth': 4, 'learning_rate': 0.2}
  CV accuracy   : 0.0978
  Val accuracy  : 0.1087
  Val precision : 0.1110
  Val recall    : 0.1089
  Val F1 score  : 0.1058

    K |   CV acc |  Val acc | Val prec |  Val rec |   Val F1
  100 |   0.0850 |   0.0833 |   0.0760 |   0.0834 |   0.0781
  300 |   0.0905 |   0.1123 |   0.1041 |   0.1122 |   0.1055
  500 |   0.0978 |   0.1087 |   0.1110 |   0.1089 |   0.1058

## eval on test set

Best K: 300
Accuracy: 0.0960
Macro F1: 0.0928
Weighted F1: 0.0927
Classification report:
              precision    recall  f1-score   support

           0       0.00      0.00      0.00        15
           1       0.17      0.20      0.18        15
           2       0.08      0.07      0.07        15
           3       0.11      0.13      0.12        15
           4       0.09      0.07      0.08        15
           5       0.20      0.27      0.23        15
           6       0.16      0.20      0.18        15
           7       0.33      0.36      0.34        14
           8       0.11      0.13      0.12        15
           9       0.18      0.13      0.15        15
          10       0.00      0.00      0.00        15
          11       0.00      0.00      0.00        14
          12       0.00      0.00      0.00        14
          13       0.00      0.00      0.00        15
          14       0.07      0.07      0.07        15
          15       0.12      0.13      0.12        15
          16       0.00      0.00      0.00        15
          17       0.12      0.13      0.13        15
          18       0.15      0.13      0.14        15
          19       0.00      0.00      0.00        15
          20       0.00      0.00      0.00        15
          21       0.12      0.13      0.13        15
          22       0.19      0.27      0.22        15
          23       0.11      0.13      0.12        15
          24       0.20      0.20      0.20        15
          25       0.08      0.07      0.07        15
          26       0.00      0.00      0.00        15
          27       0.07      0.07      0.07        15
          28       0.15      0.13      0.14        15
          29       0.08      0.07      0.07        15
          30       0.00      0.00      0.00        15
          31       0.14      0.07      0.09        15
          32       0.12      0.13      0.12        15
          33       0.00      0.00      0.00        15
          34       0.05      0.07      0.05        15
          35       0.05      0.07      0.05        15
          36       0.15      0.13      0.14        15

    accuracy                           0.10       552
   macro avg       0.09      0.10      0.09       552
weighted avg       0.09      0.10      0.09       552

## confusion matrix

shown in normalisedconfusionMatrix

# Task 4 and 5

## classes and model output

Using num_classes=37
Linear(in_features=1024, out_features=37, bias=True)

## torch shape 

torch.Size([1, 224, 224])

## converting images

before: torch.Size([32, 1, 224, 224])
after:  torch.Size([32, 3, 224, 224])

## first model output 

Epoch 1/8 | Train Loss: 3.5028 | Train Acc: 0.0703 | Val Loss: 3.2880 | Val Acc: 0.1703 | Val Prec: 0.1920 | Val Rec: 0.1699 | Val F1: 0.1571
Epoch 2/8 | Train Loss: 3.1766 | Train Acc: 0.2446 | Val Loss: 2.9674 | Val Acc: 0.3533 | Val Prec: 0.3870 | Val Rec: 0.3530 | Val F1: 0.3356
Epoch 3/8 | Train Loss: 2.9022 | Train Acc: 0.3851 | Val Loss: 2.6795 | Val Acc: 0.4837 | Val Prec: 0.4973 | Val Rec: 0.4828 | Val F1: 0.4577
Epoch 4/8 | Train Loss: 2.6721 | Train Acc: 0.4790 | Val Loss: 2.4311 | Val Acc: 0.5580 | Val Prec: 0.6009 | Val Rec: 0.5578 | Val F1: 0.5426
Epoch 5/8 | Train Loss: 2.4846 | Train Acc: 0.5443 | Val Loss: 2.2399 | Val Acc: 0.6232 | Val Prec: 0.6526 | Val Rec: 0.6227 | Val F1: 0.6036
Epoch 6/8 | Train Loss: 2.2805 | Train Acc: 0.6068 | Val Loss: 2.0420 | Val Acc: 0.6649 | Val Prec: 0.6891 | Val Rec: 0.6641 | Val F1: 0.6541
Epoch 7/8 | Train Loss: 2.1279 | Train Acc: 0.6378 | Val Loss: 1.8897 | Val Acc: 0.6993 | Val Prec: 0.7183 | Val Rec: 0.6991 | Val F1: 0.6904
Epoch 8/8 | Train Loss: 1.9963 | Train Acc: 0.6712 | Val Loss: 1.7593 | Val Acc: 0.7029 | Val Prec: 0.7177 | Val Rec: 0.7030 | Val F1: 0.6917

Baseline validation metrics
Accuracy:  0.7029
Precision: 0.7177
Recall:    0.7030
F1 score:  0.6917

Baseline test metrics
Accuracy:  0.7717
Precision: 0.7901
Recall:    0.7719
F1 score:  0.7616

## augmented shaping

Augmented loaders ready:
Train batches: 81 | Val batches: 18 | Test batches: 18

## augmented output

Epoch 1/8 | Train Loss: 3.5637 | Train Acc: 0.0520 | Val Loss: 3.4092 | Val Acc: 0.1051 | Val Prec: 0.0902 | Val Rec: 0.1053 | Val F1: 0.0878
Epoch 2/8 | Train Loss: 3.3486 | Train Acc: 0.1277 | Val Loss: 3.2047 | Val Acc: 0.2065 | Val Prec: 0.2324 | Val Rec: 0.2066 | Val F1: 0.1909
Epoch 3/8 | Train Loss: 3.1583 | Train Acc: 0.2333 | Val Loss: 3.0084 | Val Acc: 0.3406 | Val Prec: 0.3799 | Val Rec: 0.3411 | Val F1: 0.3269
Epoch 4/8 | Train Loss: 2.9884 | Train Acc: 0.3331 | Val Loss: 2.8298 | Val Acc: 0.4312 | Val Prec: 0.4451 | Val Rec: 0.4310 | Val F1: 0.4156
Epoch 5/8 | Train Loss: 2.8439 | Train Acc: 0.3870 | Val Loss: 2.6773 | Val Acc: 0.4909 | Val Prec: 0.5313 | Val Rec: 0.4907 | Val F1: 0.4751
Epoch 6/8 | Train Loss: 2.6966 | Train Acc: 0.4449 | Val Loss: 2.5322 | Val Acc: 0.5598 | Val Prec: 0.5836 | Val Rec: 0.5598 | Val F1: 0.5463
Epoch 7/8 | Train Loss: 2.5767 | Train Acc: 0.4973 | Val Loss: 2.3999 | Val Acc: 0.5942 | Val Prec: 0.6206 | Val Rec: 0.5942 | Val F1: 0.5798
Epoch 8/8 | Train Loss: 2.4625 | Train Acc: 0.5260 | Val Loss: 2.2643 | Val Acc: 0.6504 | Val Prec: 0.6754 | Val Rec: 0.6501 | Val F1: 0.6382

Augmented validation metrics
Accuracy:  0.6504
Precision: 0.6754
Recall:    0.6501
F1 score:  0.6382

Augmented test metrics
Accuracy:  0.6957
Precision: 0.7051
Recall:    0.6955
F1 score:  0.6861

Comparison (test split)
Baseline accuracy:  0.7717
Augmented accuracy: 0.6957
Baseline precision:  0.7901
Augmented precision: 0.7051
Baseline recall:  0.7719
Augmented recall: 0.6955
Baseline F1:  0.7616
Augmented F1: 0.6861

