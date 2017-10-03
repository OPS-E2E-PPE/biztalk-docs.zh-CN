---
title: "添加到 Visual Studio Team Services BizTalk Server 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d3fc8c0253c8e2517f78c2d60fdc7c74a983bdbd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a>添加到 Visual Studio Team Services BizTalk Server 应用程序
添加[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]VSTS 来自动部署使用持续集成到项目。  

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，你可以自动部署您的应用程序你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用 Visual Studio Team Services (VSTS) 的环境。 

此主题提供概述，并列出来部署你从 Visual Studio 的解决方案的关键步骤你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

## <a name="prerequisites"></a>先决条件
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* [为自动部署配置 VSTS](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)
* 知识和体验使用 Git 和 Visual Studio 中的存储库。 如果你是新手存储库和版本控制，这些可能是很好的资源： 

    [了解 Git](https://www.visualstudio.com/learn-git/)  
    [Git 和 Team Services](https://www.visualstudio.com/docs/git/overview)
* 知识和经验 BizTalk 在中使用项目[!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]

## <a name="add-biztalk-project-to-vsts"></a>将 BizTalk 项目添加到 VSTS
1. 在**Visual Studio**，连接到你**源代码存储库**，和**克隆**到您的计算机。
2. 打开或创建**BizTalk 项目**(.btproj)。

   > [!NOTE]
   > 也可以将多个项目添加到同一个解决方案。
   
3. 添加新**BizTalk 服务器应用程序项目**(.btaproj)。
4. 右键单击中的项目**解决方案资源管理器**，然后选择**属性**。
5. 配置**版本**和连接属性添加到你**Visual Studio Team Services**帐户。

    ![Visual Studio 配置 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. 添加所有程序集和应用程序所需的项目。
7. 更新**binding.xml**具有正确的绑定信息文件。
8. 更新**BizTalkServerInventory.json**与所有项目和项目上安装的正确顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。
9. 右键单击和**生成**解决方案以检查是否有任何错误。 
10. 生成成功完成后，右键单击你的解决方案，然后选择**部署**。
11. 应自动将你的应用程序部署到你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="see-also"></a>另请参阅
[配置功能包](../core/configure-the-feature-pack.md)