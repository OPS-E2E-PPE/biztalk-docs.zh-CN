---
title: 如何在多计算机方案中配置 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bdaefef80a0a3e975c9d63e1844475ae698c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386212"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a>如何在多计算机方案中配置 SSO
本部分包含有关在包含三台计算机方案中配置企业单一登录 (SSO) 的说明。  
  
 在以下方案中，计算机 A 是主密钥服务器，计算机 B 是单一登录服务器，计算机 C 存放 SSO 数据库。 计算机 B 可充当运行时服务器，为管理服务器 （SSO 管理辅助服务使用此服务器用于管理 SSO 数据库），或映射服务器 （管理和数据的 SSO 客户端辅助服务使用此服务器来管理映射）。  
  
 如果你想要将更多 SSO 服务器添加到你的环境，请按照配置计算机 B 的步骤任何新的 SSO 服务器将指向现有的 SSO 数据库，并且不能在主密钥服务器。  
  
> [!NOTE]
>  建议你从单一登录服务器和 SSO 数据库的其他计算机上配置主密钥服务器。  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a>若要配置主密钥服务器和计算机 A 上创建 SSO 数据库  
  
1.  执行自定义安装的 BizTalk Server 中，并只安装企业单一登录主密钥服务器组件。  
  
2.  运行配置向导来配置 SSO 主密钥服务器上。 上**配置问题**页上，选择选项**创建新的 SSO 系统**。  
  
3.  上**Windows 帐户**页上，指定用于 SSO 服务的服务帐户凭据。 这必须是 SSO Administrators 组的成员。  
  
4.  上**数据库配置**页上，指定 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。  
  
5.  指定要备份主密钥的选项。  
  
6.  完成配置。  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a>若要在计算机 B 上配置的 SSO 服务器  
  
1.  在计算机 b。 上安装企业单一登录  
  
    > [!NOTE]
    >  这可以是在 BizTalk Server 或 Host Integration Server 计算机、 Web 服务器或仅 SSO 服务器 （SSO 运行时组件）。  
  
2.  运行配置向导以配置 SSO。 上**配置问题**页上，选择选项**加入现有 SSO 系统**。  
  
3.  上**Windows 帐户**页上，指定用于 SSO 服务的服务帐户凭据。 这必须是 SSO Administrators 组的成员。  
  
4.  上**数据库配置**页上，指向 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。  
  
## <a name="see-also"></a>请参阅  
 [如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)   
 [安装 SSO](../core/installing-sso.md)