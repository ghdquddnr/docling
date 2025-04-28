<p align="center">
  <a href="https://github.com/docling-project/docling">
    <img loading="lazy" alt="Docling" src="https://github.com/docling-project/docling/raw/main/docs/assets/docling_processing.png" width="100%"/>
  </a>
</p>

# Docling

<p align="center">
  <a href="https://trendshift.io/repositories/12132" target="_blank"><img src="https://trendshift.io/api/badge/repositories/12132" alt="DS4SD%2Fdocling | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</p>

[![arXiv](https://img.shields.io/badge/arXiv-2408.09869-b31b1b.svg)](https://arxiv.org/abs/2408.09869)
[![Docs](https://img.shields.io/badge/docs-live-brightgreen)](https://docling-project.github.io/docling/)
[![PyPI version](https://img.shields.io/pypi/v/docling)](https://pypi.org/project/docling/)
[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/docling)](https://pypi.org/project/docling/)
[![Poetry](https://img.shields.io/endpoint?url=https://python-poetry.org/badge/v0.json)](https://python-poetry.org/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Imports: isort](https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336)](https://pycqa.github.io/isort/)
[![Pydantic v2](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/pydantic/pydantic/main/docs/badge/v2.json)](https://pydantic.dev)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![License MIT](https://img.shields.io/github/license/docling-project/docling)](https://opensource.org/licenses/MIT)
[![PyPI Downloads](https://static.pepy.tech/badge/docling/month)](https://pepy.tech/projects/docling)
[![Docling Actor](https://apify.com/actor-badge?actor=vancura/docling?fpr=docling)](https://apify.com/vancura/docling)
[![OpenSSF Best Practices](https://www.bestpractices.dev/projects/10101/badge)](https://www.bestpractices.dev/projects/10101)
[![LF AI & Data](https://img.shields.io/badge/LF%20AI%20%26%20Data-003778?logo=linuxfoundation&logoColor=fff&color=0094ff&labelColor=003778)](https://lfaidata.foundation/projects/)

Docling은 다양한 형식의 문서 처리와 파싱을 단순화하며, 고급 PDF 이해 기능을 포함하여 생성형 AI 생태계와의 원활한 통합을 제공합니다.

## 주요 기능

* 🗂️ PDF, DOCX, XLSX, HTML, 이미지 등 [다양한 문서 형식][supported_formats] 파싱
* 📑 페이지 레이아웃, 읽기 순서, 테이블 구조, 코드, 수식, 이미지 분류 등을 포함한 고급 PDF 이해
* 🧬 통합된 표현력 있는 [DoclingDocument][docling_document] 표현 형식
* ↪️ Markdown, HTML, 무손실 JSON을 포함한 다양한 [내보내기 형식][supported_formats] 및 옵션
* 🔒 민감한 데이터와 에어갭 환경을 위한 로컬 실행 기능
* 🤖 LangChain, LlamaIndex, Crew AI & Haystack을 포함한 플러그 앤 플레이 [통합][integrations] 기능
* 🔍 스캔된 PDF와 이미지를 위한 광범위한 OCR 지원
* 🥚 시각적 언어 모델 지원 ([SmolDocling](https://huggingface.co/ds4sd/SmolDocling-256M-preview)) 🆕
* 💻 간단하고 편리한 CLI

### 곧 출시 예정

* 📝 제목, 저자, 참조 및 언어를 포함한 메타데이터 추출
* 📝 차트 이해 (막대 그래프, 파이 차트, 선 그래프 등)
* 📝 복잡한 화학 구조 이해 (분자 구조)

## 설치

Docling을 사용하려면 패키지 관리자(예: pip)를 통해 `docling`을 설치하세요:
```bash
pip install docling
```

macOS, Linux 및 Windows 환경에서 작동합니다. x86_64 및 arm64 아키텍처 모두 지원합니다.

더 자세한 [설치 지침](https://docling-project.github.io/docling/installation/)은 문서에서 확인할 수 있습니다.

## 시작하기

Python으로 개별 문서를 변환하려면 `convert()`를 사용하세요. 예시:

```python
from docling.document_converter import DocumentConverter

source = "https://arxiv.org/pdf/2408.09869"  # 로컬 경로 또는 URL의 문서
converter = DocumentConverter()
result = converter.convert(source)
print(result.document.export_to_markdown())  # 출력: "## Docling Technical Report[...]"
```

더 [고급 사용 옵션](https://docling-project.github.io/docling/usage/)은 문서에서 확인할 수 있습니다.

## CLI

Docling은 변환을 실행하기 위한 내장 CLI를 제공합니다.

```bash
docling https://arxiv.org/pdf/2206.01062
```

🥚[SmolDocling](https://huggingface.co/ds4sd/SmolDocling-256M-preview) 및 기타 VLM을 Docling CLI를 통해 사용할 수도 있습니다:
```bash
docling --pipeline vlm --vlm-model smoldocling https://arxiv.org/pdf/2206.01062
```
이것은 지원되는 Apple Silicon 하드웨어에서 MLX 가속을 사용합니다.

자세한 내용은 [여기](https://docling-project.github.io/docling/usage/)에서 확인하세요.

## 문서

Docling의 [문서](https://docling-project.github.io/docling/)에서 설치, 사용법, 개념, 레시피, 확장 기능 등에 대한 자세한 내용을 확인하세요.

## 예제

Docling을 사용하여 다양한 애플리케이션 사용 사례를 해결하는 방법을 보여주는 [예제](https://docling-project.github.io/docling/examples/)를 직접 경험해보세요.

## 통합

AI 애플리케이션 개발을 더욱 가속화하려면 Docling의 인기 있는 프레임워크 및 도구와의 네이티브 [통합](https://docling-project.github.io/docling/integrations/)을 확인하세요.

## 도움말 및 지원

[토론 섹션](https://github.com/docling-project/docling/discussions)을 통해 언제든지 저희와 연락하세요.

## 기술 보고서

Docling의 내부 작동 방식에 대한 자세한 내용은 [Docling 기술 보고서](https://arxiv.org/abs/2408.09869)를 확인하세요.

## 기여하기

자세한 내용은 [Docling에 기여하기](https://github.com/docling-project/docling/blob/main/CONTRIBUTING.md)를 읽어주세요.

## 참고 문헌

프로젝트에서 Docling을 사용하는 경우 다음을 인용해 주세요:

```bib
@techreport{Docling,
  author = {Deep Search Team},
  month = {8},
  title = {Docling Technical Report},
  url = {https://arxiv.org/abs/2408.09869},
  eprint = {2408.09869},
  doi = {10.48550/arXiv.2408.09869},
  version = {1.0.0},
  year = {2024}
}
```

## 라이선스

Docling 코드베이스는 MIT 라이선스 하에 있습니다.
개별 모델 사용에 대해서는 원본 패키지에서 찾을 수 있는 모델 라이선스를 참조하세요.

## LF AI & Data

Docling은 [LF AI & Data Foundation](https://lfaidata.foundation/projects/)의 프로젝트로 호스팅됩니다.

### IBM ❤️ 오픈 소스 AI

이 프로젝트는 IBM Research Zurich의 AI for knowledge 팀에서 시작되었습니다.

[supported_formats]: https://docling-project.github.io/docling/usage/supported_formats/
[docling_document]: https://docling-project.github.io/docling/concepts/docling_document/
[integrations]: https://docling-project.github.io/docling/integrations/