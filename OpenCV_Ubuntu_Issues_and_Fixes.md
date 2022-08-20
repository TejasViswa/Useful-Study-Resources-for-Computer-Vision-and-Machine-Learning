## OpenCV installation related commands:
- Install OpenCV:
  - Follow the instructions:
    - [Guide](https://programmer.group/ubuntu-18.04-uninstalling-and-installing-opencv.html)
- Check version of OpenCV that is installed: [Reference](https://stackoverflow.com/questions/8804064/find-opencv-version-installed-on-ubuntu)
  - Depending on how OpenCV was compiled / installed, one of the following will work:
    - ```cat $(locate OpenCVConfig.cmake) | grep "SET(OpenCV_VERSION "``` (If you have used the above guide, then this will work)
    - ```dpkg -l | grep libopencv```
    - ``` pkg-config --modversion opencv```
- Uninstall OpenCV: [Reference](https://stackoverflow.com/questions/9276169/removing-all-installed-opencv-libs)
  - Go to build directory and execute:
    - ```sudo make uninstall```
  - Additionally or alternatively, remove / purge all files related to openCV (CAUTION advised) [Execute any of the following]
    - ```sudo apt-get purge '*opencv*'```
    - ```sudo find / -name "*opencv*" -exec rm -rf {} \;```
    - ```sudo rm /usr/local/{bin,lib}/*opencv*```

## OpenCV issues:
- Build or linker errors related to ffmpeg / libavformat / libavcodec / libswscale / libavutil
  - Eg: 
    - ```
      warning: libavformat.so.58, needed by /usr/local/lib/libopencv_videoio.so.4.6.0, not found (try using -rpath or -rpath-link)
      /usr/local/lib/libopencv_videoio.so.4.6.0: undefined reference to `av_log_get_level@LIBAVUTIL_56'
      ```
  - [Solution](https://cuda-chen.github.io/programming/image%20processing/2020/01/31/libavcodec-not-found-opencv.html)
