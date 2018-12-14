# data-science-toolbox-3
## what we need to do
1. choose an inference goal; <br>
2.  create `baseline model` -- a simple model<br>
----`compare the performance` with non-trivial model (eg.Regression  based on previous workshops); <br>
3. use strategy to learn any parameters of the non-trivial model; <br>
4. use strategy to learn about out-of-sample performance of the non-trivial model; <br>
5. compare performance of the non-trivial model to the baseline. <br>

what is our inference goal

what is our baseline model

how to compare the performance with the non-trivial model?  
Maybe we can try to compare the False nagetive rate or something

思路：
1. 我们使用随机森林模型，作为简单模型<br>
2. 我们想找出主要的feature对于某个特定的网络攻击<br>
3. 如何找出主要的feature<br>
通过降维，kmeans 5维，可以创造新的feature PCA的feature也是新的 tsne的feature<br>
kmeans 5维，主要的想法是将数据四种不同攻击类型分开，但是由于某些类型的数量太大，导致其余类型数据的比例太低<br>
由此可能导致无法区分数据的kmeans，或许我可以将数据的量级重新排列一下，49万个数据，或许选最少的那个类型的大小将4份攻击筛选出来再进行kmeans分类<br>
```
> length(which(connection_events$type=="u2r"))
[1] 52
> length(which(connection_events$type=="dos"))
[1] 389255
> length(which(connection_events$type=="probe"))
[1] 4107
> length(which(connection_events$type=="r2l"))
[1] 1126
> 
```
研究一下数据比例差异巨大导致的数据分类问题

