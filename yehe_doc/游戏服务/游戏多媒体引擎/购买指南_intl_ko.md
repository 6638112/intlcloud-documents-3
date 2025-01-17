﻿Gaming Multimedia Engine(GME)은 현재 다음 가격으로 실시간 음성 채팅, 음성 메시지, 음성-텍스트 변환 등의 서비스를 제공합니다.


## 실시간 음성 채팅 서비스
실시간 음성 채팅은 월별 PCU 피크값 또는 음성 시간에 따라 과금되는 종량제 서비스입니다.

### 가격 리스트

<table>
   <tr>
      <th>과금 모드</th>
      <th>음질</th>
      <th>월 PCU 피크값</th>
      <th>단가(USD/5000PCU)</th>
   </tr>
   <tr>
      <td  rowspan="5">음성 PCU 과금</td>
      <td  rowspan="5">일반 음질</td>
      <td><5000</td>
      <td>3000 </td>
   </tr>
   <tr>
      <td>5000≤PCU<50000</td>
      <td>1870 </td>
   </tr>
   <tr>
      <td>50000≤PCU<100000</td>
      <td>1560</td>
   </tr>
   <tr>
      <td>100000≤PCU<300000</td>
      <td>1250</td>
   </tr>
   <tr>
      <td>≥300000</td>
      <td>영업팀 문의</td>
   </tr>
</table>
 

>!
>- 일간 PCU는 당일 최대 동시 접속자 수를 말하며, 월간 피크 PCU는 매월 1일에서 그 달의 마지막 날 중 일간 PCU의 최고값을 의미합니다(2일의 PCU가 8400이고, 당월 다른 날의 PCU가 모두 8400보다 낮은 경우, 이번 달 PCU 피크값은 8400입니다).
>- PCU 기준으로 과금되며, 5000PCU 단위로 과금됩니다. 5000PCU 미만인 경우에도 5000PCU로 계산됩니다(월간 PCU 피크값이 8400이면, 이번 달 요금은 3000+1870달러입니다).

<table>
   <tr>
      <th>과금 모드</th>
      <th>음질</th>
      <th>월간 통화 시간</th>
      <th>단가(USD/분)</th>
   </tr>
   <tr>
      <td  rowspan="5">음성 이용 시간 과금</td>
      <td  rowspan="5">HD 음질</td>
      <td><10000 분</td>
      <td>무료 </td>
   </tr>
   <tr>
      <td>≥10000 분</td>
      <td>0.00094 </td>
   </tr>

</table>

>!음성 지속 시간은 사용자가 방에 들어오고 나가는 시간을 기준으로 계산됩니다. 사용자 A가 12시에 음성방에 입장하고, 사용자 B가 12시 30분에 방에 입장하고, 둘 다 12시 40분에 퇴장하면 음성 사용 시간은 총 50분(A 사용자 40분, B 사용자 10분)이 됩니다.

## 음성 메시지 서비스
음성 메시지 서비스는 음성 메시지 DAU를 기준으로 과금됩니다.

### 가격 리스트

<table>
   <tr>
      <th>과금 모드</th>
      <th>단가 (USD/DAU/일)</th>
   </tr>
   <tr>
      <td>음성 메시지 DAU로 과금</td>
      <td>0.0019 </td>
   </tr>
   </tr>
</table>


>? 애플리케이션 내 사용자가 음성 메시지를 발송/수신할 경우 음성 메시지 DAU로 간주합니다. 음성 메시지 DAU는 openID를 기반으로 중복 제거 후 통계합니다(openID는 애플리케이션 내 사용자의 유일한 식별자로 사용자 1명 당 openID가 1개 적용됩니다).



## 음성-텍스트 변환 서비스

음성-텍스트 변환 서비스는 일 결산 또는 월 결산을 지원하며 기본은 일 결산입니다. 월 결산으로 전환하려면 티켓을 제출하여 신청하십시오.

### 가격 리스트
<table>
   <tr>
      <th>과금 모드</th>
      <th>단가 (USD/15초)</th>
   </tr>
   <tr>
      <td  rowspan="1">음성-텍스트 변환 관련 API를 요청한 오디오 또는 오디오 스트림 과금 대상 시간</td>
      <td> 0.006(15초 단위이며, 15초 미만의 요청은 15초로 계산) </td>
   </tr>
   </tr>
</table>




## 텍스트 번역 서비스
텍스트 번역 서비스는 번역 글자 수에 따라 과금됩니다.

### 가격 리스트
<table>
   <tr>
      <th>과금 모드</th>
      <th>단가 (USD/100만 자)</th>
   </tr>
   <tr>
      <td  rowspan="1">글자 수에 따라 과금</td>
      <td> 20 </td>
   </tr>
   </tr>
</table>


>?이 기능은 아직 출시되지 않았습니다. 티켓을 제출하여 신청할 수 있습니다.


## 텍스트-음성 변환 서비스


>?이 기능은 아직 정식 출시되지 않았으니 사용이 필요한 경우, 영업팀에게 연락하거나 티켓을 제출하여 가격을 문의하십시오.


## 서비스 중지/해제 정책
계정 연체 후 24시간 경과 시 GME 서비스가 중지됩니다. 서비스 중지 후 168시간(7일) 경과 시 해당 계정의 GME 리소스가 폐기 및 회수됩니다. 서비스 연속성을 위해 계정 잔액이 항상 충분한지 확인하십시오.

## 연체 알람
GME 일 결산 후불 제품의 클라우드 리소스 서비스는 만료일 이후에 Tencent Cloud 계정 생성자와 모든 협력자에게 이메일, SMS 및 내부 메시지를 통해 연체 알림 메시지를 발송합니다.
