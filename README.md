# resnext50_for_leaves_classification
比赛是沐神动手学深度学习课程的树叶分类比赛，模型是最方便的resnext50，方法是微调一下即可。（虽然代码还是copy kaggle上的 但是改了一些加了一些注释和配置图片方便像我一样的新手从修改文件路径这样开始QAQnum_workers真的巨可恶）


## 第一版的超参数和实验结果
1.  learning_rate = 3e-4；weight_decay = 1e-3；batch_size=16；
    GPU1080显存占了4g左右，CPU3600占用率60%能飙到4GHz，45min跑了12个epoch;valid=saving model with acc 0.912;![image](https://user- images.githubusercontent.com/89777846/226321420-8232ac85-6e68-46ca-82cc-e98d2188288a.png)

    贴一个leaderboard
![image](https://user-images.githubusercontent.com/89777846/226322136-7d00ccef-715e-4b13-89bc-91f78207a7cb.png)
    感觉还不错，毕竟只跑了一会，
    之后改进的方向：更多的数据增强，多跑几次，调一下参数
备注：kaggle自带的环境给的是一张p100 16g  速度上确实不如1080，我大致比较一下时间上性能上只有1080的3/4的速度。但是架不住16g大显存和免费，其实人家真正的实力还得要多卡之类的，1080来偷袭我这个p100的老同志。
