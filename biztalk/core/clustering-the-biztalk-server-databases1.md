---
title: 聚类分析 BizTalk Server Databases1 |Microsoft Docs
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
ms.openlocfilehash: a098e465178cd696249c483a17dd65c5d595c349
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528199"
---
# <a name="clustering-the-biztalk-server-databases"></a>聚类分析 BizTalk Server 数据库
此部分提供了部署 Microsoft 的指导原则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有高可用性解决方案。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库变得不可用，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境将无法正常工作。 若要提供高可用性，可以创建的 Microsoft SQL Server 群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，如下图中所示。  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 若要提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，必须具有至少两台计算机正在运行的 SQL Server 和使用一个共享的磁盘阵列的 Windows Server 故障转移群集。  
  
## <a name="procedures-for-clustering-the-databases"></a>聚类分析数据库的过程  
  
#### <a name="before-you-start"></a>开始之前  
  
1. BizTalk Server 环境中创建域组时，必须创建 Active Directory 域全局组。  
  
2. 安装和配置之前配置 SQL Server 群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关群集 SQL Server 的详细信息，请参阅[Alwayson 故障转移群集实例](https://technet.microsoft.com/library/ms189134.aspx)。  
  
3. 如果您要群集主密钥服务器，请首先配置该服务器。 企业单一登录的高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>若要运行 BizTalk Server 配置向导  
  
1. 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器上。  
  
2. 启动 BizTalk 配置程序。 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
3. 按照中的步骤[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)应用自定义配置。 若要指定为 BizTalk 数据库的 SQL Server 群集，请输入中的 SQL Server 群集的名称**数据库**对话框中的配置程序中所述**编辑数据库**部分本主题中。  
  
4. 按照中的说明完成 BizTalk Server 配置[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [创建高度可用的 BizTalk Server 环境](../core/creating-a-highly-available-biztalk-server-environment.md)