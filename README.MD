## exTHmUI
![](logo.png)


# 下载源码

安装必要工具
```
sudo apt-get install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
```
安装repo
```
mkdir -p ~/android/lineage
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
export PATH="$HOME/bin:$PATH"
```
初始化repo
```
mkdir -p ~/android/exthm
cd ~/android/exthm
repo init -u https://github.com/exthmui/android.git -b exthm-10
(repo init -u https://github.com/exthmui/android.git -b exthm-10 --depth=1  //仅Clone一层代码，可以使Clone完成的更快)
```
同步源码
```
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```
配置编译环境
```
git clone  https://github.com/akhilnarang/scripts 
cd scripts && bash setup/android_build_env.sh && cd ../
```
初始化编译
```
. build/envsetup.sh
```
初始化设备
```
lunch lineage_[你的设备代号]-userdebug
```
编译
```
brunch [你的设备代号]
```

# 给exTHmUI提交更改

```
cd <项目目录>
git add .
git commit -m “提交内容”
git push -u origin <目标分支>
```