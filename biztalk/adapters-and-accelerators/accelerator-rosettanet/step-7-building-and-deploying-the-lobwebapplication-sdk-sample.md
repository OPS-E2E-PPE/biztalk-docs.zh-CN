---
title: "步骤 7： 构建和部署 LOBWebApplication SDK 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b101b47e2f83a0390a47cf6b1e4fc9a210950d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a>步骤 7： 构建和部署 LOBWebApplication SDK 示例
在此步骤中，将创建业务线 (LOB) 应用程序，而 Fabrikam 将使用此应用程序向 Contoso 提交合作伙伴接口流程 (PIP) 请求。 你可以在 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹中找到 LOBWebApplication 项目。 若要运行 Web 应用程序，你必须创建[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Internet 信息服务 (IIS) 虚拟目录，然后生成 LOBWebApplication 项目。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>创建 LOBWebApplication 虚拟目录  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 Internet 信息服务管理器窗口中，展开**< 计算机名 > （本地计算机）**，然后展开**网站**。  
  
3.  右键单击**Default Web Site**，指向**新建**，然后单击**虚拟目录**。  
  
4.  上**Welcometo 虚拟目录创建向导**页上，单击**下一步**。  
  
5.  上**虚拟目录别名**页上，在**别名**框中，键入**LOBWebApplication**，然后单击**下一步**。  
  
6.  上**网站内容目录**页上，单击**浏览**。 在浏览文件夹对话框中，移动到 ***\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键LOBWebApplication**，然后单击**确定**。 单击 **“下一步”**。  
  
7.  上**虚拟目录访问权限**页上，取消选择**读取**，选择**运行脚本 （如 ASP)**，然后单击**下一步**。  
  
8.  上**已成功完成虚拟目录创建向导**页上，单击**完成**可以创建虚拟目录。  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a>从 SharePoint 配置中排除 LOBWebApplication 网站  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
2.  上**管理中心**Web 页上，在**虚拟服务器配置**部分中，选择**扩展或升级虚拟服务器**。  
  
3.  如果看不到计算机上配置的 URL，请单击**完整列表**。  
  
4.  上**虚拟服务器列表**页上，选择**Default Web Site**。  
  
5.  在**虚拟服务器管理**部分中，单击**定义管理路径**。  
  
6.  在**添加新路径**部分中，在**路径**框中，键入**/LOBWebApplication**。  
  
7.  有关**类型**，选择**排除路径**，然后单击**确定**。  
  
### <a name="to-build-the-lobwebapplication-project"></a>生成 LOBWebApplication 项目  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft Visual Studio 2008**，然后单击**Microsoft Visual Studio 2008**。  
  
2.  在“文件”菜单中，指向“打开”，然后单击“项目”/“解决方案”。  
  
3.  在打开项目对话框中，移动到 ***\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\LOBWebApplication 快捷键**，选择**LOBWebApplication.sln**解决方案文件，然后单击**打开**。  
  
4.  在解决方案资源管理器，右键单击**http://localhost/LOBWebApplication**，然后单击**添加引用**。  
  
5.  在添加引用对话框中，单击**浏览**。 在添加引用对话框中，移动到 ***\<驱动器\>*: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin**文件夹。  
  
6.  从 Bin 文件夹中，选择**Microsoft.Solutions.BTARN.ConfigurationManager.dll**和**Microsoft.Solutions.BTARN.Shared.dll**程序集，，然后单击**打开。**  
  
7.  单击**确定**关闭**添加引用**对话框。  
  
8.  在解决方案资源管理器，右键单击**解决方案 LOBWebApplication** ，然后单击**生成解决方案**。  
  
9. 右键单击**default.aspx**，然后单击**设为起始页**。  
  
## <a name="see-also"></a>另请参阅  
 [测试双操作教程](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)