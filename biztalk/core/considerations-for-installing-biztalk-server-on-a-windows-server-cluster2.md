---
title: 在 Windows Server Cluster2 上安装 BizTalk Server 的注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configure Your Server Wizard
- installing, Windows Server cluster
- BizTalk Server Configuration Wizard
- Windows Server cluster, warnings
- high availability, Windows Server cluster
- clustering, Windows Server cluster
- domain groups
- Windows Server cluster, Configure Your Server Wizard
- Network DTC access
- MSDTC
ms.assetid: 4daea7c6-7d26-440c-a2a0-fa018a25b2b3
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38bd34862efb0cd73e66a2c694abd26b823766db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237933"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a>在 Windows Server 群集上安装 BizTalk Server 的注意事项
在安装时，必须进行特殊考虑[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server 群集上。 本主题中将列出这些注意事项。  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a>非群集 BizTalk 主机实例不应运行于群集了企业 SSO 服务的 Windows Server 群集上  
 建议您以主动/被动配置对企业单一登录主密钥服务器进行群集，以便确保主密钥服务器高度可用。 如果非群集 BizTalk 主机实例和企业 SSO 服务的群集实例在同一个群集节点上运行，则在将群集企业 SSO 服务移到群集中的其他节点时，BizTalk 主机实例将失败。 BizTalk 主机对企业 SSO 服务的本地运行实例有依存关系。 因此如果企业 SSO 服务配置为群集资源，则必须在群集节点上运行任何 BizTalk 主机配置为相同的群集组中的群集资源中。  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a>在群集上安装 BizTalk Server 之前将 Microsoft 分布式事务处理协调器 (MSDTC) 配置为群集资源  
 如果计划在 Windows Server 群集上安装 BizTalk Server，则必须首先对 Microsoft 分布式事务处理协调器进行群集。  
  
 若要在 Windows Server 2008 故障转移群集上群集 MSDTC，请按照中概述的步骤[清单： 在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/?LinkID=129677)  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a>必须在所有 BizTalk Server 和 SQL Server 上启用网络 DTC 访问，然后才能安装或配置 BizTalk Server。  
 若要启用网络 DTC 访问在每个群集节点上以及在将承载 BizTalk Server 数据库的 SQL 服务器，请按照中概述的步骤[如何在 Web 服务器上启用 MSDTC](http://go.microsoft.com/fwlink/?LinkId=189701) (http://go.microsoft.com/fwlink/?LinkId=189701)。 必须启用网络 DTC 访问以容纳事务支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 建议您在完成此知识库文章中的步骤后，重新启动每台服务器。  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a>配置 BizTalk Server 前必须在 Active Directory 中手动创建域组  
 如果在多台计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导中指定域组和用户帐户。 如果您将域组用于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置，则配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之前必须先手动创建这些组。