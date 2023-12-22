# Librosa API 스터디

## 코어 IO 및 DSP(Digital Signal Processor, 디지털신호처리장치)

### 오디오 로딩 함수
1. librosa.load : 오디오 파일을 부동 소수점 시계열로 로드
```python
librosa.load( 경로 , * , sr=22050 , mono=True , 오프셋=0.0 , 기간=None , dtype=<class 'numpy.float32'> , res_type='soxr_hq' )
```
