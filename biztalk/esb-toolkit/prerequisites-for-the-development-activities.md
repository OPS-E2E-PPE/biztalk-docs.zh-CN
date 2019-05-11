---
title: 开发活动的先决条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c81bd4acffed295de12e8b123451ae1eb77864f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301785"
---
# <a name="prerequisites-for-the-development-activities"></a>开发活动的先决条件
本部分介绍如何准备环境以完成作为的一部分的开发活动中的步骤[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 你在尝试任何开发活动中的过程之前，请完成以下设置：  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a>设置计算机以执行 BizTalk ESB 工具包开发活动中的过程  
  
1.  安装和部署路线示例应用程序、 动态解析示例应用程序和多个 Web 服务示例应用程序。 有关安装和部署这些应用程序的详细信息，请参阅[BizTalk ESB 工具包示例应用程序](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)。  
  
2.  运行 UDDI 发布者实用程序。  
  
3.  在开发计算机上，在 Windows 资源管理器，创建以下路径：  
  
    -   C:\HowTos  
  
    -   C:\HowTos\Itineraries  
  
    -   C:\HowTos\DropFolder  
  
    -   C:\HowTos\Out  
  
4.  确保 BizTalk Server 服务帐户具有**完全控制**C:\HowTos 目录结构的权限。  
  
5.  请确保你的 Microsoft BizTalk Server 服务帐户具有**编写**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out 的权限。  
  
6.  将以下测试消息复制到 C:\HowTos 文件夹：  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml  
  
7.  在 C:\HowTos 文件夹中，创建路线测试客户端应用程序，在以下位置找到的快捷方式：  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe  
  
## <a name="create-the-visual-studio-solution"></a>创建 Visual Studio 解决方案  
  
1.  在 Visual Studio 中，在文件菜单，指向**新建**，然后单击**项目**。  
  
2.  在**新的项目**对话框中，在项目类型窗格中，单击**Visual C#** ，然后单击**类库**在模板窗格中。  
  
3.  在中**名称**框中，键入**ItineraryLibrary**。  
  
4.  在中**位置**框中，键入**C:\HowTos**。  
  
5.  选择**创建解决方案目录**复选框。  
  
6.  在中**解决方案名称**框中，键入**模式**，然后单击**确定**创建解决方案。  
  
7.  删除**Class1.cs**文件从**ItineraryLibrary**项目。