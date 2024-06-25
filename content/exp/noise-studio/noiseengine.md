---
title: "NoiseEngine"
description: "Game engine created focussing on performance, asynchronicity, and ease of use"
background_url: "/static/img/exp/noise-studio/noiseengine-background.webp"
---

NoiseEngine is a project which is written mostly in C#, native part is in Rust. It is a game engine which is created in around 95% by me, but I created this with help of my awesome friends - [kkard2](https://kkard2.com/) and [Xori](https://xori7.github.io/). This project was created because Unity game engine was to weak for our dreams, we wanted to create a next generation voxel game called [CubeForm](cubeform). We choosed technologies like Vulkan and started work for two years, after that we written around 1000 files of code, and created somehow working game engine.

## Performance
Creating a performant engine in C# was so difficult, from the perspective of time I think this was a mistake, but I learned a lot about performance and how to create a performant code. I learned so much about low level programming, graphics APIs especially Vulkan, and many optimization tricks.

I created a lot of different benchmarks to test the performance of the engine comparing to another engines, and I can say this is awesome to see how fast C# can be. Take a look at this draw call performance comparison bellow.

### 90k draw calls in NoiseEngine
![90k draw calls in NoiseEngine](/static/videos/exp/noise-studio/noiseengine-benchmark1-ne.webm)
### 90k draw calls in Unity
![90k draw calls in Unity](/static/videos/exp/noise-studio/noiseengine-benchmark1-unity.webm)
### 90k draw calls in Godot
![90k draw calls in Godot](/static/videos/exp/noise-studio/noiseengine-benchmark1-godot.webm)

The NoiseEngine destroyed the opponents in this benchmark, although the frametime instability in this version was due to the garbage collector, you can read more [here](https://github.com/NoiseStudio/NoiseEngine/issues/298).

## Level of details in logic (ECS)
Project have their own entity component system, written by me. Whole logic is based on that thing which is called NoiseEngine Jobs, this works little different from standard ECS, because I realized problem which exists in another game engines with too much work done for one frame.
