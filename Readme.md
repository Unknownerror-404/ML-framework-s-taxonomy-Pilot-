#Summary of the Study:

The following study compared six different types of data augmentation techniques namely AutoAugment, RandAugment, TrivialAugment, CutOut, CutMix and Mixup. 
These data augmentations were used to improve the performance of pretrained classifiers specifically MobileNetV2, MobileNetV3 and EfficientNetB0.
The results obtained from said training were tested against a smaller test set and averaged across ten seeds for reproducibility.
For further details on the experimentation and the produced results, we recommend visiting: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6773969
The paper present a comprehensive view of the motivations, experimental setup, observations, results, and conclusions inferred.
*Please note that the study being a pilot was conducted on a smaller data setup with substantially less compute*

#Information regarding the repository:

The following repository provides the results and code used for studying different classifiers and the utilization of data augmentation techniques to report increased or decreased performance within strabismus classification.
The repository holds the codes, results and outputs obtained from the initial experimentation with the aim of further assisting studies aiming on reproducing said results. 
Namely, the repository holds:
1. Codes:
  a] Autoaugment
  b] Cutmix
  c] Cutout
  d] Mixup
  e] RandAugment
  f] TrivialAugment

*Note that the base codes used for this study are present within files named as <Data_Augmentation> updated.py, Other files of the naming convention: <Data_Augmentation> corrupted.py/ <Data_Augmentation> only corrupted.py/ and the same are files used for other forms of tests performed under the same study, but having not been used should not be considered*

2. Helper functions:
   Numerous helper functions have been used within the experiments, however given that not all were used within the final pilot, the following summarizes the key ones:
     a] grad-cam_mobileNetV2.py -> Used for grad-cam results over MobileNetV2.
     b] grad-cam_mobileNetV3.py -> Used for grad-cam results over MobileNetV3.
     c] grad-cam_efficient_b0.py -> Used for grad-cam results over EfficientNetB0.
     d] brier_helper.py -> Used as a helper function when processing brier decomposition scores.
     e] delong.py -> Fast computes Delong scores.
     f] McNemar.py -> Used to calculated Mcnemar scores(Mid-p and Exact-p)
     g] resize_and_pad.py -> Used to preprocess images to model acceptable format of 224x224.
     f] roundoff.py -> Used to round off the results from Delong's test, McNemar's test and Brier Decomposition.

3. Results:
   Results included consist of McNemar, Delong, Brier's decomposition, and the base model result itself.
   a] Files of the format: <McNemar_*.json> provide the McNemar results of that particular model / Augmentation pair.
   b] Files of the format: <Delong*.json> provide the Delong results of that particular model / Augmentation pair.
   c] File formats: <*brier_decomposition*.json> provide the results of the model, data augmentation technique, and dataset over which the results were obtained.
   e] .npy: Numpy files based on their prefixes can be split into pred/prob, where the pred files hold the prediction made against a test sample while the prob file holds the probability of said prediction.
   
4] Grad-cam:
  During our study Grad-cam was extensively used for verification of key assumptions or produced results, as such the results from our varying tests (some not included within the paper or repo) have also been provided within 
  Brier_decomposition_result_folder.

# Note: Following the pilot, a standard study has also been conducted; the results from that study are present at: <Dummy_Repo>. As such this repository will not be updated unless the pilot study itself is being re-evaluated.
# For further updates/information the <Dummy_Repo> is recommended.
