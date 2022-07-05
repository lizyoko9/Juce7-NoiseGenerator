# Juce7-NoiseGenerator 

一款基于Juce框架开发的噪声生成应用。

### Application Lifecycle

* __AudioAppComponent::prepareToPlay()__: 在音频处理前调用。
* __AudioAppComponent::releaseResources()__: 在音频处理结束时调用。
* __AudioAppComponent::getNextAudioBlock()__: 当有新的音频数据块进入时，进行调用。

其中 __AudioAppComponent::getNextAudioBlock()__ 函数是我们主要关注的，这是在Juce音频应用程序中生成或处理音频的地方。
音频数据块：硬件中处理传输采样后的音频数据时（以44.1kHz为例，每秒会有44100个样本发送到硬件进行播放），往往不是单独传输每个Samples的，而是将许多Samples包含在一个Blocks或者说Buffers中进行传递，比如以44.1kHz和441的Buffer大小进行处理时，__AudioAppComponent::getNextAudioBlock()__ 函数将每秒调用100次。
