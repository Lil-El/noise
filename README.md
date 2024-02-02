# Noise

## 灰度色彩空间

当 RGB 三个值始终相等时，表示使用了灰度色彩空间（grayscale color space）。在灰度色彩空间中，每个像素的颜色由一个单一的亮度值表示，而不考虑颜色的饱和度或色调。

在灰度色彩空间中，亮度值的范围通常是从 0（黑色）到 255（白色），使用 8 位的整数表示。这意味着你可以在灰度色彩空间中表示 256 种不同的灰度级别。

当 RGB 的三个值相等时，例如 (R, R, R) 或 (G, G, G) 或 (B, B, B)，它们都表示相同的亮度值。这种情况下，RGB 值的范围也是从 0 到 255，但是三个通道的值始终相等，因此可以看作是灰度值的表示。

需要注意的是，当 RGB 三个值不相等时，表示的是彩色色彩空间，其中每个通道的值可以独立地表示不同的饱和度和色调，从而产生更广泛的颜色范围。

## 噪声算法返回值

常见的噪声算法（如柏林噪声、简单噪声等）通常返回范围在 -1 到 1 之间的值。这个范围是一种标准化的方式，使得噪声的取值范围在正负之间均匀分布。

在柏林噪声算法中，每个点的噪声值是通过插值多个随机梯度向量得到的。这些梯度向量的分量通常在 -1 到 1 之间。通过对这些梯度向量进行插值和加权，最终得到的柏林噪声值也会在 -1 到 1 之间。

需要注意的是，具体的噪声算法实现可能会有所不同，有些算法可能返回的值范围是 0 到 1，或是其他不同的范围。

## [noisejs](https://github.com/josephg/noisejs)

All noise functions return values in the range of -1 to 1.

The library exposes an object called noise with the following properties:

- simplex2(x, y): 2D Simplex noise function
- simplex3(x, y, z): 3D Simplex noise function
- perlin2(x, y): 2D Perlin noise function
- perlin3(x, y, z): 3D Perlin noise function
- seed(val): Seed the noise functions. Only 65536 different seeds are supported. Use a float between 0 and 1 or an integer from 1 to 65536.

## [simplex-noise](https://github.com/jwagner/simplex-noise.js)

## 参考

- [随机不只是 Math.random —— 前端噪声应用](https://juejin.cn/post/6844903888416423943)
- [WebGL 进阶——走进图形噪声](https://segmentfault.com/a/1190000019452144)
