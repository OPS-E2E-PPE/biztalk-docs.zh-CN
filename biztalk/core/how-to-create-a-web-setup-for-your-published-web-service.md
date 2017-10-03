---
title: "如何为你的已发布的 Web 服务中创建 Web 安装程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87c5ec4fe61c8649fe951460917cfde8788f2e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a>如何为已发布的 Web Services 创建 Web 安装程序
可以创建一个安装包，以便于在生产环境中设置 Web Services。 这会生成一个 .MSI 文件。  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a>创建一个安装包以便使用 Visual Studio 生成 .MSI 文件  
  
1.  打开已发布的 ASP.NET Web Services 项目。  
  
2.  在解决方案资源管理器，右键单击解决方案节点，单击**添加**，然后单击**新项目**。  
  
3.  在**添加新项目**对话框中，在**项目类型**区域中，展开**其他项目类型**，展开**安装和部署项目**，然后选择**Visual Studio Installer**。 在**模板**区域中，选择**Web 安装程序项目**。  
  
4.  在**名称**文本框中，键入的 Web 安装程序项目的名称。 你可以使用相同的名称为 ASP.NET Web 服务项目并添加"_Setup"作为后缀，然后单击**确定**。  
  
5.  在解决方案资源管理器，右键单击新创建的 Web 安装程序项目节点，并指向**视图**，然后单击**文件系统**。  
  
6.  在**文件系统**窗口中，右键单击**Web 应用程序文件夹**节点并指向**添加**，然后单击**项目输出**。  
  
7.  在**添加项目输出组**对话框中，选择**主输出**和**内容文件**从 ASP.NET Web 服务项目，然后单击**确定**.  
  
8.  在解决方案资源管理器，展开**检测到依赖项**Web 安装程序项目下的节点。  
  
9. 选择所有的依赖项。 在**属性**窗口中，设置**排除**属性**True**。  
  
10. 生成 Web 安装项目。  
  
    > [!NOTE]
    >  有关创建 Web 安装程序项目的详细信息，请参阅"如何为创建或添加 Web 安装程序项目"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268)。  
  
## <a name="see-also"></a>另请参阅  
 [部署非 Visual Studio 计算机上的发布的 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)