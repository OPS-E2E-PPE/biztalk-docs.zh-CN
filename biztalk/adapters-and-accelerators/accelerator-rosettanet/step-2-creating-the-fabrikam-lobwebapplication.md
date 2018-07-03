---
title: 步骤 2： 创建 Fabrikam LOBWebApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c55234d8ee9c123c9efe9e7ec66b7c0db590b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966622"
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a>步骤 2： 创建 Fabrikam LOBWebApplication
在此步骤中，你将创建 Fabrikam 用于向 Contoso 提交 3A2 PIP 请求的 LOB 应用程序。 LOBWebApplication 项目安装在 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 中。 若要运行的 Web 应用程序，您必须创建一个 Microsoft Internet 信息服务 (IIS) 虚拟目录，然后生成 LOBWebApplication 项目。  
  
> [!NOTE]
>  如果已完成双操作教程，你无需执行此步骤。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>创建 LOBWebApplication 虚拟目录  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services Manager**。  
  
    > [!NOTE]
    >  如果已完成双操作教程，则应已在该教程中创建了 LOBWebApplication 虚拟目录。 如果是这样，你无需执行这些步骤。 但是，将需要更改的虚拟目录的权限**运行脚本**到**读取**。  
  
2.  在 Internet 信息服务管理器中，展开 **< 计算机名 > （本地计算机）**，然后展开**网站**。  
  
3.  右键单击**Default Web Site**，依次指向**新建**，然后单击**虚拟目录**。  
  
4.  上**Welcometo 虚拟目录创建向导页**，单击**下一步**。  
  
5.  上**虚拟目录别名**页上，在**别名**框中，键入**LOBWebApplication**，然后单击**下一步**。  
  
6.  上**网站内容目录**页上，单击**浏览**，选择**\<驱动器\>: \Program Files\Microsoft BizTalk\<版本\>RosettaNet\SDK\LOBWebApplication 的加速器**文件夹，，然后单击**确定**。 单击“下一步” 。  
  
7.  上**虚拟目录访问权限**页上，单击**下一步**。  
  
8.  单击**完成**创建虚拟目录。  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a>从 SharePoint 中排除 LOBWebApplication  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
    > [!NOTE]
    >  如果已完成双操作教程，则应已在该教程中将 LOBWebApplication 虚拟目录从 SharePoint 中排除。 如果是这样，你无需执行这些步骤。  
  
2.  上**Central Administration**页上，在**虚拟服务器配置**部分中，选择**扩展或升级虚拟服务器**。  
  
3.  如果看不到的计算机上配置的 URL，请单击**完整列表**。  
  
4.  选择**默认网站**。  
  
5.  在中**虚拟服务器管理**部分中，单击**定义管理路径**。  
  
6.  在中**添加新路径**部分中，在**路径**框中，键入"/ LOBWebApplication"。 有关**类型**，选择**排除的路径**，然后单击**确定**。  
  
### <a name="to-build-the-lobwebapplication-project"></a>生成 LOBWebApplication 项目  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  从**文件**菜单，依次指向**打开**，然后单击**项目 \ 解决方案**。  
  
3.  在打开项目对话框中，在**查找范围**，将移动到**\<驱动器\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\ SDK\LOBWebApplication**，选择**LOBWebApplication.sln**解决方案，，然后单击**打开**。  
  
4.  在解决方案资源管理器中右键单击顶级节点 (http://localhost/LOBWebApplication)，然后单击**添加引用**。  
  
5.  在添加引用对话框中，单击**浏览**并将移至**\<驱动器\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\bin**.  
  
6.  **选择 Microsoft.Solutions.BTARN.ConfigurationManager.dll 和 Microsoft.Solutions.BTARN.Shared.dll**程序集 **，然后单击确定。**  
  
7.  上**构建**菜单上，单击**生成网站**。  
  
### <a name="to-run-the-lobwebapplication-project"></a>运行 LOBWebApplication 项目  
  
1.  在解决方案资源管理器中右键单击**default.aspx**，然后选择**设为起始页**。  
  
2.  上**调试**菜单上，单击**启动但不调试**。  
  
## <a name="see-also"></a>请参阅  
 [测试解决方案](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)