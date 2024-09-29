# ExoPlayer extensions
# ExoPlayer扩展库
[ExoPlayer](https://github.com/google/ExoPlayer)版本：2.19.1    
如果你需要使用[Media3](https://github.com/androidx/media)的扩展库，详见 [Media3Extensions](https://github.com/shenbengit/Media3Extensions)
## 目前支持：
### FFmpeg
目前官方只支持**音频解码**    
`FFmpeg构建版本：6.0`    
`启用的解码器=(vorbis opus flac alac pcm_mulaw pcm_alaw mp3 amrnb amrwb aac ac3 eac3 dca truehd)`

## 引入
### 将JitPack存储库添加到您的项目中(项目根目录下build.gradle文件)
```gradle
allprojects {
    repositories {
        ...
        mavenCentral()
    }
}
```
### 添加依赖
> 在您引入项目的build.gradle中添加
```gradle
dependencies {
    implementation 'io.github.shenbengit.exoplayer-extensions:ffmpeg:1.0.0'
}
```

## 使用事例
构建ExoPlayer时设置`RenderersFactory`，并且给`RenderersFactory`设置`setExtensionRendererMode`为`EXTENSION_RENDERER_MODE_ON`即可，内部会使用反射自动加载。
``` kotlin
private val exoPlayer: ExoPlayer by lazy {
    ExoPlayer.Builder(context)
        .setRenderersFactory(DefaultRenderersFactory(context).apply {
            // 扩展渲染器模式开启
            setExtensionRendererMode(DefaultRenderersFactory.EXTENSION_RENDERER_MODE_ON)
        })
        .build()
    }

```

## 作者其他的开源项目
- 基于RecyclerView实现网格分页布局：[PagerGridLayoutManager](https://github.com/shenbengit/PagerGridLayoutManager)
- 基于Netty封装UDP收发工具：[UdpNetty](https://github.com/shenbengit/UdpNetty)
- Android端基于JavaCV实现人脸检测功能：[JavaCV-FaceDetect](https://github.com/shenbengit/JavaCV-FaceDetect)
- 使用Kotlin搭建Android MVVM快速开发框架：[MVVMKit](https://github.com/shenbengit/MVVMKit)

# [License](https://github.com/shenbengit/ExoPlayerExtensions/blob/master/LICENSE) 
