---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud 上的虛擬遞送及轉遞 (VRF) 概觀
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

依定義，虛擬遞送及轉遞 (VRF) 是網際網路通訊協定 (IP) 網路路由器中包含的技術。它提供為一項固有的骨幹服務。

## IBM Cloud 的連線功能選項

**分散雲端資源**是位於多個位置或甚至多個子網路或 VLAN 的資源。這些資源需要遞送功能以便彼此通訊，甚至是在專用網路的環境定義內通訊。本文件說明「多重隔離」的租用通訊選項，這經常稱為_客戶 VRF_。它實作為跨越全球 {{site.data.keyword.cloud}} 骨幹的 MPLS 第 3 層 VPN (RFC 4364)。

一般而言，IBM Cloud Platform 提供兩個選項以便在我們的專用網路之間遞送，並提供 Pod 及資料中心之間的連線功能：

1. **共用租用：**一個共用的邏輯網路，由使用此模型的所有承租戶所共用，且具有自動化存取控制清單 (ACL) 所提供的分隔，以及 VLAN 跨距的功能。（本文件不說明這個選項。）

2. **多重隔離：**每個承租戶一個專用的邏輯網路，這不允許與其他承租戶的邏輯網路有任何互動。  

本文件使用**客戶 VRF** 一詞來說明_多重隔離_ 網路連線功能。

## VRF 概觀（多重隔離技術）

虛擬遞送及轉遞 (VRF) 容許在路由器中存在一個遞送表的多個實例，並且同時運作。使用虛擬遞送及轉遞 (VRF)，每個雲端承租戶的 VRF 網路會在其遞送表之內分段。此分段容許 IP 位址重疊，且不會對其他承租戶 VRF 產生任何互動或干擾。IBM Cloud 利用大部分的 `10.0.0.0/8` 網路，這可能會與許多遠端網路（例如，在客戶資料中心部署的網路）重疊。

使用虛擬遞送及轉遞 (VRF)，IBM Cloud 承租戶能夠使用遠端 IP 位址，而遠端 IP 位址一般並不允許在廣域表格中重疊。IBM 仍然保留下列 RFC 1918、鏈結本地位址及多重播送位址，它們無法從此 VRF 服務遞送：

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16`（專用端點服務所使用）
* IBM 平台上，指派給您 VLAN 的任何 IP 範圍

IBM 正藉由部署下一代的 Cloud 向前邁步，在我們的「可用性區域」中啟用「虛擬專用雲端 (VPC)」。這項新的 VPC 功能可在已啟用 VPC 的「可用性區域 (AZ)」中使用自帶 IP (BYoIP)，這些 AZ 位於達拉斯、華盛頓特區、倫頓、法蘭克福、東京和雪梨。

骨幹上每個利用「虛擬遞送及轉遞 (VRF)」的承租戶，每個 Direct Link 都可以有一個（且只能有一個）_客戶 VRF_，這提供承租戶所有伺服器之間的連線功能，而不論其位置為何。不過，IBM Cloud 承租戶可能有多個 Direct Link 帳戶，饋送資訊到單一交叉連接路由器。  

* 承租戶的伺服器，無論是在任何 VLAN、任何 Pod、全球各地的任何資料中心，都可以呼叫到該承租戶的全球所有其他伺服器。

* 每個承租戶的客戶 VRF 連接至一般共用服務服務網路，以提供專用可聯繫性，讓那些伺服器使用 DNS、共用儲存空間、監視、修補等等。

* 「客戶 VRF」是一項連線功能服務，在承租戶之間提供隔離。在租賃內需要的任何其他控制措施，都必須個別佈建，並使用閘道、安全群組或以主機為基礎的控制措施。

## 移到 VRF 的好處

**主要好處包括：**

* 業界證實過且廣為接受的_多重隔離_ 分隔技術。許多雲端客戶發現第 3 層 VPN 方式（比起 ACL）對他們的審核員和法規遵循管理者而言更可接受。   

* IBM Cloud 客戶可以大幅延伸或移轉他們網路的觸及範圍，因為在整個 IBM 網路中新增了新的網站或應用程式。

* 承租戶特定的遞送表縮小 IP 位址重疊的可能性，而不會有與其他承租戶子網路或其他不適用之網路部分重疊的風險。

**與較舊的 ACL 模型相比，一些輕微的妥協：**  

* 轉換成客戶 VRF 需要維護時間，這會導致骨幹資料傳輸流有短暫的中斷。

* 利用受管理 VPN 服務（SSL、IPSec）的遠端存取，限制於本端資料中心；不過，共用的 ACL 骨幹允許從任何進入點進行廣域存取。

* 在您的_多重隔離_ 租賃內無法使用 VLAN Spanning。

## 帳戶轉換過程期間發生什麼事

許多 IBM Cloud 客戶目前在 IBM Cloud 網路上，以共用租賃模型運作。在轉換期間，租賃會轉換為使用客戶 VRF，最常具有新的 Direct Link 訂閱，或是如其他方式所要求。  

轉換過程會有網路中斷，此時 VLAN 及其子網路會從 ACL 骨幹分離，然後連接至客戶 VRF。這個過程會導致有一些時候進入或離開 VLAN 的資料流量封包流失。VLAN 內的封包會繼續流動。在牽涉到網路閘道（例如 FortiGate Security Appliance 或 Virtual Router Appliance）的情況下，連接至該閘道的 VLAN 之間不會發生中斷。伺服器本身不會發現網路中斷，大部分的工作負載會在資料傳輸流繼續時自動回復。中斷的總持續時間取決於承租戶拓蹼的延伸範圍，亦即您的租賃所包含的子網路、VLAN 及 Pod 數目。

![轉換過程](/images/vrf-on-ibm-cloud.png)

在移轉期間，VLAN 會中斷骨幹的連線，然後重新連接到「客戶 VRF」。中斷的持續時間會視相關的 VLAN、Pod 及資料中心數量而變。VLAN 之間的資料流量會中斷，但伺服器仍會連接至網路。應用程式不一定會受影響，視其對封包流失的靈敏度而定。

## 如何起始轉換
{: #how-you-can-initiate-the-conversion}

現有的 IBM Cloud 客戶可以透過 [IBM Cloud 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")]( https://control.bluemix.net/support/unifiedConsole/tickets/add) 帳戶開立支援問題單，要求移轉至 VRF。問題單應該指出：“Private Network Question”，並請在支援問題單中包含下列文字：

"We are requesting that account _fill in your account number_ is moved to its own VRF. We understand the risks and approve the change.  Please reply back with the scheduled window(s) of time where this change will be made so we can prepare for the migration."

移轉由 IBM Cloud 網路工程團隊完成。除了雙方協議的排程之外，不需要您提供其他資訊。通常封包流失可能持續 15-30 分鐘，視您帳戶的複雜性而定。（如果您的帳戶有舊式 Direct Link 連線的話可能會更久。）處理程序高度自動化，需要 IBM 團隊的最少互動，且應該是清楚可見的。
