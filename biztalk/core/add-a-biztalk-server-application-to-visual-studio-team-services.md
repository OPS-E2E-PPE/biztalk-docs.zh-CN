---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: true
ROBOTS: NOINDEX
title: 添加到 Visual Studio Team Services 的 BizTalk Server 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: 4
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: a5ab2e23c4ccca6154334af234acdbd3f1847b26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360975"
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a>添加到 Visual Studio Team Services 的 BizTalk Server 应用程序
添加[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]VSTS 使用持续集成自动部署到的项目。  

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，你可以自动部署您的应用程序在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用 Visual Studio Team Services (VSTS) 的环境。 

本主题提供了概述，并列出了主要的步骤，将从 Visual Studio 解决方案部署在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

## <a name="prerequisites"></a>先决条件
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* [步骤 3：创建生成和发布定义](../core/feature-pack-add-build-release-definitions.md)
* 知识并使用 Git 和 Visual Studio 中的存储库的体验。 如果你是全新的存储库和版本控制，这些可能是有用的资源： 

    [了解 Git](https://www.visualstudio.com/learn-git/)  
    [Git 和 Team Services](https://www.visualstudio.com/docs/git/overview)
* 知识和经验处理中的 BizTalk 项目 [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]

## <a name="add-biztalk-project-to-vsts"></a>向 VSTS 添加 BizTalk 项目
1. 在**Visual Studio**，连接到你**源代码存储库**，并**克隆**到你的计算机。
2. 打开或创建**BizTalk 项目**(.btproj)。

   > [!NOTE]
   > 可以将多个项目添加到相同的解决方案。
   
3. 添加一个新**BizTalk Server 应用程序项目**(.btaproj)。
4. 右键单击该项目中的**解决方案资源管理器**，然后选择**属性**。
5. 配置**版本**和连接属性您**Visual Studio Team Services**帐户。

    ![Visual Studio 配置 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. 添加所有程序集和项目所需的应用程序。
7. 更新**binding.xml**具有正确的绑定信息文件。
8. 更新**BizTalkServerInventory.json**与所有项目和项目上安装的正确顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。
9. 右键单击并**生成**解决方案以检查是否有任何错误。 
10. 生成成功完成后，右键单击您的解决方案，然后选择**部署**。
11. 应会自动将你的应用程序部署到你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="see-also"></a>另请参阅
[配置功能包](../core/configure-the-feature-pack.md)