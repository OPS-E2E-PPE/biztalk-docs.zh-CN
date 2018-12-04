---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: 配置 Visual Studio Team Services 部署 BizTalk Server 解决方案或项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2555712a-dfe4-420e-9a61-1d1a6d98c322
caps.latest.revision: 6
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 8b13ef6f56e892bb3598096272d876c5f0a865f3
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826301"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a>配置 Visual Studio Team Services 部署 BizTalk Server 解决方案或项目
设置 VSTS 自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]项目。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，可以自动生成你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用 Visual Studio Team Services (VSTS) 的解决方案。 

本主题演示如何设置和配置 Visual Studio Team Service (VSTS) 为 BizTalk 使用自动部署。 

> [!IMPORTANT]
> VSTS 代理只能安装一个[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。 

## <a name="prerequisites"></a>必要条件

* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一些经验和知识并通过创建和使用 VSTS 中的定义。 如果你是新手 VSTS，这些可能是有用的资源： 

  [Visual Studio Team Services 概述](https://www.visualstudio.com/docs/overview)  
  [适用于新手的 CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a>创建 VSTS 帐户并创建定义

1. 在 web 浏览器中，转到您[Visual Studio online 配置文件](https://app.vsaex.visualstudio.com/go/profile)、 登录，然后选择**创建新帐户**:

    ![创建新帐户](../core/media/create-a-new-account.png)

2. 输入帐户的名称，选择你首选的源代码存储库，并选择**继续**:

    ![创建新项目](../core/media/create-a-new-project.png)

3. 创建新帐户，和类似于站点`https://YourAccountName.visualstudio.com/MyFirstProject`随即打开。
    
4. 安装[部署 BizTalk 应用程序服务](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)到刚刚创建的帐户。

    ![生成新的发行版](../core/media/build-new-release.png)

5. 你可能会收到一些提示。 确认后才能继续。 请确保登录到你在 VSTS 中的项目。

6. 选择**生成和发布**，并创建**新建**生成定义：

    ![选择生成和发布](../core/media/select-build-and-release.png)

    > [!TIP]
    > 确保您位于`https://YourAccountName.visualstudio.com/MyFirstProject`。 否则为**新建**或**新定义**按钮可能不存在。 
    
7. 选择**Visual Studio**模板，然后选择**下一步**:

    ![选择 visual studio，然后单击下一步](../core/media/select-visual-studio-and-click-next.png)

8. 查看你的设置，然后选择**创建**。

9. 删除不需要的步骤。 对于本教程中，您可以删除以下： 
10. NuGet 还原
11. 测试程序集
12. 发布符号路径 

      ![删除不必要的步骤](../core/media/delete-steps-not-needed.png)

13. **可选**。 如果你想要启用持续集成 (CI)，选择**触发器**菜单中，并检查**持续集成 (CI)**。

接下来，在安装代理应用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

## <a name="install-the-agent"></a>安装代理

对于要使用的解决方案，来启用本地计算机上的专用 Windows 代理。 请记住，**必须在其中安装了代理[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中**。 

1. 在定义中，选择**常规**（顶部） 选项卡。
2. 有关**默认代理队列**属性中，选择**默认**从列表中的代理。 
3. 选择**管理**旁边**默认代理队列**属性。 打开一个新的浏览器选项卡。

    ![创建新的管理代理](../core/media/create-new-management-agent.png)

4. 在左窗格中，选择默认的队列。 如果代理已列出，并处于联机状态，然后完成。 安装代理，安装并运行。 

    如果未列出代理，然后选择**下载代理**，并在继续进行安装你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 **转到[部署 Windows 代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)的完整步骤**安装代理，并启动代理。 

    > [!IMPORTANT]
    > 请按照在所有步骤[Windows 上部署代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)。 请勿跳过此步骤。 

5. 使用默认代理**联机**，返回**常规**选项卡上，在定义中，并确认**默认**为选择**默认代理队列**.
6. **保存**并**使新生成入队**。

接下来，创建 BizTalk Server 应用程序部署定义。

## <a name="create-the-biztalk-deployment-definition"></a>创建 BizTalk 部署定义

1. 选择**生成**选项卡上，选择**所有定义**，然后选择**新建**:

    ![创建新发布定义](../core/media/create-new-release-definition.png)

2. 选择**空**模板，然后选择**下一步**:

    ![从空白模板创建新的定义](../core/media/create-new-definition-from-an-empty-template.png)

3. 选择你**存储库**源和**分支**有关定义的信息。
4. **可选**。 选择**持续集成**。
5. 选择**默认**代理从队列列表中，然后选择**创建**。
6. **添加生成步骤**，选择**BizTalk Server 应用程序部署**任务，并选择**添加**。 **关闭**任务目录中。

    ![添加新部署定义](../core/media/add-new-deploy-definition.png)

7. 选择**操作名称**你想要使用：

    * **创建新的 BizTalk 应用程序**部署新的应用程序。 如果应用程序已存在，它会卸载当前应用程序 （句号），并安装新的应用程序。 如果启用持续集成，则它会自动重新部署应用程序在更新存储库中时。
    * **更新现有的 BizTalk 应用程序**附加更改，例如**架构**到已运行的应用程序。 它不需要完全重新部署应用程序。

8. 输入**应用程序名称**在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。
9. 在中**部署的包路径**，选择你的存储库中的 zip 文件的路径。
10. 选择**触发器**菜单中，启用**持续集成**，并选择正确**分支**生成。
11. 选择**保存**:

    ![保存新的生成定义](../core/media/save-the-new-build-definition.png)

12. 指定新**定义**，并设置正确的路径。 
13. 保存定义后，选择**使新生成入队**。 然后，选择**队列代理**，并将注释添加到该提交。
