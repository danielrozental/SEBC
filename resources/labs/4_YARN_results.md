# 1. Results

```
Testing loop started on Tue Oct 3 18:35:55 UTC 2017
maps: 4 | reduce: 1 | mem: 512

real    0m2.030s
user    0m2.968s
sys     0m0.115s

real    2m23.382s
user    0m6.445s
sys     0m0.231s
Deleted /results/tg-10GB-4-1-512
Deleted /results/ts-10GB-4-1-512
maps: 4 | reduce: 1 | mem: 1024

real    1m7.468s
user    0m4.490s
sys     0m0.173s

real    2m20.796s
user    0m6.637s
sys     0m0.226s
Deleted /results/tg-10GB-4-1-1024
Deleted /results/ts-10GB-4-1-1024
maps: 4 | reduce: 2 | mem: 512

real    1m14.831s
user    0m4.709s
sys     0m0.203s

real    1m51.226s
user    0m6.549s
sys     0m0.215s
Deleted /results/tg-10GB-4-2-512
Deleted /results/ts-10GB-4-2-512
maps: 4 | reduce: 2 | mem: 1024

real    1m13.691s
user    0m4.717s
sys     0m0.222s

real    2m3.952s
user    0m6.754s
sys     0m0.234s
Deleted /results/tg-10GB-4-2-1024
Deleted /results/ts-10GB-4-2-1024
maps: 8 | reduce: 1 | mem: 512

real    1m9.420s
user    0m4.730s
sys     0m0.205s

real    2m30.215s
user    0m6.427s
sys     0m0.239s
Deleted /results/tg-10GB-8-1-512
Deleted /results/ts-10GB-8-1-512
maps: 8 | reduce: 1 | mem: 1024

real    1m6.710s
user    0m4.741s
sys     0m0.230s

real    2m8.128s
user    0m6.586s
sys     0m0.242s
Deleted /results/tg-10GB-8-1-1024
Deleted /results/ts-10GB-8-1-1024
maps: 8 | reduce: 2 | mem: 512

real    1m6.950s
user    0m4.569s
sys     0m0.213s

real    1m46.373s
user    0m6.494s
sys     0m0.246s
Deleted /results/tg-10GB-8-2-512
Deleted /results/ts-10GB-8-2-512
maps: 8 | reduce: 2 | mem: 1024

real    1m5.762s
user    0m4.354s
sys     0m0.217s

real    1m41.268s
user    0m6.730s
sys     0m0.225s
Deleted /results/tg-10GB-8-2-1024
Deleted /results/ts-10GB-8-2-1024
Testing loop ended on Tue Oct 3 19:01:29 UTC 2017
```

# 2. Results

Teragen 
Min 
maps: 4 | reduce: 1 | mem: 512
0m2.030s

Max
maps: 4 | reduce: 2 | mem: 512
real    1m14.831s

Terasort
Min
maps: 8 | reduce: 2 | mem: 1024
real    1m41.268s

Max
maps: 8 | reduce: 1 | mem: 512
real    2m30.215s


