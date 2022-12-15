# Reliance-Stock-Analysis
<!-- Copy and paste the converted output. -->

<!-----

You have some errors, warnings, or alerts. If you are using reckless mode, turn it off to see inline alerts.
* ERRORs: 0
* WARNINGs: 1
* ALERTS: 24

Conversion time: 4.906 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β34
* Thu Dec 15 2022 09:08:13 GMT-0800 (PST)
* Source doc: Data Science Report
* Tables are currently converted to HTML tables.

WARNING:
You have some equations: look for ">>>>>  gd2md-html alert:  equation..." in output.

* This document has images: check for >>>>>  gd2md-html alert:  inline image link in generated source and store images to your server. NOTE: Images in exported zip file from Google Docs may not appear in  the same order as they do in your doc. Please check the images!

----->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 1; ALERTS: 24.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>
<a href="#gdcalert7">alert7</a>
<a href="#gdcalert8">alert8</a>
<a href="#gdcalert9">alert9</a>
<a href="#gdcalert10">alert10</a>
<a href="#gdcalert11">alert11</a>
<a href="#gdcalert12">alert12</a>
<a href="#gdcalert13">alert13</a>
<a href="#gdcalert14">alert14</a>
<a href="#gdcalert15">alert15</a>
<a href="#gdcalert16">alert16</a>
<a href="#gdcalert17">alert17</a>
<a href="#gdcalert18">alert18</a>
<a href="#gdcalert19">alert19</a>
<a href="#gdcalert20">alert20</a>
<a href="#gdcalert21">alert21</a>
<a href="#gdcalert22">alert22</a>
<a href="#gdcalert23">alert23</a>
<a href="#gdcalert24">alert24</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>


**Stock Market Analysis on Reliance Dataset**

Suhan Bangera, Siddanth Tonne, Sudeep CK 

**_Abstract- _This document gives detailed information about the analysis done on the Reliance stock market data spanning over the last twenty years. All the while developing an appropriate model to forecast the forthcoming market trend. Here we initially perform the Exploratory Data Analysis (EDA) on daily Volume and the Closing Prices of Reliance Stocks. The Descriptive Analysis (DA) is followed by testing a hypothesis for the stationarity of the Closing Price. We then develop a series of models for stock forecasting, which are later evaluated to identify the most suitable one. **

**_Keywords:  _EDA, Hypothesis Testing, p-value. **



1. INTRODUCTION

Over the span of the last century, the Stock Markets have been one of the paramount financial platforms for investors to invest their money in the hopes of gaining lucrative returns after a certain period. 

According to the recent survey conducted by Bajaj Finserv Ltd, investments in stock markets proved to have high returns on investments though being subjected to higher risks among all its investment alternatives. 

As early as the stock market investments were under the limelight, the scientific community has strived hard to find mathematical and statistical solutions to identify and exploit the patterns in the nature of fluctuating stock prices to form investment strategies that are devoid of human emotions and provides lucrative returns. The term “Algorithmic Trading” was coined to name this field of science and finance. 

The attempts in algorithmic trading burst into popularity during the early 1970s, with varying degrees of success. In recent times, technological advancements in computer science and statistics have enabled us to develop feasible and reliable investment strategies by exploiting the computational powers of modern computers and the predictive and prescriptive capabilities of Machine Learning algorithms.  

The objective of this study is to analyze how the stock prices of Reliance have changed over time and derive inferences based on our findings. We later test some hypotheses and develop models to forecast the future trend of stock prices. We perform evaluations on set models to find the most feasible one. 



2. DATASET AND PREPROCESSING

	We form our dataset by collecting Reliance stock data from Google Finance. Our dataset contains stock market details for the last two decades,  from July 1, 2002, to December 8, 2022. 


<table>
  <tr>
   <td><strong>Date</strong>
   </td>
   <td><strong>Open</strong>
   </td>
   <td><strong>High</strong>
   </td>
   <td><strong>Low</strong>
   </td>
   <td><strong>Close</strong>
   </td>
   <td><strong>Volume</strong>
   </td>
  </tr>
  <tr>
   <td>1/4/2016 15:30:00
   </td>
   <td>497.78
   </td>
   <td>502.14
   </td>
   <td>488.72
   </td>
   <td>492.98
   </td>
   <td>6896571
   </td>
  </tr>
  <tr>
   <td>1/5/2016 15:30:00
   </td>
   <td>485.45
   </td>
   <td>500.26
   </td>
   <td>493.82
   </td>
   <td>497.86
   </td>
   <td>3416459
   </td>
  </tr>
  <tr>
   <td>1/6/2016 15:30:00
   </td>
   <td>499.07
   </td>
   <td>514.32
   </td>
   <td>495.50
   </td>
   <td>511.25
   </td>
   <td>6116855
   </td>
  </tr>
  <tr>
   <td>1/7/2016 15:30:00
   </td>
   <td>505.73
   </td>
   <td>509.17
   </td>
   <td>499.29
   </td>
   <td>501.87
   </td>
   <td>4512219
   </td>
  </tr>
</table>


**Fig 1. A Dataset sample**

**	**Since we deal with stock prices over a period of time, the High and Low columns serve very little purpose here. So we drop those columns. Furthermore, we bring the date column to a proper format (‘%m/%d/%y’) and make it our index. 

	We then add a new column indicating the returns on each day by computing the same using the following formula, 



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



	In our dataset, the Open column represents the Closing value of the previous day, so reduce the unnecessary redundancy we drop it.  So after the initial pre-processing, our dataset takes the following form. 


<table>
  <tr>
   <td>
   </td>
   <td><strong>Close</strong>
   </td>
   <td><strong>Volume</strong>
   </td>
   <td><strong>returns</strong>
   </td>
  </tr>
  <tr>
   <td><strong>1/4/2016</strong>
   </td>
   <td>492.98
   </td>
   <td>6896571
   </td>
   <td>-0.009642814
   </td>
  </tr>
  <tr>
   <td><strong>1/5/2016 </strong>
   </td>
   <td>497.86
   </td>
   <td>3416459
   </td>
   <td>0.004864265
   </td>
  </tr>
  <tr>
   <td><strong>1/6/2016 </strong>
   </td>
   <td>511.25
   </td>
   <td>6116855
   </td>
   <td>0.024405394
   </td>
  </tr>
  <tr>
   <td><strong>1/7/2016 </strong>
   </td>
   <td>501.87
   </td>
   <td>4512219
   </td>
   <td>-0.007632531
   </td>
  </tr>
</table>


**Fig 2. The Dataset after preprocessing.**



3. Exploratory Data Analysis (EDA):

In statistics, exploratory data analysis (EDA) is **an approach to analyzing data sets to summarize their main characteristics, often using statistical graphics and other data visualization methods**.



1. Summary of the dataset

    The summary indicates that all the columns in our dataset are numerical and, hence can be used for numerical analysis. 


    

<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")



    **Fig 3. Summary of dataset**

2. EDA on Volume attribute

    

<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")


<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")



    

<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")



    **Fig 4. The plots f Volume against time. **


    We can infer from the above plots that 2020 had an unusual spike in the volume of stocks for Reliance. When we compare the medians of the volume exchanged against each month of the year, we realize that in May and August there are the least exchanges done whereas it's maximum in January.


    

<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.png "image_tooltip")


<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.png "image_tooltip")



    **Fig 5. The plots indicate outliers. **


    The above plots describe the nature of outliers in the volume of the stock exchanges. As we notice the majority of the data points are converged in one value, and the rest are outliers. 

3. EDA on Closing Price attribute. 

    

<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.png "image_tooltip")


<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.png "image_tooltip")



    

<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image9.png "image_tooltip")



    **Fig 6. The plots of Closing Price against time. **


    We can infer from the above plots after 2016 Reliance saw a large spike in its Stock Prices. On further investigations, we found that the introduction of Jio was a major contributing factor to this phenomenon. 


    

<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image10.png "image_tooltip")


<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image11.png "image_tooltip")



    **Fig 7. The plots indicate outliers. **


    The above plots describe the nature of outliers in the closing prices of the stock exchanges. As we notice there are no noticeable outliers here. 

4. EDA on returns attribute. 

    

<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image12.png "image_tooltip")



    **Fig 8. The plot of returns against time. **


    We can infer from the above plot we can infer that the daily returns have always been under a certain range without much noticeable deviation in terms of real-world objectives 


    

<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image13.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image13.png "image_tooltip")


<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image14.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image14.png "image_tooltip")



    **Fig 9. The plots indicate outliers. **


    The above plots describe the nature of outliers in the closing prices of the stock exchanges. As we notice there are no noticeable outliers here. 


IV. HYPOTHESIS TESTING

Hypothesis testing is **an act in statistics whereby an analyst tests an assumption regarding a population parameter**. The methodology employed by the analyst depends on the nature of the data used and the reason for the analysis. Hypothesis testing is used to assess the plausibility of a hypothesis by using sample data.

In statistics, the **Dickey–Fuller test** tests the null hypothesis that a unit root is present in an autoregressive time series model. The alternative hypothesis is different depending on which version of the test is used but is usually stationarity or trend-stationarity. The test is named after the statisticians David Dickey and Wayne Fuller, who developed it in 1979.



<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image15.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image15.png "image_tooltip")


**Fig 10. Hypothesis test results on Closing Price without Differentiating.**

Since the above result shows that the p-value is too hence the null hypothesis passes. To tackle this we differentiate the closing price and perform the test again. 



<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image16.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image16.png "image_tooltip")


**Fig 11. Hypothesis test results on Closing Price with Differentiating.**

Here we see that the test passes and we get the differentiating factor as 1. 

V. Modelling:


## **<span style="text-decoration:underline;">ARIMA model</span>**

ARIMA is the abbreviation for AutoRegressive Integrated Moving Average. Auto Regressive (AR) terms refer to the lags of the differenced series, Moving Average (MA) terms refer to the lags of errors and I is the number of difference used to make the time series stationary.


### **Assumptions of ARIMA model**



* 1. Data should be stationary – by stationary it means that the properties of the series doesn’t depend on the time when it is captured. A white noise series and series with cyclic behavior can also be considered as stationary series.
* 2. Data should be univariate – ARIMA works on a single variable. Auto-regression is all about regression with the past values.


#### **ARIMA model :**


    ARIMA stands for AutoRegressive Integrated Moving Average and is specified by three order parameters: _(p, d, q)._



* **AR(_p_) Autoregression:** A regression model that utilizes the dependent relationship between a current observation and observations over a previous period.An auto regressive (_AR(p)_) component refers to the use of past values in the regression equation for the time series.
* ** I(_d_) Integration:** Uses differencing of observations (subtracting an observation from observation at the previous time step) in order to make the time series stationary. Differencing involves the subtraction of the current values of a series with its previous values d number of times.
* **MA(_q_) Moving Average:** A model that uses the dependency between an observation and a residual error from a moving average model applied to lagged observations. A moving average component depicts the error of the model as a combination of previous error terms. The order _q_ represents the number of terms to be included in the model.



<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image17.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image17.png "image_tooltip")


<p id="gdcalert19" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image18.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert20">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image18.png "image_tooltip")


<p id="gdcalert20" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image19.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert21">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image19.png "image_tooltip")


Results of Arima Model:



<p id="gdcalert21" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image20.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert22">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image20.png "image_tooltip")


**<span style="text-decoration:underline;">GRNN Model:</span>**

**Generalized regression neural network (GRNN)** is a variation to radial basis neural networks.

GRNN can be used for regression, prediction, and classification.GRNN represents an improved technique in the neural networks based on the nonparametric regression.


## Advantages and disadvantages

Similar to RBFNN, GRNN has the following advantages:



* Single-pass learning so no backpropagation is required.
* High accuracy in the estimation since it uses Gaussian functions.
* It can handle noises in the inputs.
* It requires only less number of datasets.

The main disadvantages of GRNN are:



* Its size can be huge, which would make it computationally expensive.
* There is no optimal method to improve it.



<p id="gdcalert22" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image21.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert23">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image21.png "image_tooltip")




<p id="gdcalert23" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image22.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert24">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image22.png "image_tooltip")


VI. Conclusion:

After implementing two models for the dataset, we found that the Grnn model is better for forecasting the data given due to the less error seen in the results.



<p id="gdcalert24" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert25">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


