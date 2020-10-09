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
model.eval()
with torch.no_grad():
  pass

# precision
Trainer(precision=16)
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
