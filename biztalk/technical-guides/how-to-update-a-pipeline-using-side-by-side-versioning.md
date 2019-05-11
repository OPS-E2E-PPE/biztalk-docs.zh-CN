---
title: 如何更新使用的并行版本控制的管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85aa5f7d134e14d16fbb4fb88fcff29cf6ce672f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400273"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>如何更新使用的并行版本控制的管道
使用新的管道的并行版本控制添加的简单方法是选择新部署的管道版本中的发送端口或接收位置。 这将使用新替换旧的管道。 但是，如果用于向后兼容性需要真正的并行功能，然后你必须创建新发送端口和接收位置并将其绑定到指定的新管道版本。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>若要添加管道组件的新版本  
  
1. 在 Visual Studio 中创建的管道组件的新版本和程序集进行签名。  
  
2. 将管道组件中的添加**管道组件**文件夹 (\<*安装文件夹*\>\Pipeline 组件)。  
  
3. 将管道组件添加到你的管道。  
  
4. 生成管道或部署你的解决方案之后, 删除从管道组件**管道组件**文件夹。  
  
5. 管道组件添加到全局程序集缓存 (GAC)。  
  
   完成这些步骤后，已编译的管道程序集将引用的管道组件的正确版本和 BizTalk Server 使用的应用程序域将在 GAC 中，而不是查找上一个查找管道组件的新版本管道组件文件夹中的管道组件的版本。  
  
## <a name="see-also"></a>请参阅  
 [更新正在使用的并排版本控制](../technical-guides/updating-using-side-by-side-versioning.md)