# Juce7-NoiseGenerator

一个基于Juce框架开发的噪声生成应用。

### Application Lifecycle

* AudioAppComponent::prepareToPlay(): This is called just before audio processing starts.
* AudioAppComponent::releaseResources(): This is called when audio processing has finished.
* AudioAppComponent::getNextAudioBlock(): This is called each time the audio hardware needs a new block of audio data.
