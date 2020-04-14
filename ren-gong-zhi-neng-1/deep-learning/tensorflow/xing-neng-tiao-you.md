# 性能调优

## 基础

* profile
* 优先使用 `tensor` （而不是 `list`…）
* 优先使用 `float` （而不是  `int`）
* 优先使用 矩阵运算（而不是 循环）
* `@tf.function`
* 考虑使用 `fp16`
* 增加 `batch_size` （跟显存大小相关）
* 数据预处理 空间换时间 `tf.data` `.npz`
* 内存缓存 减少磁盘IO
* 性能关键处考虑使用 C++ 实现（少数情况）
* 
## Python

* `__main__`

## 参考

SEE ASLO

Tensorflow Performance

[TensorFlow: Better performance with the tf.data API](https://www.tensorflow.org/guide/data_performance)

[TensorFlow: Optimize TensorFlow performance using the Profiler](https://www.tensorflow.org/guide/profiler)



