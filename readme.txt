请把该文件夹解压到 /data/local/
描述:Pulseaudio for Android NDK with experimental OpenSL ES backend driver
作者:twaik
源代码:https://github.com/twaik/pulseaudio-sles-ndk.git
在chroot:输入 export PULSE_SERVER=tcp:127.0.0.1:4714 即可使用

在android:输入 env PULSE_RUNTIME_PATH=/data/local/pulse/tmp/ PULSE_STATE_PATH=/data/local/pulse/tmp/ LD_LIBRARY_PATH=/data/local/pulse/lib/:/data/local/pulse/modules /data/local/pulse/bin/pulseaudio -vvv -n --use-pid-file=no -p /data/local/pulse/modules -L module-sles-sink  -L "module-native-protocol-tcp auth-cookie-enabled=false port=4714 auth-ip-acl=127.0.0.1/8"
