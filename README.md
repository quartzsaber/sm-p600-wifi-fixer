## SM-P600 5Ghz 와이파이 오류 수정 모듈 *(Magisk)*

### 인트로
이 Magisk 모듈은 커스텀 롬을 설치한 SM-P600 (갤럭시 노트 10.1 2014)에서 5Ghz 와이파이가 보이지 않는 오류를 고칩니다.

이 모듈은 딱 한가지 경우에만 유용할 것입니다.
바로 다른 나라의 롬파일을 설치해서 `nvram_net.txt` 라는 파일이 외국 롬의 파일로 덮어씌워진 경우입니다.
나머지의 경우에는 별로 쓸모가 없을것 같습니다.

### SM-P600이면 와이파이 모델인데, LTE 모델이나 3G 모델에서도 작동할까요?
아마 작동할것 같기는 합니다만, 테스트해보지 않아 모릅니다. 테스트 하시고 알려주세요.

테스트 하실거면 부팅이 안되는걸 대비해 magisk를 삭제하는 zip파일을 내장메모리에 넣어둔 채로 진행하세요.

성공하시면 PR이나 이슈로 알려주시고요.

### 설치 방법

이 모듈은 Magisk를 사용합니다. Magisk가 뭔지 모른다면 검색해서 설치해주세요.

이런 일은 없을거라고 생각하지만, 이 모듈을 설치해서 기기가 부팅 불가하게 될수도 있습니다.
그런 경우를 대비해 가급정 내장 메모리에 Magisk를 삭제하는 zip파일을 넣어두세요.

1. [릴리즈 페이지](https://github.com/min050820/sm-p600-wifi-fixer/releases/latest)에서 최신 릴리즈를 다운로드 하세요. (sm-p600-wifi-fixer-module.zip 파일입니다)
2. Magisk 앱을 여세요.
3. 필요하면 Magisk를 업데이트 하세요. "Magisk"와 "App" (혹은 "Manager") 모두 업데이트 해야합니다.
4. 모듈 탭으로 가주세요. (아래에서 네번째 탭입니다)
5. "저장소에서 설치" 버튼을 눌러 다운로드한 zip 파일을 선택하세요. (파일이 보이지 않는다면 ...을 눌러 'SD카드 표시'를 눌러보세요)
6. 설치가 끝나면 기기를 재부팅하세요. (설치 실패라고 떠도 사실은 설치가 완료되었을 수 있습니다)
7. 처음 설치하면 진동 소리와 함께 부팅에 실패할 수 있는데, 전원 버튼을 꾹 눌러 강제 종료하고 다시 켜보세요. 계속 부팅이 안되면 Magisk를 삭제하시면 됩니다.
8. 5Ghz 와이파이가 잘 작동할겁니다! 안되면 혹시 모를 버그를 방지하기 위해 모듈을 삭제해주세요.

### 작동 원리
이 모듈은 `/system/etc/wifi/nvram_net.txt` 파일을 한국의 킷캣 롬(SM-P600_1_20170202123013_hqux0c5j5m) 에서 추출한 파일로 덮어씁니다.
캐나라 롤리팝 롬과 비교해본 결과 ccode(country code), regrev(의미 불명)을 비롯한 각종 설정이 상당히 달랐습니다.
대부분은 출력 전원 관련 설정인듯 한데, 해당 설정을 여기서 더 바꾸면 어떻게 되는지는 테스트하지 않았습니다.
(아마도 와이파이 출력이 향상시킬 수 있을것 같은데, 이대로도 잘 작동하는데다가 전파법 위반 소지도 있으니 건드리지 않는걸 추천드립니다)

참고로 ccode만 바꿔서는 와이파이가 제대로 작동하지 않았습니다.

### 라이선스
GPL 2.0

자세한 사항은 `LICENSE` 파일을 참고하세요.
