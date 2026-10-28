#### 실습 - 승인할 것인가

1. 수락 / 내가 요청한 일이고 작업 폴더 안의 일이다
2. 거절 / 내가 요청하지 않은 일
3. 거절 / 내가 요청하지 않은 일이고 되돌릴 수 없음
4. 거절 / 내가 요청하지 않은 일이고 다른 파일에 접근함
5. 수락 / 내가 요청한 일, 작업 폴더 안의 일, 되돌릴 수 있음
6. 거절 / 되돌릴 수 없음, 정리 요청만으로 주요 코드 파일인 main.py를 영구 삭제하는 것은 위험함
---

### 맡기기 4단계 - 도구 호출 순서를 유인물에 적기
- 순서 1
도구이름: Bash 대상: 폴더(./)
- 순서 2
도구이름: Bash 대상: check.py, average_pandas.py, average_plain.py, scores.csv
- 도구를 쓴 횟수 2회, 읽은 파일 수 4/4
--- 

### 맡기기 5단계 -- 답이 맞는지 직접 열어 확인하기
- scores.csv - O
- average_plain.py. - O
- average_pandas.py - O
- Check.py - O
---

| 비교 항목       | 원본 (주석 있음)         | 사본 (주석 없음)      |
|---------------|-----------------------|--------------------|
| 받는 값의 형식 | -get_boxoffice_rank(date): `date`(8자리 날짜 문자열)<br> -get_movie_audience(date, title): `date`(8자리 날짜 문자열), `title`(찾을 영화 제목 문자열)  | -get_boxoffice_rank(date): `date`(조회할 날짜 YYYYMMDD 문자열)<br>-get_movie_audience(date, title): `date`(조회할 날짜), `title`(찾을 영화 제목)|
| 예시 값 | `date`: "20250824" | `date`: "20250824" |
| 돌려주는 것 | -get_boxoffice_rank(date): 그날 박스오피스 1위 영화의 제목(문자열), 예: "오디세이"<br>-get_movie_audience(date, title): 순위에 그 영화가 있으면 그날의 관객 수(audiCnt)를 쉽표와 "명"을 붙여 돌려줌, 순위에 없으면 "'오디세이'은 20260824 순위에 없습니다" 같은 안내 문장을 돌려줌| -get_boxoffice_rank(date): 그날 박스오피스 1위 영화의 제목(movieNum) 문자열(예:"오디세이")<br>-get_movie_audience(date, title): 그날 순위에 영화가 있으면 그날 관객수(audiCnt)를 쉼표와 "명"을 붙여 돌려주고 없으면 안내 문장을 돌려줌(예: "'오디세이'은 20260824 순위에 없습니다')|
| 틀리거나 애매한 부분 | X | X(AI 발전으로 인해 간단한 함수는 알아서 해석 하게 된 것을 확인하였다.) |
