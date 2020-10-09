```python
# Debug CUDA
os.environ['CUDA_LAUNCH_BLOCKING'] = '1'

# GPU Information
print("Device Info:")
for i in range(torch.cuda.device_count()):
  print("device ", i)
  print(torch.cuda.get_device_name(i))
  print(torch.cuda.get_device_capability(i))
  print()

print('current: ', torch.cuda.current_device())

# Random Seed
torch.manual_seed(1)

# e.g.
#  RuntimeError: one of the variables needed for gradient computation has been modified by an inplace operation
#  NaN in forward
with torch.autograd.set_detect_anomaly(True):
  pass
```
