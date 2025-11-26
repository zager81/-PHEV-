# -PHEV-
《基于车流信息的PHEV实时全局最优能量管理策略》中用于预测的数据集

Driving_Data_Raw.zip中包括两类数据：

1. 行驶数据+百度API数据

    1.1 文件名：
        年 月 日 时-分-秒.csv
        2022 Dec 13 17-51-33.csv
   
    1.2 数据结构：
   
            Seg = RAW_DATA(head:tail,1);         %Seg index                  √
        	Seg = Seg+1;	%Seg原本从0开始, 现改为从1开始
            Time = RAW_DATA(head:tail,2);        %Time
            DivDis = RAW_DATA(head:tail,3);      %行驶距离 (m)
            YoloSeg = RAW_DATA(head:tail,4);     %YOLO Seg index             √
            
            BatVlt = RAW_DATA(head:tail,5);      %电池电压 (V)               √
            BatCur = RAW_DATA(head:tail,6);      %电池电流 (A)               √
            BatSOC = RAW_DATA(head:tail,7);      %电池SOC (%)
            MotPwr = RAW_DATA(head:tail,8)*1e3;  %电机功率 (W)               √
            MotSpd = RAW_DATA(head:tail,9);      %电机转速 (rpm)
            
            MotTemp = RAW_DATA(head:tail,10);    %电机温度 (℃)
            MotCur = RAW_DATA(head:tail,11);     %电机电流 (A)               √
            MotVlt = RAW_DATA(head:tail,12);     %电机电压 (V)               √
            
            FLSpd = RAW_DATA(head:tail,13);      %左前轮车速 (km/h)
            FRSpd = RAW_DATA(head:tail,14);      %右前轮车速 (km/h)
            RLSpd = RAW_DATA(head:tail,15);      %左后轮车速 (km/h)
            RRSpd = RAW_DATA(head:tail,16);      %左后轮车速 (km/h)
            
            VehSpd = RAW_DATA(head:tail,17);     %车辆车速 (km/h)           √
            VehTrq = RAW_DATA(head:tail,18);     %车辆扭矩 (Nm)             √
            AccOrg = RAW_DATA(head:tail,19);     %原车加速踏板位置 (%)      √
            AccWir = RAW_DATA(head:tail,20);     %线控加速踏板位置 (%)
            VehGear = RAW_DATA(head:tail,21);    %车辆档位状态 (3:P档, 2:R挡, 1:D挡, 0:N档)
            
            GpsLat = RAW_DATA(head:tail,22);       %GPS纬度
            GpsLng = RAW_DATA(head:tail,23);       %GPS经度
            GpsAlt = RAW_DATA(head:tail,24);       %GPS海拔 (m)             √
            GpsSpd = RAW_DATA(head:tail,25);       %GPS车速 (km/h)          √
            GpsTime = RAW_DATA(head:tail,26);      %GPS时间
            GpsDis = RAW_DATA(head:tail,27);       %到下个路段的距离
            
            TrffStat = RAW_DATA(head:tail,28);     %0:未知路况; 1:畅通; 2:缓行; 3:拥堵; 4:严重拥堵          √
            JamDrct = RAW_DATA(head:tail,29);      %无:0; 同向:1; 反向:-1;                                  √
            TrffSpd = RAW_DATA(head:tail,30);      %车流速度 (km/h)                                         √

3. YOLO机器视觉数据

    2.1 文件名：
        年 月 日 时-分-秒_Yolo_Result.csv
        2022 Dec 13 17-51-33_Yolo_Result.csv
   
    2.2 数据结构：
   
        Yolo_Index = YOLO_RAW_DATA(:,2);    % YOLO段Index
        Yolo_VehNum = YOLO_RAW_DATA(:,3);   % 车流量
