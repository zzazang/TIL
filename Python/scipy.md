# 성적 데이터 분석 예제

## 사용한 라이브러리

* matplotlib
* scipy
* numpy
* pandas

## 주요 함수들

### pandas.read_excel()

엑셀 파일을 읽어 DataFrame 으로 만들어준다.
<http://pandas.pydata.org/pandas-docs/stable/generated/pandas.read_excel.html>

### DataFrame.plot()

<http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.plot.html>

파라미터 kind=bar 를 이용하면 막대그래프를 그려준다.
파라미터 kind=scatter 를 이용하면 산점도 혹은 산포도 그래프를 그린다.

### DataFrame.boxplot()

<http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.boxplot.html>

파라미터 return_type

return_type : {‘axes’, ‘dict’, ‘both’}, default ‘dict’

    The kind of object to return. ‘dict’ returns a dictionary whose values are the matplotlib Lines of the boxplot; ‘axes’ returns the matplotlib axes the boxplot is drawn on; ‘both’ returns a namedtuple with the axes and dict.

    When grouping with by, a dict mapping columns to return_type is returned.

### scipy.stats.ttest_ind()

<http://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.stats.ttest_ind.html>

Calculates the T-test for the means of TWO INDEPENDENT samples of scores.
두 집단의 점수의 실제 차이나는 정도를 계산

Notes

We can use this test, if we observe two independent samples from the same or different population, e.g. exam scores of boys and girls or of two ethnic groups. The test measures whether the average (expected) value differs significantly across samples. If we observe a large p-value, for example larger than 0.05 or 0.1, then we cannot reject the null hypothesis of identical average scores. If the p-value is smaller than the threshold, e.g. 1%, 5% or 10%, then we reject the null hypothesis of equal averages.

### scipy.stats.pearsonr

<http://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.stats.pearsonr.html>

Calculates a Pearson correlation coefficient and the p-value for testing non-correlation.
상관계수 와 p-value 계산.

## 패턴 분석

### 주성분 분석 (Principle component analysis)

PCA 분석은 scikit-learn이라는 라이브러리를 설치하고 수행할 수 있습니다.

http://scikit-learn.org/stable/

#### preprocessing
이 데이터를 정규화합니다. 전체 데이터를 최대, 최소를 기준으로 재 정리합니다. 정규화하는 함수는 scikit-learn 라이브러리에서 제공됩니다.

```
from sklearn.preprocessing import StandardScaler
X_std = StandardScaler().fit_transform(df[subjects])
X_std
```

#### PCA
위 행렬데이터가 PCA의 입력으로 사용됩니다. PCA 분석 함수는 scikit-learn 라이브러리에 있습니다.
```
from sklearn.decomposition import PCA
pca = PCA(n_components=2)
Y = pca.fit_transform(X_std)
Y
```

#### PCA 값으로 scatter plot 그림


## 가설 검정을 위한 scipy 라이브러리 모음

통계적 추론의 가설 검정을 위해 사용한 scipy 라이브러리를 정리한다.

scipy는 과학 기술 컴퓨팅을 다루는 과학자, 분석가, 엔지니어링이 사용하는 오픈소스 파이썬 라이브러리 이다. matplotlib, SymPy, Pandas와 같이 NumPy를 기반으로 사용된다.

### T 검정

scipy.stats.ttest_1samp
Calculates the T-test for the mean of ONE group of scores.

scipy.stats.ttest_ind
Calculates the T-test for the means of TWO INDEPENDENT samples of scores.
This is a two-sided test for the null hypothesis that 2 independent samples have identical average (expected) values. This test assumes that the populations have identical variances by default.

scipy.stats.ttest_rel
Calculates the T-test on TWO RELATED samples of scores, a and b.
This is a two-sided test for the null hypothesis that 2 related or repeated samples have identical average (expected) values.


### 정규성 검정

scipy.stats.kstest
Perform the Kolmogorov-Smirnov test for goodness of fit.
D(max distance)

scipy.stats.shapiro
Perform the Shapiro-Wilk test for normality.
The Shapiro-Wilk test tests the null hypothesis that the data was drawn from a normal distribution.


### 등분산 검정 (equal variances)

scipy.stats.levene
Perform Levene test for equal variances.
The Levene test tests the null hypothesis that all input samples are from populations with equal variances. Levene’s test is an alternative to Bartlett’s test bartlett in the case where there are significant deviations from normality.

scipy.stats.bartlett
Perform Bartlett’s test for equal variances
Bartlett’s test tests the null hypothesis that all input samples are from populations with equal variances. For samples from significantly non-normal populations, Levene’s test levene is more robust.


### 신뢰 구간 (confidence interval)

scipy.stats.bayes_mvs(<데이터>, alpha=<신뢰도>)
