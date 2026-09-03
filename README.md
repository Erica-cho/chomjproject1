# 6주차 과제 Streamlit 배포

메타코드 부트캠프 6주차 주관식 과제(Q2 / Q3 / Q5)의 Streamlit 앱입니다.
저장소 **하나**로 앱 3개를 배포합니다 — 배포할 때 main file 경로만 다르게 지정하면 됩니다.

## 구성

```
.
├── app2.py    # Q2 · 태양흑점 종합 시각화        -> ChoMyungJin2
├── app3.py    # Q3 · 인터랙션(슬라이더) 추가      -> ChoMyungJin3
├── app5.py    # Q5 · Prophet 예측 + 잔차 분석    -> ChoMyungJin5
├── requirements.txt
└── data/
    ├── sunspots.csv               # app2, app3 가 사용
    └── sunspots_for_prophet.csv   # app5 가 사용
```

## 배포 순서

1. GitHub에 새 저장소를 만들고 이 폴더 전체를 push 합니다. (`data/` 폴더 포함 필수)
2. https://share.streamlit.io 에 GitHub 계정으로 로그인합니다.
3. **New app** → Repository / Branch 선택
4. **Main file path** 에 `app2.py` 입력
5. **Advanced settings** → Custom subdomain 에 `chomyungjin2` 입력 → **Deploy**
6. 4~5번을 `app3.py` / `chomyungjin3`, `app5.py` / `chomyungjin5` 로 두 번 더 반복

배포 후 주소:

- https://ChoMyungJin2.streamlit.app
- https://ChoMyungJin3.streamlit.app
- https://ChoMyungJin5.streamlit.app

## 참고

- `app5.py`는 Prophet을 설치·컴파일하므로 **첫 배포에 5~10분** 걸릴 수 있습니다.
  로그에 cmdstan 관련 메시지가 길게 나오는 것은 정상입니다.
- 빌드가 실패하면 `requirements.txt`의 버전을 고정해 보세요.
  예: `prophet==1.1.6`, `numpy<2`
- 로컬에서 먼저 확인하려면:

  ```bash
  pip install -r requirements.txt
  streamlit run app2.py
  ```
