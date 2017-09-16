# webgpu-servo
[WebGPU](https://github.com/gpuweb/gpuweb) prototope in [Servo](https://github.com/servo/servo/) browser, backed by [gfx low-level core](https://github.com/gfx-rs/gfx).

## Build instructions

Depenencies:
- Rust

```bash
git clone --recursive https://github.com/kvark/webgpu-servo
cd webgpu-servo/servo
./mach build -d
./mach run ../examples/04-draw.html # or any other
```

## ToDo:
- [ ] move `webrender_api` from the GPU thread onto `WebGpuRenderingContext`, avoid `Present` call
- [x] have a deque of frames to show, avoid waiting as much in the external handler
- [ ] investigate one-shot channels and `Future` usage for latency hiding
- [ ] figure out `Send+Sync` bounds of `DescriptorSetLayout` and `DescriptorPool`
- [ ] textures and heaps: test [05-image](examples/05-image.html)
