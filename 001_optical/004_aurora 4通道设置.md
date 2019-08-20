## 1. Aurora IP的配置
1. IP 的配置：stream流方式
2. 时钟分享方式
![20190807112502.png](https://i.loli.net/2019/08/07/6UCdBLTFpVENtn2.png)

## 2. Aurora x4通道IP与单通aurora x1 IP的比较
### 2.1 代码的比较
1. support.v比较： 在drp 和一些处理上有些差别，差别较小；无风险
2. gt_common_wrapper.v，无差别。
3. clock.v 无差别  查看mmcm的设置作用，SYNC的时钟有什么作用，跑一个类似的工程查看一下，或者使用BUFG资源代替看看。MMCM部分不变，使用SYNC  CLK_OUT 复位的方法实现。
![20190807133858.png](https://i.loli.net/2019/08/07/tTi21pQOUlrBYZn.png)

### 16通道初步综合之后的资源
#### 工程搭建
![20190807163708.png](https://i.loli.net/2019/08/07/wiDPaX69eSbul2M.png)

#### 综合实现后资源消耗统计
![20190807163819.png](https://i.loli.net/2019/08/07/SlOozd8xnAP3HJq.png)
1. BUFG资源消耗符合预期，
2. LUT等其他资源消耗军在4%以下。