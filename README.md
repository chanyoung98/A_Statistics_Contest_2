# spotify_genre_prediction
음악 장르 예측하기

## Introduction
- 대중음악은 빠르게 변화하는 경향이 있으며, 음악 장르를 파악하는 것은 최신 트랜드를 파악하고 적절한 음악 콘텐츠 제공으로 이어질 수 있음
- Spotify의 음악 데이터를 활용하여 보다 정확한 음악 장르 예측 모델 구현 -> 음악 트랜드 파악, 음악 카테고리화 등 다방면으로 유용할 것 예상

## Objectives
- 결측치 확인 - 결측치 없음
- 종속변수인 genre를 one-hot encoding. 대조집단에 비해 사례집단 수가 현저히 떨어지는 장르는 제외 => Pop, Hiphop, R&B, Dance/Electronic 4개의 장르를 예측하는 task로 변경
- 히스토그램과 상자그림을 통해 각 장르별 변수의 특징 확인
- 3가지의 변수선택기법(Select From Model, Permutation Importance, MDI importance)과 팀원들의 도메인적 지식을 활용하여 변수 제거
- 데이터 불균형 현상을 가지는 Dance/Electronic 장르 데이터의 경우 Recall값이 현저히 낮아지는 것을 확인 -> 오버샘플링 기법(SMOTE, Borderline SMOTE, ADASYN)으로 데이터 불균형 일부 해결
- 4개의 모델(RandomForest, Gradient Boostingk, Light GBM, XGBoost)을 훈련시키고 하이퍼파리미터 튜닝 과정을 진행한 후 Hard Voting과 Soft Voting을 거져 각 장르별 가장 좋은 성능을 가지는 모델 선정

## Conclusion
- 각 모델에 대한 변수 선택, 오버샘플링을 통한 데이터 불균형 해결, Ensemble 적극 활용으로 2000개의 적은 데이터임에도 불구하고 높은 성능을 얻어낼 수 있었음
- 시간적인 문제로 실제 가사를 크롤링하여 tf-idf를 통해 가사의 키워드를 활용하는 등의 시도를 하지 못한 것에 대해 아쉬움이 있음
