## **1. train / validation / test**
### **1-1. train / test**
- **최적의 모델을 찾기 위해** 우리가 갖고 있는 데이터를 train과 test로 나눈 후, 
train data로 각각의 모델을 학습시키고, test data로 각 모델의 최종 정확도를 확인한다.
- 다시 말해서, 우리가 어떤 데이터를 사용하여 예측을 해야하는지 모르기 때문에
  1. 주어진 데이터를 train/test로 나누고,
  2. train data로만 모델을 학습하면서 최적의 매개변수를 찾은 다음,
  3. test data를 사용하여 모델의 실력을 평가한다. (정확도, MSE 등)
    
  ※ 이때, train과 test를 어떻게 나눌 것인지에 따라서도 모델의 성능이 다르기 때문에 주의해야한다. ※


### **1-2. validation**
- 데이터를 train과 test로만 분리할 경우, 정해져있는 test data만 사용하여 성능을 개선해야한다.

  이 과정을 반복하다보면 결국 모델이 현재 갖고 있는 test data에만 맞춰진 모델이 되어, 이 데이터에는 성능이 좋을 수 있으나 다른 데이터가 들어올 경우 성능이 떨어지는 상황인 **과적합(Overfitting)** 이 발생할 수 있다.

  여기서 validation을 사용할 수 있다.

  validation은 train data를 통해 훈련된 모델의 성능을 측정하기 위해 사용된다(검증). 학습이 된 여러 모델 중 가장 적합한 모델을 고르기 위한 데이터 셋이다.

- 정리하자면,
    - **train** : 모델을 학습하기 위한 데이터셋 (only 학습)
    - **validation** : 이미 학습이 완료된 모델을 검증하기 위한 데이터셋, 여러 모델 중 최적의 모델을 고르기 위한 데이터셋
    -  **test** : 모델의 최종 성능을 평가하기 위한 데이터셋 (학습 과정에 관여 X)

### **1-3. 데이터 분할**
- 보통 데이터를 분할할 때는 train : test = 8 : 2 (또는 7:3)로 나눈다.
- validation을 포함할 경우, train : validation : test = 6 : 2 : 2 로 보통 사용한다.
- train data 성능은 높은 반면, validation data의 성능이 낮다면 해당 모델은 과적합(Overfitting)되었을 가능성이 크다. 이를 막기 위해서는 train의 성능을 좀 포기하더라도 validation의 성능과 비슷하게 맞춰줄 필요가 있다.
- 전체 데이터의 양이 적을 경우, train data를 K-fold 방식으로 쪼개서 모든 데이터를 train과 validation 과정에 사용할 수 있다.


------


* 참고 링크: https://wkddmswh99.tistory.com/10
  
