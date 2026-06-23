## 1. Codex란 무엇인가?
OpenAI에서 개발한 모델로, 자연어를 코드로 변환하는 데 특화된 AI 모델입니다. GPT-3의 후속 주자이자 GitHub Copilot의 기반이 되었습니다.

### 주요 특징
* **다국어 지원:** Python, JavaScript, Java 등 다양한 언어 이해
* **컨텍스트 이해:** 단순 문장을 넘어 주석과 기존 코드를 분석

## 2. 간단한 코드 예제 (Python)
Codex API를 사용할 때 코드 블록을 활용하면 가독성이 높아집니다.

```python
import openai

# Codex API 호출 예시 (가상 코드)
response = openai.Completion.create(
    model="code-davinci-002",
    prompt="# Python function to reverse a string\ndef reverse_string(s):",
    max_tokens=100
)
print(response.choices[0].text)
