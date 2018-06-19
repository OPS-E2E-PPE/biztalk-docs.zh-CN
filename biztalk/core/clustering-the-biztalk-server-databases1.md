---
title: 群集 BizTalk Server Databases1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, how to
- clustering, SQL Servers
- SQL Server, clustering
- BizTalk Server Configuration Wizard
- high availability, databases
- clustering, BizTalk Server Configuration Wizard
- clustering, databases
- clustering, prerequisites
ms.assetid: 9a1ed843-483b-4a56-961b-bc6801a07b64
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 983023ceb88618a540d922481c4cb185a076ae3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232429"
---
# <a name="clustering-the-biztalk-server-databases"></a>群集的 BizTalk Server 数据库
本部分提供了部署具有高可用性的 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案的准则。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库不可用，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境将无法正常运行。 为确保高可用性，您可以为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库创建如下图所示的 Microsoft SQL Server 群集：  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 若要提供的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，你必须具有至少两台计算机，在由 Windows Server 故障转移群集中运行 SQL Server 和使用共享的磁盘阵列。  
  
## <a name="procedures-for-clustering-the-databases"></a>群集数据库的过程  
  
#### <a name="before-you-start"></a>开始之前  
  
1.  若要为 BizTalk Server 环境创建域组，则必须创建 Active Directory 域全局组。  
  
2.  在安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 前，请配置 SQL Server 群集。 有关群集 SQL Server 的详细信息，请参阅[Alwayson 故障转移群集实例](https://technet.microsoft.com/library/ms189134.aspx)。  
  
3.  如果你要创建群集的主密钥服务器，请首先配置该服务器。 为企业单一登录高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>运行 BizTalk Server 配置向导  
  
1.  在运行时服务器上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
2.  启动 BizTalk 配置程序。 单击**启动**，指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
3.  按照中的步骤[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)要应用自定义配置。 若要指定 BizTalk 数据库的 SQL Server 群集，请输入中的 SQL Server 群集的名称**数据库**配置程序中所述的对话框**编辑数据库**部分本主题中。  
  
4.  通过中的说明完成 BizTalk Server 配置[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [创建高度可用的 BizTalk Server 环境](../core/creating-a-highly-available-biztalk-server-environment.md)