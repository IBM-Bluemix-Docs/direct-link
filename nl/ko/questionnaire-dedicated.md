---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Dedicated, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, ticket, cross-connect, link speed, VPN, data, center, PoP, ECMP

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated 질문지
{: #ibm-cloud-direct-link-dedicated-questionnaire}

{{site.data.keyword.cloud}} Direct Link Dedicated에 대한 요청을 열어 주셔서 감사합니다.  요청을 완료하기 위해 귀하에게 몇 가지 추가 정보를 수집하려고 합니다. 질문지 프로세스 중에 언제든지 엔지니어에게 문의할 수 있습니다. 귀하가 질문지 작성을 완료하면 클라우드 디자인 엔지니어링 팀에서 이를 검토한 후 구현을 위해 특수 네트워크 서비스로 에스컬레이션합니다.

## 다음을 확인하고 이에 동의하십니까?
{: #dedicated-do-you-agree}

1. 각 Direct Link 연결에는 고유 주문이 필요합니다. 다중 연결이 필요한 경우 각 연결마다 별도의 Direct Link 주문을 여십시오.

2. Direct Link Connect 서비스 요금에는 IBM Cloud 인프라의 서비스 종료 비용이 포함됩니다. 

 * 인프라 서비스는 사전에 청구되며 주문 수락 시 시작됩니다. 그러나 IBM Cloud Direct Link의 속성으로 인해 IBM Cloud와의 BGP(Border Gateway Protocol) 세션 시작 시 또는 서비스 키가 클라이언트에 제공되고 나서 30일 후에 Direct Link 서비스 청구가 시작됩니다. 

 * 다음이 발생한 후 청구가 중지됩니다.
   * 고객이 회선을 삭제하도록 요청합니다. **그리고** 
   * Exchange 제공자 또는 네트워크 서비스 제공자가 회선을 디프로비저닝했습니다.
  * 자세한 정보는 클라우드 서비스 계약([https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html))의 **5절 - 대금**을 참조하십시오. 예를 들어, 미국 고객은 [이 클라우드 서비스 계약 문서](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en)를 참조할 수 있습니다.

3. Direct Link 서비스를 주문하면 사용자가 원격 네트워크에서 PoP(Point of Presence)에 도달하는 데 관련된 모든 비용을 부담하며 PoP 설비 내에 필요한 교차 연결을 담당합니다. 제공자가 물리적으로 PoP에 장착된 라우터 또는 기타 디바이스를 요구하는 경우 해당 장비의 코로케이션과 연관된 비용도 사용자가 부담하게 됩니다.

4. IBM Cloud는 고객을 대신하여 교차 연결을 주문하지 않습니다.

5. IBM Cloud는 당사 네트워크 PoP에서 고객 장비를 코로케이션하지 않습니다. 케이지 또는 제공자로부터 실행되는 파이버 이더넷(단일 모드 파이버 전용, 1Gig-LX 또는 10Gig-LR 1310nm 옵션)인 '교차 연결'만 허용합니다. T1, DS3, ISDN, POT 회선 등은 허용하지 않습니다. 사용자는 제공자와 함께 작업하여 IBM Cloud 네트워크 PoP가 존재하는 것과 동일한 설비에서 장비를 코로케이션해야 하는지 여부를 결정해야 합니다.

6. Direct Link 서비스는 링크 및 링크가 종료되는 IBM Cloud 라우터가 둘 다 단일 장애 지점(SPOF)인 방식으로 제공됩니다. Direct Link 서비스를 통해 중복성을 얻으려면 보조 라우터가 있는 Direct Link 연결 위치에 대한 두 개의 연결을 주문하거나 두 개의 별도 IBM Cloud PoP로 링크를 종료해야 합니다.

7. IBM Cloud 서비스 네트워크는 사용자의 원격 네트워크에서 직접 액세스할 수 없습니다. 향후 이 기능이 변경되면 알림이 제공됩니다.

8. IBM Cloud는 고객이 IBM Cloud 백본에서 자체 원격 사이트 간에 트래픽을 백홀(back-haul)하도록 허용하지 않습니다. Direct Link 제품을 사용하면 원격 네트워크에서 IBM Cloud 인프라와 개인적으로 통신할 수 있습니다.

9. 회선이 PoP에 연결되었으며 캐리어에 의해 완료되었음을 확인한 후 IBM Cloud 교차 연결 라우터(XCR)에 대한 교차 연결을 주문해야 하며, 일반적으로 이를 완료하는 데 2- 10 영업일이 걸립니다. 여기에는 SoftLayer 종료 포트까지의 패치가 포함됩니다. 완료되면 IBM Cloud에 설비 제공자의 교차 연결 완료 통지를 제공해야 합니다. IBM Cloud 네트워킹 인프라에서 IP 구현은 교차 연결이 완료된 후 3 영업일 이내에 완료됩니다.

10. IBM Cloud Direct Link Dedicated에서는 VRF(Virtual Routing and Forwarding) 인스턴스를 활용해야 합니다. 고객은 이 기능을 통해 원격 네트워크에서 사용할 자체 원격 IP 주소를 정의할 수 있습니다. 하지만 10.x.x.x 네트워크를 사용하는 경우 여전히 IBM Cloud 내의 호스트 및 IBM Cloud 서비스 네트워크(10.0.0.0/14, 10.198.0.0/15 및 10.200.0.0/14)와 겹치지 않아야 한다는 점에 유의하십시오. 사용자 계정을 VRF로 전환하려면 각각의 VLAN이 새 구성으로 마이그레이션될 때 사설 네트워크의 가동이 잠시 중단되어야 합니다. 특수 네트워크 서비스 팀에서 사용자와 함께 작업하여 이 활동에 대한 기간을 정의합니다. 특수 네트워크 서비스 팀은 월요일-금요일, 8-5시 CST(미국 중부 표준시)까지 사용 가능합니다. 이 기간을 벗어난 활성화 활동은 티켓을 통해 요청되어야 하며 가능한 경우 엔지니어가 사전에 승인해야 합니다.

11. VRF는 IBM Cloud(레거시 SoftLayer) SSL, PPTP 및 IPSEC VPN 서비스와 호환 가능하지 않습니다. 대안은 Direct Link 자체를 사용하여 서버를 관리하거나 여러 유형의 VPN으로 구성할 수 있는 사용자 고유의 VPN 솔루션(예: Vyatta)을 실행하는 것입니다. VRF로 마이그레이션한 후에 일반적으로 액세스되는 컴퓨팅과 동일한 DC 위치에 대한 VPN 연결이 설정될 때 SSL VPN이 작동하지만 글로벌하게 액세스를 허용하지 않습니다.

12. 고객의 원격 네트워크에 대한 라우트를 구현하려면 IBM Cloud Direct Link Dedicated에 BGP가 필요합니다. Direct Link 서비스가 배치되면 IBM Cloud에서 계정에 지정된 모든 사설 서브넷을 광고합니다.IBM Cloud는 고객의 원격 BGP 피어에 대한 광고에 사용자 정의 필터, AS 경로 추가 및 사용자 정의 로컬 환경 설정을 구현하지 않습니다.IBM Cloud는 IBM Cloud에 수신된 광고에 대한 필터를 구현하지 않습니다.고객이 고객의 에지 라우터에서 IBM Cloud를 오가는 광고를 적절히 관리해야 합니다.

## 기타 질문
{: #dedicated-other-questions}

* **Direct Link를 종료하려는 PoP는 무엇입니까?**

* **필요한 링크 속도(1, 2, 5 또는 10Gbps)는 무엇입니까?**

* **IBM Cloud에 대한 중복 연결을 설정하기 위해 ECMP로 BGP 다중 경로가 구성되어야 합니까?** 

    _구성되어야 하는 경우 다른 연결에 대한 티켓 ID를 포함시키십시오. 티켓 번호 ____________ (ECMP는 동일한 IBM Cloud XCR의 두 세션에만 프로비저닝될 수 있습니다.  ECMP를 원하는 경우 두 Direct Link가 모두 동일한 라우터에 도달해야 합니다.)_

* **로컬 또는 글로벌 라우팅 액세스가 필요합니까?**

    _로컬 라우팅을 선택하는 고객은 Direct Link가 주문된 PoP에서 서비스되는 데이터 센터 간에만 트래픽을 전달할 수 있습니다. Direct Link가 주문된 PoP 외부에 트래픽을 전달하려는 고객은 글로벌 라우팅 옵션을 추가해야 합니다._

* **_해당 위치_의 월별 요금과 아래 설명된 초과 요금을 포함한 글로벌 라우팅 요금에 동의하십니까?**

    _로컬 라우팅은 PoP에 직접 연결된 모든 데이터 센터에 대한 액세스를 포함하며 무제한 수신/발신 트래픽을 제공합니다. 글로벌 라우팅은 전 세계 모든 IBM Cloud 데이터 센터를 포함하도록 액세스를 확장합니다. 서비스가 트래픽을 측정할 수 있는 경우에 대역폭이 측정됩니다. 대역폭 측정이 발생하면 다음 표에 표시된 대로 마켓 가격을 기반으로 매월 비용이 청구됩니다._


### 글로벌 라우팅 가격
{: #dedicated-global-routing-pricing}

| 글로벌 라우팅 수신 | 글로벌 라우팅 발신 |
|---|---|
| 무료 | 1, 2 또는 5Gbps 회선 - 10TB 무료 대역폭 |
| 무료 | 10Gbps 회선 - 50TB 무료 대역폭 |


|대역폭 초과 요금 |
|---|
| 마켓 1: GB당 $0.05 |
| 마켓 2: GB당 $0.10 |
| 마켓 3: GB당 $0.15 |
