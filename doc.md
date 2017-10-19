# QuickStart 자습서

## 선수 지식

이 자습서를 읽기 전에 파이썬에 대해서 얼마정도 알아야 합니다. 기억을 더듬어보기 위해서 파이썬 자습서 - http://docs.python.org/tut - 보시기 바랍니다.

여기 자습서에 있는 예제를 돌려보기 위해서는 컴퓨터에 몇 소프트웨어가 설치되어야만 합니다. 여기 설명을 참고해 보세요 - http://scipy.org/install.html -

## 기초

NumPy의 주요한 객체는 동일한 요소를 같은 다중 배열입니다. 대부분 같은 타입의 숫자로 되어있는 요소들의 테이블 입니다. 요소는 양의 정수의 튜플로 인덱스 되어있습니다. Numpy에서는 차원을 축(axes)이라고 불리우고. 축의 개수가 랭크(rank)입니다.

예를 들어 3차원 공간의 점([1, 2, 1])의 좌표는 랭크 1의 배열입니다. 하나의 축만 가지고 있기 때문입니다.
그리고 그 점은 축은 3의 길이를 가지고 있습니다. 아래의 예제 코드에서 보면 2차원이기 때문에 랭크는 2를 가지고 있습니다. 첫번째 차원(축)은 길이가 2이고 다음 차원은 길이가 3입니다.

```python
[[ 1., 0., 0.],
 [ 0., 1., 2.]]
```

NumPy’s array class is called `ndarray`. NumPy의 배열 클래스는 `ndarray` 라고 합니다. `numpy.array`는 표준 파이썬 라이브러리 클래스 `array.array`와 같지 않다는 것에 주의해야 합니다. 표준 라이브러리는 1차원 배열로 다뤄지고 기능이 더 적습니다.

아래에는 ndarray 객체에서 중요한 속성들입니다 :

**`ndarray.ndim`**

축(차원)의 개수. 파이선에서는 차원의 개수를 랭크 말합니다.

**`ndarray.shape`**

배열의 차원들.각 체원에서 배열의 사이즈를 표시하는 정수들의 튜플입니다.
n 행과 m 열을 갖는 매트릭스를 예를들면 shape 은 (n,m) 입니다.
shape 튜플의 길이는 랭크입니다. ndim은  number of dimensions입니다. 

**`ndarray.size`**

배열의 모든 요소들의 개수입니다. shape의 요소들의 모두 곱한 값과 같습니다.

**`ndarray.dtype`**

배열에서의 요소들의 타입을 설명합니다. 하나의 배열은 dtype의 표준 파이선 타입들의 사용하기로 생성하거나 특정할 수 있습니다. 추가적으로 설명하자면  NumPy는 자체적으로 가진 타입을 제공합니다. 예를 들면 numpy.int32, numpy.int16, and numpy.float64 입니다.

**`ndarray.itemsize`**

the size in bytes of each element of the array.
배열의 각 요소의 바이트에서의 사이즈.
For example, an array of elements of type float64 has itemsize 8 (=64/8), while one of type complex32 has itemsize 4 (=32/8). 
예를 들면 float64 형식의 요소의 배열은 itemsize 8 (64/8)를 가지고 complex32 형식의 요소를 같는다면 itemsize 4 를 갖게 됩니다.
`ndarray.item`과 `ndarray.dtype.itemsize`는 같습니다.

**`ndarray.data`**

the buffer containing the actual elements of the array.
배열의 실제 요소를 가지고 있는 버퍼. 일반적으로 이 속성을 사용하지는 않습니다. 대신해 우리는 배열안에 있는 요소를 인덱싱 패실리티를 이용하여 접근합니다.
