---
title: "如何导入绑定 EDI AS2 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b918fa2-44f2-4f57-95af-36858cea0d86
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba7e0c601276779067c1699da1526491dc3f7ca2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-bindings-for-an-edi-as2-solution"></a>如何导入绑定 EDI AS2 解决方案
本主题介绍如何将 EDI 和/或 AS2 解决方案的配置导入另一台计算机。 EDI/AS2 解决方案的部署与 BizTalk 应用程序的部署集成在一起。 可以通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台和 BTSTask 命令行工具使用该部署。  
  
 您可以使用导出相应的绑定时在源计算机上创建的绑定文件导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置。 有关导出到绑定文件的配置信息，请参阅[如何导出绑定 EDI AS2 解决方案](../core/how-to-export-bindings-for-an-edi-as2-solution.md)。 创建从配置的绑定文件有关的信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。  
  
 您也可以在使用 .msi 文件导入应用程序时导入绑定。 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 还可以用 BTSTask 命令导出和导入绑定。 BTSTask 有关的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)中的主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员身份帐户登录。 有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   你必须添加对引用**BizTalk EDI 应用程序**从 BizTalk 应用程序将用作 EDI 应用程序。 有关添加到 BizTalk EDI 应用程序引用的说明，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
## <a name="importing-bindings"></a>导入绑定  
 导入配置时，将覆盖现有的 EDI 属性。 如果为其导入属性的参与方与一个现有参与方重名，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会重写现有参与方的 EDI 属性（或所有绑定）。 此外，如果导入 EDI 全局属性，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将覆盖现有的 EDI 全局属性。  
  
 导入配置后，必须重新配置密码。 出于安全原因，当导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从文件中删除绑定的密码。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从 EDIFACT 属性和从 X12 ISA1、 ISA2、 ISA3 和 ISA4 字段中删除 UNB6.1 和 UNB6.2 字段属性。 导入绑定后，必须重新配置这些敏感字段，然后再处理 EDI 消息。  
  
 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法导入一组绑定，则原因可能是绑定文件中的“受信任主机”属性与主机的“受信任验证”属性不相同。 可以通过更改绑定文件中的“受信任主机”属性来解决这个问题。  
  
> [!NOTE]
>  从以往版本的 BizTalk Server 到导入绑定文件[!INCLUDE[prague](../includes/prague-md.md)]可能会失败。 由于 [!INCLUDE[prague](../includes/prague-md.md)] 的合作伙伴管理模型已进行了相当大的更改，因此从早期版本的 BizTalk Server 导入绑定文件可能不会在 [!INCLUDE[prague](../includes/prague-md.md)] 中创建与新模型相对应的实体。 有关详细信息，请参阅[如何方定义中以前 BizTalk Server 版本转换为新的 TPM 实体？](../core/how-to-import-bindings-for-an-edi-as2-solution.md#BKMK_Party)。  
  
### <a name="to-import-the-configuration-from-a-binding-file"></a>导入绑定文件的配置  
  
1.  在您要导入配置的计算机上，打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。  
  
2.  右键单击你想要导入到 EDI/AS2 配置，指向的 BizTalk 应用**导入**，然后单击**绑定**。  
  
3.  在导入绑定对话框中，将移动到包含你的绑定文件的位置，然后单击**打开**。  
  
4.  在导入绑定后，打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 手动将所有 EDI 密码字段设置为适当的值。  
  
##  <a name="BKMK_Party"></a>为新的 TPM 实体如何中以前 BizTalk Server 版本转换方定义？  
 在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中，参与方定义实际是定义如何在两个贸易合作伙伴之间交换消息的协议。 在 [!INCLUDE[prague](../includes/prague-md.md)] 中，EDI 和 AS2 消息传送经历了许多更改，现在新贸易合作伙伴管理 (TPM) 模型需要在两个贸易业务配置文件之间创建协议。 因此，本质上，要让一个协议存在，首先需要定义两个贸易合作伙伴、两个贸易合作伙伴的配置文件以及两个贸易业务配置文件的协议设置。 定义这些实体后，您可以创建一个贸易合作伙伴协议。  
  
> [!NOTE]
>  相关的 TPM 中的增强功能的详细信息[!INCLUDE[prague](../includes/prague-md.md)]，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
 对于新 TPM 对象模型，这是否意味着在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中创建的 EDI 应用程序无法迁移至 [!INCLUDE[prague](../includes/prague-md.md)]？ 问题的回答是没有。 你可以重复使用现有的应用程序从 BizTalk Server 2006 R2 或中的 BizTalk Server 2009[!INCLUDE[prague](../includes/prague-md.md)]使用方迁移工具从以前的 BizTalk Server 版本迁移方数据。 有关工具的详细信息，请参阅[迁移 BizTalk Server 以前版本中的 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
## <a name="see-also"></a>另请参阅  
 [导入绑定](../core/importing-bindings2.md)