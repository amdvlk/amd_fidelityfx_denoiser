# FidelityFX Denoiser

Copyright (c) 2021 Advanced Micro Devices, Inc. All rights reserved.
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

## Overview

FidelityFX Denoiser contains a collection of highly optimized denoiser implementations for specific use cases.

## FidelityFX Shadow Denoiser

A spatio-temporal denoiser for raytraced soft shadows. It is intended to be used on a shadow mask that was created from at most one jittered shadow ray per pixel.
It makes use of a tile classification pass to skip work on areas without spatial variance in the shadow mask.
In cases of low temporal sample counts, the contribution from the spatial filters are increased, which successively cools off as the temporal sample count increases.
The denoiser aims to avoid ghosting artifacts by analyzing the local pixel neighborhood and clamping the accumulated history.

### Links

- ffx-shadows-dnsr contains the [Shadow Denoiser](https://github.com/GPUOpen-Effects/FidelityFX-Denoiser/tree/master/ffx-shadows-dnsr)

## FidelityFX Reflection Denoiser

The reflection denoiser includes a high performance spatio-temporal denoiser specialized for reflection denoising.
The preferred use case of this denoiser is within applications requiring denoised radiance values generated by some stochastic reflection implementation.
Examples of stochastic reflections:
- Stochastic Screen Space Reflections
- Stochastic Raytraced Reflections

### Links

- ffx-reflection-dnsr contains the [Reflection Denoiser](https://github.com/GPUOpen-Effects/FidelityFX-Denoiser/tree/master/ffx-reflection-dnsr)
- Visit [FidelityFX SSSR](https://github.com/GPUOpen-Effects/FidelityFX-SSSR/tree/master/sample) to see the reflection denoiser in action.

