<!--
 * @Author: zhou hong
 * @Date: 2024-07-17 10:42:41
 * @LastEditors: Do not edit
 * @LastEditTime: 2024-07-17 10:48:27
 * @FilePath: /rosbag-merge/readme.md
-->
1.首先，确保你已经安装了rosbag和rospy Python模块。如果没有安装，可以使用以下命令进行安装：
```
sudo apt-get install python-rosbag
sudo apt-get install python-rospy
```

2.给脚本添加执行权限并运行
```
chmod +x merge_bags.py

将两个bag里所有topic合并到一个bag中：
python3 merge_bags.py -v total.bag 2_hq9570_rear_lcr_2022-04-21-20-27-17_filtered.bag 3_hq9570_rear_lcr_2022-04-21-20-38-41_filtered.bag  
# 就是把 2_hq9570_rear_lcr_2022-04-21-20-27-17_filtered.bag 和 3_hq9570_rear_lcr_2022-04-21-20-38-41_filtered.bag 完全合并在一起，时间戳打的都是原来两个bag里原始的时间戳，而不是像一边rosbag play一边rosbag record一样录的是现在这个时间戳


将两个bag里某些topic合并到一个bag中

python3 merge_bags.py -v --topic '/perception/camera/camera_obstacle /perception/lidar/percept_info_rviz /perception/radar/front/radar_obstacle /perception/radar/rear_right/radar_obstacle' total.bag 2_hq9570_rear_lcr_2022-04-21-20-27-17_filtered.bag 3_hq9570_rear_lcr_2022-04-21-20-38-41_filtered.bag 
# 就是把 2_hq9570_rear_lcr_2022-04-21-20-27-17_filtered.bag 里的 /perception/camera/camera_obstacle /perception/lidar/percept_info_rviz 和 3_hq9570_rear_lcr_2022-04-21-20-38-41_filtered.bag 里的 /perception/radar/front/radar_obstacle /perception/radar/rear_right/radar_obstacle 合并在一起

```


