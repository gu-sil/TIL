# Python and Vectorization

## Vectorization

- What is 'Vectorization'?

  - 코드 상에서 for loop를 벡터를 통해 제거하는 방법

  - 예를 들어 다음과 같은 방식의 코드가 있을 수 있다.

    - ```python
      z = 0
      for i in range(n - x):
      	z += w[i] * x[i]
      ```

  - 이 코드는 벡터화를 통해 다음과 같이 바꿀 수 있다.

    - ```python
      z = 0
      z += np.dot(w, x)
      ```

  - 벡터화된 버전이 for에 비해 월등히 빠른 속도를 가지고 있다. (SIMD에서 백만*백만 일때 약 300배정도 빠름)


## Vectorizing Logistic Regression

- 벡터라이징을 통해 Logistic Regression을 for를 한 줄의 코드로 바꿀 수 있다.

  - ```python
    z = np.dot(w.T, X) + b
    ```

  - db도 같은 방식으로 벡터라이징 가능하다.

    ```python
    db = (1/m) * np.sum(dz)
    ```

## Broadcasting

