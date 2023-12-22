# Librosa API 스터디

## 코어 IO 및 DSP(Digital Signal Processor, 디지털신호처리장치)

### 오디오 로딩 함수

1. librosa.load : 오디오 파일을 부동 소수점 시계열로 로드
```python
librosa.load( path , * , sr=22050 , mono=True , 오프셋=0.0 , 기간=None , dtype=<class 'numpy.float32'> , res_type='soxr_hq' )
```

2. librosa.stream
   - 고정 길이 버퍼에서 오디오를 스트리밍
   - 한 번에 메모리에 완전히 들어가지 않는 대용량 파일을 처리하는 데 주로 유용
   - <https://librosa.org/doc/latest/generated/librosa.stream.html>
