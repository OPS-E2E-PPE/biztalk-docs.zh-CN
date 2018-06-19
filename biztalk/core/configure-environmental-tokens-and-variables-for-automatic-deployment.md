---
title: 创建环境的令牌和变量 |Microsoft 文档"
description: 更新绑定文件以使用环境标记，并在 VSTS 中自动执行部署的 BizTalk Server 应用程序中创建变量
ms.custom: ''
ms.date: 11/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: 4
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d84fa393410e3084c87e762140530a45b0b78b5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054565"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>配置环境的令牌和自动部署的变量
使用 Visual Studio Team Services (VSTS) 变量中的你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件。

## <a name="overview"></a>概述
在 VSTS 环境中，你可以添加变量，并将它们设置为一个值。 例如，你可以创建*sendPortPath*变量，并将其值设置为物理文件夹，在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]应用程序绑定文件，可配置的变量可以是任何内容中的 XML 标记，如接收位置名称、 主机、 发送端口 URI，等等。 

这些变量特定于你的 VSTS 环境，并且可以用于部署到多个相同的应用程序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 

我们向您展示如何将 VSTS 变量添加在绑定文件中，以及如何创建 VSTS 中的变量。 

## <a name="add-variables-to-the-binding-file"></a>将变量添加到绑定文件

1. 打开应用程序绑定文件：

    ![打开绑定文件](../core/media/biztalk-feature-pack-1-binding-1.png)

2. 查找你想要更改的元素：

    ![选择的元素](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. 删除的填充的值，并将其与你变量： `$(YourValue)`。 例如，输入`$(SendPort1)`: 

    ![绑定文件](../core/media/biztalk-feature-pack-1-binding-3.png)

4. 完成后，保存该绑定文件，并将其添加到 JSON 生成模板 (中的步骤[步骤 1： 添加应用程序项目 （&） 更新.json 模板](feature-pack-add-application-project.md))。

## <a name="create-the-variables-in-vsts"></a>在 VSTS 中创建变量

1. 在你的 VSTS 帐户，选择**生成和发布**，然后选择**版本**。

2. 选择你**释放定义**，然后选择**变量**:  

    ![绑定文件](../core/media/vsts-release-variables.png)

3. 选择**添加**，并创建的变量的名称和值：   

    ![配置变量](../core/media/environment-specific-variables.png)

4. **保存**所做的更改。 当启动部署时，会将值添加从绑定文件。

## <a name="see-also"></a>另请参阅
[使用 Visual Studio Team Services 中配置自动部署](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[配置功能包](configure-the-feature-pack.md)