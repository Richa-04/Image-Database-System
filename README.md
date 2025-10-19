# Image Database System

## Feature Descriptors
`{cm, elbp, hog}`

## Image Types
`{cc, con, emboss, jitter, neg, noise1, noise2, original, poster, rot, smooth, stipple}`  
*(According to the current dataset. We haven’t made any assumptions about the image type name and hence it can differ based on the dataset.)*

## Subject
`[1-40]` (string)

## Sample ID
`[1-10]` (string)

## Dimensionality Reduction Technique Used
`SVD`

## Classifier
`{decision_tree, ppr, svm}`

---

## Task 1
**Command Syntax:**
```bash
python task1.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -qf [query_images_folder_path] -c [classifier]
python task1.py -fp 'train_set/500' -f cm -k 10 -qf 'test_set/100' -c ppr
```

## Task 2
**Command Syntax:**
```bash
python task2.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -qf [query_images_folder_path] -c [classifier]
python task2.py -fp 'train_set/500' -f cm -k 10 -qf 'test_set/100' -c ppr
```

## Task 3
**Command Syntax:**
```bash
python task3.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -qf [query_images_folder_path] -c [classifier]
python task3.py -fp 'train_set/500' -f cm -k 10 -qf 'test_set/100' -c ppr
```

## Task 4
**Command Syntax:**
```bash
python task4.py -fp [folder_path] -f [feature_descriptor] -l [number_of_layers] -k [latent_semantics_num] -kh [number_of_hash_functions_per_layer]
python task4.py -fp "all" -f elbp -l 5 -k "all" -kh 10
```

## Task 5
**Command Syntax:**
```bash
python task5.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -b [bits_per_dimension]
python task5.py -fp '4000' -f cm -k -1 -b 3
```

## Task 6, 7, 8
**Command Syntax:**
```bash
python task6_7_8.py
python task6_7_8.py
python task6_7_8.py

500
index_lsh_cm_-1_5_9.json
500/image-cc-1-1.png
