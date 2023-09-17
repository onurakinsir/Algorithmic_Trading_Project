# Algorithmic trading
## Financial Data Analytics in Python
## Moving Average-based Trading Strategy
<br>

### Onur Akin **Sir**
#### m: onurakinsir@gmail.com
#### w: https://onurakinsir.com

### Overview
The model aims to implement a trading strategy using two simple moving averages (MA) though generating buy and sell signals in financial markets. The model is evaluated based on the Bitcoin Perpetual market, utilising minute-level data retrieved and trading executed through the Deribit Test API. First of all, I would like to kindly refer to the proposal of the model and strategy for better understanding. The proposal named "__MA-based_strategy_proposal__".
In addition, it is crucial to note that the model assumes that the trader is already in a long position. Therefore, before initiating the process, the position variable is set to ` position = True `, which indicates that the trader is in a long position. On the other hand, if the trader is in a short position, `position = False`. 

<br>

#### Strategy and Trading Logic
$$\textit{MA}(T) = \frac{1}{T}\sum_{t=1}^{T} P(t)
$$
The formula above indicates the moving average formula, here $t=1$ corresponds to the most recent time in the time series of historical stock prices $P(t)$ while $T$ is the length of the $MA$.

The idea of the model is defined as follows the trader should take a long position (buy and hold the financial instrument) where the short-term moving average $MA(S)$ is greater than the long-term moving average $MA(L)$.

### Installation
1. Clone the repository: `git clone https://github.com/onurakinsir/Algorithmic_Trading_Project.git`
2. Install the required dependencies: `requirements.yml` (Basically, Python 3.8 or higher.)

<br>

#### Usage
- Run the main script for the first part, which named `main.ipynb`
- If you would like to see the backtesting results for the strategy and the single moving average $MA(10)$ strategy, please run the backtesting script that named `backtesting.ipynb`
- Follow the instructions:
    - Please also follow the instructions/comments in the code
    - For instance, if would like to change the financial instrument from Bitcoin to Etherium – please use the `intrument_2` variable otherwise leave it as `instrument_1`.
    - There is no __need to__ change or reassign the length of MAs. This is because, the algorithm calculates various combinations of lengths to determine the effective lengths for our MAs. The algorithm then arranges the list of length combinations in descending order based on the edge strategy which represents the difference between strategy returns and log returns. Finally, it selects the optimal combination from the sorted list and proceeds with further analysis using those specific length combinations. Please see the proposal paper, p.2.
    - Buying and selling amount are fixed to 10 (10 amount of the financial instrument)  
    - The model will be executed for 22500 minutes (6 hours 15 minutes), feel free to change the duration by changing the `duration` variable.
    - When the live trading is finished, it will save the databse into your directory and will print `this code executed successfully`. Next, you will see two plots which will indicate the short-term and longer-term moving averages and close prices.

### Contact
For question or feedback, you can send me an [email](mailto:onurakinsir@gmail.com) or visit my [personal website](https://onurakinsir.com).
