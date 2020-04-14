# 性能调优

## 基础

* 优先使用 tensor （而不是 list…）
* 优先使用 float （而不是  int）
* 优先使用 矩阵（而不是 循环）
* `@tf.function`
* 考虑使用 `fp16`
* 增加 `batch_size` （跟显存大小相关）

## 参考

SEE ASLO: Tensorflow Performance



