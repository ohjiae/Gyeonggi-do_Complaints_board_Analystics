# ITWILL-Final_project <민원 게시판>


## 변수 목록

### 기본 세팅용 변수
- path : 현재 파일 경로
- minwon_date = 불러온 데이터 파일을 넣은 데이터 프레임


### 메인 변수
- title = 민원 제목 하나
- titles = 민원 제목 모음
- content = 민원 질문 하나
- contents = 민원 질문 모음
- reply = 민원 답변 하나
- replies = 민원 답변 모음

# 2021/08/05 project progress
[민원데이터] -- 중복 == 1 --> 형태소 분석(단어 출현 빈도수) --> 출현빈도수 n개 이상 추출 -->  향후 담당 부서 카테고리 뽑아내기 
            -- 중복 == 0 --> 카테고리 (이 경우에는 담당자가 직접 담당부서 이관) --> 민원text 형태소분석과 <부서>유사도 비교 --> 부서 할당 

# chap01 
- 단계1. 민원data_crawling ( by bs4)
- 단계2. text_preprocessing (okt)
- 2-1. tokenize
- 2-2. remove stop words(불용어처리)
- 2-3. vectorizing(x1 : titles(embedded), x2:content(embedding), 


# chap02
# 단계0
- 중복(1 or 0) --> 분류 모델링 : 앙상블모델 이용( SVM, Naive baise.. 활용)

# 단계1. 중복==1
- 형태소 분석 : 단어 출현 빈도수 
- 단어 출현 : n개 이상 선정

# 단계2. 이관부서 카테고리 분류 (수작업)
- n개 이상 출현단어 기준
- ex) <부서><단어> 
-  { '시청' : ['쓰레기', '부지 선정', ... ]} ; dict형

# 단계3. 민원 text <---> 부서 유사도 
- 민원text 형태소 분석 vs <부서> 유사도
- top2 <부서> 선정
- 유사도 0.3미만 : <부서> 없음 or '기타'
