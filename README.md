# milab-tf-gnn-research

GCN·GAT·GraphSAGE로 **Cora / CiteSeer / PubMed / PPI / Reddit** 등 대표 그래프 데이터셋의 노드 분류·표현학습을 재현한 실습 리포지터리입니다.  
TensorFlow 기반 구현과 **전처리, 샘플링, 학습, 평가 스크립트**, GPU/CPU 환경을 지원하는 **Dockerfile(GraphSAGE)**, 예제 데이터셋을 포함합니다.  

본 프로젝트는 **그래프 임베딩·어텐션·샘플링 기법의 차이를 실험적으로 검증**하며, MLOps 관점에서 재현 가능한 학습 파이프라인을 제공합니다.

## Project Structure
```bash
milab-tf-gnn-research/
├── GCN/ # GCN 모델 구현
├── GAT/ # GAT 모델 구현
├── GraphSAGE/ # GraphSAGE 모델 구현 (GPU/CPU Dockerfile 포함)
├── data/ # Cora, CiteSeer, PubMed 등 예제 데이터셋
├── utils/ # 전처리, 샘플링, 평가 모듈
├── requirements.txt # Python 의존성
└── README.md
```

## 실행 방법

### 1. 환경 세팅
```bash
git clone https://github.com/sungmin-woo-devops/milab-tf-gnn-research.git
cd milab-tf-gnn-research
pip install -r requirements.txt
```

### 2. 데이터 준비
데이터셋은 data/ 디렉토리에 포함되어 있으며, 필요시 utils/ 모듈을 통해 전처리 가능합니다.

### 3. 모델 학습
```bash
# GCN
python GCN/train.py

# GAT
python GAT/train.py

# GraphSAGE
python GraphSAGE/train.py
```

### 4. Docker (GraphSAGE 예시)
```bash
# CPU
docker build -f GraphSAGE/Dockerfile.cpu -t graphsage-cpu .

# GPU
docker build -f GraphSAGE/Dockerfile.gpu -t graphsage-gpu .
```

## 주요 기능
- GCN, GAT, GraphSAGE 모델별 학습 및 평가
- 전처리/샘플링/평가 파이프라인 제공
- Cora / SiteSeer / PubMed / PPI / Reddit 데이터셋 지원
- GPU/CPU Docker 환경 지원 → 실험 재현성 강화
- 노드 임베딩 성능 비교 및 시각화

## 사용 기술
Python, TensorFlow, Numpy, scikit-learn, Networkx, Jupyter Notebook, Docker

## 참고 문헌
- Kipf & Welling, Semi-Supervised Classification with Graph Convolutional Networks, ICLR 2017
- Velickovic et al., Graph Attention Networks, ICLR 2018
- Hamilton et al., Inductive Representation Learning on Large Graphs, NeurIPS 2017

## Author
- 연구/실습: MILAB 2024 1st Semester
- 작성자: 우성민
