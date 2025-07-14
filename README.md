# 농업 챗봇: 가뭄 대응 작물 관리 AI

이 프로젝트는 가뭄 상황에서 농작물 관리법을 안내하는 **LangChain 기반 AI 챗봇**입니다.  
Streamlit 인터페이스를 통해 사용자는 자연어로 질문하고, 챗봇은 문서를 기반으로 실시간 답변을 제공합니다.

---

## 💡 주요 기능

- 📘 PDF 문서 기반 질의응답 (가뭄 대응 농작물 관리 매뉴얼 등)
- 🧠 LangChain + GPT 기반 LLM 응답 생성
- 🔍 벡터 DB(Chroma) 기반 문서 검색
- 💬 Streamlit 챗 UI + 채팅 기록 관리
- 🧪 few-shot 예시 기반 응답 향상

---

## 📁 프로젝트 구조

\`\`\`
farm_project<br>
├── app.py                 # Streamlit 앱 진입점 (챗봇 UI)<br>
├── main.py                # 체인 생성, 벡터스토어 로드, 응답 생성 함수<br>
├── example.py             # few-shot QA 예제 정의<br>
├── create_db.ipynb        # 기본 벡터스토어 생성용 노트북<br>
├── create_parent_db.ipynb # ParentDocument 기반 벡터스토어 생성 노트북<br>
├── test.txt               # 벡터화할 문서 텍스트 (ex. 가뭄 대응 가이드)<br>
├── farm/                  # Chroma 벡터 DB 저장 경로<br>
├── parent_docstore/       # Parent 문서 docstore 저장소<br>
├── 가뭄 대비 농작물 관리 요령.pdf  # 문서 원본<br>
└── README.md              # 이 문서<br>
\`\`\`

---

## 🚀 실행 방법

1. **환경 변수 설정**

\`.env\` 파일 생성 후 OpenAI API 키 작성:

\`\`\`
OPENAI_API_KEY=sk-xxxxxxxxxx
\`\`\`

2. **패키지 설치**

\`\`\`bash
pip install -r requirements.txt
\`\`\`

3. **벡터 DB 생성 (선택)**

\`\`\`bash
# Chroma + ParentDocument 기반 벡터 저장소 생성
jupyter notebook create_db.ipynb
\`\`\`

4. **앱 실행**

\`\`\`bash
streamlit run app.py
\`\`\`

---

## 🧪 예시 질문

- \`벼는 언제 모내기해야 하나요?\`
- \`당근 가뭄 피해 어떻게 줄일 수 있나요?\`
- \`노지감귤에 가장 효과적인 물 관리법은?\`

---

## 📌 기술 스택

- Python 3.10+
- LangChain
- OpenAI GPT-4.0
- ChromaDB
- Streamlit
- dotenv

---

## 📝 참고 문서

- 📄 [가뭄 대비 농작물 관리 요령.pdf](./가뭄%20대비%20농작물%20관리%20요령.pdf)  
- 📄 \`test.txt\` (위 문서에서 벡터화된 요약 데이터)

---

## 🙌 기여자

- \`윤동일\`  
- \`jin0choi1216\` (레포 생성자)

---

## 📜 라이선스

MIT License

