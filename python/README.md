### 환경변수 셋팅

1. `python-dotenv` 패키지 설치
2. `.env` 파일 셋팅
    - 띄어쓰기 없이 입력해야함

    ```ex
    API_KEY=asd
    ACCESS_KEY=qwe
    ```

3. `python-dotenv` 패키지의 `load_dotenv()` 함수를 사용하여 환경변수 로드 및 사용

    ```ex
    import os
    from dotenv import load_dotenv

    load_dotenv()

    API_KEY = os.environ.get('API_KEY')
    ```