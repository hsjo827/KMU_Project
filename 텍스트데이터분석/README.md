본 프로젝트는 **'2024-1 텍스트데이터분석 수업'** 과제로 제출한 프로젝트입니다.

<br/>

## 👬 팀원
- 조현식, 이준혁

## 🕓 기간
- 24.04.27 ~ 24.06.02

## 📑 주제
- 뉴스 제목으로 확인하는 한국 언론 지형 파악_정치인과 주요 이슈를 중심으로

<br/> 

### 프로젝트 소개
- 언론사별 정치적 워딩 및 시각이 어떻게 다른지 파악
- 많이 접하지만 정치적 입장을 모르는 언론사 파악

  1. WordCloud
     - 보수, 진보 성향 언론사가 특정 정치인과 주요 이슈에 대해 어떤 단어를 주로 사용하는지 확인
  2. MLP
     - 네이버 뉴스에서 많이 접하는 언론사이지만, 정치적 입장이 어떠한지 알 수 없었던 언론사들 이진분류 (진보, 보수)
    
<br/>

### 언론사 선정 배경
1. 보수 언론
   - 대형 보수 언론인 **조선일보, 중앙일보, 동아일보**를 선정
2. 진보 언론
   - 대표적인 진보 언론인 **한겨례, 경향신문, 오마이뉴스**를 선정
3. 기타 언론
   - 한국인이 가장 많이 보는 언론사 top5 기준으로 선정했으며 뉴시스, 뉴시스1은 부적절한 제목이 많아 **매일경제, 머니투데이, 연합뉴스**로 선정
  
<br/>

### 키워드
![블루 화이트 심플한 회사 소개 프레젠테이션 (1)](https://github.com/hsjo827/Projects/assets/133327403/483128aa-53fd-4e85-8b2b-fe3f1fc33fcb)


### 데이터 수집

**[네이버 뉴스 API]**
<br/>
1. 네이버 검색 창에 특정 정치인 또는 이슈 관련해서 검색했을 때 나오는 뉴스 검색 결과 얻기 (ex.후쿠시마 오염수,윤석열,이재용 등)
 
2. 본 프로젝트에서는 특정 언론사의 기사만 필요 (앞에서 선정한 9개의 언론사)

3. 그러나 네이버 API에서 언론사를 필터링하는 파라미터 제공 X

4. 고민 끝에 검색하고자 하는 키워드 앞에 언론사 명을 붙이기로 결정 (ex.한겨레 후쿠시마 오염수, 중앙일보 후쿠시마 오염수)

5. 키워드 당 기사 1000개씩 수집 - 관련도 순 (title,original link,link,description,pubDate)

![image](https://github.com/hsjo827/Projects/assets/133327403/6f844e01-21fd-4b16-a8a4-948aa9000f32)


<br/>

**ex) '조선일보 해병대' 수집 결과**
![image](https://github.com/hsjo827/Projects/assets/133327403/51d55f56-6b13-40cc-bdef-c567b21ec0e7)


**ex) '오마이뉴스 해병대' 수집 결과**
![image](https://github.com/hsjo827/Projects/assets/133327403/19350e7c-1ae9-4a0c-9f84-ca7ba91d1e5e)

<br/>

**[네이버 뉴스 링크 수집]**
- 네이버 뉴스 API로 수집한 기사 링크(link) 중 네이버 뉴스 기사(n.news.naver.com)에 대해서만 링크(link) 얻기

![image](https://github.com/hsjo827/Projects/assets/133327403/32a7cdce-3d7d-4ede-bf27-1fe884bfa813)

<br/>

**[특정 언론사의 기사만 수집]**
<br/>
1. 단순히 검색 키워드 앞에 언론사명을 넣어줬기 때문에 언론사 필터링이 잘 되어있지 않음 (ex.'오마이뉴스 후쿠시마' 검색 결과에 오마이뉴스 외 언론사 기사가 존재)

2. 특정 언론사 네이버 뉴스 base link를 통해 특정 언론사 기사만 필터링 (ex.'오마이뉴스 후쿠미사' 검색 결과에 오마이뉴스 기사만 가져오기)

![image](https://github.com/hsjo827/Projects/assets/133327403/c235d40d-532a-41fc-9f6e-6c5b8a1fdf3c)

<br/>

**[특정 언론사의 가사만 수집한 결과]**

- ex) 오마이뉴스

![image](https://github.com/hsjo827/Projects/assets/133327403/37d9bfb9-f0b2-4182-8c7b-b42a5a8cd8cc)

- ex) 중앙일보

![image](https://github.com/hsjo827/Projects/assets/133327403/0688fcd1-8bf8-4866-8e8c-1f83aa55ac6b)


<br/>

**[selenium을 통해 기사 제목 및 링크 수집]**

- 각 언론사별 네이버 뉴스 링크를 하나씩 접속하여 기사 제목 및 링크 수집

![image](https://github.com/hsjo827/Projects/assets/133327403/c8bcdd27-f225-49fb-90ca-40c7514f06c9)


<br/>

**[scrapping 결과를 csv 파일로 저장]**

- Source : 언론사명
- Link : 기사 링크
- Title : 기사 제목

![image](https://github.com/hsjo827/Projects/assets/133327403/f90c3655-9548-43dd-9446-35e152288ba4)

<br/>









   





