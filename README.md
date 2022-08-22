# 軟體下載

https://drive.google.com/file/d/1im-WSuckmyLE-IgsTLJ5G4_YaWokqz2X/view?usp=sharing

# 範例專案下載

https://drive.google.com/file/d/1xLsdTmA_GUR6TGY_56L5s0NfZI905pR0/view?usp=sharing

# 步驟一、安裝 JAVA

 **jdk-8u161-windows-x64.exe**



<img src="/image/image-20220822064526251.png" alt="image-20220822064526251.png"  />

<img src="/image/image-20220822064614250.png" alt="image-20220822064614250.png"  />








# 步驟二、安裝 gcc-arm

**gcc-arm-none-eabi-7-2017-q4-major-win32-sha2.exe**



<img src="/image/image-20220822064707187.png" alt="image-20220822064707187.png"  />



<img src="/image/image-20220822064725536.png" alt="image-20220822064725536.png"  />





# 步驟三、解壓縮  gnu-mcu-eclipse

**gnu-mcu-eclipse-build-tools-2.10-20180103-1919-win64.zip**

<img src="/image/image-20220822064844122.png" alt="image-20220822064844122.png"  />



**將GNU MCU  Eclipse資料夾放到C:\目錄**



<img src="/image/image-20220822064904568.png" alt="image-20220822064904568.png"  />



# 步驟四、安裝  nRF5x-Command-Line

**nRF5x-Command-Line-Tools_9_7_2_Installer.exe**

<img src="/image/image-20220822065001564.png" alt="image-20220822065001564.png"  />

<img src="/image/image-20220822065046715.png" alt="image-20220822065046715.png"  />

# 步驟五、解壓縮 Eclipse軟體(免安裝)

**eclipse-cpp-neon-3-win32-x86_64.zip 並開啟eclipse IDE**

<img src="/image/image-20220822065125276.png" alt="image-20220822065125276.png"  />

![image-20220822065146456](C:\Users\bill\Desktop\eclipse-arm\image\image-20220822065146456.png)



# 步驟六、新建專案工作資料夾

<img src="/image/image-20220822065212308.png" alt="image-20220822065212308.png"  />

# 步驟七、安裝Eclipse Embedded C/C++ 套件

<img src="/image/image-20220822065254821.png" alt="image-20220822065254821.png"  />

<img src="/image/image-20220822065307059.png" alt="image-20220822065307059.png"  />

<img src="/image/image-20220822065320227.png" alt="image-20220822065320227.png" />

<img src="/image/image-20220822065335365.png" alt="image-20220822065335365.png" />

<img src="/image/image-20220822065351428.png" alt="image-20220822065351428.png" />





# 步驟八、開啟現有專案(AP1000  Source Code)



**File -> Import -> General -> Existing  Project into Workpace -> Next**

<img src="/image/image-20220822065531038.png" alt="image-20220822065531038.png" />



# 步驟九、設定編譯環境

## 設定arm  toolchains 路徑

**Project  -> Properties->MCU->Arm toolchains Paths**

**gcc-arm 預設安裝路徑 : C:\Program Files (x86)\GNU  Tools ARM Embedded\7 2017-q4-major\bin**

<img src="/image/image-20220822065703670.png" alt="image-20220822065703670.png" />

## 設定Build  Tools 路徑

**Project  -> Properties->MCU->Build Tools Path**

**建議放置路徑: C:\GNU MCU Eclipse\Build  Tools\2.10-20180103-1919\bin**

<img src="/image/image-20220822065833521.png" alt="image-20220822065833521.png" />



## 設置Global參數

**Window->Preferences->MCU->Global  Arm toolchains Paths**

<img src="/image/image-20220822065926603.png" alt="image-20220822065926603.png" />



**Window->Preferences->MCU->Global  Build Tools Path**

<img src="/image/image-20220822065953049.png" alt="image-20220822065953049.png" />



# 步驟十、  Clean Project & Build Project

<img src="/image/image-20220822070039499.png" alt="image-20220822070039499.png" />

<img src="/image/image-20220822070054051.png" alt="image-20220822070054051.png" />

<img src="/image/image-20220822070117114.png" alt="image-20220822070117114.png" />



## Build 完成

<img src="/image/image-20220822070142698.png" alt="image-20220822070142698.png" />



## Build  出來的hex檔在下方路徑

<img src="/image/image-20220822070233636.png" alt="image-20220822070233636.png" />



**步驟十操作完可能還會顯示很多錯誤，請參考步驟十一排除問題**

<img src="/image/image-20220822074449497.png" alt="image-20220822074449497.png" />



-----



# 步驟十一 、專案設定

## C/C++Build設定(重要)

專案環境設定 右鍵選擇properties

<img src="/image/image-20220822072653152.png" alt="image-20220822072653152.png" />

**這邊非常重要**

Make VERBOSE=1 一定要設定 不然Build完還是會一堆Error

<img src="/image/image-20220822072730174.png" alt="image-20220822072730174.png" />

## C/C++ General設定 (重要)

**非常重要**  

**如果Build還是出現錯誤，可以再來這邊確認參數有沒有設錯**

```
(.*gcc)|(.*[gc]\+\+)
```

<img src="/image/image-20220822072949276.png" alt="image-20220822072949276.png" />



**非常重要**

**如果Build還是出現錯誤，可以再來這邊確認參數有沒有設錯**

```
arm-none-eabi-gcc ${FLAGS} ${cross_toolchain_flags} -E -P -v -dD "${INPUTS}"
```

<img src="/image/image-20220822073058869.png" alt="image-20220822073058869.png" />



## 載入Source code 

Import -> File System

<img src="/image/image-20220822073858084.png" alt="image-20220822073858084.png" />



a.載入app\gfit_demo\src

<img src="/image/image-20220822073933995.png" alt="image-20220822073933995.png" />



b. 載入app\gfit_demo\inc

<img src="/image/image-20220822074000106.png" alt="image-20220822074000106.png" />

載入成功如下

<img src="/image/image-20220822074032542.png" alt="image-20220822074032542.png" />

## Build project

<img src="/image/image-20220822074619486.png" alt="image-20220822074619486.png" />

Building…



<img src="/image/image-20220822074652263.png" alt="image-20220822074652263.png" />

Build完成

<img src="/image/image-20220822074715228.png" alt="image-20220822074715228.png" />



## 錯誤排除

Build完還是有Error (code 顯示一堆驚嘆號跟問號) 可試看看以下選項

同時確認步驟**C/C++Build**設定與**C/C++ General**設定是否有錯誤或遺漏

```
Refresh 
```

```
Index->Rebuild  
```

```
Index->Freshen All Files
```

以上方法需要多嘗試幾次

不斷的Clean Project & Build Project 

有時候需要重新開啟Eclipse或是重開機才可完全排除Source code 上顯示的Error

<img src="/image/image-20220822074753073.png" alt="image-20220822074753073.png" />





## Debug 設定

**Debug Setting** 

​        

<img src="/image/image-20220822074942350.png" alt="image-20220822074942350.png" />

![image-20220822074956665](C:\Users\bill\Desktop\eclipse-arm\image\image-20220822074956665.png)



```
nRF52832_xxAA
```

```
arm-none-eabi-gdb
```

<img src="/image/image-20220822075011826.png" alt="image-20220822075011826.png" />



<img src="/image/image-20220822075030466.png" alt="image-20220822075030466.png" />
