---
title: 如何导入 EDI-AS2 解决方案的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b918fa2-44f2-4f57-95af-36858cea0d86
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cb2de1817bb43f66d21c962c88f0038300c379e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337073"
---
# <a name="how-to-import-bindings-for-an-edi-as2-solution"></a>如何导入 EDI-AS2 解决方案的绑定
本主题介绍如何导入到另一台计算机上的 EDI 和/或 AS2 解决方案的配置。 部署 EDI/AS2 解决方案的 BizTalk 应用程序部署与集成。 可通过[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台和 BTSTask 命令行工具。  
  
 您可以导入的配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用导出的相应绑定的源计算机创建的绑定文件。 有关导出到绑定文件的配置信息，请参阅[如何导出 EDI-AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)。 有关从配置创建的绑定文件的信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。  
  
 您还可以导入绑定导入使用某一.msi 文件的应用程序的一部分。 有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 或者，可以使用 BTSTask 命令导出和导入绑定。 有关 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)中的主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="prerequisites"></a>先决条件  
  
- 您必须是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
- 您必须添加对的引用**BizTalk EDI 应用程序**从将用作 EDI 应用程序的 BizTalk 应用程序。 有关添加对 BizTalk EDI 应用程序的引用的说明，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
## <a name="importing-bindings"></a>导入绑定  
 导入配置，会覆盖现有的 EDI 属性。 如果您为其导入属性具有与现有参与方，相同的名称的参与方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将替代现有参与方 EDI 属性 （或所有绑定）。 此外，如果您要导入 EDI 全局属性，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将覆盖现有的 EDI 全局属性。  
  
 导入的配置之后, 必须重新配置密码。 出于安全原因，当您导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会从文件删除绑定的密码。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从 EDIFACT 属性和 X12 中的 ISA1 和 ISA2、 ISA3，和 ISA4 字段中删除 UNB6.1 和 UNB6.2 字段属性。 导入绑定之后, 必须重新这些敏感字段配置之前处理 EDI 消息。  
  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法导入一组绑定，则原因可能是绑定文件中的受信任主机属性是不同于主机的受信任验证属性。 可以通过更改绑定文件中的受信任主机属性来解决此问题。  
  
> [!NOTE]
>  从早期版本的 BizTalk Server 的绑定文件导入 BizTalk Server 可能会失败。 由于合作伙伴管理模型已显著更改为 BizTalk Server 中，从 BizTalk Server 早期版本中导入绑定文件不能创建实体在 BizTalk Server 中根据新的模型。 有关详细信息，请参阅[如何参与方定义中上一个 BizTalk Server 版本转换到新的 TPM 实体？](../core/how-to-import-bindings-for-an-edi-as2-solution.md#BKMK_Party)。  
  
### <a name="to-import-the-configuration-from-a-binding-file"></a>若要从绑定文件导入配置  
  
1. 你想要导入配置，打开的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 右键单击 BizTalk 应用程序想要导入到的 EDI/AS2 配置，请指向**导入**，然后单击**绑定**。  
  
3. 在导入绑定对话框中，转到包含你的绑定文件的位置，然后单击**打开**。  
  
4. 在导入绑定之后, 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 手动将所有 EDI 密码字段都设置为适当的值。  
  
##  <a name="BKMK_Party"></a> 如何执行参与方定义中上一个 BizTalk Server 版本转换到新的 TPM 实体？  
 在 BizTalk Server 参与方定义是实质上是协议，用于定义两个贸易合作伙伴之间交换消息的方式。 在 BizTalk Server、 EDI 和 AS2 消息传送经历了许多更改和新的贸易合作伙伴管理 (TPM) 模型现在要求两个贸易业务配置文件之间创建协议。 因此，实质上，为一个协议存在，您首先需要定义了两个贸易合作伙伴，同时贸易合作伙伴的配置文件和两个贸易业务配置文件的协议设置。 一旦定义这些实体，可以创建贸易合作伙伴协议。  
  
> [!NOTE]
>  在 BizTalk Server 中的 TPM 增强功能的详细信息，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
 给定的新 TPM 对象模型，这意味着，不能向 BizTalk Server 迁移 BizTalk Server 中创建的 EDI 应用程序？ 答案是没有。 通过使用参与方迁移工具将从 BizTalk Server 早期版本迁移参与方数据，可以重复使用现有的应用程序从 BizTalk Server 2006 R2 或 BizTalk Server 中的 BizTalk Server 2009。 有关工具的详细信息，请参阅[从以前版本的 BizTalk Server 迁移 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
## <a name="see-also"></a>请参阅  
 [导入绑定](../core/importing-bindings2.md)