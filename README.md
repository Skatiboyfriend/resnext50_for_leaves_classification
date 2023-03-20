# resnext50_for_leaves_classification
比赛是沐神动手学深度学习课程的树叶分类比赛，模型是最方便的resnext50，方法是微调一下即可。（虽然代码还是copy kaggle上的 但是改了一些加了一些注释和配置图片方便像我一样的新手从修改文件路径这样开始QAQnum_workers真的巨可恶）


##第一版的超参数
learning_rate = 3e-4；weight_decay = 1e-3；batch_size=16；
GPU1080显存占了4g左右，CPU3600占用率60%能飙到4GHz，45min跑了12个epoch;valid=saving model with acc 0.912;![image](https://user-images.githubusercontent.com/89777846/226321420-8232ac85-6e68-46ca-82cc-e98d2188288a.png)
