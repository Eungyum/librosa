# Librosa API 스터디

## 코어 IO 및 DSP(Digital Signal Processor, 디지털신호처리장치)

### 오디오 로딩 함수

1. librosa.load
   - 오디오 파일을 부동 소수점 시계열로 로드
   - <https://librosa.org/doc/latest/generated/librosa.load.html>
   ```python
   librosa.load(path, *, sr=22050, mono=True, offset=0.0, duration=None, dtype=<class 'numpy.float32'>, res_type='soxr_hq')
   ```

2. librosa.stream
   - 고정 길이 버퍼에서 오디오를 스트리밍
   - 한 번에 메모리에 완전히 들어가지 않는 대용량 파일을 처리하는 데 주로 유용
   - <https://librosa.org/doc/latest/generated/librosa.stream.html>
   ```python
   librosa.stream(path, *, block_length, frame_length, hop_length, mono=True, offset=0.0, duration=None, fill_value=None, dtype=<class 'numpy.float32'>)
   ```

3. librosa.to_mono
   - 채널 전체의 샘플을 평균화하여 오디오 신호를 모노(1 or 0?)로 변환
   - 매개변수 : y = np.ndarray [모양=(..., n)]
   - 리턴 : y_mono np.ndarray [모양=(n,)] / y단일 시계열로
   - <https://librosa.org/doc/latest/generated/librosa.to_mono.html#librosa.to_mono>
   ```python
   librosa.to_mono(y)
   ```

4. librosa.resample
   - orig_sr에서 target_sr까지 시계열 리샘플링
   - y의 시계열 길이가 변화함
   - <https://librosa.org/doc/latest/generated/librosa.resample.html>
   ```python
   y, sr = librosa.load(librosa.ex('trumpet'), sr=22050)
   y_8k = librosa.resample(y, orig_sr=sr, target_sr=8000)
   y.shape, y_8k.shape
   # ((117601,), (42668,))
   ```

