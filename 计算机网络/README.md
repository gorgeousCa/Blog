# cisco 三层交换机实现vlan间通信
Cisco二层交换机是不能实现vlan间通讯的，这就需要三层路由功能，而Cisco3560交换机默认情况下是二层交换机，这就需要对交换机进行一些配置，实现vlan间的通信。
## 	网络拓扑图
![image](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/%E7%BD%91%E7%BB%9C%E6%8B%93%E6%89%91%E5%9B%BE.png)
## pc配置
|PC 号| ip 地址|
|:---|:---|
|PC0|IP:192.168.1.2|
|PC1|IP:192.168.1.3|
|PC2|IP:192.168.1.4|
|PC3|IP:192.168.2.2|
|PC4|IP:192.168.2.3|
|PC5|IP:192.168.2.4|
|PC6|IP:192.168.3.2|
|PC7|IP:192.168.3.3|
|PC8|IP:192.168.3.4|
|PC9|IP:192.168.4.2|
|PC10|IP:192.168.4.3|
|PC11|IP:192.168.4.4|
|PC12|IP:192.168.5.2|
|PC13|IP:192.168.5.3|
|PC14|IP:192.168.5.4|
|PC15|IP:192.168.6.2|
|PC16|IP:192.168.6.3|
|PC17|IP:192.168.6.4|
## 配置过程
- 二层交换机的配置
![image1](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/1.png)
![image1](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/2.png)
![image1](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/3.png)
![image1](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/4.png)
![image1](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/5.png)
![image1](https://github.com/gorgeousCa/Dayup/blob/master/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C/6.png)
