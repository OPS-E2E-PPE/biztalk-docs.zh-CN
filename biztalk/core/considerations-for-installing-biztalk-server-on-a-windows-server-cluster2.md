---
title: 在 Windows Server Cluster2 上安装 BizTalk Server 的注意事项 |Microsoft Docs
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
ms.openlocfilehash: 368b2c33ab81a63a870258da4077eb5e68164e53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354785"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a>Windows Server 群集上安装 BizTalk Server 的注意事项
安装时必须考虑特殊注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server 群集上。 本主题列出了这些注意事项。  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a>非群集 BizTalk 主机实例不应运行 Windows Server 群集上群集企业 SSO 服务位置  
 它是推荐的做法群集企业单一登录主密钥服务器在主动/被动配置中的主密钥服务器提供高可用性。 如果非群集 BizTalk 主机实例和群集的企业 SSO 服务的实例运行同一个群集节点上，如果群集的企业 SSO 服务移到另一个节点在群集中，BizTalk 主机实例将失败。 BizTalk 主机维护企业 SSO 服务的本地运行实例上的依赖项。 因此如果企业 SSO 服务配置为群集资源，然后必须在群集节点上运行的任何 BizTalk 主机配置为在同一群集组中的群集资源中。  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a>在群集上安装 BizTalk Server 之前将 Microsoft 分布式事务处理协调器 (MSDTC) 配置为群集资源  
 如果你打算在 Windows Server 群集上安装 BizTalk Server，必须首先群集 Microsoft 分布式事务处理协调器。  
  
 若要在 Windows Server 2008 故障转移群集上对 MSDTC 进行群集，请按照中所述的步骤[核对清单：在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/?LinkID=129677)  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a>所有 BizTalk Server 和 SQL Server 安装或配置 BizTalk Server 之前，必须启用网络 DTC 访问  
 若要启用网络 DTC 访问每个群集节点上以及在将承载 BizTalk Server 数据库的 SQL 服务器上，请按照中所述的步骤[如何在 Web 服务器上启用 MSDTC](http://go.microsoft.com/fwlink/?LinkId=189701) (<http://go.microsoft.com/fwlink/?LinkId=189701>)。 必须启用网络 DTC 访问才能提供事务性支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 我们建议您完成这篇知识库文章中的步骤后重新启动每个服务器。  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a>您必须手动创建域组在 Active Directory 中配置 BizTalk Server 之前  
 如果您在安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多台计算机，您必须指定域组和用户帐户在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导。 如果使用域组用于你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置中，您必须手动创建这些组在配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。