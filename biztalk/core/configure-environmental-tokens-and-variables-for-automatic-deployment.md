---
title: "配置环境的令牌和自动部署变量 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7d148f79fceb68b24feb45882ab89767369ed7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>配置环境的令牌和自动部署的变量
使用 Visual Studio Team Services (VSTS) 变量中的你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件。

## <a name="overview"></a>概述
在 VSTS 环境中，你可以添加变量，并将它们设置为一个值。 例如，你可以创建*sendPortPath*变量，并将其值设置为物理文件夹，在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]应用程序绑定文件，可配置的变量可以是任何内容中的 XML 标记，如接收位置名称、 主机、 发送端口 URI，等等。 

这些变量特定于你的 VSTS 环境，并且可以用于部署到多个相同的应用程序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 

在本主题中，我们演示如何添加 VSTS 变量在绑定文件中，以及如何创建 VSTS 中的变量。 

## <a name="configure-the-variables-in-your-biztalk-binding-file"></a>在 BizTalk 绑定文件中配置的变量

下面的示例摘自[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件，并演示如何应用令牌。

1. 打开应用程序绑定文件：

    ![BizTalk 功能包 1 绑定 1](../core/media/biztalk-feature-pack-1-binding-1.png)

2. 查找你想要更改的元素：

    ![BizTalk 功能包 1 绑定 2](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. 删除的填充的值，并将其与你变量： `$(YourValue)`。 例如，输入`$(SendPort1)`: 

    ![BizTalk 功能包 1 绑定 3](../core/media/biztalk-feature-pack-1-binding-3.png)


4. 完成后，保存该绑定文件，并将其应用到 JSON 生成模板。
5. 登录到 Visual Studio 团队服务解决方案，然后选择**生成和发布**。
6. 转到**版本**。 选择你**释放定义**，或创建一个新。
7. 下**环境**，选择**添加新环境**，或将更改为现有环境： 

    ![添加新的环境](../core/media/add-a-new-environment.png)

8. 单击省略号，然后选择**配置变量**:

    ![配置变量](../core/media/configure-variables.png)

9. 通过添加每个环境中使用绑定文件中创建的标记名称的变量中，你可以部署您的应用程序使用不同的值的多个环境：

    ![环境特定变量](../core/media/environment-specific-variables.png)
    
10. 选择**确定**以保存新变量。
11. 生成开始后，会将值添加从绑定文件。

## <a name="next-step"></a>下一步
[添加到 VSTS BizTalk 应用程序](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)