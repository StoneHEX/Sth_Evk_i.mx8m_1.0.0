# SthRevVar_i.mx8m_1.0.0<br>
This repo provides the patches and necessary files to patch buildroot 2023.08.4.<br>
The files are stored on this repo to have something stable and checked trough variations in the cloned repositories.<br>

## Quick instructions:

1: clone buildroot : <b>git clone https://github.com/buildroot/buildroot.git</b> or <b>git clone https://github.com/StoneHEX/buildroot-2023.08.4</b><br>
2: download <b>i.mx8evk_br-2023.08.4_001.patch</b> from here :<br>**** [https://github.com/StoneHEX/SthRevVar_i.mx8m_1.0.0/blob/master/i.mx8evk_br-2023.08.4_001.patch](https://github.com/StoneHEX/Sth_Evk_i.mx8m_1.0.0/blob/master/i.mx8evk_br-2023.08.4_001.patch) ****<br>
3: rename buildroot obtained directory in step 1 with the name you like and enter it<br>
4: if you cloned the original buildroot checkout branch 2023.08.4 : <b>git checkout 2023.08.4</b><br>
5: apply patch with <b>patch -p1 < ../i.mx8evk_br-2023.08.4_001.patch</b><br>
6: configure with <b>make sth_evk_i.mx8m_defconfig</b><br>
7: make with <b>make</b><br>
### WARNING : check your device is /dev/sdb , mksd.sh defaults to it so change it if different !!!
### WARNING : selecting the wrong device can destroy your hard disk
8: create sd card with <b>mksd.sh</b><br>

## Notes
The packages are downloaded in the directory specified by buildroot configurations, default is /Devel/buildroot/Downloads.<br>
For different download directory enter the menu configuration <b>make menuconfig</b> after the above step 5 ( <b>make sth_evk_i.mx8m_defconfig</b> )<br>
This will modify your buildroot configuration file but not the default one ( <b>sth_evk_i.mx8m_defconfig</b> ), if you prefer to make the changes
 permanent copy the <b>.config</b> file in the configs directory, e.g. <b>cp .config configs/sth_evk_i.mx8m_defconfig</b>
