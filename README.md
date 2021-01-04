# Portfolio_Stock-price-prediction-program


# 프로그램 소개
주식 Close data를 이용해 향후 주식의 흐름을 예측하는 프로그램입니다.

GOLDEN CROSS와 DEATH CROSS 개념을 활용해 향후 주식의 상승세와 하락세를 예측합니다.

ARMA, LSTM, Random forest, XGBoost 모델을 적합하고 RMSE값을 확인해 최적의 모델을 확인합니다.

# 예시 프로그램 

# 주식 데이터 불러오기 및 흐름 확인 
![stock_1](https://user-images.githubusercontent.com/29458670/87872823-c3a91f80-c9f6-11ea-9f70-41f050f0430f.PNG)
##### 2019년부터 2020년 6월까지 삼성전자의 주식 데이터를 불러옵니다. 

![stock_2](https://user-images.githubusercontent.com/29458670/87872847-14207d00-c9f7-11ea-8238-1751a84366ad.PNG)
##### golden_cross 함수, dead_cross함수를 이용해 주식 흐름을 그래프로 확인합니다. 
##### 확인결과 마지막으로 확인된 cross는 mid golden cross로 2019-09-20 지점에서 발생했습니다. 

![image](https://user-images.githubusercontent.com/29458670/103500670-1ab08d00-4e8f-11eb-8843-aa51c44db813.png)
##### 골든 GOLDEN 크로스는 단기/중기/장기 (5일/20일/60일) 이동평균선이 (20일/60일/120일) 이동평균선을 밑에서 위로 치고 올라가면서 만나는 때를 말합니다. 단기 상승추세가 지속된다는 것을 전제로 골든크로스는 매수신호로 간주되며 이때 거래량의 변화에도 주목해야 합니다. 거래량 증가는 강력한 매수신호가 되고 결국 강세장으로 전환될 가능성이 높다는 의미입니다.
##### 반대로 데드 DEATH 크로스는 반대로 단기 이동평균선이 장기 이동평균선을 위에서 아래로 뚫고 내려가는 모습을 말합니다. 즉 단기 이동평균선이 하락하고 있으며 따라서 데드크로스는 단기 하락추세가 이어진다는 전제로 매각신호로 간주됩니다.

# 모델 적합(1) - ARMA
![ARMA1](https://user-images.githubusercontent.com/29458670/87872974-55655c80-c9f8-11ea-82ea-e19d04ef3cca.PNG)
##### 시계열 데이터가 white noise일 경우 모형 설정이 불가능, white noise test 진행하였습니다. 

![ARMA2](https://user-images.githubusercontent.com/29458670/87872998-9e1d1580-c9f8-11ea-924f-42172f7e5b85.PNG)
##### ARMA 모델 적합 결과 

![ARMA3](https://user-images.githubusercontent.com/29458670/87873003-b12fe580-c9f8-11ea-9c57-461ccb1016f5.PNG)
##### 원래 데이터와 ARMA 모델의 예측 값을 그래프로 확인합니다. 
##### 추가적으로 RMSE값을 title에서 확인할 수 있습니다. 

# 모델 적합(2) - LSTM
![LSTM1](https://user-images.githubusercontent.com/29458670/87873026-e4727480-c9f8-11ea-9b4b-857e03032bef.PNG)
##### LSTM 모델은 데이터 스케일에 영향을 크게 받아서 표준화를 진행합니다. 

![LSTM2](https://user-images.githubusercontent.com/29458670/87873049-0f5cc880-c9f9-11ea-9402-7dc2715a9844.PNG)
##### 모델을 적합한 모습입니다.

![LSTM3](https://user-images.githubusercontent.com/29458670/87873063-213e6b80-c9f9-11ea-9a6e-ad194fa75bf3.PNG)
#### ARMA 모델과 함께 LSTM 모델을 그래프로 확인합니다.
#### title에 표시된 RMSE 값을 통해 우수한 모델을 확인할 수 있습니다.

# 모델 적합(3) - Random forest 
![RAM1](https://user-images.githubusercontent.com/29458670/87873079-47fca200-c9f9-11ea-9a3d-0c1bab2f96b9.PNG)
##### 주식 데이터를 이용하여 새로운 변수를 생성합니다. 

![RAM2](https://user-images.githubusercontent.com/29458670/87873097-6498da00-c9f9-11ea-8c29-a9e193ae51f6.PNG)
##### 3종류의 모델을 모두 적합한 후 그 결과를 한 그래프로 확인합니다.
##### 3종의 모델 중 RMSE값이 가장 크게 나온 Random forest 모델이 이 경우 가장 우수합니다.  


### 사용된 Library
**FinanceDataReader**,
**pandas**,
**matplotlib.pyplot**,
**statsmodels.api**,
**auto_arima**,
**math**,
**tensorflow**,
**r2_score**,
**mean_squared_error**,
**numpy**,
**MinMaxScaler**,
**Sequential**,
**warnings**,
**RandomForestClassifier**,
**classification_report**
