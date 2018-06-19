---
title: 如何配置 SSO 票证 |Microsoft 文档
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
ms.openlocfilehash: c3b19d14a35d42c4a46bf9527a97f5bf749b875f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968643"
---
# <a name="how-to-configure-the-sso-tickets"></a>如何配置 SSO 票证
可使用 MMC 管理单元或命令行对整个单一登录系统的票证行为进行控制，包括是否允许使用票证、系统是否必须验证票证。  
  
 你可以使用是，否，打开或关闭以指示是否允许和/或验证票证。 这些词不区分大小写，必须在任何语言设置下都能使用。  
  
 如果 SSO 管理功能安装在远程计算机上，则可执行远程 IssueTicket 操作。 请注意，SSO 管理模块和运行时模块（ENTSSO 服务）之间的所有通信都是加密的。  
  
 仅当执行应用程序更新时（而非创建时），才能使用命令行实用工具 ssomanage.exe 在关联应用程序级别上指定票证超时。  
  
 只有 SSO 管理员可以配置票证，SSO 系统级别和 Affiliate 应用程序级别。  
  
 如果在系统级别上禁用了票证，则也不能在关联应用程序级别上使用票证。 它可启用在系统级别的票证和 Affiliate 应用程序级别禁用它。  
  
 如果在系统级别上启用验证，则在关联应用程序级别上也需要票证验证。 但是，可以在系统级别上禁用验证，而在关联应用程序级别上启用验证。  
  
 如果在系统级别和关联应用程序级别同时指定了票证超时，则使用在关联应用程序级别上指定的票证超时确定票证过期时间。  
  
 有关票证和票证验证的详细信息，请参阅[SSO 票证](../core/sso-tickets.md)。  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a>使用 MMC 管理单元为关联应用程序配置企业单一登录票证  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在的 ENTSSO MMC 管理单元中的作用域窗格中，展开**Affiliate 应用程序**节点。  
  
3.  右键单击**Affiliate 应用程序**，然后单击**属性**。  
  
4.  单击**选项**选项卡。  
  
5.  选择**允许票证**并适当地配置的票证超时值。  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a>使用命令行配置企业单一登录系统级别票证  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-票证\<允许是/否\> *\<验证是/否\>***，其中*\<允许是/否\>* 指示或不是，是否将允许票证和*\<验证是/否\>* 指示票证是否将需要进行验证后它们兑换.  
  
    > [!NOTE]
    >  可使用 Yes、No、On 或 Off 指示是否允许使用和/或验证票证。 这些词不区分大小写，必须在任何语言设置下都能使用。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [了解 SSO](../core/understanding-sso.md)   
 [使用 SSO](../core/using-sso.md)