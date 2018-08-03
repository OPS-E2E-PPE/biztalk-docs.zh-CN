---
title: 如何配置 SSO 票证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec81ab1fa64ce7b4523771bb2c69b39c00bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018755"
---
# <a name="how-to-configure-the-sso-tickets"></a>如何配置 SSO 票证
可使用 MMC 管理单元或命令行对整个单一登录系统的票证行为进行控制，包括是否允许使用票证、系统是否必须验证票证。  
  
 可用于 Yes、 No、 On 或 Off 指示是否允许和/或验证票证。 这些词不区分大小写，必须在任何语言设置下都能使用。  
  
 如果 SSO 管理功能安装在远程计算机上，则可执行远程 IssueTicket 操作。 请注意，SSO 管理模块和运行时模块（ENTSSO 服务）之间的所有通信都是加密的。  
  
 仅当执行应用程序更新时（而非创建时），才能使用命令行实用工具 ssomanage.exe 在关联应用程序级别上指定票证超时。  
  
 只有 SSO 管理员可以在 SSO 系统级别和关联应用程序级别配置票证。  
  
 如果在系统级别上禁用了票证，则也不能在关联应用程序级别上使用票证。 就可以启用在系统级别票证和关联应用程序级别禁用它。  
  
 如果在系统级别上启用验证，则在关联应用程序级别上也需要票证验证。 但是，可以在系统级别上禁用验证，而在关联应用程序级别上启用验证。  
  
 如果在系统级别和关联应用程序级别同时指定了票证超时，则使用在关联应用程序级别上指定的票证超时确定票证过期时间。  
  
 有关票证和票证验证的详细信息，请参阅[SSO 票证](../core/sso-tickets.md)。  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a>使用 MMC 管理单元为关联应用程序配置企业单一登录票证  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  中的 ENTSSO Mmc 管理单元的作用域窗格中，展开**关联应用程序**节点。  
  
3.  右键单击**关联应用程序**，然后单击**属性**。  
  
4.  单击**选项**选项卡。  
  
5.  选择**允许使用票证**并根据需要配置票证超时。  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a>使用命令行配置企业单一登录系统级别票证  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行上，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型 * * ssomanage-tickets\<允许是/否\> *\<验证是/否\>**<em>，其中 *\<允许是/否\></em>指示是否允许使用票证，并*\<验证是/否\>* 指示是否将需要票证兑换后是否要验证。  
  
   > [!NOTE]
   >  可使用 Yes、No、On 或 Off 指示是否允许使用和/或验证票证。 这些词不区分大小写，必须在任何语言设置下都能使用。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [了解 SSO](../core/understanding-sso.md)   
 [使用 SSO](../core/using-sso.md)