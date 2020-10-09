# 性能调优

Tensor! CUDA! Profile!
Tensor! CUDA! Profile!
Tensor! CUDA! Profile!

### Memory Transfer

```python
DataLoader(dataset, pin_memory=True)

t = tensor.rand(2, 2, device=device)
# Instead of
# tensor.rand(2,2).cuda()

.detach()
# Avoid:
# .cpu()
# .item()
# .numpy()

torch.cuda.empty_cache()
```

### Computing

```python
module.eval()
with torch.no_grad():
  pass

# precision
Trainer(precision=16)

# automatic mixed precision (AMP)
# See below

# Use PyTorch JIT
# fuse pointwise operations into a single CUDA kernel
@torch.jit.script
def fused_calc(x):
  pass
# scripted module
scripted_module = torch.jit.script(module)

```

#### automatic mixed precision (AMP)

```python
import torch
# Creates once at the beginning of training
scaler = torch.cuda.amp.GradScaler()

for data, label in data_iter:
   optimizer.zero_grad()
   # Casts operations to mixed precision
   with torch.cuda.amp.autocast():
      loss = model(data)

   # Scales the loss, and calls backward()
   # to create scaled gradients
   scaler.scale(loss).backward()

   # Unscales gradients and calls
   # or skips optimizer.step()
   scaler.step(optimizer)

   # Updates the scale for next iteration
   scaler.update()
```

### Multi GPU

Use DistributedDataParallel not DataParallel

### Profile

```python
Trainer(profile=True)

profiler = AdvancedProfiler()
trainer = Trainer(profiler=profiler)
```

### Others

```python
torch.backends.cudnn.benchmark = True
```

## References

1. [7 Tips To Maximize PyTorch Performance](https://towardsdatascience.com/7-tips-for-squeezing-maximum-performance-from-pytorch-ca4a40951259)
2. [Pytorch Performance Tuning Guide](https://nvlabs.github.io/eccv2020-mixed-precision-tutorial/files/szymon_migacz-pytorch-performance-tuning-guide.pdf)
3. [Introducing native PyTorch automatic mixed precision for faster training on NVIDIA GPUs](https://pytorch.org/blog/accelerating-training-on-nvidia-gpus-with-pytorch-automatic-mixed-precision/)
