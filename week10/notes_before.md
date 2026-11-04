# week09 tools.py 함수 정리

`tools.py`는 영화진흥위원회(KOBIS) 오픈 API로 일별 박스오피스 정보를 가져오는 도구 모음이다.

## 공통 사항
- API 키는 `secret.py`의 `API_KEY`에서 불러온다.
- `BASE_URL`: 일별 박스오피스 조회 API 주소 (`searchDailyBoxOfficeList.json`)
- 두 함수 모두 `requests.get`으로 API를 호출하고(timeout 10초), 응답의 `boxOfficeResult.dailyBoxOfficeList`에서 영화 목록을 꺼낸다.

## 함수 목록

### 1. `get_boxoffice_rank_1(date)`
- **역할**: 지정한 날짜의 박스오피스 1위 영화 제목을 돌려준다.
- **입력**: `date` (문자열) — 8자리 날짜, 예: `"20260824"`
- **출력**: 1위 영화 제목 (문자열), 예: `"오디세이"`
- **동작**: 영화 목록의 첫 번째 항목(`movies[0]`)의 `movieNm`을 반환한다.

### 2. `get_movie_audience(date, title)`
- **역할**: 지정한 날짜 박스오피스에서 특정 영화의 관객 수를 돌려준다.
- **입력**:
  - `date` (문자열) — 8자리 날짜
  - `title` (문자열) — 영화 제목
- **출력**: 관객 수 문자열, 예: `"123,456명"`
- **동작**: 영화 목록을 돌며 제목이 일치하는 영화의 `audiCnt`(당일 관객 수)를 천 단위 쉼표 형식으로 반환한다. 순위에 없으면 `"'제목'은 날짜 순위에 없습니다."`라는 안내 문자열을 반환한다.

## 참고 (개선 여지)
- 두 함수에 API 호출 코드가 중복되어 있다.
- 네트워크 오류나 빈 목록(`movies`가 비어 있음)에 대한 예외 처리가 없다.
- `get_boxoffice_rank_1`의 docstring에 매개변수 이름이 `data`로 오타가 있다(실제는 `date`).
