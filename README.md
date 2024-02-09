<h2>Analysis and prediction of Microsoft's stock prices using LSTM model in Keras</h2>

<h3>Introduction</h3>

<h4>Microsoft Corporation: An Overview</h4>

<b>Headquarters:</b> Based in Redmond, Washington, United States of America. Microsoft stands as a pivotal American multinational technology firm.

<b>Core Products:</b> It is renowned for its Windows operating systems, the Microsoft 365 productivity suite, and the Edge web browser.

<b>Hardware Innovations:</b> The company is also celebrated for its innovative hardware, including the Xbox gaming consoles and the versatile Microsoft Surface product line.

<b>Market Leadership:</b> As of 2022, Microsoft has the distinction of being the world's largest software maker by revenue, and it holds the 14th spot in the Fortune 500 rankings.

<b>Industry Eminence:</b> It is acclaimed as one of the Big Five American technology companies, in the esteemed company of Alphabet, Amazon, Apple, and Meta.

<h4>Microsoft Stocks (MSFT)</h4>

<b>Ownership Representation:</b> Microsoft stocks symbolize a share of ownership in this technological powerhouse, mirroring its fiscal health and performance.

<b>Market Dynamics:</b> The value of Microsoft stocks is subject to fluctuation, influenced by market demands and various elements that affect the tech sector.

<b>Investment Activity:</b> Investors engage in the buying and selling of stocks on exchanges, seeking to capitalize on shifts in stock prices.

<b>The Stock Market:</b> This vibrant marketplace is not just a platform for trading shares; it's integral to the economy at large and serves as a channel for investors to augment their wealth.

<h3>Overview of LSTM and its suitability for stock data</h3>

<b>Invaluable Insights:</b> 
LSTM models are instrumental for investors, providing critical analysis and predictions of stock prices, thereby aiding decision-making and spotlighting potential investment opportunities.

<b>Technical Foundation:</b> LSTM, or Long Short-Term Memory, is a type of recurrent neural network (RNN) known for its proficiency in handling and forecasting time-series data. Pioneered by Sepp Hochreiter and Jurgen Schmidhuber in their seminal work published in Neural Computation, LSTM's design addresses and overcomes limitations found in traditional RNNs.

<b>Applications and Capabilities:</b> LSTMs are celebrated for their significant achievements in a broad spectrum of applications. Their advanced architecture enables them to intricately analyze historical price trends and trading volumes, equipping them to generate predictions that encapsulate the intricate patterns of market movements(2).

<b>Strategic Advantages:</b> The strength of LSTMs lies in their capacity to remember and learn from extensive sequences of data. This attribute is particularly beneficial in stock price forecasting, where the ability to recall long-term dependencies and adjust to the financial market's inherent volatility is crucial(2).

In summary, LSTMs are a powerful tool for stock price prediction due to their ability to process sequential data, remember long-term dependencies, and adapt to the volatile nature of financial markets.

<h3>Why LSTM Model was adopted for this project</h3>
LSTMs models are designed with feedback loops, enabling them to process entire sequences of data. This feature is particularly effective for identifying and forecasting sequential patterns, which is a fundamental aspect of time series data, as well as text and speech.

Unlike traditional RNNs that are prone to the vanishing gradient problem, LSTMs are built to circumvent this issue. This makes them more reliable for learning from data where the gradient might otherwise diminish through the layers over time.

LSTMs boast a sophisticated cell structure equipped with input, output, and forget gates. This complex architecture stands in contrast to the simpler structure of RNNs, which contain only a single hidden state. The intricate gate mechanism of LSTMs allows for more nuanced control over the information flow through the network.

The ability to handle long-term dependencies is a hallmark of LSTM networks. They are adept at maintaining relevant information over extended sequences, which is crucial in time series forecasting where past information can significantly influence future predictions.

LSTMs are not just suitable for financial time series analysis; they excel in a variety of tasks requiring the retention of information over long periods. Their applications range from language translation and sentiment analysis to complex time series forecasting.

<h3>Data Source and Preprocessing</h3>
The source of data for this stock market analysis was Yahoo Finance, accessed through the yfinance library. Specifically, the historical stock price data (closing prices) for Microsoft (MSFT) were retrieved for a period of 36 months. 
Data pre-processing is a significant stage of the modelling process, involving data collection, data normalization, splitting into Train and Test sets, Time series sequencing, and Reshaping. 

![image](https://github.com/DevAdedoyin/Stock-Market-Analysis/assets/59482569/993330e9-e900-4052-aec9-357a82220c42) ![image](https://github.com/DevAdedoyin/Stock-Market-Analysis/assets/59482569/e19877ed-c326-4c3b-baca-4a651e012c85)

<h3>Methodology</h3>
Microsoft stock data was retrieved from the Yahoo Finance website using the yfinance library.

The data for the Microsoft stock, identified by the ticker 'msft', covered a period of 36 months from 2020 to 2023.

The retrieved Microsoft dataset consisted of 755 rows and 7 columns, with the date serving as the index. The columns included 'open', 'high', 'low', 'close', and 'volume'.

The 'close' column, representing the closing price, was extracted from the dataset.

A line plot was created to visualize the closing price data and observe trends.

Data pre-processing was performed on the closing price using the MinMaxScaler from the sklearn library to normalize the data.

The dataset was divided into training and testing sets, implementing a 'look_back' period of 60.

Time series data were prepared for the LSTM model using the TimeseriesGenerator from the tensorflow.keras module.

An LSTM (Long Short-Term Memory) model was built with a configuration of neurons in the sequence 50, 100, 100, 100, and a final dense layer with 1 neuron.

The model was compiled with the 'Adam' optimizer and 'mean square error' loss function, and the summary of the model was displayed.

The model underwent training for 50 epochs, and predictions were made on the test data to prevent overfitting and underfitting.

Visualizations were created for the original data, along with the training and testing predictions, labeling the y-axis as 'closing price' and the x-axis as 'period'.

![image](https://github.com/DevAdedoyin/Stock-Market-Analysis/assets/59482569/adfc3843-1e3d-4fad-9501-ed927b08b9ed)

The chosen model for the time series forecasting is an LSTM (Long Short-Term Memory) neural network, implemented using the Keras library. Keras is a high-level neural networks API written in Python and capable of running on top of TensorFlow, CNTK, or Theano.
<b>Model Choice:</b> LSTM Neural Network
<b>Library:</b> Keras (utilizing TensorFlow as the backend)
<b>Model Type:</b> Sequential Model

![image](https://github.com/DevAdedoyin/Stock-Market-Analysis/assets/59482569/3b726462-ea81-494d-80c4-2ada19873883) 

![image](https://github.com/DevAdedoyin/Stock-Market-Analysis/assets/59482569/272d5090-7b83-447a-9c4f-a507446db33d)

<h3>Analysis and Prediction</h3>
![image](https://github.com/DevAdedoyin/Stock-Market-Analysis/assets/59482569/69b7a67e-368c-4746-90e8-7288b932d760)
The plot above shows a time series forecast for Microsoft's closing stock price, juxtaposing historical data with predicted future values. The graph illustrates a simulation of the stock price behaviour and extends the predictions to the next 100 days. 

<h4>Contextual Analysis</h4>
<b>Historical Trend:</b> The historical data up to the early part of 2023 reveals a stock characterized by volatility, evidenced by significant peaks and valleys. Such fluctuations are common in stock market activity and often reflect the influence of diverse factors, including market dynamics, economic conditions, and company-specific developments.

<h3>Analysis and Prediction</h3>
<b>Forecast Trend:</b> The forecasted data shows a sharp downturn following the last historical point. This suggests that the model has identified recent trends or patterns that imply a potential decline in stock value.

<h4>Real Issues Faced and Choices Made:</h4>

<b>Model Selection:</b> The choice to use an LSTM model, as typically represented in such plots, stems from its ability to capture temporal dependencies and patterns over time. LSTMs are particularly adept at handling the kind of sequential data presented in stock prices.

<b>Data Preprocessing:</b> Normalization or standardization of stock prices were carried out to help the model learn more effectively. This is particularly important when dealing with financial time series data that can have varying scales and ranges.

<b>Feature Selection:</b> The plot shows that the model was based on the closing price alone. 

<b>Overfitting Concerns:</b> In other to prevent overfitting, an LSTM (Long Short-Term Memory) model was built with a configuration of neurons in the sequence 50, 100, 100, 100, and a final dense layer with 1 neuron. The model was compiled with the 'Adam' optimizer and 'mean square error' loss function. The model underwent training for 50 epochs, and predictions were made on the test data to prevent overfitting and underfitting.

<b>Validation Strategy:</b> In other to validate the model’s prediction, a sample of 20 percent was used as test data from the overall population. This 20% test data was used to evaluate the 80% sample used as the train data.

In summary, while the plot provides a clear visual representation of the model's predictions against historical data, the real-world applicability of the forecast would depend on a range of factors including the robustness of the model, the quality of the data, and the ability to encapsulate influential external factors. The steep predicted decline may prompt further analysis to validate the model's assumptions and to potentially refine the approach based on additional data or insights.

