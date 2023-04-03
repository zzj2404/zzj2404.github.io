---
title: utils
categories: 论文
---




fft
```python
import torch
t1 = torch.arange(4)
t2 = torch.arange(2,6)
t3 = torch.stack([t1,t2],dim=0)
print(t1)   # tensor([0, 1, 2, 3])
print(t2)   # tensor([2, 3, 4, 5])
print(t3)   # tensor([[0, 1, 2, 3],
            #         [2, 3, 4, 5]])    
print(torch.fft.fft(t1))# tensor([ 6.+0.j, -2.+2.j, -2.+0.j, -2.-2.j])
print(torch.fft.fft(t2))# tensor([14.+0.j, -2.+2.j, -2.+0.j, -2.-2.j])
print(torch.fft.fft(t3))# tensor([[ 6.+0.j, -2.+2.j, -2.+0.j, -2.-2.j],
                        #         [14.+0.j, -2.+2.j, -2.+0.j, -2.-2.j]])

print(torch.fft.fft(t3).abs())  #tensor([[ 6.0000,  2.8284,  2.0000,  2.8284],
                                #         [14.0000,  2.8284,  2.0000,  2.8284]])

print(torch.fft.rfft(t1))   # tensor([ 6.+0.j, -2.+2.j, -2.+0.j])
print(torch.fft.rfft(t2))   # tensor([14.+0.j, -2.+2.j, -2.+0.j])
print(torch.fft.rfft(t3))   # tensor([[ 6.+0.j, -2.+2.j, -2.+0.j],
                            #         [14.+0.j, -2.+2.j, -2.+0.j]]) 
```