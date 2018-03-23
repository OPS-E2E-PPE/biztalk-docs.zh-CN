---
title: 生成和发布 SharePoint 站点上的 MT MX 窗体 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8bd8248a916d1e98571551a8561119b6377329
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a>生成和发布 SharePoint 站点上的 MT/MX 窗体
**若要生成和发布 SharePoint 站点上的 MT/MX 窗体：**  
  
1.  下载的窗体生成器实用程序，并将其本地保存在计算机上。  
  
2.  打开**FormGenerator.sln**从文件夹上面的下载和编译解决方案。  
  
3.  在命令提示符下，访问已编译可执行文件 (FormGenerator.exe) 的文件夹。 例如，如果已生成实用工具在调试模式下，访问**...\bin\debug**文件夹。  
  
4.  键入 FormGenerator.exe [-b] [-\<否。 模板文件夹路径\>]  
  
     `<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`中创建已分区表或索引。 将参数替换为新创建的文件夹名称。  
  
5.  上述命令还将生成所需的 MX 消息修复信封架构。  
  
6.  转到输出文件夹\<DestinationFolderPath\>。 在\<DestinationFolderPath\>，打开你想要生成的窗体的 InfoPath 窗体模板的文件夹。 例如，如果你想要生成 MT103 InfoPath 窗体，然后打开在 DestinationFolderPath MT103 文件夹并打开 TemplateDS.sln。  
  
7.  在解决方案资源管理器中，双击**manifest.xsf**。 它将打开将需要一些时间来获取打开的 InfoPath 窗体的设计文件。  
  
    > [!NOTE]
    >  MX 消息 manifest.xsf 可能需要 2-5 分钟，才能获取打开。  
  
8.  在为 manifest.xsf，转到**工具-> 窗体选项-> 安全和信任**菜单选项。 检查**完全信任**选项必须启用的权限。  
  
9. 选择**登录此窗体模板**复选框。 单击**选择的证书**。 在中，选择你想对表单进行签名的证书。 单击 **“确定”**。  
  
10. 保存**manifest.xsf**。  
  
11. 转到**视图-> 设计任务**。 设计任务窗格中，单击**发布窗体模板**选项。  
  
12. 在发布向导窗口中，选择**到网络位置**单击**下一步**。  
  
13. 在窗体模板路径和文件名称文本框中，键入**http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn**和类型 **\<MessageType\>**窗体模板中将文本框中，然后单击**下一步**。  
  
14. 单击“下一步” 。  
  
15. 单击**发布并关闭**。  
  
16. 在 Internet Explorer 中，打开你的 SharePoint 站点**http://localhost/sites/bassite/templates**。  
  
17. 指向 **\<MessageType\>**，单击它，旁边的向下箭头，然后单击**编辑属性**。  
  
18. 在模板中：\< MessageType\>窗口中的，在 Namespace 框中：  
  
    -   如果要生成 MT InfoPath 窗体，请键入： **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**  
  
    -   如果要生成 MX InfoPath 窗体，请键入：  **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_ \<MessageName\>**  
  
         这将有助于标识与相应的模板消息实例。  
  
19. 单击**保存并关闭**。