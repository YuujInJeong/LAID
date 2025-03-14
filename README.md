# Line Drawing Generator

간단한 이미지 기반 라인 드로잉 생성 도구입니다. 이 프로젝트는 사진을 라인 드로잉 스타일로 변환하는 몇 가지 방법을 제공합니다.

## 기능

- 사진에서 선화(라인 드로잉) 생성
- 일관된(Coherent) 라인 드로잉 스타일 구현
- 간단한 GUI 인터페이스

## 파일 설명

- `coherentLineDrawing.py`: 일관된 라인 드로잉 알고리즘 구현
- `makeLineDrawing.py`: 기본 라인 드로잉 변환 함수
- `guiMain.py`: 사용자 인터페이스 구현

## 사용 방법

### 설치 요구사항

```bash
pip install numpy opencv-python pillow
```

### GUI 실행

```bash
python LineDrawing/guiMain.py
```

### 코드에서 사용 예시

```python
from LineDrawing.makeLineDrawing import makeLineDrawing

# 이미지 경로를 입력하여 라인 드로잉 생성
line_drawing = makeLineDrawing("input_image.jpg")
line_drawing.save("output_image.jpg")

# 또는 일관된 라인 드로잉 사용
from LineDrawing.coherentLineDrawing import CoherentLineDrawing

cld = CoherentLineDrawing("input_image.jpg")
result = cld.generate()
result.save("coherent_output.jpg")
```

## 알고리즘 설명

이 프로젝트에서 구현된 라인 드로잉 알고리즘은 Edge Detection과 Flow-based Line Drawing 방법을 기반으로 합니다. 

1. 이미지에서 에지 검출
2. 에지 방향 및 강도 계산
3. 일관된 선 스타일 적용을 위한 텐서 필드 생성
4. 최종 라인 드로잉 렌더링

## 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다. 자세한 내용은 LICENSE 파일을 참조하세요.

## 기여

버그 신고, 기능 요청, 또는 코드 기여는 언제든지 환영합니다. 풀 리퀘스트를 통해 기여해 주세요.