# 파이썬 3.10 경량화 이미지 사용
FROM python:3.10-slim

# 작업 디렉토리 설정
WORKDIR /app

# 시스템 시간대 및 파이썬 출력 버퍼링 비활성화 설정
ENV PYTHONUNBUFFERED=1

# 의존성 파일 복사 및 설치
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# 전체 애플리케이션 코드 복사
COPY . .

# Cloud Run에서 주입하는 PORT 환경 변수를 받아 Uvicorn 실행 (기본값 8080)
ENV PORT=8080
CMD ["sh", "-c", "uvicorn main:app --host 0.0.0.0 --port ${PORT}"]
