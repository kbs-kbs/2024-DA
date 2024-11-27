random.uniform() 은 random.uniform(5, 10) 과 같이 쓸 수도 있지만,
random.random() 은 이런 선택권이 없이 0과 1 사이 소수만 반환하게 됩니다.

```
from numpy import random
```

- `random.rand()`: [0, 1) 난수 하나
- `random.rand(3)`: [0, 1) 난수 채워진 (3) 모양의 배열 생성
- `random.rand(2, 3)`: [0, 1) 난수 채워진 (2, 3) 모양의 배열 생성
- `random.random((2, 3))`: [0, 1) 난수 채워진 (2, 3) 모양의 배열 생성
