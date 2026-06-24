# 03. API 활용 예시 및 한계점

## 1. Python을 통한 Codex API 호출 예시
OpenAI 라이브러리를 활용해 Codex 모델에 프롬프트를 전달하고 코드를 생성하는 기본 파이썬 스크립트 구조입니다.

```python
import openai

# API 키 설정
openai.api_key = "YOUR_OPENAI_API_KEY"

# Codex 프롬프트 작성 (주석과 함수 시작부 제공)
prompt_text = """
# Java 구현 예시를 참고하여, 주어진 배열에서 최댓값을 구하는 Python 함수를 작성해줘.
def find_max(numbers):
"""

# API 호출 (code-davinci-002 모델 기준 예시)
response = openai.Completion.create(
    model="code-davinci-002",
    prompt=prompt_text,
    max_tokens=150,
    temperature=0,  # 0에 가까울수록 정답에 가까운 확정적인 코드를 생성
    stop=["\n\n"]    # 생성을 멈출 중단점 설정
)

print(response.choices[0].text)
