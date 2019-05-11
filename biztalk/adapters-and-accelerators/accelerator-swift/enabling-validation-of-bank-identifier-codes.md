---
title: 启用银行标识代码验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), enabling
ms.assetid: d268a892-f304-44cb-b590-28ef359c8d99
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 582fde7ad899360aaa74a5fee1ece46ef068e56b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377963"
---
# <a name="enabling-validation-of-bank-identifier-codes"></a>启用银行标识代码验证
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]架构确保银行标识代码 (BICs) SWIFT 交换文档中指定符合 SWIFT 定义 BIC 数据格式。 A4SWIFT 还支持验证与数据库中的客户指定 BIC 列表 BICs。  

 如果已启用 BRE 验证并启用 BIC 验证，可以执行此验证。  

 默认情况下，A4SWIFT 安装程序会禁用 BRE 验证。 若要启用它，必须为可用于使用 A4SWIFT 拆装器的接收管道设置 BRE 验证配置参数。 您还必须运行 BRE 部署实用工具部署的主策略和验证策略特定于该消息以进行验证 (MT*xxx*_Master_policy.xml 和 MT*xxx*_Validation_Policy.xml)。 有关详细信息，请参阅[使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)并[部署 BRE 规则](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)。  

 启用了 BRE 验证之后，必须使用发布和部署这两种 BIC 验证策略 （BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml） 使用规则引擎部署向导。 这样做之前必须执行以下操作：  

- 从 SWIFT BIC 值与数据库中填充。 您可以使用 Bicplus 表在 A4SWIFT 数据库中，通过 A4SWIFT 安装程序安装，或者可以使用自定义数据库。 有关详细信息，请参阅[管理 Bicplus 表 A4SWIFT 数据库中](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)。  

- BIC 数据库设置和启用的自定义 BIC Master 策略 BIC 验证。 请参阅下面的过程。  

  为了提高性能，您不应部署 BIC 验证策略如果 BIC 验证不需要。  

> [!NOTE]
>  您可以发布和部署 BIC 验证策略，仅当已发布 A4SWIFT_Codelist 和 A4SWIFT_Functions 词汇。 通过运行 swift 架构程序集上的 BRE 部署实用工具来发布这些词汇。 有关详细信息，请参阅[第 1 课：部署相关的业务规则](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)。  

### <a name="to-customize-the-bic-master-policy"></a>若要自定义 BIC Master 策略  

1. 打开 XML 编辑器 （如记事本)，并浏览到 **<*驱动器*Program Files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略**。  

2. 打开**BIC_Master_Policy.xml**。 将新值替换为以下现有字符串。  

   > [!NOTE]
   >  必须为 A4SWIFT 数据库中的 Bicplus 表或您自己的自定义数据库输入值。 A4SWIFT 数据库不是 BIC_Master_Policy.xml 中的默认值。  

   > [!NOTE]
   >  以下字符串必须不包含在双引号中。  

   |            现有的字符串            |                                                              替换为                                                              |
   |---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
   |      **指定 SQL SERVER 名称**      | 名称[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]包含保存 BIC 的数据库。 |
   |     **指定 BIC 数据库名称**     |                                         包含 BIC 表的数据库的名称。                                          |
   | **指定集成的安全性值** |                                                                **SSPI**                                                                |


3. 保存修改后的主策略。  

4. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则引擎部署向导**.  

5. 在欢迎页上，单击**下一步**。  

6. 在部署任务页上，单击**导入策略/词汇并发布到数据库文件从**，然后单击**下一步**。  

7. 在策略存储区页上，在**SQL Server 名称**，选择[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]包含 BizTalk 数据库。 在中**选定的服务器上配置数据库**，选择**BizTalkRuleEngineDb**，然后单击**下一步**。  

8. 在导入规则引擎策略/词汇文件页中，浏览到 **<*驱动器*files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFTMessages\A4SWIFT SRG\<版本\>\Base 策略**，单击**BIC_Master_Policy.xml**，单击**打开**，然后单击**下一步**。  

9. 在准备就绪的页上，验证数据，然后单击**下一步**。  

10. 在导入策略/词汇页上，验证该命令已成功，然后单击**下一步**。  

11. 在完成规则引擎部署向导页上，单击**再次运行此向导**，然后单击**完成**。  

12. 在欢迎页上，单击**下一步**。  

13. 在部署任务页上，单击**部署策略**，然后单击**下一步**。  

14. 上**策略存储区**页上，在**SQL Server 名称**，选择[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]包含 BizTalk 数据库。 在中**选定的服务器上配置数据库**，选择**BizTalkRuleEngineDb**，然后单击**下一步**。  

15. 上**部署策略**页上，选择**BIC_Master_Policy.1.0**，然后单击**下一步**。  

16. 上**准备好**页上，单击**下一步**。  

17. 在部署策略页中，如果成功部署后，请单击**下一步**。 单击**再次运行此向导**，然后单击**完成**。  

18. 重复步骤 5 到 17 **BIC_Validation_Policy.xml**输入**BIC_Validation_Policy**而不是**BIC_Master_Policy**。  

19. 退出规则引擎部署向导。  

20. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。 确认**策略**列表中包括**BIC_Master_Policy**并**BIC_Validation_Policy**下**策略**。  

21. 展开**版本 1.0-部署**下**BIC_Master_Policy**，然后单击**BIC_Master_Rule**。  

22. 在那么窗格中，验证列出的 SQL 连接属性正确。  

    > [!NOTE]
    >  A4SWIFT 不提取之前重新启动承载当前配置为使用 SWIFT 反汇编程序的接收管道的 BizTalk 服务，对主 BIC 验证策略进行的更改。 A4SWIFT 验证通过 BIC 主策略中指定的 BIC 列中包含的 BIC 值此管道的所有文档。 用于启动此 BizTalk 服务 (BTSNTSvc.exe) 的用户帐户必须有权 BIC 数据库和表。 为提高安全性，建议您授予对 BIC 数据库和表的只读访问权限。  

    > [!NOTE]
    >  如果使用消息修复和新提交，World Wide Web Publishing 服务必须重新启动 （通过运行 iisreset.exe） BIC 验证正常工作，从 InfoPath。  

## <a name="see-also"></a>请参阅  
 [使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)   
 [在 A4SWIFT 数据库中管理 Bicplus 表](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)