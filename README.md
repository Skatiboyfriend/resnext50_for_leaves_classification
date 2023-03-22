# resnext50_for_leaves_classification
比赛是沐神动手学深度学习课程的树叶分类比赛，模型是最方便的resnext50，方法是微调一下即可。（虽然代码还是copy kaggle上的 但是改了一些加了一些注释和配置图片方便像我一样的新手从修改文件路径这样开始QAQnum_workers真的巨可恶）

## 写在开头的备注
机器配置：锐龙3600+索泰1080    如果是用kaggle自带的环境给的是一张p100 16g  速度上确实不如1080，我大致比较一下时间上性能上只有1080的3/4的速度。但是架不住16g大显存和免费，其实人家真正的实力还得要多卡之类的，1080来偷袭我这个p100的老同志。没卡的兄弟其实用kaggle自带的也完全够用。
自己是初学者，希望各位大佬多多指教
比赛的榜单   贴一个leaderboard
![image](https://user-images.githubusercontent.com/89777846/226322136-7d00ccef-715e-4b13-89bc-91f78207a7cb.png)

## 第一版的超参数和实验结果
1.  learning_rate = 3e-4；weight_decay = 1e-3；batch_size=16；
    GPU1080显存占了4g左右，CPU3600占用率60%能飙到4GHz，45min跑了12个epoch;valid=saving model with acc 0.912;![image](https://user-images.githubusercontent.com/89777846/226321420-8232ac85-6e68-46ca-82cc-e98d2188288a.png)

 
    感觉还不错，毕竟只跑了一会，
    之后改进的方向：更多的数据增强，多跑几次，调一下参数


## 第二次用resnt34 预训练模型但是linear probing（只有最后的softmax分类头有梯度）
50s一个epoch   快是快  但是结果很低 跑了30个epoch依旧accury只有0.7   应该是模型的原因，其他的因素微调估计不会带来质的提升了
![image](https://user-images.githubusercontent.com/89777846/226873482-b149dbd8-9119-4ffd-9983-d2c11bcdc57c.png)

## 第三次用resnt34 预训练模型 所有参数都不锁梯度
90s一个epoch   慢一点  效果自然是比linear probing好的  细调一下学习率优化器估计能上90%
![image](https://user-images.githubusercontent.com/89777846/226870518-10b28295-663a-433f-8f22-c5a988e296b7.png)

