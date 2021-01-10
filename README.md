# fakenews-detector
딥러닝과 단어 임베딩 모델을 이용한 한국어 가짜뉴스 탐지기

# 1. 목적 및 필요성
SNS가 급속도로 퍼지며 거짓 정보를 언론으로 위장한 형태인 가짜뉴스는 사회적 문제를 초래하였고 허위사실에 기반을 둔 혐오 표현, 명예 훼손성 정보 등이 난무하며 사회적, 개인적 차원에서의 피해가 양산되고 있습니다.
'가짜뉴스'라 총칭되는 이러한 정보는 사회적 혼란과 분열을 조장하며 우리는 더욱 정확하고 신뢰성 있는 뉴스를 전하고자 합니다.

# 2. 과제 수행 내용
한국어 가짜뉴스 모델을 제안하고자 컨볼루션 신경망(CNN, Convolutional Neural Networks)을 활용한 시스템을 구현합니다.
입력 기사를 진짜 또는 가짜뉴스로 구분하는 모델은 이진분류를 사용하였으며, 이진분류에서는 범주화를 하지 않고 현재 예측대상이 1이 될 확률을 구합니다.
모델에서 첫번째와 두 번째 은닉층은 relu함수를 사용합니다. 이진분류의 문제이고 신경망의 출력이 확률로 나와야하므로 0~1로 출력하는 sigmoid를 사용하고 노드는 1개로 하였습니다.

데이터들을 Okt 형태소 분석기로 문장을 단어들로 쪼개는 토큰화를 진행하며,
또한 결과의 정확도를 위해서 데이터 토큰화한 문장의 각 단어를 빈도순에 따라 인덱싱을 합니다. 그리고 지정된 길이에 모자라는 것은 0으로 채우고 넘치는 것은 잘라내는 padding을 진행하는 전처리 과정을 가집니다.

# 3. 기대효과 및 활용방안
이 시스템을 통해 사용자에게 입력받은 문장을 이용해 학습된 모델 내의 데이터와 비교하여 참 값과 거짓 값을 구별해낼 수 있습니다. 또한 관련 기사를 함께 제시하여 사용자들로부터 판단에 도움을 줍니다.
기존에 영어로만 존재하던 거짓 판별 프로그램을 한국어로 구현해냈다는 것에 대해 차별성이 있으며, 한국어라는 언어의 특징을 분석하여 전처리 하였다는 점에서 경쟁력을 갖추고 있습니다.
또한 가짜뉴스 판별 기술을 팩트 체크 데이터에만 그치지 않고 가짜뉴스는 업로드가 쉬운 SNS 같은 플랫폼 데이터에 적용하여 더욱 높은 활용을 기대합니다.
그리고 무차별적으로 퍼지는 가짜뉴스를 사용자가 직접 확인하고 이만큼 많은 가짜뉴스가 퍼진다는 사실을 인지하여 정보를 수동적으로 받아들이지 않고 스스로 판단할 수 있는 기대효과를 볼 수 있습니다.
