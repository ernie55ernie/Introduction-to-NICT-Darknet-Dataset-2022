# Introduction-to-NICT-Darknet-Dataset-2022
This repository introduces the NICT Darknet Dataset 2022 https://csdataset.nict.go.jp/darknet-2022/. This dataset and the ground truth have been used in [[1]](#ref1) [[2]](#ref2) [[3]](#ref3) [[4]](#ref4) on malware detection in the darknet. The observation scale of all darknet sensors and the total observed IPv4 addresses, the malware activity threats and their characteristic of network activity, and the goal of detecting TCP ports where malware activities were observed are presented.

The data is collected with eight darknet sensors that monitor different IP address spaces and have different observation scales of the subnet. The observation scale of darknet sensors ranges from 2048 IP addresses to 32768 IP addresses. These eight darknet sensors monitor a total of 86016 IP addresses.

![Subnet mask and scale of subnet for each darknet sensor.](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/table2.png?raw=true)

To emphasize the unknown scanning activities, well-known ports 22, 23, 80, 81, 445, 1433, 2323, 3389, 5555, 8080, and 52869 are excluded when constructing observation matrices in the data processing step [1]. Port 22 is SSH service. Port 23 and 2323 are Telnet and its alternative. Port 80, 81, and 8080 are web services. Port 445 is used for file sharing of service message block in Windows. Port 1433 is Microsoft SQL Server. Port 3389 is Microsoft remote desktop. Port 5555 is SoftEther VPN SoftEther VPN (Ethernet over HTTPS). Port 52869 is Xsan, the file sharing system for macOS.

![Number of source hosts and packets related well-known ports.](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/well.png?raw=true)

For darknet sensors B and D, we observe intersecting columns of source hosts and destination ports all the time in October 2018. There is average 3742 intersecting source hosts and 1172 destination ports.

![Number of intersecting columns in October 2018.](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/intersect_cols.png?raw=true)

Ground truths were the malware activities in October 2018, labeled by human experts of operators of the National Institute of Information and Communications Technology (NICT) [1]. The ground truths are 35 TCP destination ports, 21, 25, 82, 83, 84, 85, 88, 110, 443, 444, 1701, 2004, 2480, 5358, 5379, 5431, 5900, 5984, 6379, 7379, 7547, 8000, 8001, 8010, 8081, 8088, 8181, 8291, 8443, 8888, 9000, 23023, 37215, 49152, 65000. They are grouped into IoT Malware, router vulnerability, and application vulnerability.


![Ground truth of malware activities observed in October 2018](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/table3.png?raw=true)

We can observe a spike in the number of source hosts for Mirai type I on October 20. The following figures are the number of source hosts and number of packets per half an hour in October 2018 at TCP ports where Mirai type I were observed by sensors B and D.

![Mirai I](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/mirai_1.png?raw=true)

We can observe a surge in the number of source hosts targeting port 88 and 8081 for Mirai II on October 20.

![Mirai II](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/mirai_2.png?raw=true)

We can observe a surge in the number of source hosts on October 16 and 19 for Mirai type III.

![Mirai III](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/mirai_3.png?raw=true)

For the threat related to MikroTik of router vulnerability, there are spikes of source hosts on October 13, 16, and 19. 

![Mikrotik](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/mikrotik.png?raw=true)

A surge in the number of source hosts can be observed on October 12 for application vulnerability threats part 1.

![Application 1](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/app_1.png?raw=true)

A surge in the number of source hosts can be observed on October 14 and October 30 for application vulnerability threats part 2. 

![Application 2](https://github.com/ernie55ernie/Introduction-to-NICT-Darknet-Dataset-2022/blob/main/img/app_2.png?raw=true)


# Reference
1. <a name='ref1'></a>Han, C., Takeuchi, J. I., Takahashi, T., & Inoue, D. (2021, October). Automated detection of malware activities using nonnegative matrix factorization. In 2021 IEEE 20th International Conference on Trust, Security and Privacy in Computing and Communications (TrustCom) (pp. 548-556). IEEE.
2. <a name='ref2'>Han, C., Takeuchi, J. I., Takahashi, T., & Inoue, D. (2022). Dark-TRACER: Early detection framework for malware activity based on anomalous spatiotemporal patterns. IEEE Access, 10, 13038-13058.
3. <a name='ref3'>Han, C., Shimamura, J., Takahashi, T., Inoue, D., Takeuchi, J. I., & Nakao, K. (2020). Real-time detection of global cyberthreat based on darknet by estimating anomalous synchronization using graphical lasso. IEICE TRANSACTIONS on Information and Systems, 103(10), 2113-2124.
4. <a name='ref4'>Chang, Y. W., Chen, H. Y., Han, C., Morikawa, T., Takahashi, T., & Lin, T. N. (2023). FINISH: Efficient and Scalable NMF-Based Federated Learning for Detecting Malware Activities. IEEE Transactions on Emerging Topics in Computing.