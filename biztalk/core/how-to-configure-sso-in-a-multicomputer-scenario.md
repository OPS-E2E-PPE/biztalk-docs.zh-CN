---
title: "如何在多计算机方案中配置 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, SSO
- SSO database, clustering
- clustering, Master Secret server
- SSO, configuring
- configuring, Master Secret server
- Master Secret server, clustering
- clustering, SSO database
- Master Secret server, configuring
- SSO, multiple computers
ms.assetid: 4511a03d-96f2-45f0-9891-e8b3e253499c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45bfa58c1fc11a76109f56938b8e1b43790935f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a>如何在多计算机方案中配置 SSO
本部分提供了在使用三台计算机的情况下配置企业单一登录 (SSO) 的说明。  
  
 在下面的方案中，计算机 A 是主密钥服务器，计算机 B 是单一登录服务器，计算机 C 存放 SSO 数据库。 计算机 B 可充当运行时服务器、管理服务器（SSO 的管理辅助服务使用此服务器来管理 SSO 数据库）或映射服务器（SSO 的管理和客户端辅助服务使用此服务器来管理映射）。  
  
 如果要向环境中添加更多 SSO 服务器，则按照配置计算机 B 的步骤进行操作。所有新的 SSO 服务器都将指向现有的 SSO 数据库，并且不能用作主密钥服务器。  
  
> [!NOTE]
>  建议您在单一登录服务器和 SSO 数据库所在的计算机以外的其他计算机上配置主密钥服务器。  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a>在计算机 A 上配置主密钥服务器并创建 SSO 数据库。  
  
1.  执行 BizTalk Server 的自定义安装，并且仅安装企业单一登录主密钥服务器组件。  
  
2.  运行配置向导以在主密钥服务器上配置 SSO。 上**配置问题**页上，选择该选项以**创建新的 SSO 系统**。  
  
3.  上**Windows 帐户**页上，指定 SSO 服务的服务帐户凭据。 此帐户必须为 SSO Administrators 组的成员。  
  
4.  上**数据库配置**页上，指定 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。  
  
5.  指定用于备份主密钥的选项。  
  
6.  完成配置。  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a>在计算机 B 上配置 SSO 服务器  
  
1.  在计算机 B 上安装企业单一登录。  
  
    > [!NOTE]
    >  此计算机可以是 BizTalk Server 计算机、Host Integration Server 计算机或 Web 服务器，也可以仅是 SSO 服务器（SSO 运行时组件）。  
  
2.  运行配置向导以配置 SSO。 上**配置问题**页上，选择该选项以**加入现有 SSO 系统**。  
  
3.  上**Windows 帐户**页上，指定 SSO 服务的服务帐户凭据。 此帐户必须为 SSO Administrators 组的成员。  
  
4.  上**数据库配置**页上，指向 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。  
  
## <a name="see-also"></a>另请参阅  
 [如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)   
 [安装 SSO](../core/installing-sso.md)