---
title: 如何针对 ENTSSO MA 配置 MIIS |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e536e44ec6c76ba3bf44b346fd6b44e54c3f05b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341298"
---
# <a name="how-to-configure-miis-for-entsso-ma"></a>如何针对 ENTSSO MA 配置 MIIS
在运行 Microsoft Identity Integration Server (MIIS) 的计算机上安装企业单一登录 (SSO) 管理功能 （完整版本或仅限管理员的版本），会自动安装 ENTSSO 管理代理。 这意味着，当打开 MIIS 时，几乎所有配置已经完成了。 仅缺少的部分是连接信息。  
  
 在开始之前此过程，请确保具有提供的以下信息：  
  
-   ENTSSO 服务器名称。  
  
-   用户 Id 和在其下 ENTSSO 管理代理将与 SSO 服务器通信的 Windows 帐户的密码。  
  
### <a name="to-configure-the-management-agent-within-miis"></a>若要配置 MIIS 中管理代理  
  
1.  打开 MIIS，并打开**Identity Manager**。  
  
2.  打开**创建管理代理**对话框。  
  
3.  选择**企业单一登录**列表中。  
  
     这将启动**创建管理代理向导**。  
  
4.  上**配置连接信息**页上，在**连接到：** 字段中，输入 SSO 服务器的名称。  
  
5.  输入 ENTSSO 管理代理的名称。 此名称必须与 ENTSSO.xml 文件中指定的名称匹配。  
  
6.  在中**用户**字段中，指定 ENTSSO 管理代理使用来管理 SSO 数据库中的映射的域帐户。  
  
     此帐户应是 SSO 系统中的 SSO Affiliate Administrators 或 SSO 管理员帐户的成员。  
  
7.  在中**密码**字段中，输入该用户的密码。  
  
8.  单击**下一步**，接受默认设置，直到达到**配置扩展**页。  
  
9. 附近**连接信息**密码扩展，请单击**设置**。  
  
     **连接设置**对话框随即出现。  
  
10. 在中**连接到**框中，输入相应的帐户。 此帐户必须是指定的计算机上运行的 ENTSSO 服务的服务帐户相同。  
  
11. 在中**用户**并**密码**字段中，输入用户名和密码的帐户。  
  
12. 单击“确定” 。  
  
13. 在中**MIISCreate 管理代理**，单击**完成**。  
  
14. 在仍处于**标识管理器**，单击**工具**菜单，并单击**选项**。  
  
     **选项**对话框随即出现。  
  
15. 选择**启用 metaverse 规则扩展**。  
  
16. 在中**规则扩展名称字段**，输入**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**。  
  
17. 单击**确定**并关闭 MIIS。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 ENTSSO 管理代理](../core/how-to-use-the-entsso-management-agent.md)