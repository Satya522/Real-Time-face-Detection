# Real-Time Face Detection Project

This project implements real-time face detection using Java. It leverages the OpenCV library to process video feed from the webcam and detect faces in real-time.

## Prerequisites

- Java Development Kit (JDK) 11 or higher
- IntelliJ IDEA 2023.2.7 or similar IDE
- OpenCV library (version 4.x recommended)

## Setting Up

### Step 1: Install OpenCV

1. Download OpenCV for Java from the [official OpenCV website](https://opencv.org/releases/).
2. Extract the downloaded file to a known location on your system.

### Step 2: Configure OpenCV in IntelliJ IDEA

1. Open IntelliJ IDEA and create a new Java project.
2. Go to `File` > `Project Structure` > `Libraries`.
3. Click the `+` sign and select `Java`. Navigate to the OpenCV library folder, and select the `opencv-xxx.jar` file (where `xxx` is the version number).
4. Apply the changes.

### Step 3: Load OpenCV Native Library

1. Add the following code to your main class to load the OpenCV native library:

```java
public class faceDetection{
    public static void main(String[] args){
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);
        System.out.println("OpenCV loaded Successfully");
    }
}

```

### setup haarcascade frontalface file

1. create a new directory in the project named xml
2. create new file named haarcascade_frontalface_alt.xml
3. paste below code in file 

```xml
<?xml version="1.0"?>
<!--
number of positive samples 3000
number of negative samples 1500
-->
<opencv_storage>
    <cascade type_id="opencv-cascade-classifier">
        <stageType>BOOST</stageType>
        <featureType>LBP</featureType>
        <height>24</height>
        <width>24</width>
        <stageParams>
            <boostType>GAB</boostType>
            <minHitRate>0.9950000047683716</minHitRate>
            <maxFalseAlarm>0.5000000000000000</maxFalseAlarm>
            <weightTrimRate>0.9500000000000000</weightTrimRate>
            <maxDepth>1</maxDepth>
            <maxWeakCount>100</maxWeakCount></stageParams>
        <featureParams>
            <maxCatCount>256</maxCatCount></featureParams>
        <stageNum>20</stageNum>
        <stages>
            <!-- stage 0 -->
            <_>
                <maxWeakCount>3</maxWeakCount>
                <stageThreshold>-0.7520892024040222</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 46 -67130709 -21569 -1426120013 -1275125205 -21585
                            -16385 587145899 -24005</internalNodes>
                        <leafValues>
                            -0.6543210148811340 0.8888888955116272</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 13 -163512766 -769593758 -10027009 -262145 -514457854
                            -193593353 -524289 -1</internalNodes>
                        <leafValues>
                            -0.7739216089248657 0.7278633713722229</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 2 -363936790 -893203669 -1337948010 -136907894
                            1088782736 -134217726 -741544961 -1590337</internalNodes>
                        <leafValues>
                            -0.7068563103675842 0.6761534214019775</leafValues></_></weakClassifiers></_>
            <!-- stage 1 -->
            <_>
                <maxWeakCount>4</maxWeakCount>
                <stageThreshold>-0.4872078299522400</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 84 2147483647 1946124287 -536870913 2147450879
                            738132490 1061101567 243204619 2147446655</internalNodes>
                        <leafValues>
                            -0.8083735704421997 0.7685696482658386</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 21 2147483647 263176079 1879048191 254749487 1879048191
                            -134252545 -268435457 801111999</internalNodes>
                        <leafValues>
                            -0.7698410153388977 0.6592915654182434</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 106 -98110272 1610939566 -285484400 -850010381
                            -189334372 -1671954433 -571026695 -262145</internalNodes>
                        <leafValues>
                            -0.7506558895111084 0.5444605946540833</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 48 -798690576 -131075 1095771153 -237144073 -65569 -1
                            -216727745 -69206049</internalNodes>
                        <leafValues>
                            -0.7775990366935730 0.5465461611747742</leafValues></_></weakClassifiers></_>
            <!-- stage 2 -->
            <_>
                <maxWeakCount>4</maxWeakCount>
                <stageThreshold>-1.1592328548431396</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 47 -21585 -20549 -100818262 -738254174 -20561 -36865
                            -151016790 -134238549</internalNodes>
                        <leafValues>
                            -0.5601882934570313 0.7743113040924072</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 12 -286003217 183435247 -268994614 -421330945
                            -402686081 1090387966 -286785545 -402653185</internalNodes>
                        <leafValues>
                            -0.6124526262283325 0.6978127956390381</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 26 -50347012 970882927 -50463492 -1253377 -134218251
                            -50364513 -33619992 -172490753</internalNodes>
                        <leafValues>
                            -0.6114496588706970 0.6537628173828125</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 8 -273 -135266321 1877977738 -2088243418 -134217987
                            2146926575 -18910642 1095231247</internalNodes>
                        <leafValues>
                            -0.6854077577590942 0.5403239130973816</leafValues></_></weakClassifiers></_>
            <!-- stage 3 -->
            <_>
                <maxWeakCount>5</maxWeakCount>
                <stageThreshold>-0.7562355995178223</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 96 -1273 1870659519 -20971602 -67633153 -134250731
                            2004875127 -250 -150995969</internalNodes>
                        <leafValues>
                            -0.4051094949245453 0.7584033608436585</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 33 -868162224 -76810262 -4262145 -257 1465211989
                            -268959873 -2656269 -524289</internalNodes>
                        <leafValues>
                            -0.7388162612915039 0.5340843200683594</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 57 -12817 -49 -541103378 -152950 -38993 -20481 -1153876
                            -72478976</internalNodes>
                        <leafValues>
                            -0.6582943797111511 0.5339496731758118</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 125 -269484161 -452984961 -319816180 -1594032130 -2111
                            -990117891 -488975296 -520947741</internalNodes>
                        <leafValues>
                            -0.5981323719024658 0.5323504805564880</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 53 557787431 670265215 -1342193665 -1075892225
                            1998528318 1056964607 -33570977 -1</internalNodes>
                        <leafValues>
                            -0.6498787999153137 0.4913350641727448</leafValues></_></weakClassifiers></_>
            <!-- stage 4 -->
            <_>
                <maxWeakCount>5</maxWeakCount>
                <stageThreshold>-0.8085358142852783</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 60 -536873708 880195381 -16842788 -20971521 -176687276
                            -168427659 -16777260 -33554626</internalNodes>
                        <leafValues>
                            -0.5278195738792419 0.6946372389793396</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 7 -1 -62981529 -1090591130 805330978 -8388827 -41945787
                            -39577 -531118985</internalNodes>
                        <leafValues>
                            -0.5206505060195923 0.6329920291900635</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 98 -725287348 1347747543 -852489 -16809993 1489881036
                            -167903241 -1 -1</internalNodes>
                        <leafValues>
                            -0.7516061067581177 0.4232024252414703</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 44 -32777 1006582562 -65 935312171 -8388609 -1078198273
                            -1 733886267</internalNodes>
                        <leafValues>
                            -0.7639313936233521 0.4123568832874298</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 24 -85474705 2138828511 -1036436754 817625855
                            1123369029 -58796809 -1013468481 -194513409</internalNodes>
                        <leafValues>
                            -0.5123769044876099 0.5791834592819214</leafValues></_></weakClassifiers></_>
            <!-- stage 5 -->
            <_>
                <maxWeakCount>5</maxWeakCount>
                <stageThreshold>-0.5549971461296082</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 42 -17409 -20481 -268457797 -134239493 -17473 -1 -21829
                            -21846</internalNodes>
                        <leafValues>
                            -0.3763174116611481 0.7298233509063721</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 6 -805310737 -2098262358 -269504725 682502698
                            2147483519 1740574719 -1090519233 -268472385</internalNodes>
                        <leafValues>
                            -0.5352765917778015 0.5659480094909668</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 61 -67109678 -6145 -8 -87884584 -20481 -1073762305
                            -50856216 -16849696</internalNodes>
                        <leafValues>
                            -0.5678374171257019 0.4961479902267456</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 123 -138428633 1002418167 -1359008245 -1908670465
                            -1346685918 910098423 -1359010520 -1346371657</internalNodes>
                        <leafValues>
                            -0.5706262588500977 0.4572288393974304</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 9 -89138513 -4196353 1256531674 -1330665426 1216308261
                            -36190633 33498198 -151796633</internalNodes>
                        <leafValues>
                            -0.5344601869583130 0.4672054052352905</leafValues></_></weakClassifiers></_>
            <!-- stage 6 -->
            <_>
                <maxWeakCount>5</maxWeakCount>
                <stageThreshold>-0.8776460289955139</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 105 1073769576 206601725 -34013449 -33554433 -789514004
                            -101384321 -690225153 -264193</internalNodes>
                        <leafValues>
                            -0.7700348496437073 0.5943940877914429</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 30 -1432340997 -823623681 -49153 -34291724 -269484035
                            -1342767105 -1078198273 -1277955</internalNodes>
                        <leafValues>
                            -0.5043668746948242 0.6151274442672730</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 35 -1067385040 -195758209 -436748425 -134217731
                            -50855988 -129 -1 -1</internalNodes>
                        <leafValues>
                            -0.6808040738105774 0.4667325913906097</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 119 832534325 -34111555 -26050561 -423659521 -268468364
                            2105014143 -2114244 -17367185</internalNodes>
                        <leafValues>
                            -0.4927591383457184 0.5401885509490967</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 82 -1089439888 -1080524865 2143059967 -1114121
                            -1140949004 -3 -2361356 -739516</internalNodes>
                        <leafValues>
                            -0.6445107460021973 0.4227822124958038</leafValues></_></weakClassifiers></_>
            <!-- stage 7 -->
            <_>
                <maxWeakCount>6</maxWeakCount>
                <stageThreshold>-1.1139287948608398</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 52 -1074071553 -1074003969 -1 -1280135430 -5324817 -1
                            -335548482 582134442</internalNodes>
                        <leafValues>
                            -0.5307556986808777 0.6258179545402527</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 99 -706937396 -705364068 -540016724 -570495027
                            -570630659 -587857963 -33628164 -35848193</internalNodes>
                        <leafValues>
                            -0.5227634310722351 0.5049746036529541</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 18 -2035630093 42119158 -268503053 -1671444 261017599
                            1325432815 1954394111 -805306449</internalNodes>
                        <leafValues>
                            -0.4983572661876679 0.5106441378593445</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 111 -282529488 -1558073088 1426018736 -170526448
                            -546832487 -5113037 -34243375 -570427929</internalNodes>
                        <leafValues>
                            -0.4990860521793366 0.5060507059097290</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 92 1016332500 -606301707 915094269 -1080086049
                            -1837027144 -1361600280 2147318747 1067975613</internalNodes>
                        <leafValues>
                            -0.5695009231567383 0.4460467398166657</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 51 -656420166 -15413034 -141599534 -603435836
                            1505950458 -787556946 -79823438 -1326199134</internalNodes>
                        <leafValues>
                            -0.6590405106544495 0.3616424500942230</leafValues></_></weakClassifiers></_>
            <!-- stage 8 -->
            <_>
                <maxWeakCount>7</maxWeakCount>
                <stageThreshold>-0.8243625760078430</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 28 -901591776 -201916417 -262 -67371009 -143312112
                            -524289 -41943178 -1</internalNodes>
                        <leafValues>
                            -0.4972776770591736 0.6027074456214905</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 112 -4507851 -411340929 -268437513 -67502145 -17350859
                            -32901 -71344315 -29377</internalNodes>
                        <leafValues>
                            -0.4383158981800079 0.5966237187385559</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 69 -75894785 -117379438 -239063587 -12538500 1485072126
                            2076233213 2123118847 801906927</internalNodes>
                        <leafValues>
                            -0.6386105418205261 0.3977999985218048</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 19 -823480413 786628589 -16876049 -1364262914 242165211
                            1315930109 -696268833 -455082829</internalNodes>
                        <leafValues>
                            -0.5512794256210327 0.4282079637050629</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 73 -521411968 6746762 -1396236286 -2038436114
                            -185612509 57669627 -143132877 -1041235973</internalNodes>
                        <leafValues>
                            -0.6418755054473877 0.3549866080284119</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 126 -478153869 1076028979 -1645895615 1365298272
                            -557859073 -339771473 1442574528 -1058802061</internalNodes>
                        <leafValues>
                            -0.4841901361942291 0.4668019413948059</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 45 -246350404 -1650402048 -1610612745 -788400696
                            1467604861 -2787397 1476263935 -4481349</internalNodes>
                        <leafValues>
                            -0.5855734348297119 0.3879135847091675</leafValues></_></weakClassifiers></_>
            <!-- stage 9 -->
            <_>
                <maxWeakCount>7</maxWeakCount>
                <stageThreshold>-1.2237116098403931</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 114 -24819 1572863935 -16809993 -67108865 2146778388
                            1433927541 -268608444 -34865205</internalNodes>
                        <leafValues>
                            -0.2518476545810700 0.7088654041290283</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 97 -1841359 -134271049 -32769 -5767369 -1116675 -2185
                            -8231 -33603327</internalNodes>
                        <leafValues>
                            -0.4303432404994965 0.5283288359642029</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 25 -1359507589 -1360593090 -1073778729 -269553812
                            -809512977 1744707583 -41959433 -134758978</internalNodes>
                        <leafValues>
                            -0.4259553551673889 0.5440809130668640</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 34 729753407 -134270989 -1140907329 -235200777
                            658456383 2147467263 -1140900929 -16385</internalNodes>
                        <leafValues>
                            -0.5605589151382446 0.4220733344554901</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 134 -310380553 -420675595 -193005472 -353568129
                            1205338070 -990380036 887604324 -420544526</internalNodes>
                        <leafValues>
                            -0.5192656517028809 0.4399855434894562</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 16 -1427119361 1978920959 -287119734 -487068946
                            114759245 -540578051 -707510259 -671660453</internalNodes>
                        <leafValues>
                            -0.5013077259063721 0.4570254683494568</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 74 -738463762 -889949281 -328301948 -121832450
                            -1142658284 -1863576559 2146417353 -263185</internalNodes>
                        <leafValues>
                            -0.4631414115428925 0.4790246188640595</leafValues></_></weakClassifiers></_>
            <!-- stage 10 -->
            <_>
                <maxWeakCount>7</maxWeakCount>
                <stageThreshold>-0.5544230937957764</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 113 -76228780 -65538 -1 -67174401 -148007 -33 -221796
                            -272842924</internalNodes>
                        <leafValues>
                            -0.3949716091156006 0.6082032322883606</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 110 369147696 -1625232112 2138570036 -1189900 790708019
                            -1212613127 799948719 -4456483</internalNodes>
                        <leafValues>
                            -0.4855885505676270 0.4785369932651520</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 37 784215839 -290015241 536832799 -402984963
                            -1342414991 -838864897 -176769 -268456129</internalNodes>
                        <leafValues>
                            -0.4620285332202911 0.4989669024944305</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 41 -486418688 -171915327 -340294900 -21938 -519766032
                            -772751172 -73096060 -585322623</internalNodes>
                        <leafValues>
                            -0.6420643329620361 0.3624351918697357</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 117 -33554953 -475332625 -1423463824 -2077230421
                            -4849669 -2080505925 -219032928 -1071915349</internalNodes>
                        <leafValues>
                            -0.4820112884044647 0.4632140696048737</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 65 -834130468 -134217476 -1349314083 -1073803559
                            -619913764 -1449131844 -1386890321 -1979118423</internalNodes>
                        <leafValues>
                            -0.4465552568435669 0.5061788558959961</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 56 -285249779 1912569855 -16530 -1731022870 -1161904146
                            -1342177297 -268439634 -1464078708</internalNodes>
                        <leafValues>
                            -0.5190586447715759 0.4441480338573456</leafValues></_></weakClassifiers></_>
            <!-- stage 11 -->
            <_>
                <maxWeakCount>7</maxWeakCount>
                <stageThreshold>-0.7161560654640198</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 20 1246232575 1078001186 -10027057 60102 -277348353
                            -43646987 -1210581153 1195769615</internalNodes>
                        <leafValues>
                            -0.4323809444904327 0.5663768053054810</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 15 -778583572 -612921106 -578775890 -4036478
                            -1946580497 -1164766570 -1986687009 -12103599</internalNodes>
                        <leafValues>
                            -0.4588732719421387 0.4547033011913300</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 129 -1073759445 2013231743 -1363169553 -1082459201
                            -1414286549 868185983 -1356133589 -1077936257</internalNodes>
                        <leafValues>
                            -0.5218553543090820 0.4111092388629913</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 102 -84148365 -2093417722 -1204850272 564290299
                            -67121221 -1342177350 -1309195902 -776734797</internalNodes>
                        <leafValues>
                            -0.4920000731945038 0.4326725304126740</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 88 -25694458 67104495 -290216278 -168563037 2083877442
                            1702788383 -144191964 -234882162</internalNodes>
                        <leafValues>
                            -0.4494568109512329 0.4448510706424713</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 59 -857980836 904682741 -1612267521 232279415
                            1550862252 -574825221 -357380888 -4579409</internalNodes>
                        <leafValues>
                            -0.5180826783180237 0.3888972699642181</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 27 -98549440 -137838400 494928389 -246013630 939541351
                            -1196072350 -620603549 2137216273</internalNodes>
                        <leafValues>
                            -0.6081240773200989 0.3333222270011902</leafValues></_></weakClassifiers></_>
            <!-- stage 12 -->
            <_>
                <maxWeakCount>8</maxWeakCount>
                <stageThreshold>-0.6743940711021423</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 29 -150995201 2071191945 -1302151626 536934335
                            -1059008937 914128709 1147328110 -268369925</internalNodes>
                        <leafValues>
                            -0.1790193915367127 0.6605972051620483</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 128 -134509479 1610575703 -1342177289 1861484541
                            -1107833788 1577058173 -333558568 -136319041</internalNodes>
                        <leafValues>
                            -0.3681024610996246 0.5139749646186829</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 70 -1 1060154476 -1090984524 -630918524 -539492875
                            779616255 -839568424 -321</internalNodes>
                        <leafValues>
                            -0.3217232525348663 0.6171553134918213</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 4 -269562385 -285029906 -791084350 -17923776 235286671
                            1275504943 1344390399 -966276889</internalNodes>
                        <leafValues>
                            -0.4373284578323364 0.4358185231685638</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 76 17825984 -747628419 595427229 1474759671 575672208
                            -1684005538 872217086 -1155858277</internalNodes>
                        <leafValues>
                            -0.4404836893081665 0.4601220190525055</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 124 -336593039 1873735591 -822231622 -355795238
                            -470820869 -1997537409 -1057132384 -1015285005</internalNodes>
                        <leafValues>
                            -0.4294152259826660 0.4452161788940430</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 54 -834212130 -593694721 -322142257 -364892500
                            -951029539 -302125121 -1615106053 -79249765</internalNodes>
                        <leafValues>
                            -0.3973052501678467 0.4854526817798615</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 95 1342144479 2147431935 -33554561 -47873 -855685912 -1
                            1988052447 536827383</internalNodes>
                        <leafValues>
                            -0.7054683566093445 0.2697997391223908</leafValues></_></weakClassifiers></_>
            <!-- stage 13 -->
            <_>
                <maxWeakCount>9</maxWeakCount>
                <stageThreshold>-1.2042298316955566</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 39 1431368960 -183437936 -537002499 -137497097
                            1560590321 -84611081 -2097193 -513</internalNodes>
                        <leafValues>
                            -0.5905947685241699 0.5101932883262634</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 120 -1645259691 2105491231 2130706431 1458995007
                            -8567536 -42483883 -33780003 -21004417</internalNodes>
                        <leafValues>
                            -0.4449204802513123 0.4490709304809570</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 89 -612381022 -505806938 -362027516 -452985106
                            275854917 1920431639 -12600561 -134221825</internalNodes>
                        <leafValues>
                            -0.4693818688392639 0.4061094820499420</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 14 -805573153 -161 -554172679 -530519488 -16779441
                            2000682871 -33604275 -150997129</internalNodes>
                        <leafValues>
                            -0.3600351214408875 0.5056326985359192</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 67 6192 435166195 1467449341 2046691505 -1608493775
                            -4755729 -1083162625 -71365637</internalNodes>
                        <leafValues>
                            -0.4459891915321350 0.4132415652275085</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 86 -41689215 -3281034 1853357967 -420712635 -415924289
                            -270209208 -1088293113 -825311232</internalNodes>
                        <leafValues>
                            -0.4466069042682648 0.4135067760944367</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 80 -117391116 -42203396 2080374461 -188709 -542008165
                            -356831940 -1091125345 -1073796897</internalNodes>
                        <leafValues>
                            -0.3394956290721893 0.5658645033836365</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 75 -276830049 1378714472 -1342181951 757272098
                            1073740607 -282199241 -415761549 170896931</internalNodes>
                        <leafValues>
                            -0.5346512198448181 0.3584479391574860</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 55 -796075825 -123166849 2113667055 -217530421
                            -1107432194 -16385 -806359809 -391188771</internalNodes>
                        <leafValues>
                            -0.4379335641860962 0.4123645126819611</leafValues></_></weakClassifiers></_>
            <!-- stage 14 -->
            <_>
                <maxWeakCount>10</maxWeakCount>
                <stageThreshold>-0.8402050137519836</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 71 -890246622 15525883 -487690486 47116238 -1212319899
                            -1291847681 -68159890 -469829921</internalNodes>
                        <leafValues>
                            -0.2670986354351044 0.6014143228530884</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 31 -1361180685 -1898008841 -1090588811 -285410071
                            -1074016265 -840443905 2147221487 -262145</internalNodes>
                        <leafValues>
                            -0.4149844348430634 0.4670888185501099</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 40 1426190596 1899364271 2142731795 -142607505
                            -508232452 -21563393 -41960001 -65</internalNodes>
                        <leafValues>
                            -0.4985891580581665 0.3719584941864014</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 109 -201337965 10543906 -236498096 -746195597
                            1974565825 -15204415 921907633 -190058309</internalNodes>
                        <leafValues>
                            -0.4568729996681213 0.3965812027454376</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 130 -595026732 -656401928 -268649235 -571490699
                            -440600392 -133131 -358810952 -2004088646</internalNodes>
                        <leafValues>
                            -0.4770836830139160 0.3862601518630981</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 66 941674740 -1107882114 1332789109 -67691015
                            -1360463693 -1556612430 -609108546 733546933</internalNodes>
                        <leafValues>
                            -0.4877715110778809 0.3778986334800720</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 49 -17114945 -240061474 1552871558 -82775604 -932393844
                            -1308544889 -532635478 -99042357</internalNodes>
                        <leafValues>
                            -0.3721654713153839 0.4994400143623352</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 133 -655906006 1405502603 -939205164 1884929228
                            -498859222 559417357 -1928559445 -286264385</internalNodes>
                        <leafValues>
                            -0.3934195041656494 0.4769641458988190</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 0 -335837777 1860677295 -90 -1946186226 931096183
                            251612987 2013265917 -671232197</internalNodes>
                        <leafValues>
                            -0.4323300719261169 0.4342164099216461</leafValues></_>
                    <!-- tree 9 -->
                    <_>
                        <internalNodes>
                            0 -1 103 37769424 -137772680 374692301 2002666345 -536176194
                            -1644484728 807009019 1069089930</internalNodes>
                        <leafValues>
                            -0.4993278682231903 0.3665378093719482</leafValues></_></weakClassifiers></_>
            <!-- stage 15 -->
            <_>
                <maxWeakCount>9</maxWeakCount>
                <stageThreshold>-1.1974394321441650</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 43 -5505 2147462911 2143265466 -4511070 -16450 -257
                            -201348440 -71333206</internalNodes>
                        <leafValues>
                            -0.3310225307941437 0.5624626278877258</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 90 -136842268 -499330741 2015250980 -87107126
                            -641665744 -788524639 -1147864792 -134892563</internalNodes>
                        <leafValues>
                            -0.5266560912132263 0.3704403042793274</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 104 -146800880 -1780368555 2111170033 -140904684
                            -16777551 -1946681885 -1646463595 -839131947</internalNodes>
                        <leafValues>
                            -0.4171888828277588 0.4540435671806335</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 85 -832054034 -981663763 -301990281 -578814081
                            -932319000 -1997406723 -33555201 -69206017</internalNodes>
                        <leafValues>
                            -0.4556705355644226 0.3704262077808380</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 24 -118492417 -1209026825 1119023838 -1334313353
                            1112948738 -297319313 1378887291 -139469193</internalNodes>
                        <leafValues>
                            -0.4182529747486115 0.4267231225967407</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 78 -1714382628 -2353704 -112094959 -549613092
                            -1567058760 -1718550464 -342315012 -1074972227</internalNodes>
                        <leafValues>
                            -0.3625369668006897 0.4684656262397766</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 5 -85219702 316836394 -33279 1904970288 2117267315
                            -260901769 -621461759 -88607770</internalNodes>
                        <leafValues>
                            -0.4742925167083740 0.3689507246017456</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 11 -294654041 -353603585 -1641159686 -50331921
                            -2080899877 1145569279 -143132713 -152044037</internalNodes>
                        <leafValues>
                            -0.3666271567344666 0.4580127298831940</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 32 1887453658 -638545712 -1877976819 -34320972
                            -1071067983 -661345416 -583338277 1060190561</internalNodes>
                        <leafValues>
                            -0.4567637443542481 0.3894708156585693</leafValues></_></weakClassifiers></_>
            <!-- stage 16 -->
            <_>
                <maxWeakCount>9</maxWeakCount>
                <stageThreshold>-0.5733128190040588</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 122 -994063296 1088745462 -318837116 -319881377
                            1102566613 1165490103 -121679694 -134744129</internalNodes>
                        <leafValues>
                            -0.4055117964744568 0.5487945079803467</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 68 -285233233 -538992907 1811935199 -369234005 -529
                            -20593 -20505 -1561401854</internalNodes>
                        <leafValues>
                            -0.3787897229194641 0.4532003402709961</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 58 -1335245632 1968917183 1940861695 536816369
                            -1226071367 -570908176 457026619 1000020667</internalNodes>
                        <leafValues>
                            -0.4258328974246979 0.4202791750431061</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 94 -1360318719 -1979797897 -50435249 -18646473
                            -608879292 -805306691 -269304244 -17840167</internalNodes>
                        <leafValues>
                            -0.4561023116111755 0.4002747833728790</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 87 2062765935 -16449 -1275080721 -16406 45764335
                            -1090552065 -772846337 -570464322</internalNodes>
                        <leafValues>
                            -0.4314672648906708 0.4086346626281738</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 127 -536896021 1080817663 -738234288 -965478709
                            -2082767969 1290855887 1993822934 -990381609</internalNodes>
                        <leafValues>
                            -0.4174543321132660 0.4249868988990784</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 3 -818943025 168730891 -293610428 -79249354 669224671
                            621166734 1086506807 1473768907</internalNodes>
                        <leafValues>
                            -0.4321364760398865 0.4090838730335236</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 79 -68895696 -67107736 -1414315879 -841676168
                            -619843344 -1180610531 -1081990469 1043203389</internalNodes>
                        <leafValues>
                            -0.5018386244773865 0.3702533841133118</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 116 -54002134 -543485719 -2124882422 -1437445858
                            -115617074 -1195787391 -1096024366 -2140472445</internalNodes>
                        <leafValues>
                            -0.5037505626678467 0.3564981222152710</leafValues></_></weakClassifiers></_>
            <!-- stage 17 -->
            <_>
                <maxWeakCount>9</maxWeakCount>
                <stageThreshold>-0.4892596900463104</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 132 -67113211 2003808111 1862135111 846461923 -2752
                            2002237273 -273154752 1937223539</internalNodes>
                        <leafValues>
                            -0.2448196411132813 0.5689709186553955</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 62 1179423888 -78064940 -611839555 -539167899
                            -1289358360 -1650810108 -892540499 -1432827684</internalNodes>
                        <leafValues>
                            -0.4633283913135529 0.3587929606437683</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 23 -285212705 -78450761 -656212031 -264050110 -27787425
                            -1334349961 -547662981 -135796924</internalNodes>
                        <leafValues>
                            -0.3731099069118500 0.4290455579757690</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 77 341863476 403702016 -550588417 1600194541
                            -1080690735 951127993 -1388580949 -1153717473</internalNodes>
                        <leafValues>
                            -0.3658909499645233 0.4556473195552826</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 22 -586880702 -204831512 -100644596 -39319550
                            -1191150794 705692513 457203315 -75806957</internalNodes>
                        <leafValues>
                            -0.5214384198188782 0.3221037387847900</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 72 -416546870 545911370 -673716192 -775559454
                            -264113598 139424 -183369982 -204474641</internalNodes>
                        <leafValues>
                            -0.4289036989212036 0.4004956185817719</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 50 -1026505020 -589692154 -1740499937 -1563770497
                            1348491006 -60710713 -1109853489 -633909413</internalNodes>
                        <leafValues>
                            -0.4621542394161224 0.3832748532295227</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 108 -1448872304 -477895040 -1778390608 -772418127
                            -1789923416 -1612057181 -805306693 -1415842113</internalNodes>
                        <leafValues>
                            -0.3711548447608948 0.4612701535224915</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 92 407905424 -582449988 52654751 -1294472 -285103725
                            -74633006 1871559083 1057955850</internalNodes>
                        <leafValues>
                            -0.5180652141571045 0.3205870389938355</leafValues></_></weakClassifiers></_>
            <!-- stage 18 -->
            <_>
                <maxWeakCount>10</maxWeakCount>
                <stageThreshold>-0.5911940932273865</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 81 4112 -1259563825 -846671428 -100902460 1838164148
                            -74153752 -90653988 -1074263896</internalNodes>
                        <leafValues>
                            -0.2592592537403107 0.5873016119003296</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 1 -285216785 -823206977 -1085589 -1081346 1207959293
                            1157103471 2097133565 -2097169</internalNodes>
                        <leafValues>
                            -0.3801195919513702 0.4718827307224274</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 121 -12465 -536875169 2147478367 2130706303 -37765492
                            -866124467 -318782328 -1392509185</internalNodes>
                        <leafValues>
                            -0.3509117066860199 0.5094807147979736</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 38 2147449663 -20741 -16794757 1945873146 -16710 -1
                            -8406341 -67663041</internalNodes>
                        <leafValues>
                            -0.4068757295608521 0.4130136370658875</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 17 -155191713 866117231 1651407483 548272812 -479201468
                            -447742449 1354229504 -261884429</internalNodes>
                        <leafValues>
                            -0.4557141065597534 0.3539792001247406</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 100 -225319378 -251682065 -492783986 -792341777
                            -1287261695 1393643841 -11274182 -213909521</internalNodes>
                        <leafValues>
                            -0.4117803275585175 0.4118592441082001</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 63 -382220122 -2002072729 -51404800 -371201558
                            -923011069 -2135301457 -2066104743 -1042557441</internalNodes>
                        <leafValues>
                            -0.4008397758007050 0.4034757018089294</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 101 -627353764 -48295149 1581203952 -436258614
                            -105268268 -1435893445 -638126888 -1061107126</internalNodes>
                        <leafValues>
                            -0.5694189667701721 0.2964762747287750</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 118 -8399181 1058107691 -621022752 -251003468 -12582915
                            -574619739 -994397789 -1648362021</internalNodes>
                        <leafValues>
                            -0.3195341229438782 0.5294018983840942</leafValues></_>
                    <!-- tree 9 -->
                    <_>
                        <internalNodes>
                            0 -1 92 -348343812 -1078389516 1717960437 364735981
                            -1783841602 -4883137 -457572354 -1076950384</internalNodes>
                        <leafValues>
                            -0.3365339040756226 0.5067458748817444</leafValues></_></weakClassifiers></_>
            <!-- stage 19 -->
            <_>
                <maxWeakCount>10</maxWeakCount>
                <stageThreshold>-0.7612916231155396</stageThreshold>
                <weakClassifiers>
                    <!-- tree 0 -->
                    <_>
                        <internalNodes>
                            0 -1 10 -1976661318 -287957604 -1659497122 -782068 43591089
                            -453637880 1435470000 -1077438561</internalNodes>
                        <leafValues>
                            -0.4204545319080353 0.5165745615959168</leafValues></_>
                    <!-- tree 1 -->
                    <_>
                        <internalNodes>
                            0 -1 131 -67110925 14874979 -142633168 -1338923040
                            2046713291 -2067933195 1473503712 -789579837</internalNodes>
                        <leafValues>
                            -0.3762553930282593 0.4075302779674530</leafValues></_>
                    <!-- tree 2 -->
                    <_>
                        <internalNodes>
                            0 -1 83 -272814301 -1577073 -1118685 -305156120 -1052289
                            -1073813756 -538971154 -355523038</internalNodes>
                        <leafValues>
                            -0.4253497421741486 0.3728055357933044</leafValues></_>
                    <!-- tree 3 -->
                    <_>
                        <internalNodes>
                            0 -1 135 -2233 -214486242 -538514758 573747007 -159390971
                            1994225489 -973738098 -203424005</internalNodes>
                        <leafValues>
                            -0.3601998090744019 0.4563256204128265</leafValues></_>
                    <!-- tree 4 -->
                    <_>
                        <internalNodes>
                            0 -1 115 -261031688 -1330369299 -641860609 1029570301
                            -1306461192 -1196149518 -1529767778 683139823</internalNodes>
                        <leafValues>
                            -0.4034293889999390 0.4160816967487335</leafValues></_>
                    <!-- tree 5 -->
                    <_>
                        <internalNodes>
                            0 -1 64 -572993608 -34042628 -417865 -111109 -1433365268
                            -19869715 -1920939864 -1279457063</internalNodes>
                        <leafValues>
                            -0.3620899617671967 0.4594142735004425</leafValues></_>
                    <!-- tree 6 -->
                    <_>
                        <internalNodes>
                            0 -1 36 -626275097 -615256993 1651946018 805366393
                            2016559730 -430780849 -799868165 -16580645</internalNodes>
                        <leafValues>
                            -0.3903816640377045 0.4381459355354309</leafValues></_>
                    <!-- tree 7 -->
                    <_>
                        <internalNodes>
                            0 -1 93 1354797300 -1090957603 1976418270 -1342502178
                            -1851873892 -1194637077 -1153521668 -1108399474</internalNodes>
                        <leafValues>
                            -0.3591445386409760 0.4624078869819641</leafValues></_>
                    <!-- tree 8 -->
                    <_>
                        <internalNodes>
                            0 -1 91 68157712 1211368313 -304759523 1063017136 798797750
                            -275513546 648167355 -1145357350</internalNodes>
                        <leafValues>
                            -0.4297670423984528 0.4023293554782867</leafValues></_>
                    <!-- tree 9 -->
                    <_>
                        <internalNodes>
                            0 -1 107 -546318240 -1628569602 -163577944 -537002306
                            -545456389 -1325465645 -380446736 -1058473386</internalNodes>
                        <leafValues>
                            -0.5727006793022156 0.2995934784412384</leafValues></_></weakClassifiers></_></stages>
        <features>
            <_>
                <rect>
                    0 0 3 5</rect></_>
            <_>
                <rect>
                    0 0 4 2</rect></_>
            <_>
                <rect>
                    0 0 6 3</rect></_>
            <_>
                <rect>
                    0 1 2 3</rect></_>
            <_>
                <rect>
                    0 1 3 3</rect></_>
            <_>
                <rect>
                    0 1 3 7</rect></_>
            <_>
                <rect>
                    0 4 3 3</rect></_>
            <_>
                <rect>
                    0 11 3 4</rect></_>
            <_>
                <rect>
                    0 12 8 4</rect></_>
            <_>
                <rect>
                    0 14 4 3</rect></_>
            <_>
                <rect>
                    1 0 5 3</rect></_>
            <_>
                <rect>
                    1 1 2 2</rect></_>
            <_>
                <rect>
                    1 3 3 1</rect></_>
            <_>
                <rect>
                    1 7 4 4</rect></_>
            <_>
                <rect>
                    1 12 2 2</rect></_>
            <_>
                <rect>
                    1 13 4 1</rect></_>
            <_>
                <rect>
                    1 14 4 3</rect></_>
            <_>
                <rect>
                    1 17 3 2</rect></_>
            <_>
                <rect>
                    2 0 2 3</rect></_>
            <_>
                <rect>
                    2 1 2 2</rect></_>
            <_>
                <rect>
                    2 2 4 6</rect></_>
            <_>
                <rect>
                    2 3 4 4</rect></_>
            <_>
                <rect>
                    2 7 2 1</rect></_>
            <_>
                <rect>
                    2 11 2 3</rect></_>
            <_>
                <rect>
                    2 17 3 2</rect></_>
            <_>
                <rect>
                    3 0 2 2</rect></_>
            <_>
                <rect>
                    3 1 7 3</rect></_>
            <_>
                <rect>
                    3 7 2 1</rect></_>
            <_>
                <rect>
                    3 7 2 4</rect></_>
            <_>
                <rect>
                    3 18 2 2</rect></_>
            <_>
                <rect>
                    4 0 2 3</rect></_>
            <_>
                <rect>
                    4 3 2 1</rect></_>
            <_>
                <rect>
                    4 6 2 1</rect></_>
            <_>
                <rect>
                    4 6 2 5</rect></_>
            <_>
                <rect>
                    4 7 5 2</rect></_>
            <_>
                <rect>
                    4 8 4 3</rect></_>
            <_>
                <rect>
                    4 18 2 2</rect></_>
            <_>
                <rect>
                    5 0 2 2</rect></_>
            <_>
                <rect>
                    5 3 4 4</rect></_>
            <_>
                <rect>
                    5 6 2 5</rect></_>
            <_>
                <rect>
                    5 9 2 2</rect></_>
            <_>
                <rect>
                    5 10 2 2</rect></_>
            <_>
                <rect>
                    6 3 4 4</rect></_>
            <_>
                <rect>
                    6 4 4 3</rect></_>
            <_>
                <rect>
                    6 5 2 3</rect></_>
            <_>
                <rect>
                    6 5 2 5</rect></_>
            <_>
                <rect>
                    6 5 4 3</rect></_>
            <_>
                <rect>
                    6 6 4 2</rect></_>
            <_>
                <rect>
                    6 6 4 4</rect></_>
            <_>
                <rect>
                    6 18 1 2</rect></_>
            <_>
                <rect>
                    6 21 2 1</rect></_>
            <_>
                <rect>
                    7 0 3 7</rect></_>
            <_>
                <rect>
                    7 4 2 3</rect></_>
            <_>
                <rect>
                    7 9 5 1</rect></_>
            <_>
                <rect>
                    7 21 2 1</rect></_>
            <_>
                <rect>
                    8 0 1 4</rect></_>
            <_>
                <rect>
                    8 5 2 2</rect></_>
            <_>
                <rect>
                    8 5 3 2</rect></_>
            <_>
                <rect>
                    8 17 3 1</rect></_>
            <_>
                <rect>
                    8 18 1 2</rect></_>
            <_>
                <rect>
                    9 0 5 3</rect></_>
            <_>
                <rect>
                    9 2 2 6</rect></_>
            <_>
                <rect>
                    9 5 1 1</rect></_>
            <_>
                <rect>
                    9 11 1 1</rect></_>
            <_>
                <rect>
                    9 16 1 1</rect></_>
            <_>
                <rect>
                    9 16 2 1</rect></_>
            <_>
                <rect>
                    9 17 1 1</rect></_>
            <_>
                <rect>
                    9 18 1 1</rect></_>
            <_>
                <rect>
                    10 5 1 2</rect></_>
            <_>
                <rect>
                    10 5 3 3</rect></_>
            <_>
                <rect>
                    10 7 1 5</rect></_>
            <_>
                <rect>
                    10 8 1 1</rect></_>
            <_>
                <rect>
                    10 9 1 1</rect></_>
            <_>
                <rect>
                    10 10 1 1</rect></_>
            <_>
                <rect>
                    10 10 1 2</rect></_>
            <_>
                <rect>
                    10 14 3 3</rect></_>
            <_>
                <rect>
                    10 15 1 1</rect></_>
            <_>
                <rect>
                    10 15 2 1</rect></_>
            <_>
                <rect>
                    10 16 1 1</rect></_>
            <_>
                <rect>
                    10 16 2 1</rect></_>
            <_>
                <rect>
                    10 17 1 1</rect></_>
            <_>
                <rect>
                    10 21 1 1</rect></_>
            <_>
                <rect>
                    11 3 2 2</rect></_>
            <_>
                <rect>
                    11 5 1 2</rect></_>
            <_>
                <rect>
                    11 5 3 3</rect></_>
            <_>
                <rect>
                    11 5 4 6</rect></_>
            <_>
                <rect>
                    11 6 1 1</rect></_>
            <_>
                <rect>
                    11 7 2 2</rect></_>
            <_>
                <rect>
                    11 8 1 2</rect></_>
            <_>
                <rect>
                    11 10 1 1</rect></_>
            <_>
                <rect>
                    11 10 1 2</rect></_>
            <_>
                <rect>
                    11 15 1 1</rect></_>
            <_>
                <rect>
                    11 17 1 1</rect></_>
            <_>
                <rect>
                    11 18 1 1</rect></_>
            <_>
                <rect>
                    12 0 2 2</rect></_>
            <_>
                <rect>
                    12 1 2 5</rect></_>
            <_>
                <rect>
                    12 2 4 1</rect></_>
            <_>
                <rect>
                    12 3 1 3</rect></_>
            <_>
                <rect>
                    12 7 3 4</rect></_>
            <_>
                <rect>
                    12 10 3 2</rect></_>
            <_>
                <rect>
                    12 11 1 1</rect></_>
            <_>
                <rect>
                    12 12 3 2</rect></_>
            <_>
                <rect>
                    12 14 4 3</rect></_>
            <_>
                <rect>
                    12 17 1 1</rect></_>
            <_>
                <rect>
                    12 21 2 1</rect></_>
            <_>
                <rect>
                    13 6 2 5</rect></_>
            <_>
                <rect>
                    13 7 3 5</rect></_>
            <_>
                <rect>
                    13 11 3 2</rect></_>
            <_>
                <rect>
                    13 17 2 2</rect></_>
            <_>
                <rect>
                    13 17 3 2</rect></_>
            <_>
                <rect>
                    13 18 1 2</rect></_>
            <_>
                <rect>
                    13 18 2 2</rect></_>
            <_>
                <rect>
                    14 0 2 2</rect></_>
            <_>
                <rect>
                    14 1 1 3</rect></_>
            <_>
                <rect>
                    14 2 3 2</rect></_>
            <_>
                <rect>
                    14 7 2 1</rect></_>
            <_>
                <rect>
                    14 13 2 1</rect></_>
            <_>
                <rect>
                    14 13 3 3</rect></_>
            <_>
                <rect>
                    14 17 2 2</rect></_>
            <_>
                <rect>
                    15 0 2 2</rect></_>
            <_>
                <rect>
                    15 0 2 3</rect></_>
            <_>
                <rect>
                    15 4 3 2</rect></_>
            <_>
                <rect>
                    15 4 3 6</rect></_>
            <_>
                <rect>
                    15 6 3 2</rect></_>
            <_>
                <rect>
                    15 11 3 4</rect></_>
            <_>
                <rect>
                    15 13 3 2</rect></_>
            <_>
                <rect>
                    15 17 2 2</rect></_>
            <_>
                <rect>
                    15 17 3 2</rect></_>
            <_>
                <rect>
                    16 1 2 3</rect></_>
            <_>
                <rect>
                    16 3 2 4</rect></_>
            <_>
                <rect>
                    16 6 1 1</rect></_>
            <_>
                <rect>
                    16 16 2 2</rect></_>
            <_>
                <rect>
                    17 1 2 2</rect></_>
            <_>
                <rect>
                    17 1 2 5</rect></_>
            <_>
                <rect>
                    17 12 2 2</rect></_>
            <_>
                <rect>
                    18 0 2 2</rect></_></features></cascade>
</opencv_storage>
```