---
title: 生成和发布 MT MX SharePoint 站点上的窗体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492eda3b4bf3d3950c084bc9234b52b911b84a2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980046"
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a>生成和发布在 SharePoint 站点上的 MT/MX 表单
**若要生成和发布 MT/MX 表单上的 SharePoint 站点：**  

1. 下载表单生成器实用程序，并将其保存在计算机上的本地。  

2. 打开**FormGenerator.sln**从文件夹上面的下载和编译解决方案。  

3. 在命令提示符下，访问已编译可执行文件 (FormGenerator.exe) 的文件夹。 例如，如果您已经生成实用工具在调试模式下，访问 **...\bin\debug**文件夹。  

4. 键入 FormGenerator.exe [-b] [-\<不可以。 模板文件夹路径的\>]  

    `<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`的用户。 参数替换为新创建的文件夹名称。  

5. 上述命令还将生成所需的 MX 消息修复的信封架构。  

6. 转到输出文件夹\<DestinationFolderPath\>。 在中\<DestinationFolderPath\>，打开你想要生成窗体的 InfoPath 表单模板的文件夹。 例如，如果你想要生成 MT103 InfoPath 窗体，然后打开在 DestinationFolderPath MT103 文件夹并打开 TemplateDS.sln。  

7. 在解决方案资源管理器，双击**manifest.xsf**。 它将打开 InfoPath 窗体将需要一些时间才能获取打开的设计的文件。  

   > [!NOTE]
   >  MX 消息 manifest.xsf 可能需要 2 到 5 分钟，以获取打开。  

8. 在 manifest.xsf，转到**工具-> 窗体选项-> 安全和信任**菜单选项。 检查**完全信任**必须启用选项的权限。  

9. 选择**登录此窗体模板**复选框。 单击**选择证书**。 在中，选择你想对表单进行签名的证书。 单击“确定” 。  

10. 保存**manifest.xsf**。  

11. 转到**视图-> 的设计任务**。 在设计任务窗格中，单击**发布窗体模板**选项。  

12. 在发布向导窗口中，选择**到网络位置**然后单击**下一步**。  

13. 在窗体模板路径和文件名称文本框中，键入<strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong>并键入**\<MessageType\>** 窗体模板中命名文本框，然后单击**下一步**.  

14. 单击“下一步” 。  

15. 单击**发布并关闭**。  

16. 在 Internet Explorer 中，打开您的 SharePoint 站点**http://localhost/sites/bassite/templates**。  

17. 指向 **\<MessageType\>**，单击它，旁边的向下箭头，然后单击**编辑属性**。  

18. 在模板中：\< MessageType\>窗口中的，在 Namespace 框中：  

    - 如果生成 MT InfoPath 窗体，请键入： **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**  

    - 如果生成 MX InfoPath 表单，请键入： <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong>  

       这将有助于标识与相应的模板的消息实例。  

19. 单击**保存并关闭**。
