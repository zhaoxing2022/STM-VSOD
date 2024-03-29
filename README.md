
# [Motion-aware Memory Network for Fast Video Salient Object Detection]()

This article is still under review. The training code, metric calculations (in Python), and other information will be organized and commented in detail later :).
## Requirements
Packages not included in Anaconda:
* Pytorch, Torchvision
* OpenCV-python
* [Pytorch-OpCounter](https://github.com/Lyken17/pytorch-OpCounter) (If you want to count the MACs / FLOPs of the model.)
## Test
1. Download the [weights](https://drive.google.com/file/d/11QKyj0INLx6xWs-8c_1BdC3SSxG7kHTa/view?usp=sharing). You can download our [pre-calculated saliency maps](https://drive.google.com/file/d/1T2uoPS0PBWeWD8n4b0BWVhc_4soYM_Nm/view?usp=sharing) and results from [other methods](https://drive.google.com/drive/folders/1CdSj0IR9-Rvnj-7zeUnYv05ii4jZ6UGj?usp=sharing) I've collected on Google Drive.
2. Align the dataset folder directory with **[dataset/test](dataset/test)**. Because we don't read the labels during the testing stage, you can test any videos.
3. Modify the parameters at the top of **[test/test.py](test/test.py)**, I have provided detailed comments, you need to change it to your own configuration.
4. ```CUDA_VISIBLE_DEVICES=xxxx python test.py```. Our model supports multiple GPUs and batch size > 1 during inference. Our model is highly efficient.
5. ```CUDA_VISIBLE_DEVICES=0 python speed.py```. The inference speed will be evaluated on your machine with one GPU and one batch. If you want to count the MACs / FLOPs of the model, uncomment the code in this file.