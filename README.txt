FFmpeg 64-bit static Windows build from www.gyan.dev

Version: 2021-09-20-git-59719a905c-full_build-www.gyan.dev

License: GPL v3

Source Code: https://github.com/FFmpeg/FFmpeg/commit/59719a905c

git-full build configuration: 

    --enable-gpl
    --enable-version3
    --enable-static
    --disable-w32threads
    --disable-autodetect
    --enable-fontconfig
    --enable-iconv
    --enable-gnutls
    --enable-libxml2
    --enable-gmp
    --enable-lzma
    --enable-libsnappy
    --enable-zlib
    --enable-librist
    --enable-libsrt
    --enable-libssh
    --enable-libzmq
    --enable-avisynth
    --enable-libbluray
    --enable-libcaca
    --enable-sdl2
    --enable-libdav1d
    --enable-libzvbi
    --enable-librav1e
    --enable-libsvtav1
    --enable-libwebp
    --enable-libx264
    --enable-libx265
    --enable-libxvid
    --enable-libaom
    --enable-libopenjpeg
    --enable-libvpx
    --enable-libass
    --enable-frei0r
    --enable-libfreetype
    --enable-libfribidi
    --enable-libvidstab
    --enable-libvmaf
    --enable-libzimg
    --enable-amf
    --enable-cuda-llvm
    --enable-cuvid
    --enable-ffnvcodec
    --enable-nvdec
    --enable-nvenc
    --enable-d3d11va
    --enable-dxva2
    --enable-libmfx
    --enable-libglslang
    --enable-vulkan
    --enable-opencl
    --enable-libcdio
    --enable-libgme
    --enable-libmodplug
    --enable-libopenmpt
    --enable-libopencore-amrwb
    --enable-libmp3lame
    --enable-libshine
    --enable-libtheora
    --enable-libtwolame
    --enable-libvo-amrwbenc
    --enable-libilbc
    --enable-libgsm
    --enable-libopencore-amrnb
    --enable-libopus
    --enable-libspeex
    --enable-libvorbis
    --enable-ladspa
    --enable-libbs2b
    --enable-libflite
    --enable-libmysofa
    --enable-librubberband
    --enable-libsoxr
    --enable-chromaprint


MP4 TO  H264
ffmpeg -i original.mp4 -an -vcodec libx264 -crf 23  result264.h264

MP4 TO H265
ffmpeg -i original.mp4 -an -vcodec libx265 -crf 23  result265.h265


MP4 TO VP9
ffmpeg  -i original.mp4 -c:v libvpx-vp9 -c:a libopus resultvp9.webm

TO ADD SSIM PSNR AND VMAF 
ffmpeg -i compressed.mp4 -i original.mp4 -lavfi libvmaf="model_path='C\:\\PATH_programs\\vmaf_v0.6.1.json':psnr=1:ssim=1:log_fmt=csv:log_path=VMAF.csv" -f null -


