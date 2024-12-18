- df.append(): 사라질 메서드 시험에 안나옴
- df.loc[len(df)]: 시험에x
- `df.sort_index(axis=1, ascending=False)` # 인덱스 정렬에 axis 필요한 이유? false일때만 axis 통하는 이유
- 인덱스 순서 바꾸지 않고 컬럼 순서 바꾸는 방법
- ox 2, 괄호 2, 객관식 5, 맵 코드 문제, np 난수 종류, 데이터프레임 코드 문제, hist + random.choice 문제 예제 참고, age.csv 제주 연령별 plt.scatter 컬러 지정 등 사용해서 그림 그리기
- 1월 중 특강
- 

```
# 숫자 리스트
numbers = [1, 2, 3, 4, 5]

# map 함수와 람다 함수 사용
result = map(lambda x: x * 2, numbers)

# 결과를 리스트로 변환하여 출력
print(list(result))
```

```
import pandas as pd

# 시리즈 생성
data = [10, 20, 30, 40, 50]
index = ['a', 'b', 'c', 'd', 'e']
series = pd.Series(data, index=index)

print(series)
```

```
dice = np.random.choice(range(1, 7), 1000000, p = [0.15, 0.25, 0.3, 0.1, 0.1, 0.1])
plt.figure(figsize=(5, 3), dpi=200)

plt.hist(dice, rwidth=.98, bins=np.arange(.5, 7))
plt.xticks(range(1, 7))

plt.savefig('주사위.png')
plt.show()
```

```
f = open('gender.csv', encoding='cp949')
data = csv.reader(f)
header = next(data)

name = input('궁금한 지역의 이름을 입력하세요: ')
# 제주특별자치도

for row in data :
    if name in row[0] :
        male = 0
        female = 0
        for i in row[3:104] :
            i = i.replace(',', '')
            male = male + int(i)
        for i in row[106:] :
            i = i.replace(',', '')
            female = female + int(i)
        break

f.close()

plt.rc('font', family ='Malgun Gothic')
labels = ['male','female']
colors = ['skyblue', 'pink']

plt.pie([male, female], labels=labels, autopct ='%.1f%%', colors=colors, startangle =90)
plt.title(name + ' 지역의 남녀 성별 비율')
plt.axis('equal')
plt.show()
```


```
np.random.seed(2025)

N = 80
x = np.random.rand(N) # 80개의 랜덤한 수 0. ~ 1
y = np.random.rand(N)
colors = np.random.rand(N)
area = (20 * np.random.rand(N)) ** 2

plt.scatter(x, y, s=area, c=colors, alpha=0.7)
plt.colorbar()
plt.show()
```
