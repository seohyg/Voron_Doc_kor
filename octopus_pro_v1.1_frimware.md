
# BigTreeTech Octopus-Pro

## Octopus-Pro-V1.1
***V1.1은 STM32H723 버전의 DFU 모드에서 Hotend 포트가 계속 활성화되는 문제를 해결하기 위한 것입니다***
### V1.0과 V1.1의 차이점
* 핀 배치 변경
  제목 | Octopus Pro V1.0/V1.0.1 | Octopus Pro V1.1
  -- | -- | --
  HE0 | PA2  | PA0
  HE2 | PB10  | PB0
  Motor4-EN | PA0  | PA2
  RGB | PB0  | PB10

* CAN 버스 인터페이스 하위 모델
  Octopus Pro V1.0/V1.0.1 | Octopus Pro V1.1
  -- | --
  RJ11  | XH2.54*2핀

## Octopus Pro에 대한 경고
* 8개의 드라이버 전압은 점퍼로 선택할 수 있습니다. 점퍼가 왼쪽에 삽입된 경우 해당 드라이버 전압은 `MOTOR_POWER`이고, 오른쪽에 삽입된 경우 `Main Power`입니다. `MOTOR_POWER` 포트의 최대 지원 전압은 60V이고, `Main Power` 포트의 최대 지원 전압은 28V입니다. 이 메인보드의 8개의 드라이버는 `MOTOR_POWER` 또는 `Main Power`의 조합으로 사용할 수 있습니다.<br/>
***주의: 점퍼로 올바른 전압이 선택되었는지 확인한 후, 고전압 버전이 아닌 드라이버(예: TMC2209, TMC2130 또는 비고전압 버전 TMC5160)를 사용해야 합니다. 그렇지 않으면 드라이버가 손상되거나 메인보드가 손상될 수 있습니다.***<br/>
  <img src=Images/stepper_60V.png width="600" /><br/>
  <img src=Images/stepper_24V.png width="600" /><br/>
  <img src=Images/board.jpg width="800" /><br/>

## Octopus-Pro와 Octopus V1.0 / V1.1의 차이점
  1. 최대 60V 고전압 스테퍼 드라이버를 지원하며, 각 드라이버는 점퍼를 통해 `MOTOR_POWER` 또는 `Main Power` 전압을 선택할 수 있습니다.
  2. `NPN` 및 `PNP` 타입 근접 스위치를 `Probe` 포트에서 모두 지원합니다(V1.0 / V1.1은 `PNP` 타입만 지원). ***이 포트의 IO는 더 이상 Bltouch와 다중화되지 않으며, 이 포트에 별도의 IO `PC5`가 사용됩니다.***
  3. 온보드 `INA826`이 `Max31865`로 수정되어 PT100 / PT1000을 지원하며, 더 높은 정확도를 제공합니다.
  4. Raspberry Pi 헤더의 핀 배치가 Raspberry Pi와 정확히 동일하게 수정되었습니다. 상단에서 하단으로: `5V 5V GND RX TX`.

## 펌웨어
  * Octopus-Pro V1.0과 Octopus (non-pro) V1.0 / V1.1의 IO는 동일하지만, 근접 스위치 `Probe` 포트의 IO는 더 이상 Bltouch와 다중화되지 않고 별도의 IO `PC5`로 수정되었습니다. [Octopus V1.0/V1.1을 여기에서 참고하세요](https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0).
  * Octopus-Pro V1.1의 IO는 위의 표에 나와 있듯이 V1.0과 차이가 있습니다.

## 리뷰
  * 전자 제품의 모든 기능을 자세히 설명한 리뷰를 [스페인어](https://3dwork.io/btt-octopus-pro)와 [영어](https://3dwork.io/en/btt-octopus-pro)로 [3dwork.io](https://3dwork.io/)에서 확인할 수 있습니다.
