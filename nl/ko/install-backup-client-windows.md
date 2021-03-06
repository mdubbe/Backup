---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Windows에서 백업 클라이언트 설치

Windows에서 {{site.data.keyword.backup_full}} 설치는 {{site.data.keyword.backup_notm}} 서비스용으로 지정된 서버에서 일련의 상호작용을 통해 완료됩니다.

Windows 2016 서버의 백업에 대한 정보는 [Windows 2016에서 {{site.data.keyword.backup_notm}} 구성](install-backup-client-windows2016.html)을 참조하십시오.
{:tip}

## 대상 디바이스 서버에 로그인

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://console.bluemix.net/catalog/){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오. 

   또는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다. 
2. 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하여 사용 가능한 서버의 목록을 보십시오. 
3. {{site.data.keyword.backup_notm}} 서비스가 구매된 대상 디바이스를 찾고 이의 공인 IP 주소를 기록하십시오. 
4. 오른쪽을 지시하는 화살표를 클릭하여 펼치고 사용자 이름과 비밀번호를 포함해 디바이스에 대한 자세한 정보를 표시하십시오. 비밀번호가 표시되지 않은 경우, **비밀번호 표시**를 클릭하면 비밀번호가 표시됩니다.
5. 원격 데스크탑 연결을 사용하여 대상 디바이스에 로그인하십시오.

## 백업 클라이언트 다운로드

1. 대상 서버에서 브라우저 세션을 열고 다음의 URL을 입력하여 {{site.data.keyword.backup_notm}} 클라이언트에 대한 실행 파일을 다운로드하십시오. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. 다운로드한 파일을 두 번 클릭하십시오.
3. **실행**을 클릭하십시오.


## 백업 에이전트 설치 및 등록

1. 네트워크 주소를 입력하십시오. <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. **사용자 이름** 필드에 사용자 이름을 입력하십시오.
3. **비밀번호** 필드에 비밀번호를 입력하십시오.
6. **다음**을 클릭하십시오.
7. **설치**를 클릭하여 설치를 완료하십시오.

## 백업 에이전트 구성

WebCC에 로그인하여 백업 에이전트를 구성하고 관리하십시오. 자세한 정보는 [시작하기 튜토리얼](index.html#configuring-the-backup-agent-in-webcc)을 참조하십시오. 
