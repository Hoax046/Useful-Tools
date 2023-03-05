## Linux中cdo命令  
### 时间合并
```bash
cdo  mergetime  gpp_Lmon-MPI*.nc  05gpp_Lmon-MPI-2001-2014.nc
```
### 二次线性插值  
```bash
cdo remapbil,r720*361 input1.nc output.nc
```
### 批量插值
```bash
for i in $(ls) ;do cdo remapbil,r720x361 ${i} 0.5_${i} ;done
```
### 时间切片
```bash
cdo seldate,2000-01-16,2014-12-16 input.nc output.nc
for i in $(ls) ;do cdo seldate,2000-01-16,2014-12-16 input.nc output.nc ;done
```
### 多模型平均
```bash
cdo ensmean infile1.nc infile2.nc infile3.nc infile4.nc outfile.nc
cdo ensmean infile*.nc outfile.nc
```
