---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: VRF, IP, routers, backbone, service, VLAN, multiple isolation, tenant, tenancy, datacenters, data, center, shared tenancy, private endpoint, Customer VRF, Private Network Question, support, ticket

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud의 VRF(Virtual Routing and Forwarding) 개요
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

정의상 VRF(Virtual Routing and Forwarding)는 인터넷 프로토콜(IP) 네트워크 라우터에 포함된 기술입니다. 내재적 백본 서비스로 제공됩니다.

## IBM Cloud에 대한 연결 옵션
{: #connectivity-options-for-ibm-cloud}

**분산된 클라우드 리소스**는 두 곳 이상의 위치에 또는 두 개 이상의 서브넷 또는 VLAN에 있는 리소스입니다. 이러한 리소스는 리소스 사이에서 또는 사설 네트워크 컨텍스트 내에서 통신하기 위해 라우팅 기능이 필요합니다. 이 문서에서는 보통 _고객 VRF_라고 부르는 "다중 격리" 테넌시 통신 옵션에 대해 설명하고 있습니다. 글로벌 {{site.data.keyword.cloud}} 백본에서 MPLS Layer-3 VPN(RFC 4364)으로 구현됩니다.

일반적으로 IBM Cloud 플랫폼은 사설 네트워크에서 라우팅을 위한 두 가지 옵션을 제공하며 팟(Pod)과 데이터 센터 간의 연결을 제공합니다.

1. **공유 테넌시:** 일반 논리 네트워크로, 이 모델을 사용하는 모든 테넌트에서 공유하며, 자동화된 액세스 제어 목록(ACL)에 의해 분리되고, VLAN Spanning이 사용 가능합니다. (이 문서에서는 이 옵션에 대해 설명하지 않습니다.)

2. **다중 격리:** 테넌트당 전용 논리 네트워크이며 다른 테넌트의 논리 네트워크와 상호 작용이 허용되지 않습니다.  

이 문서에서는 _다중 격리_ 네트워크 연결을 설명하기 위해 **고객 VRF**라는 용어를 사용합니다.

## VRF 개요(다중 격리 기술)
{: #vrf-overview}

VRF(Virtual Routing and Forwarding)를 통해 라우팅 테이블의 여러 인스턴스가 라우터에 존재할 수 있으며 동시에 작동할 수 있습니다. VRF(Virtual Routing and Forwarding)를 사용하면 각 클라우드 테넌트의 VRF 네트워크가 해당 라우팅 테이블 내에서 세그먼트화됩니다. 이 세그먼트화는 IP 주소 겹침을 고려하여 다른 테넌트 VRF와의 상호 작용이나 간섭은 생성하지 않습니다. IBM Cloud는 대다수의 `10.0.0.0/8` 네트워크를 이용하며 여러 원격 네트워크(예: 고객 데이터 센터에 배치된 네트워크)와 겹칠 수 있습니다.

IBM Cloud 테넌트는 VRF(Virtual Routing and Forwarding)를 사용하여 보통 글로벌 테이블에서 겹침이 허용되지 않는 원격 IP 주소를 사용할 수 있습니다. IBM은 이 VRF 서비스에서 라우팅할 수 없는 다음의 RFC 1918, 링크 로컬 주소 및 멀티캐스트 주소를 계속 보유합니다.

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16`(개인용 엔드포인트 서비스에서 사용함)
* IBM 플랫폼에서 VLAN과 연관된 IP 범위

IBM은 가용성 구역에서 가상 프라이빗 클라우드(VPC)를 사용할 수 있도록 차세대 Cloud 배치를 추진 중입니다. 이 새로운 VPC 기능을 통해 댈러스, 워싱톤 DC, 런던, 프랑크푸르트, 도쿄 및 시드니에 위치하는 VPC 사용 AZ에서 BYoIP(Bring Your own IP)를 사용할 수 있습니다.

VRF(Virtual Routing and Forwarding)를 활용하는 백본의 각 테넌트는 Direct Link당 하나(및 단 하나)의 _고객 VRF_를 포함할 수 있으며 위치에 상관없이 모든 테넌트 서버 간의 연결을 제공합니다. 그러나 IBM Cloud 테넌트는 단일 교차 연결 라우터로 피드되는 두 개 이상의 Direct Link 계정을 포함할 수 있습니다.  

* VLAN, 팟(Pod) 및 전 세계 데이터 센터에 있는 테넌트의 서버는 해당 테넌트의 전 세계 다른 모든 서버에 접속할 수 있습니다.

* 모든 테넌트의 고객 VRF는 DNS, 공유 스토리지, 모니터링, 패칭 등을 사용하는 데 이러한 서버에 대한 프라이빗 도달 가능성을 제공하기 위해 일반 공유 서비스 네트워크에 연결됩니다.

* 고객 VRF는 테넌트 간의 격리를 제공하는 연결 서비스입니다. 게이트웨이, 보안 그룹 또는 호스트 기반 제어를 사용하여 테넌시 내에서 필요한 추가적인 제어를 별도로 제공해야 합니다.

## VRF 이전의 이점
{: #benefits-of-moving-to-vrf}

**기본적인 이점에는 다음이 포함됩니다.**

* 업계에서 검증된 광범위하게 허용되는 _다중 격리_ 구분 기술. 많은 클라우드 고객들은 레벨 3 VPN 접근 방식이 해당 감사자 및 특별 감사 책임자에 더 적합하다는 것을 알게 되었습니다.   

* IBM 네트워크를 통해 새 사이트 또는 애플리케이션을 추가한 덕분에 IBM Cloud 고객들은 네트워크의 범위를 크게 확장하거나 마이그레이션할 수 있습니다.

* 테넌트 특정 라우팅 테이블은 다른 테넌트의 서브넷 또는 적용할 수 없는 네트워크의 다른 일부와 겹칠 위험 없이 IP 주소 겹침에 대한 간극을 좁힐 수 있습니다.

**이전 ACL 모델과 비교했을 때 몇 가지 사소한 트레이드 오프:**  

* 고객 VRF로 변환하려면 유지보수 기간이 필요하며 이 때 백본 트래픽 플로우는 잠시 중단됩니다.

* 관리 VPN 서비스(SSL, IPSec)를 사용하는 원격 액세스는 로컬 데이터 센터로 제한되지만, 공유 ACL 백본을 통해 모든 시작점에서 글로벌 액세스가 가능합니다.

* _다중 격리_ 테넌시 내의 VLAN Spanning은 사용할 수 없습니다.

## 계정 변환 프로세스 동안 진행되는 작업
{: #what-happens-during-the-account-conversion-process}

현재 많은 IBM Cloud 고객들은 IBM Cloud 네트워크의 공유 테넌시 모델에서 운영 중입니다. 변환하는 동안 테넌시는 가장 일반적으로 새 Direct Link 구독을 사용하여, 또는 필요하거나 요청한 대로, 고객 VRF를 사용하도록 변환됩니다.  

VLAN 및 해당 서브넷이 ACL 백본에서 분리된 후 고객 VRF에 연결되는 동안 변환 프로세스에는 네트워크 중단이 발생합니다. 이 프로세스의 결과로 VLAN에 들어가거나 나오는 트래픽의 일부 패킷이 유실됩니다. VLAN 내의 패킷은 계속 흐릅니다. FortiGate 보안 어플라이언스 또는 가상 라우터 어플라이언스와 같은 네트워크 게이트웨이가 포함되는 경우, 해당 게이트웨이에 VLAN이 연결되는 동안 중단은 발생하지 않습니다. 서버에 네트워크 가동 중단이 발생하지 않으며 트래픽 플로우가 재개되면 대부분의 워크로드는 자동으로 복구됩니다. 총 중단 기간은 테넌트의 토폴로지 범위 즉, 테넌시에 포함된 서브넷, VLAN 및 팟(Pod)의 수에 따라 달라집니다.

![변환 프로세스](/images/vrf-on-ibm-cloud.png)

마이그레이션하는 동안 백본에서 고객 VLAN의 연결이 끊어지고 고객의 VRF로 다시 연결됩니다.  중단 기간은 관련된 VLAN, 팟(Pod) 및 데이터 센터의 수량에 따라 달라집니다. VLAN 간의 트래픽이 중단되지만 서버는 네트워크에 연결된 상태를 유지합니다. 애플리케이션은 패킷 손실에 대한 민감도에 따라 영향을 받거나 받지 않을 수도 있습니다.

## 변환을 시작할 수 있는 방법
{: #how-you-can-initiate-the-conversion}

IBM Cloud 고객은 [IBM Cloud 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")]( https://cloud.ibm.com/unifiedsupport/cases/add) 계정을 통해 VRF로 마이그레이션을 요청하는 [지원 티켓을 열 수 있습니다](https://cloud.ibm.com/unifiedsupport/cases/add). 티켓에 “사설 네트워크 질문”이라고 명시해야 하며 지원 티켓에는 다음 텍스트가 포함되어야 합니다.

"_사용자 계정 번호 입력_ 계정을 고유 VRF로 이동하도록 요청합니다.가능한 위험성을 인지하고 있으며 변경을 승인합니다. 마이그레이션을 준비할 수 있도록 이 변경이 진행될 예정 시간에 대해 다시 알려주시기 바랍니다."

IBM Cloud 네트워크 엔지니어링 팀에서 마이그레이션을 완료합니다. 합의된 스케줄 외에 고객 측의 다른 정보는 필요하지 않습니다. 일반적으로 계정의 복잡도에 따라 패킷 손실은 15-30분 정도 지속될 수 있습니다. (계정에 레거시 Direct Link 연결을 사용하는 경우 더 오래 걸릴 수 있음). 이 프로세스는 대부분 자동화되어 있으므로 IBM 팀에 의한 최소한의 상호작용이 포함되며 투명하게 제공되어야 합니다.

티켓을 열 때 이전에 제공된 텍스트를 포함하는 경우 모든 옵션이 작동할 수 있지만 다음 그림에 표시된 대로 "기술" 옵션을 선택하는 것이 좋습니다.

![이미지](https://media.github.ibm.com/user/11495/files/4474c300-4bd9-11e9-9bc7-d6242d7997e9)
