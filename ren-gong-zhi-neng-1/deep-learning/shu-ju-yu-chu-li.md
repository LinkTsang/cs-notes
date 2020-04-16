# 数据预处理

## Feature scaling\(特征缩放\)

 **Rescaling \(min-max normalization\)**

$$
x' = \frac{x - \text{min}(x)}{\text{max}(x)-\text{min}(x)}
$$

 **Mean normalization**

$$
x' = \frac{x - \text{average}(x)}{\text{max}(x)-\text{min}(x)}
$$

#### Standardization \(Z-score Normalization\)

$$
x' = \frac{x - \bar{x}}{\sigma}
$$

 **Scaling to unit length**

$$
x'= \frac{x}{\|x\|}
$$

**归一化：Rescaling 和**  **Standardization，作用：提升梯度下降速度。**

