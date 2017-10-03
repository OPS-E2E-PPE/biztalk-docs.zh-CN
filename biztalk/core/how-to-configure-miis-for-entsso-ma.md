---
title: "如何为 ENTSSO MA 配置 MIIS |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 969a52beb02c3d2ba237369c16efec9ee84e2ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-miis-for-entsso-ma"></a>如何针对 ENTSSO MA 配置 MIIS
当在运行 Microsoft Identity Integration Server (MIIS) 的计算机上安装企业单一登录 (SSO) 管理功能（完整版本或仅管理版本）时，将自动安装 ENTSSO 管理代理。 这表示当打开 MIIS 时，几乎已完成所有配置， 唯一缺少的部分是连接信息。  
  
 在启动此过程前，请确保具有下列可用信息：  
  
-   ENTSSO 服务器名称。  
  
-   ENTSSO 管理代理与 SSO 服务器通信所使用的 Windows 帐户的用户 ID 和密码。  
  
### <a name="to-configure-the-management-agent-within-miis"></a>在 MIIS 中配置管理代理  
  
1.  打开 miis 进行，并打开**Identity Manager**。  
  
2.  打开**创建管理代理**对话框。  
  
3.  选择**企业单一登录**列表中。  
  
     这将启动**创建管理代理向导**。  
  
4.  上**配置连接信息**页上，在**连接到：**字段中，输入 SSO 服务器的名称。  
  
5.  输入 ENTSSO 管理代理的名称。 该名称必须与 ENTSSO.xml 文件中指定的名称匹配。  
  
6.  在**用户**字段中，指定用于管理 SSO 数据库中的映射 ENTSSO 管理代理的域帐户。  
  
     此帐户应是 SSO 系统中的 SSO Affiliate Administrators 或 SSO Administrator 帐户的成员。  
  
7.  在**密码**字段中，输入该用户的密码。  
  
8.  单击**下一步**，接受默认值，直至到达**配置扩展**页。  
  
9. 附近**连接信息**密码扩展，请单击**设置**。  
  
     **连接设置**对话框随即出现。  
  
10. 在**连接到**框中，输入合适的帐户。 该帐户必须与指定计算机上运行的 ENTSSO 服务的服务帐户相同。  
  
11. 在**用户**和**密码**字段，输入帐户的用户名和密码。  
  
12. 单击 **“确定”**。  
  
13. 在**MIISCreate 管理代理**，单击**完成**。  
  
14. 仍中时，在**Identity Manager**，单击**工具**菜单，，然后单击**选项**。  
  
     **选项**对话框随即出现。  
  
15. 选择**启用 metaverse 规则扩展**。  
  
16. 在**规则扩展名称字段**，输入**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**。  
  
17. 单击**确定**并关闭 miis 进行。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用 ENTSSO 管理代理](../core/how-to-use-the-entsso-management-agent.md)