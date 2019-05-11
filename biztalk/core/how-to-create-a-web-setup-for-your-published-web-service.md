---
title: 如何为已发布的 Web 服务创建 Web 安装程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0325b45c3daf7bcf6cc0dc90c83c60a41f25fcf9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385537"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a>如何为已发布的 Web 服务创建 Web 安装程序
可以创建安装包，以便于您在生产环境中的 Web 服务设置。 这将产生。MSI 文件。  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a>若要创建一个安装包，以便生成。使用 Visual Studio 的 MSI 文件  
  
1. 打开已发布的 ASP.NET Web 服务项目。  
  
2. 在解决方案资源管理器，右键单击解决方案节点，单击**外**，然后单击**新项目**。  
  
3. 在中**添加新项目**对话框中**项目类型**区域中，展开**其他项目类型**，展开**安装和部署项目**，然后选择**Visual Studio 安装程序**。 在中**模板**区域中，选择**Web 安装项目**。  
  
4. 在中**名称**文本框中，键入的 Web 安装项目的名称。 可以使用相同的名称为 ASP.NET Web 服务项目并添加"揰 _Setup"作为后缀，然后单击**确定**。  
  
5. 在解决方案资源管理器，右键单击新创建的 Web 安装项目节点，然后指向**视图**，然后单击**文件系统**。  
  
6. 在中**文件系统**窗口中，右键单击**Web 应用程序文件夹**节点，指向**添加**，然后单击**项目输出**。  
  
7. 在**添加项目输出组**对话框中，选择**主输出**并**内容文件**从 ASP.NET Web 服务项目，然后单击**确定**.  
  
8. 在解决方案资源管理器，展开**检测到依赖项**Web 安装项目下的节点。  
  
9. 选择所有依赖项。 在中**属性**窗口中，将**排除**属性设置为**True**。  
  
10. 生成 Web 安装程序项目。  
  
    > [!NOTE]
    >  有关创建 Web 安装项目的详细信息，请参阅"如何创建或添加 Web 安装项目"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合中处[ http://go.microsoft.com/fwlink/?LinkId=62268 ](http://go.microsoft.com/fwlink/?LinkId=62268)。  
  
## <a name="see-also"></a>请参阅  
 [在无 Visual Studio 的计算机上部署已发布 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)