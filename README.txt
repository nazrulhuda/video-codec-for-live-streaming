# Project Name: Devising Faster Video Streaming Architecture with Low Bandwidth Video Compression Techniques

We compare H264, H265, and VP9 objectively by quality metrics like
(PSNR, SSIM, etc.) and encoding time. To encode the videos we use FFmpeg. 

FFmpeg is the most used multimedia framework, capable of
decoding, encoding, transcoding, muxing, demuxing, streaming,
ltering, and playing almost everything that humans and machines
have developed. It's portable: FFmpeg compiles, runs, and passes our
FATE testing infrastructure on Linux, Mac OS X, Windows, BSDs, Solaris,
and other platforms. 

We use libx264 of FFmpeg library for x264, H.264/MPEG-4 AVC, libx265 for x265 H.265/HEVC, and libvpx-vp9 for VP9.



To run this project locally, follow these steps:


  git init
  git add README.md
  git commit -m "first commit"
  git branch -M main
  git remote add origin https://github.com/nazrulhuda/video-codec-for-live-streaming.git
  git push -u origin main


FROM MP4 TO  H264

  ffmpeg -i original.mp4 -an -vcodec libx264 -crf 23  result264.h264

FROM MP4 TO H265
 
  ffmpeg -i original.mp4 -an -vcodec libx265 -crf 23  result265.h265


FROM MP4 TO VP9

  ffmpeg  -i original.mp4 -c:v libvpx-vp9 -c:a libopus resultvp9.webm

FROM TO ADD SSIM PSNR AND VMAF 

  ffmpeg -i compressed.mp4 -i original.mp4 -lavfi libvmaf="model_path='C\:\\PATH_programs\\vmaf_v0.6.1.json':psnr=1:ssim=1:log_fmt=csv:log_path=VMAF.csv" -f null -


