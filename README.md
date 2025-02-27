# 국민동의청원 분류하기

본 프로젝트는 AI 핵심 기술 집중 클래스(160 시간) 에 대한 미니 프로젝트입니다.

국민 청원 사이트 대신 국민동의청원 사이트를 통해서 크롤링 및 Text-CNN 모델링을 진행할 예정입니다.

## Getting Started

로컬 환경으로만 구성되어 있으며,

.py를 통해 파이썬 코드 실행 또는 notebook 폴더에서 .ipynb 파일을 실행할 수 있습니다.

### Installing

크롤링과 데이터셋 구성을 위해 다음 모듈 설치 필요함.

```
pip install requests pandas
```

## Running the tests

```
# Create list csv file.
python 01-crawling-petitions-assembly-list.py

# Output filename : extracted-crawling-petitions-assembly-list.csv


# Create code csv file.
python 02-extract-code-data.py 

# Output filename : extracted-code-data.csv


# Create dataset for project
python 03-create-petitions-assembly-dataset.py

# Output filename : petitions-assembly-dataset.csv

# Clean the dataset
python 04-clean-petitions-assembly-dataset.py

# Output filename : petitions-assembly-dataset-clean.csv

```

## Data layout

크롤링 추출 데이터에서 프로젝트에 필요한 타겟 데이터 구성

|항목명|원본 영문명|타켓 영문명|타입|데이터 포멧|비고|
|------|---|---|--|--|--|
|글번호|rowNum|rowno|Number|||
|카테고리|petitRealmNm|category|Text|||
|청원제목|petitSj|title|Text|||
|청원내용|petitCn|content|Text|||
|참여인원|agreCo|count|Number|||
|청원 시작일|agreBeginDe|start|Timestamp|%Y-%m-%d||
|청원 마감일|agreEndDe|end|Timestamp|%Y-%m-%d||

```
# dataset for project
convert_dataset = ['rowNum','category', 'title', 'content', 'count', 'start', 'end']
```

## Etc

### Jupyter Notebook 변환 라이브러리

Python 파일(.py)을 Jupyter Notebook 파일(.ipynb)로 변환합니다.

기존 코드 내에서 주석을 기준으로 코드 실행 영역이 만들어 집니다.
```
# install
pip install p2j

# covnert command
p2j {python file}
```
- 장점 : 간편하게 Notebook 파일을 생성
- 단점 : 보기 좋게 하기 위해서는 Markdown 등 추가 작업이 필요함.
