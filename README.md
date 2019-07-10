## 위드캣 챗봇을 위한 교과서 PDF 파싱 파이썬 스크립트 입니다.

PDF파일을 일일이 복붙하여 문서화 시키는 작업이 번거러워서, 이를 보다 쉽게 할 수 있지 않을까 해서 짠 파이썬 스크립트입니다.

**주의** <br>
이 스크립트는 공개되어 있으며 배포 및 수정이 자유로우나, (주)위드캣 소프트웨어에서 사용하기 위함입니다.

이 스크립트로 파싱한 결과물은 완벽하지 않습니다. 대부분의 텍스트를 긁어와서 태그까지 붙여주도록 하지만, PDF의 텍스트를 긁어오는거다 보니 서순이 맞지 않고, 어색하게 배치가 될 수 있습니다. 이를 정리하기 위해서는 수작업이 필요합니다.

#### 설치법
파이썬 기본적으로 설치 후, 루트 디렉토리에서 아래 명령어로 필요한 패키지를 설치해 줍니다.

`pip install -r requirements.txt`

혹은 필요로 하는 패키지를 수동으로 설치해 주셔도 됩니다.

#### 사용법
`python PdfParser.py -o {outputPath} -j {jsonPath} -p {pdfPath}`

{outputPath} : 추출된 텍스트가 쓰여질 경로입니다.<br>
{jsonPath} : 교과목 인덱스가 담길 json파일 경로입니다.<br> 
{pdfPath} : 추출 대상 pdf 교과 파일입니다.

Json 파일 형식은 수동으로 작성하셔야 하며, 아래와 같은 형식으로 작성하시면 됩니다.<br>
Key값은 텍스트파일에서 사용될 목차명, Value값은 페이지를 적어주시면 되는데, 연속된 페이지는 '-'로 처리하셔도 무방합니다. <br>
**참고로, json파일에 적혀있지 않은 페이지는 추출하지 않습니다.**
```json
{
    "1_1_1": "12-17",
    "1_1_2": "18-19,21,23-24"
}
```

참고용 JSON 파일 : <https://github.com/NaLDo627/PDFParser/blob/master/Source/WorldHistoryIndex.json>
