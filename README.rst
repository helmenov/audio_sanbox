#############
audio_sandbox
#############



Micで音を拾う: python-sounddevice, (pyaudio))
- Mic -> stream

拾った音を系列にする: python-sounddevice, (pyaudio)
- stream -> np.ndarray

系列を貯める:list.append

Micで音拾いをやめる: python-sounddevicd, (pyaudio)

ファイルから系列を読む: soundfile,wave
- file -> np.ndarray

貯めた系列を
- ファイルに保存する(np.ndarray -> file): sounddfile, audioread
- キャリアに変調する(np.ndarray -> np.ndarray)
- 整形する(np.ndarray -> np.ndarray)
- 解析する: librosa

音を再生する
- ファイルを再生する (file->Sp): IPykernel.Audio
- ファイルからreadframeして，streamに流し，pyaudioでスピーカにつなげる
- pyaudio(SpPointer=pyaudio.PyAudio(), stream = SPPointer.open

==================================
portaudioのpythonバインディング
==================================

古いために，低遅延のASIOに対応していない．python3.7以上非対応

python-sounddeviceに乗り換えよう．


====
FAQ
====

- python-sounddeviceは
- pyaudioはportaudioのportaudio.hが必要
- soundfileはlibsndfileのsndfile.hが必要
1. `sudo find / -name "xxx.h"`　でincludeパスを見つける-> `{prefix}/include/xxx.h`
2. `pip install --global-option='build_ext' --global-option='-I{prefix}/include' --global-option='-L{prefix}/lib' pyaudio







