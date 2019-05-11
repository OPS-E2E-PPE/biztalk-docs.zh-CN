---
title: 创建环境令牌和变量 |Microsoft Docs"
description: 更新绑定文件以使用环境令牌和在 VSTS 自动执行部署的 BizTalk Server 应用程序中创建变量
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
ms.openlocfilehash: 2d3af4817e2974d1196fb08acf94195b997b0c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356438"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>配置环境令牌和变量自动部署
使用 Visual Studio Team Services (VSTS) 中的变量在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件。

## <a name="overview"></a>概述
在 VSTS 环境中，可以添加变量，并将其设置为一个值。 例如，可以创建*sendPortPath*变量，并将其值设置为物理文件夹，在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]应用程序绑定文件，可配置的变量可以是任何内容中的 XML 标记，如接收位置名称、 主机、 发送端口的 URI，等等。 

这些变量特定于你的 VSTS 环境，也可用于部署到多个相同的应用程序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 

我们展示如何将 VSTS 变量添加在绑定文件中，以及如何创建在 VSTS 中的变量。 

## <a name="add-variables-to-the-binding-file"></a>将变量添加到绑定文件

1. 打开应用程序绑定文件：

    ![打开绑定文件](../core/media/biztalk-feature-pack-1-binding-1.png)

2. 找到你想要更改的元素：

    ![选择的元素](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. 删除填充的值并将其替换为你的变量： `$(YourValue)`。 例如，输入`$(SendPort1)`: 

    ![绑定文件](../core/media/biztalk-feature-pack-1-binding-3.png)

4. 完成后，保存绑定文件，并将其添加到 JSON 生成模板 (中的步骤[步骤 1:添加应用程序项目和更新.json 模板](feature-pack-add-application-project.md))。

## <a name="create-the-variables-in-vsts"></a>在 VSTS 中创建的变量

1. 在 VSTS 帐户中，选择**生成和发布**，然后选择**版本**。

2. 选择你**发布定义**，然后选择**变量**:  

    ![绑定文件](../core/media/vsts-release-variables.png)

3. 选择**添加**，并创建变量名称和值：   

    ![配置变量](../core/media/environment-specific-variables.png)

4. **保存**所做的更改。 启动部署时，从绑定文件添加值。

## <a name="see-also"></a>另请参阅
[使用 Visual Studio Team Services 中配置自动部署](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[配置功能包](configure-the-feature-pack.md)