---
title: 步骤 7： 生成和部署 LOBWebApplication SDK 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a0716c854c20f5ea7fa7d2ad91576cb142f6a02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996182"
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a>步骤 7： 生成和部署 LOBWebApplication SDK 示例
在此步骤中，将创建业务线 (LOB) 应用程序，而 Fabrikam 将使用此应用程序向 Contoso 提交合作伙伴接口流程 (PIP) 请求。 您可以 Microsoft® 中找到 LOBWebApplication 项目[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK 文件夹。 若要运行的 Web 应用程序，您需要创建一个 Microsoft Internet 信息服务 (IIS) 虚拟目录，然后生成 LOBWebApplication 项目。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>创建 LOBWebApplication 虚拟目录  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 Internet 信息服务管理器窗口中，展开 **< 计算机名 > （本地计算机）**，然后展开**网站**。  
  
3.  右键单击**Default Web Site**，依次指向**新建**，然后单击**虚拟目录**。  
  
4.  上**Welcometo 虚拟目录创建向导**页上，单击**下一步**。  
  
5.  上**虚拟目录别名**页上，在**别名**框中，键入**LOBWebApplication**，然后单击**下一步**。  
  
6.  上**网站内容目录**页上，单击**浏览**。 在浏览文件夹对话框中，转到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication**，，然后单击**确定**。 单击“下一步” 。  
  
7.  上**虚拟目录访问权限**页上，取消选中**读取**，选择**运行脚本 （如 ASP)**，然后单击**下一步**。  
  
8.  上**您已成功完成虚拟目录创建向导**页上，单击**完成**创建虚拟目录。  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a>从 SharePoint 配置中排除 LOBWebApplication 网站  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
2.  上**Central Administration**中的 Web 页上，**虚拟服务器配置**部分中，选择**扩展或升级虚拟服务器**。  
  
3.  如果看不到的计算机上配置的 URL，请单击**完整列表**。  
  
4.  上**虚拟服务器列表**页上，选择**Default Web Site**。  
  
5.  在中**虚拟服务器管理**部分中，单击**定义管理路径**。  
  
6.  在中**添加新路径**部分中，在**路径**框中，键入 **/LOBWebApplication**。  
  
7.  有关**类型**，选择**排除的路径**，然后单击**确定**。  
  
### <a name="to-build-the-lobwebapplication-project"></a>生成 LOBWebApplication 项目  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Visual Studio 2008**，然后单击**Microsoft Visual Studio 2008**。  
  
2.  在“文件”菜单中，指向“打开”，然后单击“项目”/“解决方案”。  
  
3.  在打开项目对话框中，转到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication**，选择**LOBWebApplication.sln**解决方案文件，然后单击**打开**。  
  
4.  在解决方案资源管理器中右键单击**http://localhost/LOBWebApplication**，然后单击**添加引用**。  
  
5.  在添加引用对话框中，单击**浏览**。 在添加引用对话框中，转到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin**文件夹。  
  
6.  从 Bin 文件夹中，选择**Microsoft.Solutions.BTARN.ConfigurationManager.dll**并**Microsoft.Solutions.BTARN.Shared.dll**程序集，并单击**打开。**  
  
7.  单击**确定**以关闭**添加引用**对话框。  
  
8.  在解决方案资源管理器中右键单击**解决方案 'LOBWebApplication'** ，然后单击**生成解决方案**。  
  
9. 右键单击**default.aspx**，然后单击**设为起始页**。  
  
## <a name="see-also"></a>请参阅  
 [测试双操作教程](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)